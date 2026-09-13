# 🍳 Rezepte-Vault

Meine persönliche Rezeptsammlung als Markdown — gepflegt in Obsidian, versioniert mit Git, und über [HomeDocs](https://github.com/wendevlin/homeassistant-addons) live in Home Assistant eingebunden.

## Wie das funktioniert

- Jedes Rezept ist eine eigene `.md`-Datei unter [`recipes/`](./recipes).
- Ein Home-Assistant-Server pullt dieses Repo regelmäßig und rendert die Dateien über das HomeDocs-Add-on als kleine Web-Doku — Rezepte sind damit von jedem Gerät im Netzwerk aus abrufbar, ohne separate App.
- Änderungen passieren einfach per Git-Commit — kein Build-Schritt, keine Datenbank-Migration.

## Rezept-Format

Jedes Rezept nutzt YAML-Frontmatter für strukturierte Metadaten (Zutaten, Zeit, Tags), gefolgt vom eigentlichen Rezepttext in normalem Markdown:

```markdown
---
title: Pasta Carbonara
tags: [pasta, italienisch, schnell]
vegan: false
vegetarisch: false
zeit_minuten: 25
portionen: 2
---

## Zutaten
- 200 g Spaghetti
- 100 g Guanciale
- 2 Eier
- 50 g Pecorino

## Zubereitung
1. ...
```

Die Frontmatter-Felder sind bewusst simpel gehalten, damit sie sich später auch strukturiert auswerten lassen (z. B. Filtern nach Zeit oder Ernährungsform).

## Struktur

```
recipes/
├── carbonara.md
├── risotto.md
└── ...
```

## Nutzung / eigenes Setup

Wer das Setup nachbauen will: Repo klonen, `git pull` per `shell_command` + Automation in Home Assistant einrichten, Zielordner ist das `homedocs`-Verzeichnis des [HomeDocs-Add-ons](https://community.home-assistant.io/t/home-assistant-add-on-homedocs/735151). Details dazu findet ihr in der Add-on-Doku.

## Lizenz

Der Inhalt dieses Repos steht unter [CC BY-ND 4.0](./LICENSE) — Nutzung und Weitergabe (auch kommerziell) sind erlaubt, solange die Urheberschaft genannt wird. Veränderte/abgeleitete Versionen dürfen nicht weiterverbreitet werden. Nachkochen und für den eigenen Gebrauch anpassen ist davon natürlich unbenommen — das betrifft nur das Weiterverbreiten veränderter Inhalte.
