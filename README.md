# A Multi-Agent Generative AI System for Scientific Literature Analysis — IEEE Overleaf Package

## Contents
| File | Purpose |
|---|---|
| `main.tex` | Full paper, IEEEtran `conference` mode. Figures are native TikZ/pgfplots — no external images needed. |
| `IEEEtran.cls` | IEEE class v1.8b, bundled so the project compiles anywhere. |
| `references.bib` | Optional BibTeX database (mirrors the inline bibliography). Not used by default. |
| `main.pdf` | Reference build (7 pages, pdfLaTeX, zero errors). |

## Overleaf
1. Overleaf → **New Project → Upload Project** → select this ZIP.
2. Set **Main document** = `main.tex` (Menu → Main document).
3. Compiler: **pdfLaTeX**. Click Recompile. One pass is enough.

## Local
```bash
pdflatex main.tex && pdflatex main.tex
```

## Notes
- References are written as an inline `thebibliography` block so numbering matches
  the source paper exactly, `[1]`–`[17]`. Switching to BibTeX (`\bibliographystyle{IEEEtran}`
  + `\bibliography{references}`) renumbers by first-citation order.
- Fig. 1 (architecture) is TikZ; Fig. 2 (metric bars) is pgfplots. Both are editable
  vector figures — change values in the `\addplot coordinates {...}` lines.
- `\IEEEoverridecommandlockouts` is commented out; uncomment only if you add a
  `\thanks{}` block that trips IEEEtran's command lockouts.
- For the double-blind / anonymous version, replace the `\author{}` block with
  `\author{\IEEEauthorblockN{Anonymous Submission}}`.
