# Kapitel 2: Unser erstes richtiges Dokument

Nachdem wir in [Kapitel 1](Readme.md) ein erstes kleines Dokument erstellt und hoffentlich sauber übersetzen konnten, schauen wir uns jetzt an, wie man ein Dokument _richtig_ aufsetzt. Mit _richtig_ meine ich damit die Auswahl der passenden TeX-Engine, die Wahl der richtigen Pakete und Einstellungen.

## Die richtige Dokumentenklasse

Im ersten Kapitel hatten wir ein Beispiel gesehen, das die Dokumentenklasse `article` benutzt hat. Diese Klasse, sowie auch `book` und `report` sind für typografische Gewohnheiten im US-amerikanischen bzw. angelsächsischen Raum erstellt worden. Für deutsche bzw. europäische Texte sind sie aus typografischer Sicht nicht geeignet, da gibt es bessere!

Ganz klar zu empfehlen sind die Klassen aus dem KOMA-Script Paket von Markus Kohm. Sie ersetzen die ursprünglichen Klassen perfekt und produzieren wohlfeile Dokumente. Es gilt also:

* Lass article, report und book weg, wenn es keinen _spezifischen_ Grund dafür gibt.
* Ersetze:
	* `article` durch `scrartcl`
	* `report` durch  `scrreprt`
	* `book` durch `scrbook`

## Die richtige TeX-Engine

Es gibt mehr als einen Weg, ein TeX-Dokument zu übersetzen. Im ersten Kapitel hatten wir  `pdflatex` benutzt, es gibt aber Alternativen. Hier eine kurze Übersicht.

* **pdflatex**: die schnellste Engine, sehr ausgereift. Kann aber nicht mit OpenType-Fonts umgehen, die Integration von Schriften ist sehr komplex und wird daher keinem Anfänger empfohlen
* **xelatex**: kann mit den Systemschriften umgehen, ist aber AFAIK nicht mehr aktiv in der Entwicklung
* **lualatex**: aktiv in der Entwicklung, die langsamste der Engines. Wie xelatex kann luaLaTeX mit Systemfonts im OTF-Format umgehen. Ein Hauptvorteil ist die integrierte Lua-Engine, die vieles in der Arbeit mit dem TeX-Kern leichter macht. Siehe dazu auch [Kapitel 14](Kapitel14.md).

Hinweis: alle drei Programme gibt es auch ohne das "la" im Namen, also als `pdftex`, `xetex` und `luatex`. Diese drei Programme verstehen nur pures TeX, mit LaTeX können sie nichts anfangen und werfen schon beim "\documentclass{}" Fehlermeldungen. Die Arbeit mit TeX ist noch ein wenig `komischer` als die Arbeit mit LaTeX. Ich empfehle daher, mit LaTeX anzufangen.

Welche TeX-Engine solltet ihr nehmen? Hängt davon ab, aber mit `pdflatex` macht man als Anfänger nichts falsch. Wenn man Systemschriften nutzen möchte oder muss, kommt man um xelatex/lualatex üblicherweise nicht herum, wenn es um weitergehende Programmierung geht, ist sicherlich `lualatex` das Mittel der Wahl.

Da dies hier ein Anfängertutorial sein soll, werden wir uns im folgenden auf `pdflatex` konzentrieren. 

## Unser erstes 'richtiges' Dokument

Im folgenden bauen wir Schritt für Schritt ein komplettes Dokument auf.

Beginnen wir mit dem folgenden Schnipsel, der die KOMA-Klasse `scrartcl` mit der Grundschrifthöhe 12pt nutzt:

**document-01.tex**

```latex
\documentclass[12pt]{scrartcl}

\begin{document}

Hallo Welt!

\end{document}
```

![document-01.png](./code/document-01.png)

Als nächstes teilen wir LaTeX mit, dass wir mit westeuropäischen Schriften arbeiten und die deutsche Silbentrennung haben möchten. 

Hinweis: die oft gesehene Zeile ``\usepackage[utf8]{inputenc}`` braucht man nicht mehr, UTF-8 ist seit mehreren Jahren Standard-Einstellung.

**document-02.tex**

```latex
\documentclass[12pt]{scrartcl}


\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

Hallo Welt!

\end{document}
```

![document-02.png](./code/document-02.png)

Dies ist das Grundgerüst für jedes `pdflatex`-Dokument, diese paar Zeilen kann man sich merken oder abspeichern. 

`babel` sorgt dabei nicht nur für die richtige Silbentrennung, es deutscht auch das Datum ein und die Überschriften für die verschiedenen Verzeichnisse wie Inhalts- oder Abbildungsverzeichnis.

Geben wir dem Dokument als nächstes den Autor und Titel mit und lassen diesen Titel dann mit dem Befehl `\maketitle` setzen:

**document-03.tex**

```latex
\documentclass[12pt,ngerman]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\author{Max Mustermann}
\title{Mein erstes Dokument}

\begin{document}
\maketitle

Hallo Welt!

\end{document}
```

![document-03.png](./code/document-03.png)

Aufgabe: Ersetzt doch einmal testweise die `scrartcl` Dokumentenklasse durch `scrreprt` oder `scrbook`! Was verändert sich?

Ein Hinweis zur Titelseite: individuelle Titelseiten lassen sich mit der `titlepage`-Umgebung auch erstellen. Das ist aber recht komplex und wird daher -- wenn überhaupt -- erst in einem späteren Kapitel behandelt.

Weiter geht es im [nächsten Kapitel](Kapitel3.md)
