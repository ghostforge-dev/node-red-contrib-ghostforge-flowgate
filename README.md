# node-red-contrib-ghostforge-arrows

**GhostForge™ Arrows** — Visual flow routing nodes for Node-RED.

Part of the [GhostForge™](https://github.com/ghostforge) Node-RED toolkit.

---

## What it does

Four directional arrow nodes that pass messages unchanged and serve as visual guides in complex Node-RED flows:

- **gf-arrow-up** ↑
- **gf-arrow-down** ↓
- **gf-arrow-left** ←
- **gf-arrow-right** →

---

## Design philosophy

Node-RED flows can become visually complex with many crossing wires. Arrow nodes give you a way to indicate flow direction explicitly - making flows readable at a glance without relying on wire routing alone.

All arrow nodes are minimal: black background, white icon, no label. They blend naturally into the GhostForge™ node family.

---

## Installation

Via Node-RED Palette Manager: search for `ghostforge-arrows`

Or via npm:
```bash
npm install node-red-contrib-ghostforge-arrows
```

---

## Usage

Drop an arrow node anywhere in your flow to visually indicate direction. Wire it in-line like any other node - it simply passes `msg` through unchanged.

```
[node A] → [gf-arrow-down] → [node B]
```

---

## Part of the GhostForge™ toolkit

- **ghostforge-vaultkey** — JIT auth & secret burning
- **ghostforge-flowgate** — API call queue & rate limiting
- **ghostforge-arrows** — Visual flow routing nodes (this package)

---

*GhostForge™ is a trademark of Zerr Remoteservice*
