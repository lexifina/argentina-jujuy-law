# How this repository was made (Jujuy)

This file is written by the build on 2026-10-30, the day the source data was retrieved.

## Sources

| Source | Address | Retrieved | Licence |
| --- | --- | --- | --- |
| Legislatura de la Provincia de Jujuy (www.legislaturajujuy.gov.ar) | <https://www.legislaturajujuy.gov.ar/> | 2026-10-30 | Official legal texts of the province, published by its government for public consultation. Argentina's copyright law (Ley 11.723) has no express exclusion for them; laws are public acts of government, binding on everyone once officially published (Código Civil y Comercial, art. 5). The source states no restriction on reuse. Reproduced with attribution, following the official text. |

Every word of law in this repository comes from these sources. Lexifina reads them and records each act's dated versions, and the laws that made each change, in one corpus file. This repository is built from that file.

## What is in it

| Act | Title | Versions | Span |
| --- | --- | ---: | --- |
| `constitucion` | Constitución de la Provincia de Jujuy | 1 | 2023-06-21 to 2023-06-21 |

The build made 1 commits:

| Commits | Kind |
| ---: | --- |
| 1 | first version of an act |
| 0 | one law on its in-force day |
| 0 | changes no amendment note explains, credited to the publisher |

Other counts:
- 0 commits on the branch `futuro`: laws not yet in force on 2026-10-30.
- 0 commits dated 1 January 1970: in force before 1970, with the real day in their `In-force` trailer.
- 1 laws in the record.
- 2 tags.

## Dates

Each commit is dated at noon (America/Argentina/Jujuy) on the day the change took effect. The other dates, enacted and published, are trailers.

When a law gives no date of its own, the default rule applies: Código Civil y Comercial de la Nación, art. 5: "Las leyes rigen después del octavo día de su publicación oficial, o desde el día que ellas determinen", counted under art. 6 (the day of publication is excluded), so a law without its own vigencia clause is in force from the ninth day after its publication in the provincial Boletín Oficial (before 1 August 2015, Código Civil art. 2 as replaced by Ley 16.504, to the same effect). A law's own vigencia clause overrides the rule. https://servicios.infoleg.gob.ar/infolegInternet/anexos/235000-239999/235975/texact.htm

## How the history is built

`tools/build.py` turns the corpus into this history in one pass: one commit per law, on the day it took effect. The same corpus always gives the same commit hashes. `tools/check_repo.py` reads every version back from git and compares it with the corpus. `tools/on.py` shows the law as it stood on any date. The corpus format is described in `tools/SCHEMA.md`.

- Corpus: sha256 `cd4f60f620827fec10ff7fbbf26a8b57b148c90efc411a6ae8c9ace5704c2538` (254992 bytes).
- Builder blob hashes (`git hash-object`): `build.py` `35388bee5aa05369f7da68f5a8fa015ea8d442b8`, `check.py` `5d719354ea4c62d240c93d2cae446307d81d9e81`, `on.py` `aff48cf1b68d50c7ba8f399ca32261871c301824`.
- Python 3.14.4; git version 2.53.0.

## Checks

1 versions of 1 acts read back from git on the day each took effect and on the day before: 0 mismatches. Trailers: 0 commits whose trailers git cannot parse. Health: 0 merge commits on main, 0 commit dates that go backwards, 0 commits dated after the build.

No second build of this corpus has been compared yet.

## Decisions made by hand

- Constitution: the Legislatura's PDF of the Constitución de la Provincia de Jujuy (sanctioned 20 June 2023; published in Boletín Oficial Nº 68 of 21 June 2023; cláusula transitoria primera: "Esta Constitución entrará en vigencia a partir del día de su publicación"), shown as enacted, dated 21 June 2023. The constitution of 1986 it replaced is not shown.
- Laws are not built yet.
- Units: the heading (encabezado: everything before Artículo 1, the preamble included) and one file per article, holding the article and everything printed after it up to the next article (section headings, the transitional clauses after the last article, signatures, page numbers). Nothing is dropped. One paragraph per line, spacing normalised.

## What AI did and did not do

The scripts that read the sources and build this repository were written by Claude Code running Claude Opus 5.5 (`claude-opus-5-5`) under Lexifina's direction.

No model wrote, translated or corrected legal text. No model runs at build time. Every word of law in this repository comes from the official sources above.

The commit messages are written by `build.py` from the source data.

Model use at data-build time:
- A model (Claude) wrote the fetch and parse code and chose which norms to include; it wrote no law text. Every word of law comes from the provincial source's own texts.
