# ufca — LaTeX class for academic works at the Federal University of Cariri

Version: 3.0 (2026-11-06)
Author: Vicente Helano <vicente.sobrinho@ufca.edu.br>
License: GNU General Public License, version 3 (see `LICENSE.md`)

## Abstract (English)

The `ufca` class typesets undergraduate final projects, master's dissertations
and doctoral theses of the Universidade Federal do Cariri (UFCA), Brazil,
following the standards of the Brazilian Association of Technical Standards
(ABNT) and the normalisation manual of the UFCA Library. It builds the cover,
title page and approval page from data declared in the preamble; numbers pages
as required by ABNT; formats the table of contents according to NBR 6027:2012;
produces lists of figures, tables, abbreviations and symbols with automatically
measured columns; and handles references through `biblatex` with the `abnt`
style. The documentation is written in Brazilian Portuguese, the language of
its intended users.

## Installation

```
luatex ufca.ins
```

This generates `ufca.cls` and `ufca.ist`. Move both to a directory searched by
TeX, or to the folder of your document. The documentation is rebuilt with

```
pdflatex ufca.dtx
```

LuaTeX is recommended for the `.ins` step because it preserves the accented
characters of the class's fixed strings; `tex` and `pdftex` write them in the
`^^xx` notation, which is equivalent but unreadable.

## Contents

| File | Description |
|---|---|
| `ufca.dtx` | class source and documentation |
| `ufca.ins` | docstrip script |
| `ufca.pdf` | documentation |
| `template/` | ready-to-use document skeleton |
| `LICENSE.md` | GNU GPL version 3 |

## Requirements

LaTeX 2020 or later, `biber`, and the packages `biblatex` (with the `abnt`
style), `tocloft`, `titlesec`, `caption`, `geometry`, `setspace`, `etoolbox`,
`xpatch`, `eqparbox`, `pdfpages`, `ulem` and `newtx`.

---

## Resumo (português)

A classe `ufca` compõe trabalhos de conclusão de curso, dissertações e teses da
Universidade Federal do Cariri segundo as normas da ABNT e o manual de
normalização da Biblioteca da UFCA. O objetivo é que o autor se concentre no
texto: margens, entrelinhas, numeração de páginas, sumário, listas e
referências são tratados pela classe.

A documentação completa da interface — todos os comandos, os parâmetros
ajustáveis e as decisões de conformidade com as normas — está em `ufca.pdf`.

### Para escrever um trabalho

Gere a classe com `luatex ufca.ins`, copie `ufca.cls` e `ufca.ist` para a pasta
`template/` (ou instale-os na sua árvore TeX) e compile:

```
cd template
latexmk -pdf TCC.tex
```

São necessárias duas ou três passadas: várias medidas da classe são tomadas
numa compilação e aplicadas na seguinte, através do arquivo `.aux`. O `latexmk`
cuida disso, inclusive das chamadas ao `biber` e ao `makeindex`.

### Para alterar a classe

Edite `ufca.dtx` — nunca o `ufca.cls` gerado — e regenere com `luatex ufca.ins`.
