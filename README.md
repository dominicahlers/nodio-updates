# Nodio

**Nodio** ist eine Desktop-Anwendung für strukturierte, visuelle Wissensarbeit: Inhalten auf einem **World-Canvas** (Graph), **Nodes** mit reichem Markdown-Editor, **typisierten Verbindungen**, SQLite-Projekten und Exporten (PDF, TOON). Technisch: **Electron**, **React**, **SQLite** (`better-sqlite3`). Hersteller: [Obelisk Systems](https://obelisk.systems/).

---

## Was die App bereits kann (Stand Codebase)

- **Projekte & Workspace** — Mehrere Projekte; jede Projektdatei ist eine portable **SQLite**-DB. Zentrale `workspace.db` unter dem App-Datenordner (`~/.nodio/`); externe `.db` per Dialog registrieren. **Dashboard**: anlegen, öffnen, umbenennen, **Archiv** mit Wiederherstellung, **„Zuletzt geöffnet“**-Hervorhebung.
- **World-Canvas** — Graph-Ansicht mit **@xyflow/react**: Nodes positionieren (Drag), **Pan**, **Mausrad-Zoom**, **Toolbar** (Zoom, Fit to content, neue Node in Viewport-Mitte), **Minimap** (einschließlich Tastenkürzel / Speicherung pro Projekt).
- **Gruppen** — **Hierarchische Gruppen** auf dem Canvas (Farbe, Ein-/Ausklappen, Verschachtelung).
- **Verbindungen** — **Typisierte Relationen** innerhalb des Projekts: Kanten per Anker oder Konfigurations-Flow am Node-Body; **Cross-Project** nur als Referenz-Link im Editor (kein Canvas-Edge in v1).
- **Node-Editor** — **TipTap** + Markdown in der DB: WYSIWYG-Toolbar (Überschriften, Listen, Zitat, Code, Links, Tabellen, Aufgaben, Bilder), **@-Mentions** (`nbn:`), automatische **references**-Verbindungen aus Inhalten, **Read-Ansicht** mit GFM (`remark-gfm`), Assets pro Projekt.
- **Suche & Filter** — **Titelleisten-Suche**, Treffer als Auswahl mit **Zentrierung im Viewport**, Filter nach Typ/Status/Tags, FTS-unterstützt (`nodes_fts`); Minimap-Hervorhebung.
- **Export** — **PDF** (Puppeteer, Fortschritt, Abbruch, merkbare Einstellungen); **TOON-Projektexport** inkl. Smart Export (remark-Pipeline), Dry-Run, Zielordner, optional **„Made with Nodio“** im PDF. **Markdown-Import** (Analyse, Konflikte, Fortschritt); **PNG** des Canvas über Export-Center (Presets; Detail siehe Post-MVP-Status). **Template-Bibliothek**: gebündelte und nutzerimportierte Vorlagen (`.db`).
- **Versionierung & Duplikation** — **Node-Verlauf** in SQLite (`node_history`): Snapshots, Diff/Restore in der UI, konfigurierbar. **Node duplizieren** mit Optionen für Teilbaum und Kanten.
- **Erscheinungsbild & Bedienung** — **Hell/Dunkel/OS** über Design-Tokens, **Sound-Feedbacks** (Howler, abschaltbar), **UI-Motion** (Toasts, Modale, Menüs) mit Rücksicht auf **prefers-reduced-motion**; **Tastenkürzel-Hilfe** und Overrides über Konfiguration; **Fokus-/Immersiv-Modus** (Vollbild, kompakte Chrome); **Auto-Save**-Status in der UI.
- **Lokalisierung** — **Deutsch** und **Englisch** (i18next), Modi inkl. OS und Entwickler-Modus