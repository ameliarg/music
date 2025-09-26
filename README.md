# music
 desktop music player built with Electron. It features a sparkly UI, animated GIF art, a minimal playlist, and simple controls (play/pause/skip) powered by the HTML5 Audio element.
✨ Features
Adorable UI with animated star “glitter” and pastel gradients
Now Playing panel with title + artist
Play / Pause / Skip controls
Seekable progress bar with current time & duration
Local playlist defined in JavaScript (no network required)
Packaged app via electron-builder (DMG on macOS by default)

Project Structure
melia-music-player/
├─ assets/
│  ├─ music/
│  │  ├─ song1.mp3
│  │  ├─ song2.mp3
│  │  └─ ...
│  └─ cinnamoroll.gif
├─ icon.icns
├─ index.html          # UI (HTML/CSS/JS inline)
├─ main.js             # Electron main process
├─ preload.js          # (kept for isolation-ready bridge; minimal)
├─ package.json
└─ README.md


Quick Start (Dev)
Requirements
Node.js 18+ (recommended)
macOS, Windows, or Linux
Install & Run
npm install
npm start
Electron will open a 400 × 600 window with your player UI.

Build a Desktop App
This repo is set up with electron-builder. By default your package.json builds a macOS DMG:
npm run dist

Output
macOS: dist/Melia Music Player-*.dmg
Want Windows/Linux builds too? Add targets in package.json > build, for example:
"build": {
  "appId": "com.melia.musicplayer",
  "productName": "Melia Music Player",
  "mac": { "target": "dmg", "icon": "icon.icns" },
  "win": { "target": "nsis", "icon": "icon.ico" },
  "linux": { "target": "AppImage", "icon": "icons/" },
  "files": ["index.html","main.js","preload.js","assets/**/*","icon.icns"]
}

Customize the Playlist
In index.html, update the songs array:
const songs = [
  { title: "runaway", artist: "mars argo", path: "assets/music/song1.mp3" },
  { title: "black sheep", artist: "metric", path: "assets/music/song2.mp3" },
  // add or remove entries as you like
];
⚠️ Only include audio you own or are allowed to distribute. Consider leaving assets/music/ empty in the repo and asking users to drop in their own files.

MIT License

Copyright (c) 2025 Amelia Gannon

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
...

Credits
UI font: Cherry Bomb One (Google Fonts)
Icons: inline SVGs in index.html
Concept & design by Amelia Gannon
