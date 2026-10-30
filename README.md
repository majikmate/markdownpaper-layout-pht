# markdownpaper-layout-pht

The layouts of the Pädagogische Hochschule Tirol (PHT) for
[nimblescape Markdown Paper](https://github.com/nimblescape/markdownpaper-vscode),
the extension of VS Code and the command `markdownpaper` that make the pages and
the PDF of a Markdown document in a layout.

| Folder | Layout | State |
| --- | --- | --- |
| [`thesis/`](thesis/) | The thesis (Abschlussarbeit) of the PHT, in German (`de-AT`) | the citation style is done; the look of the Word template of the PHT follows |

The GitHub topic `nimblescape-markdownpaper-layout` marks this repository as a
repository of layouts for Markdown Paper; the page
<https://github.com/topics/nimblescape-markdownpaper-layout> lists all public
ones.

## The citation style of the PHT

[`thesis/pht-apa7.csl`](thesis/pht-apa7.csl) is the citation style of the
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
are listed here when a layout holds them.
