# Nordicta Internal Website — struktur & versionering

## Mappstruktur

```
Nordicta Internal Website/
├── index.html                  ← startsidan (ligger kvar i roten, navet)
├── README_struktur.md          ← den här filen
│
├── jourschema/
│   ├── jourschema_v1.0.html    ← original (innan ombyggnad)
│   ├── jourschema_v2.0.html    ← 3-kolumnslayout (stor ändring)
│   ├── jourschema_v2.1.html    ← + klickbara veckor i kalendern (liten ändring)
│   └── jourschema_v3.0.html    ← Kommande veckor: majoritet/klick/scroll + sticky sidokolumner (stor ändring)  ← AKTUELL
│
├── Städföretag/
│   └── Städföretag_v5.html
│
├── Nordicta_Protocol/
│   └── Nordicta_Protocol_i_web_form_v4.html
│
└── Inventarielista/
    └── inventarie_v1.0.html
```

Varje sida har fått en egen mapp. **index.html ligger kvar i roten** eftersom
det är startsidan – då fungerar den som nav och länkarna blir enklast. (Lägg den
inte i en undermapp; då slutar den fungera som naturlig ingång.)

## Hur länkarna fungerar nu

- Startsidans kort pekar in i undermapparna, t.ex.
  `jourschema/jourschema_v3.0.html`.
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

De andra sidorna behåller sin befintliga numrering (Städföretag v5, Protokoll v4, Inventarielista v1.0).
Nästa ändring på dem följer samma system (t.ex. v5 → v5.1 vid liten ändring).
