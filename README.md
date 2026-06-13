# 📏 Online Ruler

**A free, actual-size ruler that lives in your browser.** Measure any object directly on your screen in centimeters, millimeters, or inches — no app, no sign-up, works on any phone, tablet, or desktop.

> Calibrate once with a credit card, then drag the orange block to wrap your object. Width and height read out live, at true real-world size.

---

## ✨ Features

- **Actual-size measuring** — the scale runs along the top *and* left edges at once, so you read width and height together.
- **Drag-to-measure block** — grab the orange block and stretch it over your object; live readouts update instantly.
- **Credit-card calibration** — screens vary in pixel density, so calibrate once against a standard 85.6 mm card for true accuracy. The setting is saved on your device.
- **cm / mm / inch units** — switch between metric and imperial on the fly.
- **Lock to prevent bumps** — lock the calibration so you don't nudge it by accident mid-measurement.
- **Works everywhere** — responsive layout for phone, tablet, and desktop. Use your phone as a pocket ruler.
- **Zero dependencies** — a single self-contained `index.html`. No build step, no frameworks, no tracking.

## 🚀 Getting started

It's one static file. Either open it locally or host it anywhere.

```bash
# Clone the repo
git clone https://github.com/dotbatch/onlineruler.git
cd onlineruler

# Open the page in your browser
open "Ruler website/index.html"      # macOS
start "Ruler website\index.html"     # Windows
```

Or drop the `Ruler website` folder onto any static host (GitHub Pages, Netlify, Vercel, S3) and you're live.

## 🎯 How to use

1. **Calibrate** — tap **⚙ Calibrate**, lay a bank or credit card flat on your screen, and drag the slider until the orange bar exactly matches the card's width. Tap **Save**.
2. **Lock** — tap the 🔒 so you don't bump the calibration later.
3. **Measure** — place your object in the top-left corner and drag the handles until the block covers it. The live width and height update in cm or inches.

## 🛠️ Tech

Plain HTML, CSS, and vanilla JavaScript in a single file. Calibration is persisted with `localStorage`, so each device remembers its own pixel density (default fallback is 96 DPI / 37.8 px per cm).

## 📁 Repository structure

```
onlineruler/
├── README.md
├── .gitignore
└── Ruler website/
    ├── index.html                     # the app — open this
    ├── Online_Ruler_SEO_Keywords.md   # SEO keyword research
    └── Online_Ruler_SEO_Keywords.xlsx
```

## 🤝 Contributing

Issues and pull requests are welcome. Since it's a single static file, contributing is as simple as editing `index.html` and opening it in your browser to test.

## 📄 License

No license specified yet. If you'd like others to reuse this, consider adding one (e.g. MIT).
