[Letztes Kapitel](Kapitel9.md)

# Kapitel 10: Briefe schreiben mit ``scrlttr2``

## Allgemeines

* Die ``scrlttr2`` Klasse gehört zum KOMA-Script Paket
* ``scrlttr2``ist eine sehr mächtige Klasse, sie lässt sich sehr gut an ein vorgegebenes Corporate Design anpassen
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

![brief-01.png](https://github.com/UweZiegenhagen/LaTeXEinsteigerKurs/blob/master/code/brief-01.png)

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

## Briefe schreiben mit dem ``scrletter`` Paket

Neben der Nutzung der ``scrlttr2`` Klasse kann man auch die Brief-Funktionen nutzen, indem man in einer KOMA-Klasse das ``scrletter`` Paket lädt. 

**code/**

```latex
\documentclass[12pt,ngerman]{scrartcl}
 
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{palatino}
\usepackage{blindtext}
\usepackage{scrletter}
 
\setkomavar{fromname}{Max Mustermann}
\setkomavar{fromemail}{Max@Mustermann.de}
\setkomavar{fromaddress}{Musterweg 221, 12345 Musterstadt}
\setkomavar{firstfoot}{\usekomavar{fromemail}}
 
\begin{document}
\begin{letter}{Maria Mustermann \\ Mustergasse 1 \\ 12346 Musterstadt}
 
\opening{Hallo Maria,}
 
\blindtext[2]
 
\closing{Mit freundlichen Grüßen}
 
\end{letter}
\end{document}
```

Weiter geht es im [nächsten Kapitel](Kapitel11.md) mit der Erstellung von Grafiken.
