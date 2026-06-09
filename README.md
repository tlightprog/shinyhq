# ShinyHQ Website

The official website for **ShinyHQ, LLC** — an independent app studio. Built as a single static page; no build step, no dependencies to install.

```
site/
├── index.html        ← the website (loads at the root URL)
├── .nojekyll         ← tells GitHub Pages to serve files as-is
└── assets/
    ├── favicon.svg
    ├── cravlo-icon.png
    ├── cravlo-home.png
    ├── cravlo-discover.png
    └── cravlo-tracking.png
```

## Editing later
Everything is plain HTML/CSS in `index.html`. To swap a screenshot, replace the matching file in `assets/` (keep the same filename) and re-upload. Fonts load from Google Fonts over the network.
