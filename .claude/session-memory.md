# Session Memory - Peppermint Digital Website Redesign

## Session-Notizen

### Session 3 - 15. Januar 2026
- Team-Bilder auf Agentur-Seite hinzugefügt (8 Mitglieder von Original-Seite)
- Hero-Bild URL korrigiert (404 fix → `header-agentur.webp`)
- Team-Bild Hintergrund-Problem behoben (orange an runden Kanten)
- **Filmproduktion Prozess-Sektion komplett neu designed:** Glasmorphism, gleich hohe Karten, Fortschrittsbalken, dezente große Nummern
- Commits gemacht, noch nicht gepusht

### Session 2 - [Datum unbekannt]
- Alle Hauptseiten erstellt
- Bilder von Original-Seite integriert
- Navigation und Layout fertiggestellt

### Session 1 - [Datum unbekannt]
- Projekt initialisiert
- Nuxt 4 Setup mit @nuxt/ui
- Grundstruktur angelegt

---

## Projektübersicht
Neugestaltung der Webseite für Peppermint Digital basierend auf https://peppermint-digital.de/
- Framework: Nuxt 4 mit @nuxt/ui
- Styling: Tailwind CSS
- Farbschema: Dunkel (gray-950) mit Orange (#f97316) als Akzentfarbe

---

## Erledigte Aufgaben

### 1. Grundstruktur erstellt
- [x] Nuxt-Konfiguration angepasst (`nuxt.config.ts`)
- [x] CSS-Styling eingerichtet (`app/assets/css/main.css`)
- [x] App-Konfiguration (`app/app.config.ts`)
- [x] Haupt-App-Komponente (`app/app.vue`)

### 2. Layout & Navigation
- [x] Default Layout mit Navigation und Footer (`app/layouts/default.vue`)
- [x] Dropdown-Menüs für "Agentur" und "Service"
- [x] Mobile-responsive Navigation mit Hamburger-Menü
- [x] Aktive Seiten werden orange hervorgehoben

### 3. Erstellte Seiten

| Seite | Pfad | Status |
|-------|------|--------|
| Homepage | `/` | ✅ Fertig |
| Agentur | `/agentur` | ✅ Fertig |
| Services Übersicht | `/services` | ✅ Fertig |
| Filmproduktion | `/services/filmproduktion` | ✅ Fertig |
| Webdesign | `/services/webdesign` | ✅ Fertig |
| Software | `/services/software` | ✅ Fertig |
| Marketing | `/services/marketing` | ✅ Fertig |
| Studio | `/studio` | ✅ Fertig |
| Projekte/Success Stories | `/projekte` | ✅ Fertig |
| Kontakt | `/kontakt` | ✅ Fertig |

### 4. Bilder integriert
- [x] Hero-Hintergrundbilder (rotierende Slideshow)
- [x] Kunden-Logos (Cars & Bytes, Hannover 96, Domino's, Bentley, TÜV Nord, etc.)
- [x] Projekt-Bilder (PAYEASY, Agritechnica, Cars & Bytes, etc.)
- [x] Studio-Bilder (Werkstattstudio Hannover)
- [x] Nuxt Image für externe Domain konfiguriert
- [x] Team-Bilder auf Agentur-Seite (8 Teammitglieder mit echten Fotos)
- [x] Hero-Bild auf Agentur-Seite (`header-agentur.webp`)

### 5. Features implementiert
- [x] Animierte Stats-Zähler
- [x] Marquee-Animation für Kunden-Logos
- [x] Hover-Effekte auf Cards
- [x] Smooth Scrolling
- [x] Responsive Design

### 6. Design-Verbesserungen (Session 15.01.2026)
- [x] **Agentur-Seite Team-Bereich:**
  - Team-Bilder von Original-Seite integriert (8 Mitglieder)
  - Hero-Bild korrigiert (war 404, jetzt `header-agentur.webp`)
  - Hintergrund bei Teambildern entfernt (war orange sichtbar an runden Kanten)
  - `object-top` für bessere Gesichter-Fokussierung

- [x] **Filmproduktion Prozess-Sektion:**
  - Komplett neu designt mit modernem Look
  - Alle Karten gleich hoch durch Flexbox-Layout
  - Glasmorphism-Effekt (`backdrop-blur-sm`, halbtransparenter Hintergrund)
  - Große dezente Schrittnummern (01, 02, 03, 04) als Designelement
  - Icons für jeden Prozessschritt
  - Fortschrittsbalken am unteren Rand (25%, 50%, 75%, 100%)
  - Subtile Hover-Effekte ohne sprunghafte Animation
  - Gradient-Hintergrund für mehr Tiefe

---

## Offene Aufgaben / TODOs

### Priorität Hoch
- [ ] Server neu starten um alle Seiten zu erkennen
- [ ] Impressum-Seite erstellen (`/impressum`)
- [ ] Datenschutz-Seite erstellen (`/datenschutz`)

### Priorität Mittel
- [ ] Echte Kontaktformular-Funktionalität (Backend/API)
- [ ] SEO Meta-Tags pro Seite
- [ ] Favicon und Open Graph Images
- [ ] 404-Seite gestalten

### Priorität Niedrig
- [ ] Animationen optimieren
- [ ] Lazy Loading für Bilder
- [ ] Performance-Optimierung
- [ ] Unit Tests

---

## Technische Details

### Dateistruktur
```
app/
├── app.vue
├── app.config.ts
├── assets/
│   └── css/
│       └── main.css
├── layouts/
│   └── default.vue
└── pages/
    ├── index.vue
    ├── agentur/
    │   └── index.vue
    ├── services/
    │   ├── index.vue
    │   ├── filmproduktion.vue
    │   ├── webdesign.vue
    │   ├── software.vue
    │   └── marketing.vue
    ├── studio/
    │   └── index.vue
    ├── projekte/
    │   └── index.vue
    └── kontakt/
        └── index.vue
```

### Externe Bild-URLs
Die Bilder werden direkt von `peppermint-digital.de` geladen:
- Hero-Bilder: `/wp-content/uploads/2024/09/peppermint-digital-header-*.webp`
- Logos: `/*.webp` / `/*.png`
- Projekt-Bilder: `/wp-content/uploads/2024/*/`
- Studio-Bilder: `/wp-content/uploads/2024/06/werkstattstudio-*.webp`
- Team-Bilder: `/teambilder/*.webp` (z.B. `volker-tolksdorf.webp`, `roman-jordan.webp`)
- Agentur Hero: `/header-agentur.webp`

### Wichtige Konfigurationen
```typescript
// nuxt.config.ts
image: {
  domains: ['peppermint-digital.de'],
  alias: {
    peppermint: 'https://peppermint-digital.de'
  }
}
```

---

## Bekannte Probleme

1. **Dev-Server erkennt neue Seiten nicht automatisch**
   - Lösung: Server manuell neu starten mit `npm run dev`

2. **Bilder können nicht lokal heruntergeladen werden**
   - Workaround: Externe URLs verwenden

---

## Nächste Schritte für folgende Session

1. Server neu starten und alle Seiten testen
2. Fehlende Seiten (Impressum, Datenschutz) erstellen
3. Kontaktformular-Backend implementieren
4. SEO-Optimierung

---

## Git Status

### Commits (noch nicht gepusht)
Es gibt mehrere lokale Commits die noch auf `origin/main` gepusht werden müssen:
- Team-Bilder auf Agentur-Seite hinzugefügt
- Hero-Bild URL korrigiert (404 fix)
- Hintergrund bei Team-Bildern entfernt
- Prozess-Sektion Redesign auf Filmproduktion-Seite

**Wichtig:** User muss manuell `git push origin main` ausführen!

---

## Code-Snippets für Referenz

### Team-Array (agentur/index.vue)
```typescript
const team = [
  { name: 'Volker Tolksdorf', role: 'Geschäftsführer', image: 'https://peppermint-digital.de/teambilder/volker-tolksdorf.webp' },
  { name: 'Roman Jordan', role: 'Geschäftsführer', image: 'https://peppermint-digital.de/teambilder/roman-jordan.webp' },
  { name: 'Chris Tolksdorf', role: 'Prokurist', image: 'https://peppermint-digital.de/teambilder/chris-tolksdorf.webp' },
  { name: 'Sarah Kurzidim', role: 'Buchhaltung', image: 'https://peppermint-digital.de/teambilder/sarah.webp' },
  { name: 'Bastian Henneberg', role: 'Head of Development', image: 'https://peppermint-digital.de/teambilder/bastian-henneberg.webp' },
  { name: 'Pauline Weber', role: 'Mediengestalterin', image: 'https://peppermint-digital.de/teambilder/pauline-gottschalk.webp' },
  { name: 'Mika Lehr', role: '3D Artist & Video-Operator', image: 'https://peppermint-digital.de/teambilder/mika-lehr.webp' },
  { name: 'Klaus Henneberg', role: 'Produktion', image: 'https://peppermint-digital.de/teambilder/klaus-henneberg.webp' },
]
```

### Prozess-Array (filmproduktion.vue)
```typescript
const prozess = [
  { step: '01', title: 'Konzeption', description: '...', icon: 'i-heroicons-light-bulb' },
  { step: '02', title: 'Pre-Production', description: '...', icon: 'i-heroicons-clipboard-document-list' },
  { step: '03', title: 'Produktion', description: '...', icon: 'i-heroicons-video-camera' },
  { step: '04', title: 'Post-Production', description: '...', icon: 'i-heroicons-scissors' },
]
```

---

## Kontakt Original-Webseite
- Telefon: +49 (0) 176 3189 0002
- Standort: Hannover / Langenhagen
- Social: Instagram, TikTok, LinkedIn
