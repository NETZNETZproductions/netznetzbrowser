# NN Browser

A lightweight, custom desktop browser built with Electron by **NetzNetzProductions™**.

[![Latest release](https://img.shields.io/github/v/release/NETZNETZproductions/netznetzbrowser)](https://github.com/NETZNETZproductions/netznetzbrowser/releases)
[![Downloads](https://img.shields.io/github/downloads/NETZNETZproductions/netznetzbrowser/total)](https://github.com/NETZNETZproductions/netznetzbrowser/releases)

## Features

- **Custom window design**: frameless, transparent window with its own title bar
- **Built-in ad blocker**: blocks common ad and tracking domains, with a live counter and an on/off toggle
- **Live network traffic**: see download and upload speed in real time
- **Memory usage per tab**: check how much RAM each tab uses
- **Download manager**: progress tracking and "show in folder"
- **Context menu**: open links in a new tab (also in the background), copy link, copy text, inspect element
- **Automatic updates**: checks GitHub for new releases and installs them for you

## Installation

1. Go to the [Releases page](https://github.com/NETZNETZproductions/netznetzbrowser/releases).
2. Download the latest `NN-Browser-Setup-x.x.x.exe`.
3. Run it. That's it.

The browser updates itself from now on. It checks for new versions on startup and every 30 minutes, downloads them in the background, and asks you when to restart and install.

> **Platform:** Windows 10/11

## Development

**Requirements:** [Node.js](https://nodejs.org/) (LTS recommended)

```bash
git clone https://github.com/NETZNETZproductions/netznetzbrowser.git
cd netznetzbrowser
npm install
npm start
```

Auto-update is disabled when running with `npm start`. It only works in the built app.

### Build locally

```bash
npm run build
```

The installer is created in the `dist` folder.

## Publishing a new release

1. Bump `version` in `package.json` (it must be higher than the previous one).
2. Write the changes into `release-notes.md`.
3. Create a GitHub personal access token with `repo` permission and set it in your terminal (never commit it):
   ```bash
   set GH_TOKEN=your_token
   ```
4. Publish:
   ```bash
   npm run release
   ```

This builds the app and uploads the installer, `latest.yml`, and the `.blockmap` file to GitHub Releases. Installed browsers pick it up automatically. Do not delete `latest.yml`, the updater needs it.

## Project structure

| File | Purpose |
| --- | --- |
| `main.js` | Electron main process: window, ad blocker, traffic, downloads, auto-updater |
| `index.html` | Browser interface |
| `package.json` | App info, scripts, and build/publish configuration |
| `release-notes.md` | Changelog text used for GitHub releases |
| `logo.ico` | App icon |

## License

© NetzNetzProductions™. All rights reserved.
