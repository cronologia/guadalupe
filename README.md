# cronologia/guadalupe

An open, source-referenced **chronology of Our Lady of Guadalupe** — the
apparitions reported at Tepeyac in December 1531, the documentary record that
carries them, the scholarly dispute over their historicity, and the judgments
the Catholic Church has made (1531–2002).

Part of the [Cronologia](https://github.com/cronologia) project family: a single
JSON file is the source of truth, and a zero-dependency Node script compiles it
into a static site in three languages.

## What this project does and does not say

This repository documents a **religious claim and its reception**, so its
posture is deliberate and narrow:

- The apparitions are recorded as **reported events**. The dataset says who
  reported what and when, and it says what the Church ruled and when, citing the
  ruling document. **It never asserts the supernatural claim as fact — and never
  asserts its falsity either.**
- The **historicity dispute is carried as a recorded disagreement, not a
  resolved one.** The documentary record (the *Nican Mopohua* in the 1649 *Huei
  tlamahuiçoltica*, Miguel Sánchez's 1648 *Imagen de la Virgen María*, the
  *Informaciones Jurídicas de 1666*, the disputed Codex Escalada) sits in the
  same chronology as the silence problem (nothing about Juan Diego or the
  apparitions in Zumárraga's surviving papers; the 1556 Bustamante sermon and
  Montúfar's inquiry, which mention neither). Named scholars appear on **both**
  sides, each attributed: Stafford Poole, Edmundo O'Gorman and Guillermo
  Schulenburg against historicity; the cause's historical commission — Fidel
  González Fernández, Eduardo Chávez Sánchez, José Luis Guerrero Rosado — and
  *L'Osservatore Romano* for it. The site's own voice takes neither side.
- **The 1531 dates are Julian** (the Gregorian reform came in 1582), and they are
  internal to a narrative first printed in 1648–1649. They are therefore flagged
  as not verified against a primary source, and the calendar question is stated
  rather than silently converted.
- Sources span the spectrum by design: Holy See documents, a secular-humanist
  magazine, peer-reviewed history, Catholic university apologetics, and general
  reference works — each characterised in its `publisherNote`.

See `context.md` for the current state and the open questions, and
`KEYWORDS.md` before running any search over a corpus.

## Layout

```
data/chronology.json     source of truth (hand-edited, English)
data/i18n/{es,pt}.json   exact-key translation dictionaries (committed)
build.js                 compiler: data -> docs/{en,es,pt}/
scripts/validate-data.js schema + cross-reference check
test/                    node:test suites, including per-locale completeness
docs/                    compiled output, served by GitHub Pages (committed)
AGENTS.md                operating guide for agents and humans
```

## Working on it

Every data change runs the same loop, and the regenerated `docs/` is committed
in the **same** change (never hand-edit generated files):

```sh
node scripts/validate-data.js
node build.js
node --test
```

The shared method lives in `cronologia/core` — read the `sourcing-rules` skill
before editing any data file.

## Languages

English is authoritative. Spanish and Portuguese are compiled from the committed
dictionaries in `data/i18n/`; the localized pages carry a visible notice that
they are translations of the English page. Spanish, Nahuatl and Latin proper
nouns and work titles (Tepeyac, Cuauhtlatoatzin, *Nican Mopohua*, *Huei
tlamahuiçoltica*) are left as they are in every locale.

## Licence and corrections

Open data. Corrections against primary sources are welcome via pull request or
issue — especially anything that can replace a tertiary source (currently two
Wikipedia entries) with the primary press or archival record.
