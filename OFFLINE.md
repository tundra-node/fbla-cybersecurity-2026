# Running offline

The live site needs internet. To study somewhere without it (a plane, a hotel with bad Wi-Fi), set this up while you still have a connection.

## One-time setup (needs internet)

You need Node.js 18 or newer and Git.

```bash
git clone https://github.com/tundra-node/fbla-cybersecurity-2026.git
cd fbla-cybersecurity-2026
npm ci
npm run build
```

## Running it (no internet needed)

### Option A: built version

```bash
npm run preview
```

Open http://localhost:4173/fbla-cybersecurity-2026/

The build is made for GitHub Pages, so every asset path starts with `/fbla-cybersecurity-2026/`. Serving `dist/` at the root with `npx serve dist` or `python3 -m http.server` gives a blank page, and opening `dist/index.html` directly does not work either. Use `npm run preview`.

### Option B: dev server

```bash
npm run dev
```

Open http://localhost:3000/fbla-cybersecurity-2026/

## Notes

- The JetBrains Mono font loads from Google Fonts. Offline, the app falls back to your system monospace font. Everything else works.
- Progress, the wrong answer bank, flashcard state and session history live in your browser's localStorage. They stay between sessions on the same browser and port, and they do not sync between devices.
- Changing the port (for example `npm run preview -- --port 8080`) gives the page a new origin, so saved progress will not carry over.

## Pre-flight checklist

- [ ] Clone the repo
- [ ] `npm ci`
- [ ] `npm run build`
- [ ] Run `npm run preview` and confirm the page loads
- [ ] Bookmark http://localhost:4173/fbla-cybersecurity-2026/
