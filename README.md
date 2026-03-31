# Anwit's Notepad ✦

A private, real-time shared canvas for two people — with a Stranger Things aesthetic.

Create a room, share the code, draw and write together. No accounts. No tracking. Just a private shared space.

**[→ Live Demo](https://anwit16.github.io/Anwit-Notepad)**

---

## What it looks like

- Dark Upside Down aesthetic — deep blacks, red glow, Nosifer font
- 26 Christmas lights across the top (A–Z) that can spell out words letter by letter
- Real-time stroke sync — your partner sees your drawing as you draw it
- Waiting room with admin admit/deny — nobody gets in without your permission
- "The Gate is Open" cinematic sequence when a second user joins

---

## Features

| Feature | Description |
|---|---|
| **Private rooms** | 6-character room code + 4-digit PIN. Each room is completely isolated. |
| **Real-time canvas** | Strokes sync to all users in under a second via Firebase. |
| **Multiple pages** | Add, rename, delete pages. All synced. |
| **Per-user undo** | Undo removes only your own last stroke. |
| **Admin controls** | Kick users, lock canvas to read-only, clear all. |
| **Message in lights** | Type a word — the lights bar spells it out letter by letter. |
| **Morse code mode** | Tap the canvas to send pulse ripples to your partner. |
| **Export PNG** | Download the current canvas as a dark-background PNG. |
| **Auto-resume** | Reload the page — your room and canvas state are restored. |
| **Mobile responsive** | Works on iPhone, Android, desktop. Draw with finger or mouse. |

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML, CSS, JavaScript — single file, zero build step |
| Real-time sync | Firebase Realtime Database |
| Hosting | GitHub Pages (free, no bandwidth limits) |
| Fonts | Google Fonts — Nosifer, DM Mono |

No frameworks. No npm. No bundler. One HTML file.

---

## Setup

### 1. Fork or clone this repo

```bash
git clone https://github.com/Anwit16/Anwit-Notepad.git
cd Anwit-Notepad
```

### 2. Create a Firebase project

1. Go to [console.firebase.google.com](https://console.firebase.google.com)
2. Click **Add project** → give it a name → disable Google Analytics → **Create**
3. In your project, go to **Build → Realtime Database**
4. Click **Create Database** → choose a region → select **Start in test mode** → **Enable**
5. Go to **Project Settings** (gear icon) → **Your apps** → click the **`</>`** (Web) icon
6. Register the app with any nickname → copy the `firebaseConfig` object

### 3. Add your Firebase config to the app

Open `app.html` and find this section near the top of the `<script>`:

```javascript
const FB = {
  apiKey:           "YOUR_API_KEY",
  authDomain:       "YOUR_PROJECT_ID.firebaseapp.com",
  databaseURL:      "https://YOUR_PROJECT_ID-default-rtdb.YOUR_REGION.firebasedatabase.app",
  projectId:        "YOUR_PROJECT_ID",
  storageBucket:    "YOUR_PROJECT_ID.firebasestorage.app",
  messagingSenderId:"YOUR_MESSAGING_SENDER_ID",
  appId:            "YOUR_APP_ID"
};
```

Replace each placeholder with your actual values from Firebase.

### 4. Apply Firebase security rules

1. In Firebase Console → **Realtime Database → Rules**
2. Replace the default rules with the contents of `firebase-rules.json` in this repo
3. Click **Publish**

### 5. Deploy to GitHub Pages

1. Push your changes to your GitHub repository
2. Go to **Settings → Pages**
3. Source: **Deploy from a branch** → `main` → **Save**
4. Your site will be live at `https://yourusername.github.io/your-repo-name`

---

## File Structure

```
/
├── index.html          # Landing page
├── app.html            # The notepad app
├── firebase-rules.json # Firebase security rules
├── LICENSE             # MIT License
├── README.md           # This file
└── CONTRIBUTING.md     # How to contribute
```

---

## How rooms work

- Each room gets a **unique 6-character code** (e.g. `XK9P2M`) generated on creation
- Rooms are stored in Firebase under `rooms/{roomCode}/`
- The **room creator is always the admin** — saved in localStorage per room
- Guests go through a **waiting room** — admin admits or denies them
- A shareable link (`?room=XKPQ2M`) auto-fills the room code for the joiner
- Canvas state persists in Firebase — reloading restores the last state

---

## Contributing

Contributions are welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

---

## License

MIT — see [LICENSE](LICENSE) for details.

---

## Acknowledgements

- Inspired by the Stranger Things Christmas lights scene
- Built with [Firebase](https://firebase.google.com) and [Nosifer font](https://fonts.google.com/specimen/Nosifer)
