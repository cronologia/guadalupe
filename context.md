# context.md — cronologia/guadalupe

Read with `AGENTS.md` and the `sourcing-rules` skill before changing anything.

## What this repo is

A chronology of **Our Lady of Guadalupe**: the setting in New Spain before 1531,
the apparitions reported at Tepeyac in December 1531, the documents that carry
the account, the dispute over whether any of it is historical, the Church's
judgments from 1754 to 2002, the successive shrines at Tepeyac, and what has
been *reported* there since — down to the pilgrimage counts of 2025.

It differs from a devotional timeline and from a debunking timeline in the same
way: **the disagreement is the object of the record.** Neither the supernatural
claim nor its negation is asserted anywhere in the dataset or the site copy. The
chronology holds, side by side and dated:

- **the documentary record** — the *Nican Mopohua* printed in Luis Laso de la
  Vega's *Huei tlamahuiçoltica* (1649) and attributed, traditionally and
  disputedly, to Antonio Valeriano; Miguel Sánchez's *Imagen de la Virgen María*
  (1648), the earliest known printed account, 117 years after the reported
  events; the *Informaciones Jurídicas de 1666*; the Codex Escalada, surfaced
  1995, whose authenticity is itself contested;
- **the silence problem** — no contemporary 1531 document; nothing about Juan
  Diego or the apparitions in Zumárraga's surviving papers; and the earliest
  substantial documentation of the cult, the 1556 Bustamante sermon and
  Montúfar's *Información*, mentions neither the visionary nor the visions;
- **the Church's rulings, with their documents** — Benedict XIV's patronage and
  feast (1754), the canonical coronation (1895), the beatification (1990),
  *Ecclesia in America* (1999), the canonization (2002), and the decree of
  20 December 2001 on a miracle attributed to Bl. Juan Diego's intercession;
- **the setting, as context and never as corroboration** — the fall of
  Tenochtitlan (1521), the landing of the first twelve Franciscans (1524) and
  Zumárraga's arrival as bishop-elect (1528). These entries say what New Spain
  looked like in the decade the account describes. Each of them says, in its own
  text, that it is not evidence for or against the apparition account. Nothing
  in this half may be written so that it reads as support for either side;
- **the afterlife** — the shrines (1622, 1709, 1976), the patronage sworn by
  Mexico City in 1737 and accepted across New Spain in 1746, Guadalupe as an
  insurgent and national emblem (1810, 1914), the 1921 bombing, and the
  pilgrimage counts as published by the bodies that count.

Every contested characterisation is attributed to a named person or body.
Skeptical side: Stafford Poole (1930–2020), Edmundo O'Gorman, Guillermo
Schulenburg, Rafael Tena, Mario Méndez Acosta. Pro-historicity side: the cause's
historical commission — Fidel González Fernández (president), Eduardo Chávez
Sánchez (postulator), José Luis Guerrero Rosado (vice-postulator) — Xavier
Escalada, Charles E. Dibble, the Congregation for the Causes of Saints,
*L'Osservatore Romano*. Two of the loudest skeptics are a Catholic priest and a
basilica abbot: this is an intra-Church dispute, and the dataset shows it as one.

## How reported miracles are handled (core#71)

**A miracle is a claim, not an event.** Only two things attached to one are
datable, and only these are in `events[]`:

1. **The account** — that a cure or wonder was *reported*, by whom, and when the
   report is first attested. The event is the reporting. `title` names the
   reporter, never the beneficiary: "Bernal Díaz del Castillo reports miracles
   at the Tepeaquilla chapel", never "N was cured".
2. **The recognition act** — a dated Church judgment with a document. Here there
   is exactly one: the Holy See bulletin of 20 December 2001 promulgating a
   decree on a miracle attributed to Bl. Juan Diego's intercession. It judges an
   intercession inside a canonization cause; it is not a ruling on 1531.

Consequences that hold and must keep holding:

- No cure is recorded as having happened, anywhere in the dataset.
- A claimed cure with neither a named reporter nor a Church act is **left out**.
  The devotional literature carries many; none of them is here.
- Aggregate claims are attributed to whoever counts. The 2025 pilgrimage figure
  is the Mexico City government's `Operativo Basílica` estimate; the annual
  30-million figure is the city tourism office's; the dataset says so and does
  not reconcile them, because their counters do not.
- Claims about the image itself — preservation, pigments, the eye reflections —
  are attributed to the researchers who made them and dated to when they made
  them (Callahan 1981, Aste Tönsmann from 1979). The 1921 bombing is recorded
  as an event; the intactness of the image afterwards is recorded as a *report*.
- **Cures get no approval-ladder rungs.** The ladder judges the apparitions.
  The 2001 decree did not change it and must not.

## Current state (2026-08-05)

