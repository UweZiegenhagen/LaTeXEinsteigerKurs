[Letztes Kapitel](Kapitel6.md)

# Kapitel 7: Mathesatz

## Allgemeines

* Der Satz von mathematischen Formeln ist **die** Vorzeige-Funktion von TeX
* Sogar Word unterstützt in der neuesten Version die LaTeX-Notation für Formeln, kann also nicht so schlecht sein
* Übersicht über defacto alle Symbole, die sich setzen lassen: http://tug.ctan.org/info/symbols/comprehensive/symbols-a4.pdf
* bei lokal installiertem TeX Live erreichbar über `texdoc symbols-a4`

## Meine erste Formel

**code/document-13.tex**

```latex
\documentclass[12pt,ngerman]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

Innerhalb des Fließtextes kann man eine Formel $a^2 + b^2 = c^2$ setzen.

Auch abgesetzte Formeln sind möglich.

\[ a^2 + b^2 = c^2 \]

\end{document}
```

![document-13.png](https://github.com/UweZiegenhagen/LaTeXEinsteigerKurs/blob/master/code/document-13.png)


Hinweis: Es gibt noch die  `$$a^2+b^2=c^2$$`-Notation für abgesetzte Formeln, diese wird aber nicht empfohlen,denn:

* Sie ist aber offiziell kein Teil des LaTeX-Funktionsumfangs.
* Die `fleqn` Optionen zum linksbündigen Positionieren von Formeln funktioniert nicht mehr
* Es kann "Problem" mit vertikalen Abständen geben

Hinweis: Nutzt man `\[ \]`, dann wird das Laden von `amsmath` empfohlen: `\usepackage{amsmath}`.

## Formeln mit Nummern

Nummerierte Formeln setzt man mittels `equation`-Umgebung:

**code/document-14.tex**

```latex
\documentclass[12pt,ngerman]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

Eine abgesetzte Formeln mit Nummer:

\begin{equation}
a^2 + b^2 = c^2 \label{eq:Pythagoras}
\end{equation}

Siehe Gleichung \ref{eq:Pythagoras} auf Seite \pageref{eq:Pythagoras}.

\end{document}
```

![document-14.png](https://github.com/UweZiegenhagen/LaTeXEinsteigerKurs/blob/master/code/document-14.png)

Hinweis: Unter https://tex.stackexchange.com/questions/173102/table-of-equations-like-list-of-figures findet man Tipps dazu, wie man analog zu den Inhaltverzeichnissen für Bilder und Tabellen auch für Formeln ein Inhaltsverzeichnis erstellen kann.

## Weitere Beispiele für Formeln

**code/document-15.tex**

```latex
\documentclass[12pt,ngerman]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

$a_23 \not= a_{23}$

\[\sum_{i=1}^{\infty} i = n \]

\[ \sqrt[3]{a+b} \]

\[x_{1/2} = -\frac{p}{2} \pm  
\sqrt{ 
   \left( 
        \frac{p}{2}
   \right)^2 - q } \]
   
   
\[ \overbrace{a^2 + b^2} 
= \underbrace{c^2 }\]


\begin{eqnarray}
 y & = & d\\
 y & = & c_x+d\\
 y & = & b_x^{2}+c_x+d\\
 y & = & a_x^{3}+b_x^{2}
\end{eqnarray}


\[
\begin{array}{lcr}
 y & = & d\\
 y_{a}& = & c_x+d\\
 y & = & b_x^{2}+c_x+d\\
 y & = & a_x^{3}+b_x^{2}
\end{array}\]


\[
\bordermatrix{%
 & 0 & 1 & 2 \cr
 0 & A & B & C \cr
 1 & d & e & f \cr
 2 & 1 & 2 & 3 \cr
}
\]

\end{document}
```

![document-15.png](https://github.com/UweZiegenhagen/LaTeXEinsteigerKurs/blob/master/code/document-15.png)

Eine gute Übersicht über den Satz von Formeln aller Art findet man im Buch von Herbert Voß: https://www.lehmanns.de/shop/mathematik-informatik/23095957-9783865414854-mathematiksatz-mit-latex


Weiter geht es im [nächsten Kapitel](Kapitel8.md) mit 