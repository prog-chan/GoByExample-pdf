# Go by Example — The Edited Reference

**Complete and self-contained Go examples.**

This repository contains an **independently edited, offline Go programming reference** based on the open-licensed [Go by Example](https://gobyexample.com/) project created by **Mark McGranaghan**, with contributions from others, **including Eli Bendersky**.. The book is written and maintained as a **LaTeX manuscript** and compiled into a searchable PDF.

## Files

| File | Purpose |
| --- | --- |
| `go_by_example_reference.tex` | **Master manuscript**: typesetting, explanations, examples, outputs, and attribution. |
| `go_by_example_reference.pdf` | Built reference book for reading offline. |
| `README.md` | Build instructions, credits, and license information. |

## Build the PDF

### Requirements

- **XeLaTeX** (included in a TeX Live distribution or another distribution that provides `xelatex`)
- **latexmk** (recommended; resolves the table of contents, page numbers, and references automatically)
- LaTeX packages: `geometry`, `fontspec`, `microtype`, `xcolor`, `hyperref`, `bookmark`, `listings`, `fancyhdr`, `titlesec`, `parskip`, and `needspace`
- Installed fonts: **Liberation Serif**, **Liberation Sans**, and **DejaVu Sans Mono** (these are explicitly named in the manuscript)

On Ubuntu or Debian, a suitable starting point is:

```bash
sudo apt update
sudo apt install \
  texlive-xetex texlive-latex-extra texlive-latex-recommended \
  latexmk fonts-liberation fonts-dejavu-core
```

Other platforms can use a full **TeX Live** or **MacTeX** installation, plus the named fonts. The manuscript currently uses `fontspec`, so compile with **XeLaTeX**, not `pdflatex`.

### Recommended: latexmk

From the directory containing the `.tex` file:

```bash
mkdir -p build
latexmk -xelatex -interaction=nonstopmode -halt-on-error \
  -file-line-error -outdir=build go_by_example_reference_updated.tex
```

The finished file is:

```text
build/go_by_example_reference_updated.pdf
```

`latexmk` runs XeLaTeX again when required to resolve the **contents links, page numbers, and PDF bookmarks**. To clean intermediate files:

```bash
latexmk -c -outdir=build go_by_example_reference_updated.tex
```

### Alternative: XeLaTeX directly

```bash
mkdir -p build
xelatex -interaction=nonstopmode -halt-on-error \
  -output-directory=build go_by_example_reference_updated.tex
xelatex -interaction=nonstopmode -halt-on-error \
  -output-directory=build go_by_example_reference_updated.tex
```

## Original project and attribution

The **original Go by Example project** was created by **Mark McGranaghan**, with contributions from others, **including Eli Bendersky**.

- Project website: <https://gobyexample.com/>
- Original source repository: <https://github.com/mmcgrana/gobyexample>
- Original repository's license statement: <https://github.com/mmcgrana/gobyexample#license>
- Creative Commons Attribution 3.0 Unported (CC BY 3.0): <https://creativecommons.org/licenses/by/3.0/>
- Full CC BY 3.0 legal text: <https://creativecommons.org/licenses/by/3.0/legalcode>

**Copyright notice for the original material:** Copyright Mark McGranaghan, as stated in the original project's README. Other contributors retain any applicable rights in their respective contributions.

**Changes made in this edition:** The source material was **adapted, revised, corrected, reorganized, and typeset** as an offline LaTeX/PDF reference. Explanations, code examples, program output, chapter presentation, and typography have been edited. This is **not** an unmodified copy of the website or a build of the original website's toolchain.

**No endorsement:** This is an independently edited adaptation. Mark McGranaghan, Eli Bendersky, the original project contributors, and the original Go by Example project **have not endorsed or approved this edition**.

## License and redistribution

The original project expressly identifies its work as licensed under **Creative Commons Attribution 3.0 Unported (CC BY 3.0)**. Under that license, you may copy, share, and adapt the licensed material, including for commercial purposes, **provided that you satisfy the license conditions**.

When sharing or adapting material from the original project:

1. **Credit the original creator and contributors** as appropriate, retain the original copyright notice where applicable, and identify the source and the title *Go by Example*.
2. **Link to the original source** and the **CC BY 3.0 license**.
3. **Clearly identify that changes were made**, including changes in this edition and any later modifications you make.
4. **Do not imply sponsorship, affiliation, or endorsement** by the original authors.
5. **Do not impose additional legal or technical restrictions** on others' exercise of the rights granted by CC BY 3.0 in the licensed material.

The CC BY 3.0 grant applies to the **material licensed by the original rightsholder**. It does **not** automatically establish the license status of unrelated third-party content or independent new contributions. Anyone distributing further editions should ensure that they have appropriate rights in all newly added content and should state the license for their own additions explicitly. Nothing in this README revokes or narrows the original project's CC BY 3.0 grant.

The original repository separately credits **Renée French** for the **Go Gopher** artwork, under **CC BY 3.0**. This text-based reference does not depend on reproducing that artwork; **if a future edition includes it**, retain the Renée French credit and the applicable license notice. The artwork license does not imply rights to unrelated logos, trademarks, or third-party assets.

For authoritative license terms, consult the [full CC BY 3.0 legal code](https://creativecommons.org/licenses/by/3.0/legalcode). The [Creative Commons summary](https://creativecommons.org/licenses/by/3.0/) is not a replacement for the legal text. This README provides practical attribution and distribution guidance, not a legal opinion.
