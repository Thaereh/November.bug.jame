
# HauntQuest — Automated UI Tests (pytest + Selenium)

A lightweight Python test suite for the **HauntQuest** web app.

**Target URL (default):**
`https://ryanzomparelli.github.io/Oct-Code-Jam-2025/index.html`

## Features covered
- Header & menu navigation (Home, Calendar, My Events, logo info)
- Filtering by Time (Future/Past) and Activity (Food, Dance, Costumes, Crafts)
- Search (with validation rules, clear/reset)
- Event pop-up (Save / Remove)
- Keyboard accessibility (Tab focus order & Enter/Space activation on key elements)
- Responsive checks (desktop 1920x1080 and small 700x600)
- Basic performance smoke using Navigation Timing (page load time threshold)

## Quick start

1) Create a virtualenv (recommended) and install deps:
```bash
python -m venv .venv && source .venv/bin/activate   # (Windows: .venv\Scripts\activate)
pip install -r requirements.txt
```

2) Run the tests (headless by default):
```bash
pytest -v
```

### Useful env vars
- `BASE_URL` — override target url (default is the URL above)
- `HEADLESS` — set "0" to see the browser: `HEADLESS=0 pytest -v`
- `BROWSER` — "chrome" (default) or "firefox"
- `LOAD_THRESHOLD_MS` — perf threshold (default 4000 ms)

## Structure
```
hauntquest_pytests/
  conftest.py
  requirements.txt
  pages/
    base_page.py
    home_page.py
  tests/
    test_header_menu.py
    test_filters.py
    test_search.py
    test_event_popup.py
    test_accessibility_keyboard.py
    test_responsive.py
    test_performance.py
```

> Notes:
> * Locators rely on visible text, ARIA roles, and placeholder values to stay resilient to markup tweaks.
> * Feel free to refine selectors if the app’s DOM changes.
# November.bug.jame
