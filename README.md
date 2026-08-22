SATRI Arcade — 500+ Question Bank
What changed
The original SATRI Arcade page had its question/word pools hard-coded inside `index.html`. The original file contained small pools such as a 62-word typing pool, 20 SQL challenges, 20 Git challenges, and only a handful of Bug Hunter challenges per field. The new version moves the data into `questions.json` so the HTML contains the game engine/UI instead of thousands of hard-coded questions.
Question-bank size
Speed Typing: 520 words
Word Scramble: 520 words
Color Flash: 520 rounds
Memory Grid: 520 patterns
Flash Recall: 520 numbers
SQL Master: 520 challenges
Git Master: 520 challenges
Bug Hunter: 25 fields × 520 challenges = 13000 field-specific challenges
Bug Hunter fields:
fullstack, mern, react, nextjs, laravel, django, wordpress, flutter, crossplatform, uiux, graphics, productdesign, python, data, iot, smartiot, cybersecurity, qa, devops, digitalmarketing, socialmedia, contentmarketing, projectbased, internship, genai
Folder structure
Keep these files in the same Netlify publish/deploy folder:
```text
SATRI GAME/
├── index.html
├── questions.json
├── README.md
└── image.png          # your existing SATRI logo
```
There is no separate JavaScript file required. The game logic remains inside `index.html`, while all large data is loaded from `questions.json`.
Netlify deployment
Put `index.html`, `questions.json`, `README.md`, and your existing `image.png` in the same folder.
Deploy that folder to Netlify.
Netlify must serve `questions.json` at:
`https://YOUR-SITE/questions.json`
Open the site.
The menu shows `Question bank ready` when the JSON loaded successfully.
Important
Do not open the HTML by double-clicking it as a `file://` page and expect `fetch("./questions.json")` to work in every browser. Use Netlify, VS Code Live Server, or another local HTTP server.
No-repeat system
This version does more than random selection.
Each pool uses a persistent no-repeat cycle:
A question is marked as used in browser `localStorage`.
The next round/player on the same browser/device will not get that used item again.
The pool is reshuffled only after every item in that pool has been used.
SQL, Git, Scramble, Typing, Color, Memory, Flash Recall, and each Bug Hunter field have separate histories.
The Reset Question History button on the main menu clears the local history and starts a fresh cycle.
Limitation of a static Netlify site
Because this is a static HTML/JSON game, the no-repeat history is stored on the player's browser.
That means:
Same browser/device → persistent no-repeat works.
Refreshing the page → history remains.
Different browser/device → that device has its own history.
Multiple players on completely different devices cannot share one global question history without a backend/database.
If later you want one shared question pool for every player worldwide, the next step is a small backend/API or database.
Question sources / attribution
Existing questions
The original questions supplied with the SATRI Arcade project were preserved and moved out of `index.html` into `questions.json`.
Expanded bank
The additional 500+ entries are SATRI original/template-generated educational content aligned with the listed domains. They are not presented as verbatim copies from an external question bank.
The following official documentation/reference sites are used as topic references for the expanded material:
MDN Web Docs — https://developer.mozilla.org/
React Documentation — https://react.dev/
Next.js Documentation — https://nextjs.org/docs
Laravel Documentation — https://laravel.com/docs
Django Documentation — https://docs.djangoproject.com/
WordPress Developer Resources — https://developer.wordpress.org/
Flutter Documentation — https://docs.flutter.dev/
Python Documentation — https://docs.python.org/3/
PostgreSQL Documentation — https://www.postgresql.org/docs/
Git Documentation — https://git-scm.com/docs
OWASP — https://owasp.org/
Khan Academy Statistics & Probability — https://www.khanacademy.org/math/statistics-probability
The purpose of these references is to keep the generated material aligned with real technologies and standard concepts. The JSON does not claim that every generated question is a quotation from those sites.
How to add more questions later
You do not need to edit the game logic.
SQL
Add an object to `sqlChallenges`:
```json
{
  "id": "sql-custom-001",
  "objective": "Your question here",
  "options": ["Correct", "Wrong", "Wrong", "Wrong"],
  "correctIndex": 0
}
```
Git
Add an object to `gitChallenges`:
```json
{
  "id": "git-custom-001",
  "objective": "Your task here",
  "options": ["Correct command", "Wrong command", "Wrong command", "Wrong command"],
  "correctIndex": 0
}
```
Bug Hunter
Each field has its own array. A challenge looks like:
```json
{
  "id": "react-custom-001",
  "difficulty": "medium",
  "lines": [
    "line 1",
    "line 2",
    "line 3",
    "line 4"
  ],
  "bugIndex": 2,
  "explanation": "Explain why line 3 is wrong."
}
```
`bugIndex` is zero-based:
`0` = line 1
`1` = line 2
`2` = line 3
etc.
Important JSON rule
If you manually edit `questions.json`, keep it valid JSON:
Use double quotes for keys and string values.
Do not leave trailing commas.
Keep exactly four options for SQL/Git questions.
Keep `correctIndex` between `0` and `3`.
Version
`2.0.0`
The UI/game flow was kept inside the original SATRI Arcade structure; the major change is the external question-bank architecture and persistent no-repeat selection.

Opening the game directly
This version also works when you double-click `index.html` and the browser shows a `file:///.../index.html` address. Modern browsers block JavaScript `fetch()` requests for local files, which caused the earlier `Question bank failed to load` message. The fixed `index.html` contains an embedded fallback copy of the same question bank for `file://` mode.
When deployed to Netlify (or any normal HTTP/HTTPS host), the game loads `questions.json` normally. Keep `index.html` and `questions.json` in the same published folder.
The small `\n` text that appeared above the error message was also removed.