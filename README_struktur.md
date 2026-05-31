# Nordicta Internal Website — struktur & versionering

## Mappstruktur

```
Nordicta Internal Website/
├── index.html                  ← startsidan (ligger kvar i roten, navet)  ← AKTUELL
├── index_v1.0.html             ← arkiv (innan unified header)
├── README_struktur.md          ← den här filen
│
├── jourschema/
│   ├── jourschema_v1.0.html    ← original (innan ombyggnad)
│   ├── jourschema_v2.0.html    ← 3-kolumnslayout (stor ändring)
│   ├── jourschema_v2.1.html    ← + klickbara veckor i kalendern (liten ändring)
│   ├── jourschema_v3.0.html    ← Kommande veckor: majoritet/klick/scroll + sticky sidokolumner (stor ändring)
│   ├── jourschema_v3.1.html    ← unified header (liten ändring)
│   └── jourschema_v4.0.html    ← redigeringslås (flytande lås, auto-lås 30s) (stor ändring)  ← AKTUELL
│
├── Städföretag/
│   ├── Städföretag_v5.html     ← original
│   └── Städföretag_v5.1.html   ← unified header (liten ändring)  ← AKTUELL
│
├── Nordicta_Protocol/
│   ├── Nordicta_Protocol_i_web_form_v4.html     ← original
│   └── Nordicta_Protocol_i_web_form_v4.1.html   ← unified header (liten ändring)  ← AKTUELL
│
└── Inventarielista/
    ├── inventarie_v1.0.html    ← original
    └── inventarie_v1.1.html    ← unified header (liten ändring)  ← AKTUELL
```

Varje sida har fått en egen mapp. **index.html ligger kvar i roten** eftersom
det är startsidan – då fungerar den som nav och länkarna blir enklast. (Lägg den
inte i en undermapp; då slutar den fungera som naturlig ingång.)

## Hur länkarna fungerar nu

- Startsidans kort pekar in i undermapparna, t.ex.
  `jourschema/jourschema_v4.0.html`.
- Varje undersida länkar tillbaka till startsidan med `../index.html`
  (en nivå upp).

**Viktigt:** När du gör en ny version av en sida – uppdatera länken i `index.html`
så den pekar på den nya filen (t.ex. `jourschema_v2.1.html` → `jourschema_v2.2.html`).
Det är en enda rad per sida.

## Versioneringssystem

- **Stor ändring** (ny funktion, ombyggnad av layout): höj huvudversionen
  → v2.0 → **v3.0** → v4.0 …
- **Liten ändring** (justering, fix, mindre tillägg): höj undernumret
  → v2.0 → **v2.1** → v2.2 …

Behåll de gamla filerna i mappen som arkiv – då kan man alltid gå tillbaka.

### Versionshistorik – jourschema
| Version | Ändring | Typ |
|---|---|---|
| v1.0 | Original | – |
| v2.0 | Kalendern i mitten, "Kommande veckor" + "Storhelger" på sidorna | Stor |
| v2.1 | Hela veckor klickbara (klick på veckonummer byter jour för hela veckan) | Liten |
| v3.0 | "Kommande veckor" speglar kalendern (majoritetsfärg), raderna klickbara, scrollbar lista med ~35 veckor (täcker upp till v53). Sidokolumner (Kommande veckor + Storhelger) följer med vid scroll genom kalendern. | Stor |
| v3.1 | Unified header (matchar övriga sidor: centrerad bildlogo, Georgia h1, Städföretags bubble-decor) | Liten |
| v4.0 | Redigeringslås: flytande lås-knapp, allt låst som standard, auto-lås efter 30s inaktivitet (timern förnyas vid varje ändring), manuell låsning | Stor |

### Versionshistorik – Städföretag
| Version | Ändring | Typ |
|---|---|---|
| v5 | Tidigare baseline | – |
| v5.1 | Unified header | Liten |

### Versionshistorik – Nordicta_Protocol
| Version | Ändring | Typ |
|---|---|---|
| v4 | Tidigare baseline | – |
| v4.1 | Unified header (behåller "Nordicta Guest Care"-tag och legend) | Liten |

### Versionshistorik – Inventarielista
| Version | Ändring | Typ |
|---|---|---|
| v1.0 | Original (första byggnad) | – |
| v1.1 | Unified header | Liten |

### Versionshistorik – index (startsidan)
Index versioneras genom arkiverade kopior i roten (`index_v1.0.html`, `index_v1.1.html` etc.).
Live-versionen ligger alltid som `index.html`.

| Version | Ändring | Typ |
|---|---|---|
| v1.0 | Före unified header (gradient bg + logo höger) | – |
| v1.1 | Unified header (samma som alla undersidor); kortlänkar bumpade till v3.1/v5.1/v4.1/v1.1 | Liten |
