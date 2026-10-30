# Jujuy: law history in git

The law of the Province of Jujuy (Provincia de Jujuy, Argentina) as a git history: one file per article, one commit per norm on the day it took effect. `git log` lists the changes to an article; checking out a date gives the text the record holds for that day.

It follows the shared design of [lexifina/global-law](https://github.com/lexifina/global-law), which places it at `ar-y/`. Argentina's national law is in [lexifina/argentina-law](https://github.com/lexifina/argentina-law).

The text is in Spanish, exactly as the source prints it.

## What this repository holds

1 norm so far: the constitution first, then the codes, then laws, newest first, added in parts. 1 of them are shown as enacted; the rest are their current consolidated text only (see Dates).

| Folder | Norm | History |
| --- | --- | --- |
| `constitucion/` | Constitución de la Provincia de Jujuy | as enacted, in force 21 June 2023 |

## Source

Legislatura de la Provincia de Jujuy (www.legislaturajujuy.gov.ar), <https://www.legislaturajujuy.gov.ar/>. The constitution: the Legislatura's PDF of the Constitución de la Provincia de Jujuy sanctioned on 20 June 2023 and published in Boletín Oficial Nº 68 of 21 June 2023.

## Dates

- Each commit is dated at **noon, America/Argentina/Jujuy, on the day the norm took effect**: the day its own vigencia clause names, or otherwise the ninth day after its publication in the Boletín Oficial de la Provincia de Jujuy (Código Civil y Comercial de la Nación, arts. 5 and 6).
- The constitution of 2023 is shown as enacted, dated 21 June 2023, the day of its publication, from which its cláusula transitoria primera puts it in force. It has not been amended since.
- Versions that take effect after the retrieval day are on the `futuro` branch, never merged into `main`.

## Files

`<norm>/art-005.md` is Artículo 5, `art-005-bis.md` Artículo 5 bis; `encabezado.md` holds the number, the enacting formula and anything printed before Artículo 1. Section headings, signatures and the source's amendment notes stay in the file of the article they follow. One paragraph per line.

## How it is checked

- Every version of every norm is read back from git on the day it took effect and on the day before (`tools/check_repo.py`); both must match `corpus.json`.
- The letters and digits of every version equal those of the source document it was read from (read again with an independent HTML reader), so no word is lost or added.
- Health checks: no merge commits, commit dates never go backwards, nothing dated in the future, and every commit's trailers parse.

## Limits

This is not an official publication. The binding text is the one published in the Boletín Oficial de la Provincia de Jujuy. Only the norms listed above are included, and most show only their current text.
