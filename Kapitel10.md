[Letztes Kapitel](Kapitel6.md)

# Kapitel 10: Briefe schreiben mit ``scrlttr2``

## Allgemeines

* Die ``scrlttr2`` Klasse gehört zum KOMA-Script Paket
* Sehr mächtige Klasse, lässt sich sehr gut auf eigene Wünsche anpassen
* Alternative: ``dinbrief``

## Meine erster Brief

**code/brief-01.tex**

```latex
\documentclass[12pt,ngerman]{scrlttr2}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{blindtext}
\usepackage{palatino} 

\begin{document}
 
\setkomavar{fromname}{Max Mustermann}
\setkomavar{fromaddress}{Musterstr. 12 \\ 12345~Musterstadt}
\setkomavar{subject}{Mahnung}
\setkomavar{myref}{2017-xyz}
\setkomavar{yourref}{08.09.2017}

\begin{letter}{Martina Musterfrau \\ Musterweg 4 \\ 12346~Musterdorf}
\opening{Sehr geehrte Damen und Herren,}
 
\blindtext[1]

\closing{Mit freundlichen Grüßen,}
\encl{Dokument 1 \\ Dokument 2}
\end{letter}
 
\end{document}
```

## Auslagerung von Stammdaten

Stammdaten wie Absender und Absenderadresse sind statisch und ändern sich nur selten. Diese lassen sich in eine Datei mit der Endung ``.lco`` auslagern. Den Namen der Datei (ohne das ``.lco``) lädt man dann als Klassenoption

**code/brief-02.tex**

```latex
\documentclass[12pt,ngerman,max]{scrlttr2}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{blindtext}
\usepackage{palatino} 

\begin{document}
 
\setkomavar{subject}{Mahnung}
\setkomavar{myref}{2017-xyz}
\setkomavar{yourref}{08.09.2017}

\begin{letter}{Martina Musterfrau \\ Musterweg 4 \\ 12346~Musterdorf}
\opening{Sehr geehrte Damen und Herren,}
 
\blindtext[1]

\closing{Mit freundlichen Grüßen,}
\encl{Dokument 1 \\ Dokument 2}
\end{letter}
 
\end{document}
```

Die passende ``max.lco`` Datei sieht so aus:

**code/max.lco**

```latex
\setkomavar{fromname}{Max Mustermann}
\setkomavar{fromaddress}{Musterstr. 12 \\ 12345~Musterstadt}

```





Weiter geht es im [nächsten Kapitel](Kapitel8.md) mit 