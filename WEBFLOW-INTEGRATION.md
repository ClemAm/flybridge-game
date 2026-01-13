# Webflow Integration - Flybridge Radar Run

## Option 1: GitHub + jsDelivr (Empfohlen)

### Schritt 1: GitHub Repository erstellen
1. Gehe zu https://github.com/new
2. Repository Name: `flybridge-radar-run`
3. Auf "Create repository" klicken
4. Die Datei `dist/game.min.js` hochladen

### Schritt 2: In Webflow einbetten

Füge folgenden Code in ein **Embed**-Element auf deiner Webflow-Seite ein:

```html
<!-- Game Container -->
<div id="game-container" style="width:100%;max-width:800px;aspect-ratio:4/3;margin:0 auto;background:#0d1f3c;border-radius:8px;overflow:hidden;box-shadow:0 4px 20px rgba(0,0,0,0.5);"></div>

<!-- Phaser 3 Engine -->
<script src="https://cdn.jsdelivr.net/npm/phaser@3.80.1/dist/phaser.min.js"></script>

<!-- Game Code von jsDelivr (ersetze USERNAME mit deinem GitHub-Benutzernamen) -->
<script src="https://cdn.jsdelivr.net/gh/USERNAME/flybridge-radar-run@main/dist/game.min.js"></script>
```

**Wichtig:** Ersetze `USERNAME` mit deinem GitHub-Benutzernamen!

---

## Option 2: Externe Hosting (z.B. Cloudflare R2, AWS S3)

1. Lade `dist/game.min.js` auf deinen Hosting-Service hoch
2. Verwende die URL im Embed-Code:

```html
<!-- Game Container -->
<div id="game-container" style="width:100%;max-width:800px;aspect-ratio:4/3;margin:0 auto;background:#0d1f3c;border-radius:8px;overflow:hidden;box-shadow:0 4px 20px rgba(0,0,0,0.5);"></div>

<!-- Phaser 3 Engine -->
<script src="https://cdn.jsdelivr.net/npm/phaser@3.80.1/dist/phaser.min.js"></script>

<!-- Game Code von deinem Hosting -->
<script src="https://deine-domain.com/game.min.js"></script>
```

---

## Option 3: Inline Code (falls <100KB)

Falls der Code klein genug ist, kannst du ihn direkt in Webflow's Custom Code einbetten:

### Im Page Settings > Custom Code > Before </body>:

```html
<!-- Game Container muss zuerst auf der Seite existieren via Embed-Element -->
<script src="https://cdn.jsdelivr.net/npm/phaser@3.80.1/dist/phaser.min.js"></script>
<script>
// Hier den Inhalt von dist/game.min.js einfügen
</script>
```

---

## Styling Optionen

### Responsive Container (empfohlen):
```html
<div id="game-container" style="
  width: 100%;
  max-width: 800px;
  aspect-ratio: 4/3;
  margin: 0 auto;
  background: #0d1f3c;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 4px 20px rgba(0,0,0,0.5);
"></div>
```

### Vollbreite:
```html
<div id="game-container" style="
  width: 100%;
  max-width: 1200px;
  aspect-ratio: 4/3;
  margin: 0 auto;
"></div>
```

---

## Troubleshooting

### Game wird nicht angezeigt:
1. Prüfe Browser-Console (F12) auf Fehler
2. Stelle sicher, dass Phaser VOR dem Game-Code geladen wird
3. Container muss `id="game-container"` haben

### Touch funktioniert nicht auf Mobile:
Füge dem Container hinzu: `touch-action: none;`

### Performance-Probleme:
- Das Spiel ist für 60 FPS optimiert
- Bei älteren Geräten kann die Performance variieren

---

## Dateigrösse

- **game.min.js**: ~80 KB
- **Phaser 3**: ~1.2 MB (von CDN, wird gecached)
- **Gzip komprimiert**: ~23 KB + ~350 KB

---

## Updates

Bei Änderungen am Spiel:
1. `npm run build` ausführen
2. Neue `dist/game.min.js` auf GitHub/Hosting hochladen
3. jsDelivr Cache leeren: https://purge.jsdelivr.net/gh/USERNAME/flybridge-radar-run@main/dist/game.min.js
