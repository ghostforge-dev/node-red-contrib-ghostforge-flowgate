# node-red-contrib-ghostforge-flowgate

**GhostForge™ FlowGate** — API call queue and rate limiting for Node-RED.

Part of the [GhostForge™](https://github.com/ghostforge) Node-RED toolkit.

---

## What it does

Two nodes that work as a pair to serialize API calls and prevent rate limit errors:

**gf-gate-opener** — Passes the message through when the gate is free. If the gate is already open (an API call is in progress), the message is queued and waits automatically.

**gf-gate-closer** — Placed after your API response handler. Waits a configurable delay, then releases the gate. If messages are queued, the next one fires automatically.

---

## Design philosophy

- **Zero message loss** — All messages are queued, never dropped
- **Configurable delay** — Fine-tune the release timing to match your API rate limits
- **Topic-based** — Multiple independent gates can run in parallel using different topics
- **Self-healing** — Gate resets to free on Node-RED restart

---

## Installation

Via Node-RED Palette Manager: search for `ghostforge-flowgate`

Or via npm:
```bash
npm install node-red-contrib-ghostforge-flowgate
```

---

## Usage

```
[incoming msg] → [gf-gate-opener] → [API call] → [response handler] → [gf-gate-closer]
```

Set the same **Topic** on both Opener and Closer. The Opener uses global context to track gate state, so it works across subflows and tabs.

---

## Part of the GhostForge™ toolkit

- **ghostforge-vaultkey** — JIT auth & secret burning
- **ghostforge-flowgate** — API call queue & rate limiting (this package)
- **ghostforge-arrows** — Visual flow routing nodes

---

*GhostForge™ is a trademark of Zerr Remoteservice*
