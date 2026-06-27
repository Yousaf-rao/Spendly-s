# Spendly — Personal Expense Tracker

> **Track every rupee. Own your finances.**

Spendly is a lightweight, self-hosted personal finance tracker built with **Flask** and **SQLite**. It helps you log daily expenses, understand your spending patterns by category, and review your financial activity over any date range.

This repository currently contains the **landing, authentication, and project scaffolding**. The expense-tracking CRUD features are progressively being built out in numbered steps (see [Roadmap](#-roadmap)).

---

## ✨ Features

### Live
- 📄 **Editorial landing page** — hero, feature highlights, and call-to-action
- 🔐 **Sign-up & sign-in flows** — styled auth forms with validation slots
- 🎨 **Polished design system** — paper-and-ink palette, DM Serif Display + DM Sans typography
- 📱 **Fully responsive** — mobile-friendly navbar, hero, and auth layouts

### Planned (see [Roadmap](#-roadmap))
- 📒 **Log expenses** — amount, category, date, description
- 📊 **Category breakdowns** — see where your money goes
- 📅 **Date-range filtering** — last week, last month, custom period
- 👤 **User profiles** — per-user expense history
- ✏️ **Edit & delete** — full CRUD on each expense

---

## 🖼️ Preview

The app runs at **`http://localhost:5001`** in development mode.

```
┌─────────────────────────────────────────────┐
│  ◈ Spendly                Sign in  Get started│
├─────────────────────────────────────────────┤
│                                              │
│  Personal Finance Tracker                    │
│  Know where your        ┌──────────────────┐ │
│  money goes             │ March 2026       │ │
│                         │ ₹12,450          │ │
│  Log expenses, under-   │ ─────────────    │ │
│  stand your patterns,   │ Bills    ▆▆▆ ₹4.5k│ │
│  and take control...    │ Food     ▆▆  ₹3.2k│ │
│                         │ Health   ▆   ₹2.0k│ │
│  [Start tracking free]  │ Transp.  ▆   ₹1.8k│ │
│  [Sign in]              └──────────────────┘ │
└─────────────────────────────────────────────┘
```

---

## 🧰 Tech Stack

| Layer       | Technology                              |
|-------------|------------------------------------------|
| Backend     | Python 3.x, **Flask 3.1.3**              |
| WSGI utils  | Werkzeug 3.1.6 (password hashing)        |
| Database    | **SQLite** (file-based, zero-config)      |
| Templating  | Jinja2 (server-rendered)                 |
| Frontend    | Vanilla CSS + JavaScript (no framework)  |
| Typography  | DM Serif Display + DM Sans (Google Fonts)|
| Tests       | pytest 8.3.5 + pytest-flask 1.3.0        |

---

## 📁 Project Structure

```
Spendly/
├── expense-tracker/
│   ├── app.py                  # Flask entry point + routes (Controller)
│   ├── requirements.txt        # Pinned Python dependencies
│   ├── .gitignore              # Python, venv, DB, OS junk
│   │
│   ├── database/               # Data layer (Model)
│   │   ├── __init__.py
│   │   └── db.py               # get_db / init_db / seed_db (Step 1)
│   │
│   ├── templates/              # View layer (Jinja2)
│   │   ├── base.html           # Layout shell — navbar, footer, fonts
│   │   ├── landing.html        # Public landing page
│   │   ├── login.html          # Sign-in form
│   │   └── register.html       # Sign-up form
│   │
│   └── static/
│       ├── css/style.css       # Full design system + responsive rules
│       └── js/main.js          # Reserved for client-side scripts
│
└── README.md                   # You are here
```

---

## 🚀 Getting Started

### 1. Prerequisites

- **Python 3.10+** (Flask 3.x requires 3.8+; 3.10+ recommended)
- **pip** (bundled with Python)
- A virtual environment tool (`venv` is recommended)

### 2. Clone & enter the project

```bash
git clone https://github.com/Yousaf-rao/Spendly-s.git
cd Spendly-s/expense-tracker
```

### 3. Create a virtual environment

**Windows (PowerShell):**
```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
```

**macOS / Linux:**
```bash
python3 -m venv venv
source venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the app

```bash
python app.py
```

Open your browser and visit:

```
http://localhost:5001
```

You should see the Spendly landing page.

---

## 🌐 Routes

| Method | Path                          | Status        | Description                       |
|--------|-------------------------------|---------------|-----------------------------------|
| GET    | `/`                           | ✅ Live        | Landing page                      |
| GET    | `/register`                   | ✅ Live        | Sign-up form                      |
| GET    | `/login`                      | ✅ Live        | Sign-in form                      |
| GET    | `/logout`                     | 🚧 Placeholder | Step 3                            |
| GET    | `/profile`                    | 🚧 Placeholder | Step 4                            |
| GET    | `/expenses/add`               | 🚧 Placeholder | Step 7                            |
| GET    | `/expenses/<id>/edit`         | 🚧 Placeholder | Step 8                            |
| GET    | `/expenses/<id>/delete`       | 🚧 Placeholder | Step 9                            |

---

## 🗺️ Roadmap

The project is built in **numbered steps** so each one is small and reviewable:

| Step | Title             | Status     | Goal                                                       |
|------|-------------------|------------|------------------------------------------------------------|
| 1    | Database Setup    | 🚧 Pending  | Implement `database/db.py` (users + expenses schema)       |
| 2    | Registration      | 🚧 Pending  | Hash passwords, insert users, redirect to login            |
| 3    | Login + Logout    | 🚧 Pending  | Session-based auth, `secret_key`, logout clears session    |
| 4    | Profile Page      | 🚧 Pending  | Show logged-in user info                                   |
| 5    | Expense Listing   | 🚧 Pending  | List expenses for current user                             |
| 6    | Filters & Reports | 🚧 Pending  | Category and date-range filtering, monthly summaries       |
| 7    | Add Expense       | 🚧 Pending  | Form + handler, ownership via `user_id`                    |
| 8    | Edit Expense      | 🚧 Pending  | Pre-fill form, verify ownership                            |
| 9    | Delete Expense    | 🚧 Pending  | Confirm + ownership check                                  |
| 10   | Polish            | 🚧 Pending  | Tests, README polish, deploy notes                         |

---

## 🎨 Design System

The visual language is intentionally editorial — newspaper-like warmth rather than dashboard chrome.

### Palette

| Token             | Hex      | Usage                          |
|-------------------|----------|--------------------------------|
| `--ink`           | `#0f0f0f` | Primary text, buttons          |
| `--paper`         | `#f7f6f3` | Page background                |
| `--paper-warm`    | `#f0ede6` | Section dividers (features)    |
| `--paper-card`    | `#ffffff` | Card surfaces                  |
| `--accent`        | `#1a472a` | Brand green — CTAs, highlights |
| `--accent-2`      | `#c17f24` | Warm orange — secondary accent |
| `--danger`        | `#c0392b` | Error states                   |
| `--border`        | `#e4e1da` | Subtle dividers                |

### Typography

- **Display**: `DM Serif Display` — hero titles, feature titles
- **Body**: `DM Sans` — all UI text, forms, buttons

Both fonts load from Google Fonts via `base.html`.

### Responsive Breakpoints

- `@media (max-width: 900px)` — stacks the hero, hides the mock card
- `@media (max-width: 600px)` — collapses the navbar, tightens spacing

---

## 🧪 Testing

The project ships with `pytest` and `pytest-flask` configured, but no tests yet. Once you add logic in `database/db.py` and the POST handlers, drop tests into a `tests/` directory:

```
tests/
├── conftest.py             # pytest-flask fixtures (app, client)
├── test_routes.py          # GET smoke tests for live routes
├── test_auth.py            # register, login, logout (Step 3)
└── test_expenses.py        # CRUD tests (Steps 7–9)
```

Run them with:

```bash
pytest
```

---

## 🛡️ Security Notes

Before going to production:

- **Set a real `SECRET_KEY`** — load from environment, never commit. Add `.env` to `.gitignore`.
- **Enable CSRF protection** — Flask-WTF or manual tokens on every form.
- **Add password complexity rules** — minimum length, common-password blocklist.
- **Validate all inputs server-side** — never trust client-side validation alone.
- **Turn off `debug=True`** — expose via a WSGI server (gunicorn, waitress) instead of `app.run()`.

---

## 🤝 Contributing

This is a learning-focused project, so contributions should be:

1. **Small** — one step at a time.
2. **Documented** — update the [Roadmap](#-roadmap) when you complete a step.
3. **Tested** — add pytest cases for new logic.
4. **Styled** — match the existing design tokens; avoid raw hex values.

### Local workflow

```bash
git checkout -b feature/step-1-database
# … make changes …
git add .
git commit -m "Step 1: implement get_db / init_db / seed_db"
git push origin feature/step-1-database
# open a Pull Request on GitHub
```

---

## 📜 License

To be decided — currently unlicensed. Add an `MIT`, `Apache-2.0`, or similar `LICENSE` file before publishing broadly.

---

## 🙏 Acknowledgments

- Design inspiration: editorial finance journalism (serif headlines, paper textures)
- Fonts: [DM Serif Display](https://fonts.google.com/specimen/DM+Serif+Display) and [DM Sans](https://fonts.google.com/specimen/DM+Sans) by Colophon Foundry
- Built with [Flask](https://flask.palletsprojects.com/) and [Werkzeug](https://werkzeug.palletsprojects.com/)

---

<div align="center">

**Spendly** · Track every rupee. Own your finances.

[Report a bug](https://github.com/Yousaf-rao/Spendly-s/issues) · [Request a feature](https://github.com/Yousaf-rao/Spendly-s/issues)

</div>
