# Flybridge Radar Run

Browser-basiertes 90-Sekunden Arcade-Game für [flybridge.ch](https://www.flybridge.ch).

## Spielen

**Live:** [flybridge.ch/game](https://www.flybridge.ch/game)

## Steuerung

- **Pfeiltasten / A+D** - Boot steuern
- **Q / E** - Crew-Boost aktivieren (wenn Meter voll)
- **1 / 2 / 3** - Strategy Gate wählen
- **H / ESC** - Pause

## Entwicklung

```bash
# Dependencies installieren
npm install

# Dev-Server starten
npm run dev

# Production Build
npm run build
```

## Webflow Integration

Siehe [WEBFLOW-INTEGRATION.md](WEBFLOW-INTEGRATION.md) für Details.

### Schnell-Embed:

```html
<div id="game-container" style="width:100%;max-width:800px;aspect-ratio:4/3;margin:0 auto;background:#0d1f3c;border-radius:8px;overflow:hidden;"></div>
<script src="https://cdn.jsdelivr.net/npm/phaser@3.80.1/dist/phaser.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/DEIN-USERNAME/flybridge-radar-run@main/dist/game.min.js"></script>
```

## Tech Stack

- **Engine:** Phaser 3
- **Build:** Vite + Terser
- **Backend:** Supabase (Leaderboard)
- **Assets:** 100% prozedural generiert

## Lizenz

Proprietary - Flybridge AG
