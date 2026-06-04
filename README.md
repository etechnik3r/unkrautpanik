# 🌿 Merles Unkrautpanik

> **Survival-Clicker im Browserfenster** – Rette den Hof vor dem Unkraut, bevor alles zugewuchert ist!

![HTML5](https://img.shields.io/badge/HTML5-Canvas-E34F26?logo=html5&logoColor=white)
![JavaScript](https://img.shields.io/badge/Vanilla_JS-ES6+-F7DF1E?logo=javascript&logoColor=black)
![Responsive](https://img.shields.io/badge/Responsive-Desktop_%26_Mobile-4CAF50)
![License](https://img.shields.io/badge/License-MIT-blue)

---

## 🎮 Spielidee

Ein Pflasterhof wird von Unkraut überrannt. Du musst Gräser und Löwenzahn aus den Fugen entfernen, bevor der Hof komplett zugewuchert ist. Die Schwierigkeit steigt exponentiell – wie lange hältst du durch?

**[▶️ Jetzt spielen](https://DEIN-USERNAME.github.io/merles-unkrautpanik/merles_unkrautpanik.html)**
*(Link nach Deployment anpassen)*

---

## ✨ Features

| Feature | Details |
|---|---|
| **Isometrische Perspektive** | 45°-Ansicht, prozedural gerenderte Pflastersteine |
| **Zufällige Stein-Skins** | Betongrau · Anthrazit · Klinker × Rechteck · Sechseck · S-Stein |
| **2 Unkraut-Typen** | Gras (Standard) und Löwenzahn (mit Wurzelmechanik) |
| **4 Wachstumsstadien** | Keimling → Klein → Reif → Wuchernd |
| **Werkzeuge** | ✋ Hand – 🔧 Wurzelstecher |
| **3 Superwaffen** | 🔥 Abflammer · ❄️ Spray · ⚡ Vibro-Stampfer |
| **Energie-System** | Ernten füllt die Leiste, Superwaffen verbrauchen Energie |
| **Prozedurale Sounds** | Web Audio API – keine externen Audio-Dateien nötig |
| **Partikeleffekte** | Ernte-Partikel, Feuer-Overlay, Frost-Effekt, Screen-Shake |
| **Responsive** | Desktop (Maus + Tastatur) & Mobil (Touch, optimierte Hitboxen) |
| **Achievement-System** | Pop-ups bei Meilensteinen (10, 50, 100, 250, 500, 1000) |
| **Zero Dependencies** | Keine Frameworks, keine externen Assets – eine einzige HTML-Datei |

---

## 🚀 Installation & Start

```bash
# Repository klonen
git clone https://github.com/DEIN-USERNAME/merles-unkrautpanik.git
cd merles-unkrautpanik

# Datei im Browser öffnen – fertig!
open merles_unkrautpanik.html        # macOS
xdg-open merles_unkrautpanik.html    # Linux
start merles_unkrautpanik.html       # Windows
```

Alternativ: Datei direkt per **Drag & Drop** in den Browser ziehen.

Für **GitHub Pages**: Repository-Settings → Pages → Branch `main` → Ordner `/ (root)` → Save.

---

## 🎯 Steuerung

### Desktop

| Taste | Aktion |
|---|---|
| **Mausklick** | Unkraut ernten |
| **1** | Hand auswählen |
| **2** | Wurzelstecher auswählen |
| **Q** | 🔥 Abflammer aktivieren |
| **W** | ❄️ Spray aktivieren |
| **E** | ⚡ Vibro-Stampfer aktivieren |

### Mobil

- **Tap** auf Unkraut → Ernten
- **Toolbar** am unteren Bildschirmrand für Werkzeug- und Superwaffen-Wechsel

---

## ⚙️ Balancing & Konfiguration

Alle Spielparameter sind zentral im `CONFIG`-Objekt am Anfang des `<script>`-Blocks definiert:

```javascript
const CONFIG = {
  GRID_COLS: 10,                // Raster-Breite
  GRID_ROWS: 10,                // Raster-Höhe
  BASE_SPAWN_INTERVAL: 2500,    // Basis-Spawn in ms
  GROWTH_TICK_MS: 3000,         // Wachstums-Intervall in ms
  GROWTH_RATE_INCREASE: 0.0004, // Exponentielle Schwierigkeitskurve
  DANDELION_CHANCE: 0.25,       // Löwenzahn-Wahrscheinlichkeit (0–1)
  ABFLAMMER_COST: 100,          // Energie-Kosten Abflammer
  SPRAY_COST: 60,               // Energie-Kosten Spray
  STAMPFER_COST: 40,            // Energie-Kosten Vibro-Stampfer
  SPRAY_DURATION: 10000,        // Spray-Wirkdauer in ms
  // ... weitere Parameter im Code
};
```

Einfach Werte anpassen, Datei speichern, Browser neu laden.

---

## 🧩 Architektur

```
merles_unkrautpanik.html   ← Alles in einer Datei
│
├─ HTML          Struktur: Canvas, HUD-Overlay, Toolbar, Screens
├─ CSS           Styling: Responsive Layout, Animationen, Dark-UI
└─ JavaScript
   ├─ CONFIG     Zentrale Spielparameter
   ├─ State      Globaler Spielzustand (Grid, Score, Energie, ...)
   ├─ Audio      Prozedurale Sounds via Web Audio API
   ├─ Rendering  Isometrische Projektion, prozedurale Grafiken
   ├─ Logik      Spawn, Wachstum, Ernte, Superwaffen, Achievements
   ├─ Input      Maus, Touch, Tastatur – adaptiv nach Endgerät
   └─ Game Loop  requestAnimationFrame-basiert, 60 FPS
```

---

## 🗺️ Roadmap (Ideen)

- [ ] Progression-Curve: Neue Unkraut-Typen nach Score/Zeit freischalten
- [ ] Highscore-Persistenz via `localStorage`
- [ ] Mehrere Hof-Layouts / Level
- [ ] Saisonale Skins (Herbstlaub, Schnee)
- [ ] Sound-Optionen (Lautstärkeregler)
- [ ] Multiplayer-Modus (geteiltes Feld)

---

## 📄 Lizenz

Dieses Projekt steht unter der [MIT-Lizenz](LICENSE).

---

<p align="center">
  Made with 🌿 and too much ☕
</p>
