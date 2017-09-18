[Letztes Kapitel](Kapitel8.md)

# Kapitel 9: Präsentationen mit dem ``beamer`` Paket

## Allgemeines

* ``beamer`` ist ein sehr mächtiges Paket für die Folienerstellung
* Das Handbuch dazu (``texdoc beamer``) hat knapp 250 Seiten und ist lesenswert nicht nur für die technische Seite
* Alternative: ``prosper``

## Meine erste Präsentation

* Als Dokumentenklasse nutzt man ``beamer``
* Autor und Titel werden wie üblich definiert, die Titelfolie setzt man auch mit ``\maketitle``
* Die einzelnen Folien werden innerhalb von ``frame`` Umgebungen gesetzt.
* Übliche Umgebungen für Aufzählungen und Bullet-Listen gehen auch, sogar verschachtelt.

**code/beamer-01.tex**

```latex
\documentclass[12pt,ngerman]{beamer}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\author{Max Mustermann}
\title{Meine erste Präsentation}

\begin{document}

\begin{frame}

\maketitle

\end{frame}

\begin{frame}

\tableofcontents

\end{frame}
 

\section{Einleitung}

\begin{frame}
\frametitle{Hallo Welt}
\framesubtitle{Foo Bar}

\begin{itemize}
\item Hallo
\item das
\item ist 
\item eine 
\item Item-Liste
\end{itemize}
\end{frame}

\section{Hauptteil}

\begin{frame}
\frametitle{Mathematik}
\framesubtitle{geht auch}

\[ a^2 + b^2 = c^2 \]

\begin{itemize}
\item Ich
\item bin 
\item eine
\item Aufzählung
\end{itemize}
\end{frame}

\end{document}
```

![beamer-01-0.png](./code/beamer-01-0.png)

![beamer-01-1.png](./code/beamer-01-1.png)

![beamer-01-2.png](./code/beamer-01-2.png)

![beamer-01-3.png](./code/beamer-01-3.png)

## Designs setzen

Mit nur zwei Befehlen lassen sich das generelle Design und das Farbdesign anpassen:

* ``\usetheme{Warsaw}`` für das Design
* ``\usecolortheme{wolverine}`` für das Farb-Design

Das folgende Beispiel setzt diese um.

**code/beamer-02.tex**

```latex
\documentclass[12pt,ngerman]{beamer}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\usetheme{Warsaw}
\usecolortheme{wolverine}

\author{Max Mustermann}
\title{Meine erste Präsentation}

\begin{document}

\begin{frame}

\maketitle

\end{frame}

\begin{frame}

\tableofcontents

\end{frame}


\section{Einleitung}

\begin{frame}
\frametitle{Hallo Welt}
\framesubtitle{Foo Bar}

\begin{itemize}
\item Hallo
\item das
\item ist 
\item eine 
\item Item-Liste
\end{itemize}
\end{frame}

\section{Hauptteil}

\begin{frame}
\frametitle{Mathematik}
\framesubtitle{geht auch}

\[ a^2 + b^2 = c^2 \]

\begin{itemize}
\item Ich
\item bin 
\item eine
\item Aufzählung
\end{itemize}
\end{frame}

\end{document}
```

![beamer-02-0.png](code/beamer-02-0.png)

![beamer-02-1.png](code/beamer-02-1.png)

![beamer-02-2.png](code/beamer-02-2.png)

![beamer-02-3.png](code/beamer-02-3.png)


## Text-Animationen

Mit wenig Aufwand lassen sich auch Bullet-Points erstellen, die erst nach und nach aufgeblättert werden:

**code/beamer-03.tex**

```latex
\documentclass[12pt,ngerman]{beamer}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\usetheme{Warsaw}
\usecolortheme{wolverine}

\begin{document}

\begin{frame}
\frametitle{Hallo Welt}
\framesubtitle{Foo Bar}

\begin{itemize}
\item<5->  Hallo
\item<3->  das
\item<2->  ist 
\item<4->  eine 
\item<1->  Item-Liste
\end{itemize}
\end{frame}


\begin{frame}
\frametitle{Hallo Welt}
\framesubtitle{Foo Bar}

\begin{itemize}[<+->]
\item  Hallo
\item  das
\item  ist 
\item  eine 
\item  Item-Liste
\end{itemize}
\end{frame}



\end{document}
```

![beamer-032-0.png](code/beamer-03-0.png)

![beamer-03-1.png](code/beamer-03-1.png)

![beamer-03-2.png](code/beamer-03-2.png)

![beamer-03-3.png](code/beamer-03-3.png)


## Mehr

Wie oben erwähnt lässt sich mit Beamer noch sehr viel mehr anstellen, als es in diesem Kapitel beschrieben werden kann.

Ein guter Überblick findet sich in [https://en.wikibooks.org/wiki/LaTeX/Presentations#Animations](https://en.wikibooks.org/wiki/LaTeX/Presentations#Animations).




Weiter geht es im [nächsten Kapitel](Kapitel10.md) mit der Erstellung von Briefen.