[Letztes Kapitel](Kapitel2.md)

# Kapitel 3: Wir strukturieren das Dokument


Als nächstes geben wir unserem Dokument Struktur im Sinne von Abschnitten und Unterabschnitten. LaTeX kennt dafür verschiedene Befehle, in der `scrartcl` Dokumentenklasse sind die folgenden verfügbar:

* `\section{}`
* `\subsection{}`
* `\subsubsection{}`

Diese drei sind abgesetzt und werden nummeriert. Zusätzlich gibt es noch `\paragraph` und `\subparagraph`, persönlich nutze ich diese jedoch eher selten.

`scrreprt` und `scrbook` kennen zusätzlich noch `\chapter{}` für Kapitel, `scrbook` weiterhin noch `\part{}`.

Zusätzlich fügen wir noch den Befehl `\tableofcontents` ein, um ein Inhaltsverzeichnis zu erhalten. 

Hinweis: Wir müssen das Dokument ab jetzt immer (zumindest immer wenn wir die Sections editieren) zweimal übersetzen! Beim ersten Übersetzen erstellt LaTeX das Inhaltsverzeichnis in einer externen Datei (Dateiname.**toc**), beim zweiten Lauf wird der Inhalt dieser **.toc** Datei dann in das Dokument eingefügt und gesetzt.

**Dateiname.tex**
```latex
\documentclass[12pt]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\author{Max Mustermann}
\title{Mein erstes Dokument}

\begin{document}
\maketitle

\tableofcontents


\section{Hallo}

Hallo Welt!

\section{Welt}
\subsection{Foo}

Hallo Welt

\subsection{Welt}



\end{document}
```

`scrartcl` erzeugt keine abgesetzte Titelseite, `scrbook` und `scrreprt` schon. Probiert das mal aus! Neben `\tableofcontents` für das Inhaltsverzeichnis gibt es noch `\listoffigures` für Abbildungen und `\listoftables` für Tabellen. Dazu aber später mehr.

Weiter geht es im [nächsten Kapitel](Kapitel4.md) mit Aufzählungen und Textauszeichnungen.