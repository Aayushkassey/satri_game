SATRI Arcade 🎮
SATRI Arcade is a browser-based indoor game collection built for SATRI.
It includes educational mini-games focused on programming, technology, memory, typing, problem solving, and general technical knowledge.
🎮 Games
⚡ Speed Typing — Type the displayed word as quickly and accurately as possible.
🎨 Color Flash — Test your visual attention and reaction speed.
🧠 Memory Grid — Memorize and reproduce the displayed pattern.
🔤 Word Scramble — Unscramble the given letters using the provided clue.
🐞 Bug Hunter — Find the incorrect line in a code snippet.
🗄️ SQL Master — Test SQL and database knowledge.
🌿 Git Master — Practice Git commands and version control concepts.
🔢 Flash Recall — Memorize numbers and recall them correctly.
📚 Question Bank
The game uses an external `questions.json` question bank.
500+ items for each main game
13,000+ Bug Hunter challenges across 25 fields
Randomized question selection
No immediate question repeats
Separate question history for each game
Question history is stored locally in the browser
Works on local development and Netlify
Bug Hunter Fields
Bug Hunter includes challenges from:
Full Stack
MERN
React
Next.js
Laravel
Django
WordPress
Flutter
Cross Platform
UI/UX
Graphics
Product Design
Python
Data
IoT
Smart IoT
Cybersecurity
QA
DevOps
Digital Marketing
Social Media
Content Marketing
Project Based
Internship
GenAI
📁 Project Structure
```text
SATRI GAME/
├── index.html
├── questions.json
├── image.png
└── README.md
```
🚀 Run Locally
Open `index.html` in your browser.
For the best local development experience, you can also use VS Code Live Server or another local HTTP server.
The project includes a fallback question bank so the game can also work when `index.html` is opened directly.
🌐 Deploy to Netlify
Upload or deploy the project folder to Netlify.
Make sure `index.html` and `questions.json` are in the same published folder:
```text
index.html
questions.json
```
Netlify should be able to serve the question bank at:
```text
https://satrigames.netlify.app/questions.json
```
No build step or separate JavaScript file is required.
🔄 No-Repeat System
SATRI Arcade uses a local no-repeat system.
Questions already used in a game are stored in the browser's local storage. The game continues selecting unused items until the current pool has been completed, after which a new cycle begins.
Each game has its own question history.
Refreshing the page does not immediately reset the history.
The question history can be reset using the Reset Question History option in the game.
> Question history is stored per browser/device. Different players or devices have separate histories.
📖 Question References
The question bank contains original SATRI content and educational material prepared with reference to official documentation and trusted educational resources.
Technology & Programming
MDN Web Docs — Web development, JavaScript, HTML, and CSS
https://developer.mozilla.org/
React Documentation — React development and concepts
https://react.dev/
Next.js Documentation — Next.js development
https://nextjs.org/docs
Laravel Documentation — Laravel and PHP web development
https://laravel.com/docs
Django Documentation — Django and Python web development
https://docs.djangoproject.com/
WordPress Developer Resources — WordPress development
https://developer.wordpress.org/
Flutter Documentation — Flutter and cross-platform development
https://docs.flutter.dev/
Python Documentation — Python programming
https://docs.python.org/3/
Database & Version Control
PostgreSQL Documentation — SQL and PostgreSQL concepts
https://www.postgresql.org/docs/
Git Documentation — Git commands and version control
https://git-scm.com/docs
Security & Other Topics
OWASP — Web security and cybersecurity concepts
https://owasp.org/
Khan Academy — Statistics and probability concepts
https://www.khanacademy.org/math/statistics-probability
These references are used to keep the educational material aligned with real technologies, standard concepts, and commonly accepted practices.
The SATRI question bank is not intended to reproduce these websites verbatim. The additional educational questions are original/template-generated content based on the referenced topics.
🛠️ Adding Questions
Additional questions can be added directly to `questions.json` without changing the game engine.
SQL Example
```json
{
  "id": "sql-custom-001",
  "objective": "Your question here",
  "options": [
    "Correct answer",
    "Wrong answer",
    "Wrong answer",
    "Wrong answer"
  ],
  "correctIndex": 0
}
```
Git Example
```json
{
  "id": "git-custom-001",
  "objective": "Your Git task here",
  "options": [
    "Correct command",
    "Wrong command",
    "Wrong command",
    "Wrong command"
  ],
  "correctIndex": 0
}
```
Bug Hunter Example
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
  "explanation": "Explain why line 3 is incorrect."
}
```
`bugIndex` is zero-based:
```text
0 = line 1
1 = line 2
2 = line 3
3 = line 4
```
⚠️ JSON Rules
When editing `questions.json`:
Use double quotes for keys and string values.
Do not add trailing commas.
Keep JSON valid.
SQL and Git questions should contain exactly four options.
`correctIndex` must be between `0` and `3`.
Give every question a unique `id`.
📌 Version
Version: 2.0
---
Built for SATRI 🎮