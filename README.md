# markdownpaper-layout-pht

The layouts of the Pädagogische Hochschule Tirol (PHT) for
[nimblescape Markdown Paper](https://github.com/nimblescape/markdownpaper-vscode),
the extension of VS Code and the command `markdownpaper` that make the pages and
the PDF of a Markdown document in a layout.

| Folder | Layout | State |
| --- | --- | --- |
| [`thesis/`](thesis/) | The thesis (Abschlussarbeit) of the PHT, in German (`de-AT`): each chapter starts on a new page | done |
| [`concept/`](concept/) | The concept paper (Konzeptpapier) of the PHT, in German (`de-AT`): the same pages, but a chapter follows the text before it | done |

Both layouts have the look of the PHT template: a cover page with the logo of
the PHT, the type of the work, the title, the author, the degree and the
supervisor; A4 with margins of 30 mm, 25 mm, 22 mm and 35 mm; Liberation Serif
in 12 pt with a line spacing of 1.5; a footer with the author and "Seite N"
below a line; footnotes at the foot of the page; and the citation style of the
PHT. The fields of the front matter are in German, as in the template:
`title`, `subtitle`, `type`, `author`, `grad`, `betreuerin`,
`matrikelnummer`, `studium`, `lehrveranstaltung`, `date` and
`kapitelumbruch`. `layout.json` of each folder describes them, and the name of
the PDF file is `{{matrikelnummer}}_{{author}}_{{lehrveranstaltung}}_{{type}}`.

The two layouts differ only in three defaults: the type of the work
(`Bachelorarbeit` or `Konzeptpapier`), `kapitelumbruch` (`ja` or `nein`), and
the heading of the reference list: the concept paper also finds the heading
"Erste Auswahl an (Grundlagen-)Literatur und Quellen" of the concept template
of the PHT. Each folder holds its own copies of the files, because the paths
of a layout stay inside its folder.

A document names its layout in the front matter, for example
`layout: concept`. Today Markdown Paper reads a layout only from the folder
`layouts/` of the repository of the document, so a document uses a copy of the
layout folder there, for example `layouts/concept/`. Loading a layout directly
from this repository is planned; until the first release this repository has
no release tag, so a document will name a branch or a commit.

The GitHub topic `nimblescape-markdownpaper-layout` marks this repository as a
repository of layouts for Markdown Paper; the page
<https://github.com/topics/nimblescape-markdownpaper-layout> lists all public
ones.

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

- `fonts/LiberationSerif-*.ttf` in each layout: Liberation Serif, copyright
  (c) 2010 Google Corporation and (c) 2012 Red Hat, Inc., under the SIL Open
  Font License 1.1, see `fonts/LICENSE-LiberationSerif.txt`. It has the
  metrics of Times New Roman, the font of the PHT template.
- `images/pht-logo.png` in each layout: the logo of the Pädagogische
  Hochschule Tirol. It is not under CC BY-SA 4.0; the PHT holds its rights.
  It is here only for the cover pages of works at the PHT.
