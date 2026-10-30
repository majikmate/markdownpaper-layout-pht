# markdownpaper-layout-pht

The layouts of the Pädagogische Hochschule Tirol (PHT) for
[nimblescape Markdown Paper](https://github.com/nimblescape/markdownpaper-vscode),
the extension of VS Code and the command `markdownpaper` that make the pages and
the PDF of a Markdown document in a layout.

There are two versions of each layout, and two more versions of the thesis,
each in a folder of its own. A document names the folder in the front matter,
for example
`layout: concept-v2`, so a new version never changes the pages of a document
that names an older one.

| Folder | Layout | Version |
| --- | --- | --- |
| [`thesis-v1/`](thesis-v1/) | The thesis (Abschlussarbeit) of the PHT, in German (`de-AT`): each chapter starts on a new page | 1: the look of the skill `markdown-to-paper`, with Liberation Sans for the Word template |
| [`concept-v1/`](concept-v1/) | The concept paper (Konzeptpapier) of the PHT, in German (`de-AT`): the pages of `thesis-v1/`, but a chapter follows the text before it | 1: as `thesis-v1/` |
| [`thesis-v2/`](thesis-v2/) | The thesis of the PHT | 2: the look of the Word template for theses, measured line by line |
| [`concept-v2/`](concept-v2/) | The concept paper of the PHT | 2: the look of the Word template of the concept paper, measured line by line |
| [`thesis-v3/`](thesis-v3/) | The thesis of the PHT | 3: the look of `thesis-v2/` with a closer cover page: the title and the subtitle with a line spacing of 1.1, and half the space between a label and its value |
| [`thesis-v4/`](thesis-v4/) | The thesis of the PHT | 4: the look of `thesis-v2/`, with a cover page whose title and subtitle have a single line spacing, and whose spaces from the logo to the date shrink by the same factor for a long title |

All layouts have a cover page with the logo of the PHT, the type of the
work, the title, the author, the degree and the supervisor; footnotes at the
foot of the page; and the citation style of the PHT. The fields of the front
matter are in German, as in the templates: `title`, `subtitle`, `type`,
`author`, `grad`, `betreuerin`, `matrikelnummer`, `studium`,
`lehrveranstaltung`, `date`, `kapitelumbruch` and `variante`. `layout.json` of
each folder describes them, and the name of the PDF file is
`{{matrikelnummer}}_{{author}}_{{lehrveranstaltung}}_{{type}}`.

All layouts have the two parameters `variante` and `kapitelumbruch`, fields of
`layout.json` with a list of names to choose from. The thesis layouts also
have the parameter `type`:

| Field | Names | What it changes |
| --- | --- | --- |
| `variante` | `vorlage` (default), `klassisch` | `vorlage` is the look of the Word template of the PHT (see the next table). `klassisch` is the look of earlier works made with the skill `markdown-to-paper` of `scalarion/transcribe`: Liberation Serif, with the metrics of Times New Roman, 12 pt with a line spacing of 1.5, margins of 30 mm, 25 mm, 22 mm and 35 mm, and a footer with the author and "Seite N" below a line. |
| `kapitelumbruch` | `ja`, `nein` | `ja`: each chapter (`#`) starts on a new page; `nein`: a chapter follows the text before it, with a space. |
| `type` (only the thesis layouts) | `Seminararbeit`, `Abschlussarbeit`, `Bachelorarbeit` (default), `Masterarbeit` | The type of the work above the title of the cover page and in the name of the PDF file. The names are those of the list of the Word template "Vorlage Abschlussarbeit". |

The look `vorlage` of each layout:

| Layout | Word template | Look |
| --- | --- | --- |
| `thesis-v1/`, `concept-v1/` | "Vorlage Abschlussarbeit", version 4.1 | The look of the skill with the font and the bottom margin of the Word template: Liberation Sans, with the metrics of Arial, 12 pt with a line spacing of 1.5; margins of 30 mm, 25 mm, 25 mm and 35 mm with the footer inside the bottom margin; headings of 16 pt, 14 pt and 12 pt; the footer with the author and "Seite N" below a line; block quotes 0.5 cm indented in 11 pt; the reference list with a hanging indent of 1.25 cm. |
| `thesis-v2/` | "Vorlage Abschlussarbeit" (`Abschlussarbeit_Vorlage.docx`) | Liberation Sans, with the metrics of Arial, 12 pt with a line spacing of 1.5 and 6 pt before and after a paragraph; margins of 30 mm, 25 mm, 25 mm and 35 mm; headings of 16 pt, 14 pt and 12 pt with the indents of the template; a title without a number, such as "Verzeichnisse", in capitals; no footer on the pages before the first chapter, "Seite 1" on the first page of the first chapter, and "Anhang I", "Anhang II", … in the appendix part; captions of 10 pt in dark blue, below a figure and above a table; lists with "•" or "a)". A cover page that a long title or programme would make longer than one page shrinks the large spaces of the template, as a Word user deletes empty lines. |
| `concept-v2/` | "Vorlage für Konzeptpapier – Sekundarpädagogik" (`bac_konzeptpapierBA_SEK_2022.doc`) | The cover page with two tables; Carlito, with the metrics of Calibri, 11 pt with a line spacing of 1.15 and 10 pt after a paragraph; margins of 29 mm, 20 mm, 27.5 mm and 25 mm; numbered headings of 14 pt; "Seite N von M" at the bottom right. |
| `thesis-v3/` | as `thesis-v2/` | The look of `thesis-v2/`, with two changes on the cover page, where the PHT overrules the template: the title and the subtitle have a line spacing of 1.1 instead of 1.5, and the space between "Verfasser:in" and the name and between "angestrebter akademischer Grad" and the degree is half of the space of the template (the labels have a single line spacing, and the name and the degree 6 pt instead of 12 pt above them). |
| `thesis-v4/` | as `thesis-v2/` | The look of `thesis-v2/`, with these changes on the cover page: the title and the subtitle have a single line spacing instead of 1.5, the line below the title lies in the middle between the title and the subtitle, and the date stays where it is on a cover with one line for each text: when the title, the subtitle or a value has more lines, all spaces from the bottom of the logo to the date, also the spaces above and below the type of the work, shrink by the same factor, but the rows of the table stay at least as far apart as the lines of a long value. The sizes of the fonts and the other line spacings do not change. The logo is the word mark of the PHT in the red of the PHT (RGB 238/17/23). |

The thesis and the concept paper of a version also differ in three defaults:
the type of the work (`Bachelorarbeit` or `Konzeptpapier`), `kapitelumbruch`
(`ja` or `nein`), and the heading of the reference list: the concept paper
also finds the heading "Erste Auswahl an (Grundlagen-)Literatur und Quellen"
of the concept template of the PHT. Version 2 of the thesis also numbers the
reference list and the lists of figures, tables and listings as chapters, and
leaves the chapters before the first chapter out of the table of contents, as
the Word template does. Each folder holds its own copies of the files, because
the paths of a layout stay inside its folder.

### How close the pages of version 2 are to Word

The look `vorlage` of version 2 was measured line by line against PDFs of the templates.
The browser puts each line on a whole pixel (0.26 mm), so a line can be up to
0.13 mm away from its place in Word.

- `concept-v2/`: against a PDF that Word made from a concept paper in the
  template, 176 of 207 lines of text have the same words, and all of them are
  at most 0.2 mm away from their place in Word. Each page has the same lines.
  The other lines break at another place, mostly because Word hyphenates some
  words at another syllable or breaks an address at another character.
- `thesis-v2/`: no PDF of Word was at hand, so the pages were measured against
  the PDF that LibreOffice 24.2 makes from the template. The lines with the
  same words are at most 0.16 mm away from their place in LibreOffice, also
  the cover page, the headings, the figures and their captions, the footers
  and the footnotes. Some lines break at another place, where LibreOffice,
  unlike Word, shrinks the spaces of a line by more than a fifth, or keeps a
  word whole because of the hyphenation zone of the template, which Word does
  not apply (the PDF of the concept paper shows this). A Word PDF of the
  thesis template would allow a check against Word itself.
- `thesis-v3/` and `thesis-v4/`: the pages after the cover page are the pages of `thesis-v2/`. The cover page
  of `thesis-v4/` with one line for each text is the cover page of `thesis-v2/` with the title and the subtitle at a
  single line spacing.
- A Markdown table has no widths of its columns, so the browser gives each
  column its width, and the columns of a table can differ from Word.

A document names its layout in the front matter, for example
`layout: concept-v2`. Today Markdown Paper reads a layout only from the folder
`layouts/` of the repository of the document, so a document uses a copy of the
layout folder there, for example `layouts/concept-v2/`. Loading a layout directly
from this repository is planned; until the first release this repository has
no release tag, so a document will name a branch or a commit.

The GitHub topic `nimblescape-markdownpaper-layout` marks this repository as a
repository of layouts for Markdown Paper; the page
<https://github.com/topics/nimblescape-markdownpaper-layout> lists all public
ones.

## The empty paper document and its preview

Each layout folder holds its empty paper document, `document.md`, and the PDF
of it, `document.pdf`, which shows the pages of the layout with example texts
before a person chooses it (the fields `document` and `preview` of
`layout.json`). `markdownpaper create` and the command "New Project" of VS
Code copy the empty paper document into `paper/paper.md` of a new project,
with the files that it links to.

| Layout | `document.md` |
| --- | --- |
| `thesis-v1/` to `thesis-v4/` | The front matter with the texts of the cover page of the Word template ("Titel eintragen", "Matrikelnummer eintragen", …); the "Eidesstattliche Erklärung", the "Abstract" and the "Vorwort" with the texts of the template; then eight chapters that explain in German how to work with the document in VS Code with nimblescape Markdown Paper and nimblescape Markdown Notes: the folders of a project, the cover page, text, headings, footnotes, the Markdown of the styles of the template, figures, tables, code, sources and citations, AI tools and agents, notes, the pages, the PDF, and the texts of the template on gender-fair language and accessibility; then the lists, the list of abbreviations and the appendix of the template. The figure is `images/projekt-ordner.svg`, the listing shows `code/mittelwert.py`, and the example citation is the source `hattie2007`, whose metadata `markdownpaper source` took from doi.org. |
| `concept-v1/`, `concept-v2/` | The front matter with the texts of the cover page of the concept template ("Geben Sie hier Ihren Vor- und Familiennamen ein!", …); the five chapters of the template with its hints, each followed by a short explanation of how to write it, with a table and the same example citation. |

`npx -y @nimblescape/markdownpaper preview <folder> --write` formats the
empty paper document of a folder and writes its `document.pdf` again; run it
after a change of the layout or of the document.

## Sources

The layouts were made on 2026-10-30 from these files of the PHT. The page
"Bachelorarbeit" of the PHT, <https://ph-tirol.ac.at/bachelorarbeit/>
(accessed on 2026-10-30), links them under these addresses. The look of the
pages was ported from the skill `markdown-to-paper` of the repository
`scalarion/transcribe`, which was made from version 4.1 of the Word template
for theses (`Abschlussarbeit_Vorlage_V4_1.docx`).

| File | Download | Accessed | Used for |
| --- | --- | --- | --- |
| "Vorlage Abschlussarbeit", the Word template for theses | <https://cms.ph-tirol.ac.at/documents/Abschlussarbeit_Vorlage.docx> | 2026-10-30 | the look `vorlage` of `thesis-v2/`, `thesis-v3/` and `thesis-v4/`; in `document.md` of all thesis layouts the texts of the cover page, of the "Eidesstattliche Erklärung", the "Abstract" and the "Vorwort", the styles of table 1, the texts on AI tools with table 2, on gender-fair language and on accessibility, and the texts of the lists, of the list of abbreviations and of the appendix |
| "Corporate Design" of the PHT, the page with the logos and the colors | <https://ph-tirol.ac.at/corporate-design-pht/> | 2026-10-30 | the red of the PHT, RGB 238/17/23 (`#EE1117`, HKS 13), as in the logo of the web site |
| "Wortmarke" of the PHT (`PHT_wortmarke.zip`), from the page "Corporate Design" | <https://cms.ph-tirol.ac.at/documents/PHT_wortmarke.zip> | 2026-10-30 | `images/pht-logo.png` of `thesis-v4/`, made from `PHT_wortmarke_rgb.pdf` |
| "Zitationsrichtlinien für Abschlussarbeiten" (Zitation nach APA 7), version 2.0 | <https://cms.ph-tirol.ac.at/documents/APA7-V2_0.pdf> | 2026-10-30 | `pht-apa7.csl` |
| "Vorlage für Konzeptpapier – Sekundarpädagogik", the Word template of the concept paper | <https://cms.ph-tirol.ac.at/documents/bac_konzeptpapierBA_SEK_2022.doc> | 2026-10-30 | the look `vorlage` of `concept-v2/`; in `document.md` of `concept-v1/` and `concept-v2/` the texts of the cover page, the chapter headings and the hints below them; the heading of their reference list |
| "Vorlage für Konzeptpapier – Primarpädagogik" | <https://cms.ph-tirol.ac.at/documents/konzeptpapierBA.PRIMAR.doc> | 2026-10-30 | not used: a concept paper of the primary level starts from this template instead |

The Word template for theses at the address above has the same text,
margins and styles as version 4.1, which the skill was made from (checked on
2026-10-30). The look `vorlage` follows the Word templates; the look
`klassisch` keeps the font and the bottom margin of the skill.

## The citation style of the PHT

[`thesis-v2/pht-apa7.csl`](thesis-v2/pht-apa7.csl) (and its copy in each other folder) is the citation style of the
guide of the PHT, "Zitationsrichtlinien für Abschlussarbeiten an der PHT,
Zitation nach APA 7", version 2.0, in the Citation Style Language (CSL). The
field `"citationStyle": "pht-apa7.csl"` of `layout.json` names it, and Markdown
Paper applies it with citeproc-js to the citations and the reference list.

The file is a changed copy of `apa.csl`, "APA Style 7th edition", of the CSL
styles (<https://github.com/citation-style-language/styles>, updated
2026-02-07), by Brenton M. Wiernik and Andrew Dunning with Jay Pfaffman, under
the Creative Commons Attribution-ShareAlike 3.0 License. The changes for the
PHT:

- the German terms of the guide: `o. D.` for a source without a year,
  `S. 51 – 70` with an en dash between no-break spaces, `Abgerufen am … von …`;
- the short labels of all places in a source: `S.`, `Kap.`, `Abschn.`, `Abs.`,
  `Abb.`, `Tab.`, `H.`, `Fn.`, `T.`, `Anh.`;
- the day before the month: `(2018, 1. Oktober)`;
- the day of the access whenever the metadata of a source has one.

The names of the months come from the CSL locale `de-AT` of Markdown Paper, so
January is `Jänner`.

## License

The content of this repository is licensed under the
[Creative Commons Attribution-ShareAlike 4.0 International License](LICENSE)
(CC BY-SA 4.0); the changed copy of `apa.csl` too, as the share-alike rule of
CC BY-SA 3.0 allows. Fonts and logos with licenses of their own keep them and
are listed here when a layout holds them:

- `fonts/LiberationSans-*.ttf` and `fonts/LiberationSerif-*.ttf` in each
  layout: Liberation Sans and Liberation Serif 2.1.5, copyright (c) 2010 Google
  Corporation and (c) 2012 Red Hat, Inc., under the SIL Open Font License 1.1,
  see `fonts/LICENSE-Liberation.txt`. They have the metrics of Arial, the font
  of the PHT template, and of Times New Roman.
- `fonts/Carlito-*.ttf` in `concept-v2/`: Carlito 1.104, copyright (c) 2010-2013
  by tyPoland Łukasz Dziedzic, under the SIL Open Font License 1.1, see
  `fonts/LICENSE-Carlito.txt`. It has the metrics of Calibri, the font that
  Word shows for the concept template.
- `images/pht-logo.png` in each layout: the logo of the Pädagogische
  Hochschule Tirol. It is not under CC BY-SA 4.0; the PHT holds its rights.
  It is here only for the cover pages of works at the PHT. In `thesis-v4/` it
  is the word mark of the page "Corporate Design" in the red of the PHT; the
  other layouts have the logo of the Word template, whose red is darker.
