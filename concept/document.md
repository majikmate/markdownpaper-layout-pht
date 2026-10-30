---
title: "Arbeitstitel eintragen"
author: "Geben Sie hier Ihren Vor- und Familiennamen ein!"
grad: "Bachelor of Education (BEd)"
betreuerin: "Klicken oder tippen Sie hier, um Text einzugeben."
matrikelnummer: "Klicken oder tippen Sie hier, um Text einzugeben."
studium: "Klicken oder tippen Sie hier, um Text einzugeben."
date: "Klicken oder tippen Sie, um ein Datum einzugeben."
---

# Arbeitstitel

> [!NOTE]
> Bitte achten Sie darauf, dass der Bezug zum Berufsfeld Schule oder zum Schulunterricht im Titel sichtbar ist.

Diese Datei ist das leere Konzeptpapier der Pädagogischen Hochschule Tirol (PHT), in Markdown geschrieben. Das Deckblatt hat die Texte der Word-Vorlage der PHT, und die Kapitel haben die Überschriften der Vorlage. Unter jeder Überschrift steht der Hinweis der Vorlage im blauen Kasten, wie in der Vorlage, und darunter eine kurze Erklärung, wie Sie mit der Datei arbeiten. Ersetzen Sie jede Erklärung durch Ihren Text. Die Datei `document.pdf` im Ordner des Layouts zeigt die Seiten dieser Datei als PDF.

In der Datei ist ein Hinweis ein Hinweisblock von GitHub: die Zeile `> [!NOTE]` und darunter `> ` mit dem Text des Hinweises. GitHub zeigt ihn ebenfalls als Kasten. Löschen Sie die Zeilen eines Hinweises, wenn Sie ihn nicht mehr brauchen.

Sie schreiben in [Visual Studio Code](https://code.visualstudio.com/) mit den Erweiterungen [nimblescape Markdown Paper](https://github.com/nimblescape/markdownpaper-vscode) und [nimblescape Markdown Notes](https://github.com/nimblescape/markdownnotes-vscode). Das Deckblatt entsteht aus den Feldern im Kopf der Datei zwischen den zwei Zeilen `---`: Schreiben Sie Ihren Namen in `author`, die Matrikelnummer in `matrikelnummer` und so weiter. Strg+K und dann V zeigt die Seiten neben dem Text, und „Export PDF“ im Menü „Ausführen“ oben rechts im Editor erstellt das PDF. Die leere Abschlussarbeit des Layouts `thesis` erklärt alle Funktionen ausführlich.

**Arbeitstitel eintragen**

# Persönliche und berufsfeldbezogene Relevanz des Themas

> [!NOTE]
> Stellen Sie an den Anfang eine kurze Begründung Ihres Arbeitsvorhabens! Was sind Ihre Motive, sich mit diesem Thema auseinanderzusetzen? Was beschäftigt Sie bei diesem Thema? Warum ist eine Auseinandersetzung mit diesem Thema von pädagogischem, schulrelevantem Interesse?

Schreiben Sie jeden Absatz in eine Zeile; eine leere Zeile trennt zwei Absätze. `**fett**` wird **fett**, `*kursiv*` wird *kursiv*, und eine Zeile mit `- ` am Anfang ist ein Punkt einer Aufzählung. Eine Fußnote hat einen Verweis im Text und ihren Text in einer eigenen Zeile.[^1] Die Silbentrennung macht Markdown Paper selbst.

[^1]: So sieht eine Fußnote aus. In VS Code schreibt `/footnote` nach einem Wort eine neue Fußnote.

# Kurzbeschreibung der (fachl. und wissenschaftl.) Ausgangslage

> [!NOTE]
> Was ist der fachliche Ausgangspunkt Ihrer Überlegungen? Wie wird das Thema in der von Ihnen bisher gesichteten Literatur dargestellt? Diese Ausführungen untermauern Sie mit drei bis fünf relevanten Literaturquellen.

Ein Zitat ist ein Link auf die ID einer Quelle, mit der Stelle in der Quelle als Titel des Links: Feedback wirkt stark auf das Lernen ([Hattie & Timperley, 2007, S. 81](#hattie2007 "page 81")). Die Daten der Quellen stehen in einem Kommentar am Ende der Datei. Schreiben Sie sie nicht selbst: Ein KI-Agent holt sie mit `npx -y @nimblescape/markdownpaper source paper/paper.md` und der DOI der Quelle von doi.org. Den Text der Zitate und das Literaturverzeichnis in Kapitel 5 schreibt der Formatierer beim Speichern. Für ein Argument ohne Quelle markieren Sie es und tippen `/research`: An seinem Ende steht dann `(RESEARCH)`, und ein KI-Agent sucht Quellen, die es stützen, und setzt ihre Zitate an diese Stelle.

# Forschungsfrage(n) und Forschungsskizze

> [!NOTE]
> Durch die Wahl der Forschungsmethode(n) generieren Sie Ihre Forschungsdaten auf Basis derer Sie zur Beantwortung Ihrer Forschungsfrage(n) gelangen. Die Wahl der Methode(n) sollte daher gut überlegt sein und sicherstellen, dass Sie mit deren Hilfe tatsächlich zu Antworten für Ihre Forschungsfragen kommen können. Achten Sie v.a. auf die Einhaltung der Gütekriterien bei der Umsetzung Ihres gewählten Forschungsvorgehens.

`##` vor einer Zeile macht einen Abschnitt, zum Beispiel für die Forschungsfragen, die Methode und den Zeitplan. Eine Tabelle besteht aus Zeilen mit `|` zwischen den Spalten; der Absatz `Tabelle 1:` direkt davor ist ihre Beschriftung. `/table` in einer leeren Zeile schreibt eine Tabelle, `/figure` eine Abbildung aus dem Ordner `images/`.

Tabelle 1: Zeitplan <a id="tab-zeitplan"></a>

| Zeitraum | Arbeitsschritt |
| --- | --- |
| Monat 1 | Literatur und Leitfaden |
| Monat 2 | Erhebung |
| Monat 3 | Auswertung und Schreiben |

# Erste Auswahl an (Grundlagen-)Literatur und Quellen

> [!NOTE]
> Führen Sie hier mind. 5 Werke an und beachten Sie die Zitationsvorgaben gem. aktueller APA-Style-Richtlinien

<a id="hattie2007"></a>Hattie, J., & Timperley, H. (2007). The Power of Feedback. *Review of Educational Research, 77*(1), 81 – 112. https://doi.org/10.3102/003465430298487

<!-- Der Formatierer schreibt die Einträge der zitierten Quellen unter den Hinweis. -->

<!-- nimblescape-sources
{"id":"hattie2007","type":"article-journal","author":[{"family":"Hattie","given":"John"},{"family":"Timperley","given":"Helen"}],"issued":{"date-parts":[[2007,3]]},"title":"The Power of Feedback","container-title":"Review of Educational Research","container-title-short":"Review of Educational Research","volume":"77","issue":"1","page":"81-112","publisher":"American Educational Research Association (AERA)","ISSN":"0034-6543","DOI":"10.3102/003465430298487","language":"en"}
-->
