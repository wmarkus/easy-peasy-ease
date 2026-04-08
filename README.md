# easy-peasy-ease

> Client-side video editor that stitches segments into seamless loops with custom ease curves and background music — no server, no upload, runs entirely in the browser.

Best on desktop Chrome or Firefox. Weekend project — known frame-drop issue on Android Chrome.

```mermaid
flowchart LR
    U["Upload\nvideo segments"] --> O["Order\n& trim"]
    O --> B["Apply\nBezier speed curve"]
    B --> S["Stitch\ninto MP4"]
    S --> A["Mix\naudio"]
    A --> D["Download"]
```

## Features

- **Browser-only** — all encoding via [Mediabunny](https://mediabunny.dev/) (WASM/JS), no server
- **Custom speed curves** — cubic Bezier editor + presets for ease-in, ease-out, bounce, spring
- **Audio mixing** — layer background music over the stitched video client-side
- **Visual timeline** — drag to reorder clips, scrub to trim
- **Waveform visualization** — see audio shape while mixing
- **Session-only** — no storage, no account; data is ephemeral

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Framework | Next.js 16 (App Router) + React 19 |
| Language | TypeScript 5 |
| Video engine | Mediabunny (client-side MP4 encoding) |
| Styling | Tailwind CSS 4 + shadcn/ui |
| Animation | Motion (Framer Motion) |
| Testing | Vitest |

## Getting Started

```bash
npm install
npm run dev      # localhost:3000
```

```bash
npm run build    # Production build
npm run lint     # ESLint
npm test         # Vitest
```

## Architecture

See [ARCHITECTURE.md](ARCHITECTURE.md) for component breakdown and data flow.