Second wave: the chronology widened before and after the apparitions (core#71).

- `data/chronology.json` — 30 events (1521–2025), 6 facts, 12 figures,
  2 organizations, 6 disambiguation entries, 34 references.
- `data/i18n/es.json`, `data/i18n/pt.json` — 186/186 translatable strings each,
  hand-authored by an LLM, `humanReviewed: false`. No native speaker has read
  them yet.
- `docs/` — built for `en`, `es`, `pt`.
- No `meta.threads` taxonomy yet (see below), no `data/archives.json` yet, no
  `data/places.json` yet.

Eight events carry `dateVerified: false` and render with a `?` flag:

| date | why it is flagged |
|---|---|
| 1528-12 | the Franciscan encyclopedia gives "fines de 1528"; other accounts give 6 December, with no document cited |
| 1531-12-09 | Julian date internal to a narrative first printed 1648–49; no contemporary source attests it |
| 1531-12-12 | same; 12 December is documented only as the feast fixed in 1754 |
| 1548-05-30 | day given by Britannica; no contemporary record of Juan Diego's death exists, and the only document claimed to record it (Codex Escalada) is disputed |
| 1568 | the conventional year for Bernal Díaz's completed manuscript; the text was first printed in 1632 and the interval is not documented here |
| 1754-05-25 | year verified; the day usually given for the bull *Non est equidem* not checked against the bull's text |
| 1939 | Poole's dating of the start of the beatification process, not checked against the cause's own documents |
| 1995 | the parchment's surfacing date — its provenance is part of the dispute |

Three further events are dated to the year or carry a `dateNote` recording a
disagreement rather than resolving it: 1737-04-27 (Rodríguez Navarijo's diary
against accounts giving 24 April), 1709-05-01 (dedication 27 April vs. transfer
1 May) and 1810 (the year is verified; the Atotonilco standard tradition of
16 September is not documented by any source consulted and is not recorded).

## Open questions

1. **Two tertiary sources are load-bearing.** `wikipedia-schulenburg` carries the
   1996 *Ixtus* interview and the resignation; `wikipedia-codex-escalada` carries
   the expert opinions on both sides of the codex. The primary press (New York
   Times, 8 September 1996; *La Jornada*, 22 January 2002) and the *Ixtus* issue
   itself were not reachable from the bootstrap session. Replacing these is the
   highest-value next research task. The *El Universal* piece of 22 January 2002
   (`eluniversal-2002`) was reachable and now carries part of that weight.
2. **`Non est equidem` (1754) has not been read.** The 25 May date and the exact
   content of the papal act need the bull's text or a critical edition.
3. **The 1556 *Información* has not been read in the original.** O'Gorman's
   reconstruction is cited; the transcribed testimony would be better.
4. **The pro-historicity case is thinner than the skeptical case in this
   dataset** — a real asymmetry to fix, not a verdict. `El encuentro de la Virgen
   de Guadalupe y Juan Diego` (Porrúa, 1999) is cited through press coverage
   rather than read; the Scripta Theologica review at `dadun.unav.edu` returned
   403 to this session's egress (browser UA did not help — see the `net-access`
   ladder). Chávez Sánchez's own publications are not yet in `references[]`.
5. **The *Tonantzin* question is deliberately absent from the chronology.** The
   claim that the Guadalupe cult continued or displaced a pre-conquest cult at
   Tepeyac (Sahagún) is itself contested, and no event records it yet. It is
   listed in `KEYWORDS.md` as a search term. Omission editorialises: this note is
   the record that it was left out on purpose, pending sources good enough to
   attribute both readings.
6. **No thread taxonomy (`meta.threads`) has been declared.** For this subject
   the obvious lanes — "the documentary record", "the Church's judgments", "the
   historicity dispute" — are tempting and dangerous: they would imply a parity
   between the sides that the sources may not support (`sourcing-rules`, "beware
   false symmetry"). Declaring them is an editorial decision for a ticket of its
   own, with the omissions written down.
7. **Calendar.** The 1531 dates are Julian and are given as the tradition
   reports them. If a source is ever found that states a calendar explicitly,
   the disambiguation entry should cite it.
8. **The i18n dictionaries need a native reader.** The Spanish is written to read
   as Mexican-inflected Spanish; nothing in it has been reviewed by a human.
9. **Things deliberately left out of the miracle half.** Written down because
   omission editorialises. The 1936 claim attributed to the chemist Richard Kuhn
   that the tilma's pigments are of no known origin is repeated everywhere and
   rests on no locatable publication or archival record — there is no source that
   says who reported it and when, so it is not in the dataset. The *Nican
   Motecpana*'s fourteen individual miracle accounts of 1649 are named in
   `facts[]` and in the disambiguation but are not broken out as fourteen events:
   they would need the Sousa/Poole/Lockhart critical edition, which was not
   reachable, and fourteen thin rows would drown the sourced ones. The healing
   behind the 2001 decree (Juan José Barragán Silva, 1990) is described only in
   press and devotional accounts; the event records the *decree*, names the press
   attribution as such, and asserts no cure.
10. **`memoricamexico.gob.mx` returned 403** to this session, so the official
   Mexican archive page on the insurgent Guadalupan standard could not be used;
   the INEHRM PDF on Hidalgo's route is image-only and not text-extractable. The
   1810 event therefore rests on Britannica and stops at the year. Both are worth
   another attempt via the `net-access` ladder.

## Conventions specific to this repo

- Never write "the Virgin appeared" in the site's voice. Write "the narrative
  reports", "according to the *Nican Mopohua*", "the tradition places".
- Never write that Juan Diego did not exist, or that the image was painted, in
  the site's voice either. Bustamante *reportedly said* the image was painted by
  an Indian; Poole *argues* the codex is a forgery.
- Church rulings are recorded with their document and date. A canonization is a
  judgment about a cult and a cause, not a historical-critical verdict — the
  disambiguation section says so explicitly.
- Nahuatl and Spanish proper nouns and work titles are never translated, in any
  locale.
