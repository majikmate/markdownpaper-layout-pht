# markdownpaper-layout-pht

The layouts of the Pädagogische Hochschule Tirol (PHT) for
[nimblescape Markdown Paper](https://github.com/nimblescape/markdownpaper-vscode),
the extension of VS Code and the command `markdownpaper` that make the pages and
the PDF of a Markdown document in a layout.

There is one layout for each kind of work, each in a folder of its own. A
document names the folder in the front matter, for example `layout: thesis`.

| Folder | Layout |
| --- | --- |
| [`thesis/`](thesis/) | The thesis (Abschlussarbeit) of the PHT, in German (`de-AT`): each chapter starts on a new page. |
| [`concept/`](concept/) | The concept paper (Konzeptpapier) of the PHT, in German (`de-AT`): a chapter follows the text before it. |

Both layouts have a cover page with the logo of the PHT, the type of the
work, the title, the author, the degree and the supervisor; footnotes at the
foot of the page; and the citation style of the PHT. The fields of the front
matter are in German, as in the templates: `title`, `subtitle`, `type`,
`author`, `grad`, `betreuerin`, `matrikelnummer`, `studium`,
`lehrveranstaltung`, `date`, `kapitelumbruch` and `variante`. `layout.json` of
each folder describes them, and the name of the PDF file is
`{{matrikelnummer}}_{{author}}_{{lehrveranstaltung}}_{{type}}`.

Both layouts have the two parameters `variante` and `kapitelumbruch`, fields of
`layout.json` with a list of names to choose from. The thesis layout also has
the parameter `type`:

| Field | Names | What it changes |
| --- | --- | --- |
| `variante` | `vorlage` (default), `klassisch` | `vorlage` is the look of the Word template of the PHT (see the next table). `klassisch` is the look of earlier works made with the skill `markdown-to-paper` of `scalarion/transcribe`: Liberation Serif, with the metrics of Times New Roman, 12 pt with a line spacing of 1.5, margins of 30 mm, 25 mm, 22 mm and 35 mm, and a footer with the author and "Seite N" below a line. |
| `kapitelumbruch` | `ja`, `nein` | `ja`: each chapter (`#`) starts on a new page; `nein`: a chapter follows the text before it, with a space. |
| `type` (only the thesis layout) | `Seminararbeit`, `Abschlussarbeit`, `Bachelorarbeit` (default), `Masterarbeit` | The type of the work above the title of the cover page and in the name of the PDF file. The names are those of the list of the Word template "Vorlage Abschlussarbeit". |

The look `vorlage` of each layout:

| Layout | Word template | Look |
| --- | --- | --- |
| `thesis/` | "Vorlage Abschlussarbeit" (`Abschlussarbeit_Vorlage.docx`) | Liberation Sans, with the metrics of Arial, 12 pt with a line spacing of 1.5 and 6 pt before and after a paragraph; margins of 30 mm, 25 mm, 25 mm and 35 mm; headings of 16 pt, 14 pt and 12 pt with the indents of the template; a title without a number, such as "Verzeichnisse", in capitals; no footer on the pages before the first chapter, "Seite 1" on the first page of the first chapter, and "Anhang I", "Anhang II", … in the appendix part; captions of 10 pt in dark blue, above a figure, a table and a listing, as in APA 7 (the template has the caption of a figure below it); lists with "•" or "a)". The cover page has the logo of the PHT (the word mark in the red of the PHT, RGB 238/17/23), and the title and the subtitle have a single line spacing with the line below the title in the middle between them. The date stays where it is on a cover with one line for each text: when the title, the subtitle or a value has more lines, all spaces from the bottom of the logo to the date shrink by the same factor, but the rows of the table stay at least as far apart as the lines of a long value. |
| `concept/` | "Vorlage für Konzeptpapier – Sekundarpädagogik" (`bac_konzeptpapierBA_SEK_2022.doc`) | The cover page with two tables; Carlito, with the metrics of Calibri, 11 pt with a line spacing of 1.15 and 10 pt after a paragraph; margins of 29 mm, 20 mm, 27.5 mm and 25 mm; numbered headings of 14 pt; the hint under a chapter heading in the light blue box of the template, over the width of the text, italic 10 pt in dark grey, 3 pt from its top and bottom edge (an alert of GitHub in the file); "Seite N von M" at the bottom right. |

The thesis and the concept paper also differ in three defaults: the type of
the work (`Bachelorarbeit` or `Konzeptpapier`), `kapitelumbruch` (`ja` or
`nein`), and the heading of the reference list: the concept paper also finds
the heading "Erste Auswahl an (Grundlagen-)Literatur und Quellen" of the
concept template of the PHT. The thesis layout also numbers the reference list
and the lists of figures, tables and listings as chapters, and leaves the
chapters before the first chapter out of the table of contents, as the Word
template does. A hint (`> [!NOTE]`) is the light blue box of the concept
template in both layouts, also in the look `klassisch`. Each folder holds its
own copies of the files, because the paths of a layout stay inside its folder.

### How close the pages are to Word

The look `vorlage` was measured line by line against PDFs of the templates.
The browser puts each line on a whole pixel (0.26 mm), so a line can be up to
0.13 mm away from its place in Word.

- `concept/`: against a PDF that Word made from a concept paper in the
  template, 176 of 207 lines of text have the same words, and all of them are
  at most 0.2 mm away from their place in Word. Each page has the same lines.
  The other lines break at another place, mostly because Word hyphenates some
  words at another syllable or breaks an address at another character.
- `thesis/`: no PDF of Word was at hand, so the pages were measured against
  the PDF that LibreOffice 24.2 makes from the template. The lines with the
  same words are at most 0.16 mm away from their place in LibreOffice, also
  the headings, the footers and the footnotes. Some lines break at another
  place, where LibreOffice, unlike Word, shrinks the spaces of a line by more
  than a fifth, or keeps a word whole because of the hyphenation zone of the
  template, which Word does not apply (the PDF of the concept paper shows
  this). The cover page and the place of the caption of a figure differ from
  the template on purpose, as described above. A Word PDF of the thesis
  template would allow a check against Word itself.
- A Markdown table has no widths of its columns, so the browser gives each
  column its width, and the columns of a table can differ from Word.

A document names its layout in the front matter, for example
`layout: thesis`. Today Markdown Paper reads a layout from the folder
`layouts/` of the repository of the document, so a document uses a copy of the
layout folder there, for example `layouts/thesis/`; `markdownpaper create
--layout github:majikmate/markdownpaper-layout-pht/thesis` makes this copy.
Until the first release this repository has no release tag.

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
| `thesis/` | The front matter with the texts of the cover page of the Word template ("Titel eintragen", "Matrikelnummer eintragen", …); the "Eidesstattliche Erklärung", the "Abstract" and the "Vorwort" with the texts of the template; then eight chapters that explain in German how to work with the document in VS Code with nimblescape Markdown Paper and nimblescape Markdown Notes: the folders of a project, the cover page, text, headings, footnotes, the Markdown of the styles of the template, figures, tables, code, sources and citations, AI tools and agents, notes, the pages, the PDF, and the texts of the template on gender-fair language and accessibility; then the lists, the list of abbreviations and the appendix of the template. The figure is `images/projekt-ordner.svg`, the listing shows `code/mittelwert.py`, and the example citation is the source `hattie2007`, whose metadata `markdownpaper source` took from doi.org. |
| `concept/` | The front matter with the texts of the cover page of the concept template ("Geben Sie hier Ihren Vor- und Familiennamen ein!", …); the five chapters of the template, each with the hint of the template word for word under its heading, as an alert of GitHub (`> [!NOTE]` and the text in the next line), which the look `vorlage` draws as the light blue box of the template (RGB 219/229/241, italic 10 pt, dark grey) and GitHub shows as a box too; after each hint a short explanation of how to write the chapter, with a table and the same example citation. |

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
| "Vorlage Abschlussarbeit", the Word template for theses | <https://cms.ph-tirol.ac.at/documents/Abschlussarbeit_Vorlage.docx> | 2026-10-30 | the look `vorlage` of `thesis/`; in `document.md` of `thesis/` the texts of the cover page, of the "Eidesstattliche Erklärung", the "Abstract" and the "Vorwort", the styles of table 1, the texts on AI tools with table 2, on gender-fair language and on accessibility, and the texts of the lists, of the list of abbreviations and of the appendix |
| "Corporate Design" of the PHT, the page with the logos and the colors | <https://ph-tirol.ac.at/corporate-design-pht/> | 2026-10-30 | the red of the PHT, RGB 238/17/23 (`#EE1117`, HKS 13), as in the logo of the web site |
| "Wortmarke" of the PHT (`PHT_wortmarke.zip`), from the page "Corporate Design" | <https://cms.ph-tirol.ac.at/documents/PHT_wortmarke.zip> | 2026-10-30 | `images/pht-logo.png` of `thesis/`, made from `PHT_wortmarke_rgb.pdf` |
| "Zitationsrichtlinien für Abschlussarbeiten" (Zitation nach APA 7), version 2.0 | <https://cms.ph-tirol.ac.at/documents/APA7-V2_0.pdf> | 2026-10-30 | `pht-apa7.csl` |
| "Vorlage für Konzeptpapier – Sekundarpädagogik", the Word template of the concept paper | <https://cms.ph-tirol.ac.at/documents/bac_konzeptpapierBA_SEK_2022.doc> | 2026-10-30 | the look `vorlage` of `concept/`; in `document.md` of `concept/` the texts of the cover page, the chapter headings and the hints below them; the heading of their reference list |
| "Vorlage für Konzeptpapier – Primarpädagogik" | <https://cms.ph-tirol.ac.at/documents/konzeptpapierBA.PRIMAR.doc> | 2026-10-30 | not used: a concept paper of the primary level starts from this template instead |

The Word template for theses at the address above has the same text,
margins and styles as version 4.1, which the skill was made from (checked on
2026-10-30). The look `vorlage` follows the Word templates; the look
`klassisch` keeps the font and the bottom margin of the skill.

## The citation style of the PHT

[`thesis/pht-apa7.csl`](thesis/pht-apa7.csl) (and its copy in `concept/`) is the citation style of the
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
  `Abb.`, `Tab.`, `H.`, `Fn.`, `T.`, `Anh.`, and `Art.` and `§` in a law, each
  with a no-break space before the place (`S. 81`);
- the day before the month: `(2018, 1. Oktober)`;
- the day of the access whenever the metadata of a source has one;
- a law (`legislation`) or an ordinance (`regulation`) in the form of the
  guide: `Lehrplan der Volksschule. BGBl. Nr. 134/1963 in der Fassung BGBl. II
  Nr. 303/2012 vom 13. September 2012.` The fields of CSL JSON:

  | Field | Content | Example |
  | --- | --- | --- |
  | `title` | The title of the law or the ordinance | `Lehrplan der Volksschule` |
  | `container-title` | The gazette of the first publication | `BGBl.`, `BGBl. I`, `BGBl. II`, `ABl. L` |
  | `number` | The number of the first publication, as the gazette writes it | `Nr. 134/1963` |
  | `references` | The version that the text cites, without "in der Fassung"; left out for the first version | `BGBl. II Nr. 303/2012` |
  | `issued` | The day of that version, or of the law without a version, with day, month and year | `{"date-parts":[[2012,9,13]]}` |

  The citation names the title and the year of `issued`:
  `(Lehrplan der Volksschule, 2012)`, `(Schulorganisationsgesetz, 1962, § 65)`.
  Zotero writes these fields for an item of the type "Statute": "Code",
  "Public Law Number", "History" and "Date Enacted".

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
- `fonts/Carlito-*.ttf` in `concept/`: Carlito 1.104, copyright (c) 2010-2013
  by tyPoland Łukasz Dziedzic, under the SIL Open Font License 1.1, see
  `fonts/LICENSE-Carlito.txt`. It has the metrics of Calibri, the font that
  Word shows for the concept template.
- `images/pht-logo.png` in each layout: the logo of the Pädagogische
  Hochschule Tirol. It is not under CC BY-SA 4.0; the PHT holds its rights.
  It is here only for the cover pages of works at the PHT. In `thesis/` it
  is the word mark of the page "Corporate Design" in the red of the PHT; the
  concept layout has the logo of the Word template, whose red is darker.
