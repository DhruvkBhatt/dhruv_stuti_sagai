# 💍 Dhruv & Stuti — Sagai

A white-and-gold one-page countdown for the ring ceremony: **Sunday, 18 October 2026, 11:00 PM IST**.

| File | |
|---|---|
| `index.html` | The whole site — HTML, CSS and JS in one file. No build step. |
| `.nojekyll` | Tells GitHub Pages to serve files as-is. |

## Editing

Everything editable is in the `CONFIG`, `STORY`, `RECRUITMENT`, `TITLES`, `CHECKLIST`, `CLAUSES`, `RITUALS` and `THINGS` blocks at the top of the `<script>`:

```js
const CONFIG = {
  start: '2026-10-18T23:00:00+05:30',
  venue: 'Ahmedabad', city: 'Gujarat, India', mapUrl: '…',  // add the hall name + exact map pin
  music: '',                          // optional mp3 → shows a ♪ button
  wishEndpoint: ''                    // optional Google Apps Script URL to collect blessings
};
```

## Countdown states

| When | What shows |
|---|---|
| > 24 h before | Live countdown |
| < 24 h / < 1 h | Countdown + excited status line |
| 11:00 PM – 1:00 AM | Clock flips to **"Engaged for"** and counts up (12:00 AM → 00d 01h 00m) + confetti |
| After | Keeps counting up forever: days · hours · minutes · seconds since the ring |

Preview any state before the day: `index.html?preview=day`, `?preview=hour`, `?preview=live`, `?preview=midnight`, `?preview=after`.

## Run / deploy

Open `index.html` in a browser. To deploy: push to GitHub → Settings → Pages → `main` / root, or drag the folder onto https://app.netlify.com/drop.

Blessings are kept in the visitor's browser (`localStorage`) unless `wishEndpoint` is set.
