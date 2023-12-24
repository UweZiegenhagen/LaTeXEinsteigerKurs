[Letztes Kapitel](Kapitel12.md)

# Längere Dokumente schreiben

Bei längeren Dokumenten ist es recht umständlich, durch den Quellcode zu scrollen. LaTeX hat aber einige Features, die uns die Verwaltung von größeren Projekten erleichtert. 

* ``\input`` und ``\include``
*  Arara und andere Build-Tools

## ``\input`` und ``\include`` 

Mit dem ``\input`` Befehl kann man Inhalte aus einer Datei in eine andere Datei  einfügen. Der eingefügte Text/Quellcode wird dabei so behandelt, als hätte man ihn direkt in die andere Datei geschrieben.

Ich nutze ``\input`` meistens, um die Präambel eines Dokuments in eine externe Datei auszulagern.

Eine Datei, die mittels ``\input`` eingebunden wird, kann weitere Dateien mittels ``\input`` einbinden.

Im Gegensatz zu ``\input`` führt ``\include`` vor dem Einfügen des Inhalts ein ``\clearpage`` aus. Üblicherweise nutzt man ``\include``, um einzelne Kapitel einer längeren Arbeit auszulagern. 

Dann lässt sich nämlich mit ``\includeonly{Kapitel1,Kapitel3}`` eine Liste von Dateien angeben, die aktuell in Bearbeitung sind. Insbesondere in früheren Zeiten, als LaTeX-Läufe noch eine halbe Stunde dauerten, war dies ein sinnvolles Feature.

Hinweis: Eine Datei, die mittels ``\include`` eingebunden wird, kann keine weiteren Dateien mittels ``\include`` einbinden.

**Beispiel**

Schauen wir uns ein Beispiel für die Funktion von ``\input`` und ``\include`` an. Speichere die Inhalte der folgenden vier Dateien unter den angegebenen Namen.

**main.tex**
```latex
\documentclass[12pt,ngerman]{scrreprt}

\input{preamble}

\begin{document}

\include{kapiteldatei01}

\include{kapiteldatei02}

\end{document}
```


**preamble.tex**
```latex
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{blindtext}
```


**kapiteldatei01.tex**
```latex
%!TeX root=main.tex
\chapter{Erstes Kapitel}

\blindtext[3]
```


**kapiteldatei02.tex**
```latex
%!TeX root=main.tex
\chapter{Zweites Kapitel}

\blindtext[3]
```

Das Hauptdokument ``main.tex`` können wir jetzt übersetzen, alle Kapitel werden eingebunden. Zu jeder Kapiteldatei wird  eine _.aux_ Datei angelegt, in der die Seitenzahl und diverse Zählerstände gespeichert werden. Mittels ``\includeonly`` können wir jetzt die erste Datei aus der Übersetzung aussschließen. Beim Übersetzen von ``main.tex`` wird jetzt nur das zweite Kapitel übersetzt, die Seitenzahl (2) wird aber korrekt angezeigt. ``%!TeX root=main.tex`` sorgt übrigens in TeXworks (und eventuell auch anderen Editoren) dafür, dass man auch aus den einzelnen Kapiteln heraus die gesamte Arbeit kompilieren kann.

**main.tex**
```latex
\documentclass[12pt,ngerman]{scrreprt}
\input{preamble}

\includeonly{kapiteldatei02}

\begin{document}
    \include{kapiteldatei01}
    \include{kapiteldatei02}
\end{document}
```

## Arara und andere Build-Tools

Weiter geht es im [nächsten Kapitel](Kapitel14.md)
