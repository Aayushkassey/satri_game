<div align="center">

# 🎮 SATRI Arcade

**A browser-based arcade collection built for SATRI — 9 mini-games, 13,000+ questions, zero dependencies.**

[![Version](https://img.shields.io/badge/version-2.1-blue.svg)]()
[![License](https://img.shields.io/badge/license-MIT-green.svg)]()
[![Platform](https://img.shields.io/badge/platform-browser-orange.svg)]()
[![Netlify](https://img.shields.io/badge/deploy-Netlify-00C7B7.svg)](https://netlify.com)

---

*Type. Match. Remember. Unscramble. Hunt. Query. Commit. Recall. Snake.*

</div>

---

## 🕹️ Games Overview

| Game | Description | Mechanics | Questions |
|------|-------------|-----------|-----------|
| **⚡ Speed Typing** | Type tech words at max WPM | 30s timer, accuracy tracking | 520+ |
| **🎨 Color Flash** | Ink vs word color match | Reflex test, 5% faster each round | 49 unique |
| **🧠 Memory Grid** | Reproduce flashing patterns | Increasing sequence length | 520+ patterns |
| **🔤 Word Scramble** | Unscramble with clues | 30s/word, contextual hints | 520+ |
| **🐞 Bug Hunter** | Spot the buggy line | 25 fields, 15s timer | **13,000+** |
| **🗄️ SQL Master** | Pick correct query | 15s, 4 options | 520+ |
| **🌿 Git Master** | Pick correct command | 15s, 4 options | 520+ |
| **🔢 Flash Recall** | Memorize & recall numbers | KBC-style, digits increase | 520+ |
| **🐍 Snake** | Classic arcade | Keyboard + touch, high score | — |

---

## ✨ Key Features

### 🎯 Smart No-Repeat Engine
- **Per-game question history** stored in `localStorage`
- Questions never repeat until the **entire pool is exhausted**
- "Play Again" **continues from where you left off** — no fresh reset
- Works offline (file://) and on Netlify

### 📱 Fully Responsive
- **Desktop**: Full viewport fit, keyboard controls
- **Tablet**: Adaptive layout, touch optimized
- **Mobile**: Compact UI, bottom controls, no scrolling

### 🎨 Polished UI
- Dark theme with SATRI branding
- Smooth animations & feedback (green/red flashes)
- Accessible: ARIA labels, focus states, touch-action

### ⚡ Zero Build Step
- Single `index.html` + `questions.json`
- Runs by double-clicking or via any static host
- Embedded fallback question bank for `file://` protocol

---

## 🚀 Quick Start

```bash
# Option 1: Double-click index.html
# Option 2: VS Code Live Server
# Option 3: Any static server
npx serve .
python -m http.server 8000
```

**Deploy to Netlify** — drag & drop the folder. Ensure both files are in root:
```
📁 your-site/
├── index.html
├── questions.json
└── image.png
```

---

## 📂 Project Structure

```
SATRI GAME/
├── index.html          # Complete game (HTML + CSS + JS)
├── questions.json      # 15,000+ question bank
├── image.png           # SATRI logo
└── README.md           # This file
```

---

## 🧠 Question Bank Details

| Pool | Count | Source |
|------|-------|--------|
| Typing Words | 520+ | Tech vocabulary |
| Color Rounds | 49 | Rainbow combinations |
| Memory Patterns | 520+ | Unique sequences |
| Scramble Words | 520+ | With contextual clues |
| SQL Challenges | 520+ | Real query patterns |
| Git Challenges | 520+ | Real commands |
| Flash Items | 520+ | Number sequences |
| **Bug Hunter** | **13,000+** | **25 specialized fields** |

### Bug Hunter Fields (520 each)
```
Full Stack · MERN · React · Next.js · Laravel · Django · WordPress
Flutter · Cross Platform · UI/UX · Graphics · Product Design
Python · Data · IoT · Smart IoT · Cybersecurity · QA · DevOps
Digital Marketing · Social Media · Content Marketing
Project Based · Internship · GenAI
```

---

## 🔧 Adding Custom Questions

Edit `questions.json` — no code changes needed.

### SQL Example
```json
{
  "id": "sql-custom-001",
  "objective": "Get users with more than 5 orders",
  "options": [
    "SELECT u.* FROM users u JOIN orders o ON u.id = o.user_id GROUP BY u.id HAVING COUNT(*) > 5;",
    "SELECT * FROM users WHERE orders > 5;",
    "SELECT * FROM users HAVING COUNT(orders) > 5;",
    "GET users WHERE order_count > 5;"
  ],
  "correctIndex": 0
}
```

### Git Example
```json
{
  "id": "git-custom-001",
  "objective": "Undo last commit but keep changes staged",
  "options": [
    "git reset --soft HEAD~1",
    "git reset --hard HEAD~1",
    "git revert HEAD",
    "git undo"
  ],
  "correctIndex": 0
}
```

### Bug Hunter Example
```json
{
  "id": "react-custom-001",
  "difficulty": "medium",
  "lines": [
    "function UserCard({ user }) {",
    "  const [name, setName] = useState(user.name);",
    "  return <div onClick={() => setName('')}>{name}</div>;",
    "}"
  ],
  "bugIndex": 2,
  "explanation": "Line 3: onClick clears name on every render due to missing dependency in useEffect (not shown) or should use callback."
}
```

> `bugIndex` is **0-based**: line 1 = 0, line 2 = 1, etc.

---

## 📖 References & Attributions

Questions curated from official documentation:

| Technology | Source |
|------------|--------|
| Web APIs, JS, HTML, CSS | [MDN Web Docs](https://developer.mozilla.org/) |
| React | [React.dev](https://react.dev/) |
| Next.js | [Next.js Docs](https://nextjs.org/docs) |
| Laravel | [Laravel Docs](https://laravel.com/docs) |
| Django | [Django Docs](https://docs.djangoproject.com/) |
| WordPress | [WP Developer Resources](https://developer.wordpress.org/) |
| Flutter/Dart | [Flutter Docs](https://docs.flutter.dev/) |
| Python | [Python Docs](https://docs.python.org/3/) |
| PostgreSQL/SQL | [PostgreSQL Docs](https://www.postgresql.org/docs/) |
| Git | [Git SCM Docs](https://git-scm.com/docs) |
| Security | [OWASP](https://owasp.org/) |
| Statistics | [Khan Academy](https://www.khanacademy.org/math/statistics-probability) |

---

## 🎯 Pro Tips

- **Speed Typing**: Don't look at keyboard — watch the word preview
- **Color Flash**: Focus on *ink color*, ignore the word meaning
- **Memory Grid**: Chunk patterns into shapes (L, line, square)
- **Word Scramble**: Read the clue first — it narrows possibilities
- **Bug Hunter**: Scan for syntax errors first (missing `;`, `,`, brackets)
- **SQL/Git**: Eliminate obviously wrong options first
- **Flash Recall**: Verbalize the number while it flashes
- **Snake**: Plan 2-3 moves ahead; use walls to turn sharply

---

## 📜 Version History

| Version | Date | Changes |
|---------|------|---------|
| **2.1** | 2026-09-06 | Added Snake game; fixed no-repeat persistence; responsive viewport fit; bug fixes |
| **2.0** | 2026-08 | External question bank; 13k Bug Hunter; no-repeat engine; Netlify support |
| **1.0** | 2026-07 | Initial release with 8 games |

---

## 🤝 Contributing

1. Fork the repo
2. Add questions to `questions.json` (follow JSON rules)
3. Test locally: `open index.html`
4. Submit PR

**JSON Rules:**
- Double quotes for keys/strings
- No trailing commas
- Valid JSON only
- SQL/Git: exactly 4 options, `correctIndex` 0-3
- Unique `id` per question

---

## 📄 License

MIT License — free to use, modify, distribute.

---

<div align="center">

**Built with ❤️ for SATRI**

[🌐 Play Now](https://satrigames.netlify.app) · [⭐ Star Repo](https://github.com/Aayushkassey)

</div>