# NAPALM Daily Check In

A two minute end of day check in for mood, stress and triggers. It runs entirely in the browser. There is no server, and every entry stays on the device that made it.

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app: screens, styles and logic |
| `manifest.webmanifest` | Lets phones install it to the home screen with the NAPALM name and icon |
| `sw.js` | Offline support, so check ins work without a connection |
| `icons/` | App icons for Android, iPhone and the browser tab |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |

## Deploy to GitHub Pages

1. Sign in to GitHub and create a new repository, for example `napalm`. It can be public or private (Pages from a private repository needs a paid GitHub plan).
2. On the repository page, choose **Add file > Upload files**. Drag in `index.html`, `manifest.webmanifest`, `sw.js`, `.nojekyll`, `README.md` and the whole `icons` folder. Commit to the `main` branch.
   - `.nojekyll` starts with a dot, so your computer may hide it. On a Mac press Cmd + Shift + . in Finder to show it. If it will not upload, skip it; the app still works.
3. Go to **Settings > Pages**. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to **main**, folder to **/ (root)**, then **Save**.
4. Wait one to two minutes. The page shows your address, for example `https://your-username.github.io/napalm/`.

To update the app later, upload the new `index.html` over the old one. If you change `sw.js` or want phones to pick up changes faster, change `napalm-v1` to `napalm-v2` in `sw.js`.

## Install on a phone

- iPhone: open the address in Safari, tap Share, then **Add to Home Screen**.
- Android: open it in Chrome, tap the menu, then **Install app** or **Add to Home screen**.

Once installed, it opens full screen like an app and works offline after the first visit. The Call and Text buttons on the Support page open the phone's dialler and messages app.

## Privacy notes

- Data is stored in the browser's local storage for that site address only. It does not sync between devices or browsers.
- Clearing the browser's site data, or deleting the home screen app on iPhone, erases all entries. Use **Settings > Export your data > Full backup** regularly, and **Restore from a full backup** to move data to a new device.
- Entries made in the Claude preview version do not carry over. Export a full backup there and restore it in the deployed app.
- The passcode lock encrypts entries with AES 256. A forgotten passcode cannot be recovered.
- The GitHub Pages address is public. Anyone with the link can open the app, but they only see their own entries, never yours. `noindex` asks search engines not to list it.

## Not a medical device

NAPALM helps people track how they feel and what affects them. It does not diagnose, treat or replace care from a qualified health professional. In an emergency, call 000.
