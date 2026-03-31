# Contributing to Anwit's Notepad

Thank you for your interest in contributing. This document explains how to get involved.

---

## What we're looking for

Good contributions include:

- **Bug fixes** — something broken? Fix it and open a PR
- **Mobile improvements** — better touch handling, layout fixes on specific devices
- **Performance** — canvas rendering, Firebase query optimisation
- **Accessibility** — keyboard navigation, screen reader support
- **New features** — see the roadmap below before building something new

We are NOT looking for:

- Dependency additions (this project intentionally has zero npm dependencies)
- Framework rewrites (vanilla JS is a deliberate choice)
- Features that require a backend server (out of scope for now)

---

## Getting started

### 1. Fork the repo

Click **Fork** on GitHub, then clone your fork:

```bash
git clone https://github.com/YOUR_USERNAME/Anwit-Notepad.git
cd Anwit-Notepad
```

### 2. Set up Firebase

Follow the **Setup** steps in [README.md](README.md) to create your own Firebase project for development. Never use the production Firebase config for development.

### 3. Run locally

No build step needed. Just open `app.html` directly in your browser, or use a simple local server:

```bash
# Python
python3 -m http.server 8080

# Node.js
npx serve .
```

Then open `http://localhost:8080/app.html`

---

## Making changes

### Branch naming

```
fix/describe-the-bug
feat/describe-the-feature
chore/describe-the-task
```

### Commit messages

Keep them short and clear:

```
fix: canvas not resizing on iOS Chrome
feat: add page duplication
chore: clean up unused CSS
```

### Code style

- **No frameworks, no build tools** — plain HTML, CSS, JS only
- **No external libraries** beyond Firebase (already included via CDN)
- Keep JavaScript readable — descriptive variable names, comments on non-obvious logic
- CSS variables are defined in `:root` — use them, don't hardcode colours
- Mobile-first: test on a real mobile device before submitting

---

## Submitting a pull request

1. Make your changes on a new branch
2. Test on both desktop and mobile (Chrome and Safari on iOS if possible)
3. Open a PR against `main` with a clear description of what you changed and why
4. Link any related issues

---

## Reporting bugs

Open an issue with:

- What you expected to happen
- What actually happened
- Device and browser (e.g. iPhone 14, iOS 17, Chrome 122)
- Steps to reproduce

---

## Roadmap (good first issues)

These are things we'd welcome contributions on:

- [ ] Room expiry — auto-delete rooms inactive for 30 days via Firebase rules
- [ ] Shareable room name in the URL (in addition to the code)
- [ ] Better touch drawing on Android (pressure sensitivity)
- [ ] Dark/light theme toggle
- [ ] Keyboard shortcut for undo (Cmd/Ctrl+Z)
- [ ] Show which page the other user is currently on

---

## Questions

Open an issue and tag it `question`. We'll respond as fast as we can.
