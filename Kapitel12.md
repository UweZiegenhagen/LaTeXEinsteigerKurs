[Letztes Kapitel](Kapitel11.md)

# Einheiten setzen mit ``siunitx``

## Allgemeines

* Für die Formatierung von physikalischen Einheiten gibt es genaue Vorgaben, Einheiten werden beispielsweise aufrecht gesetzt.
* Eine Darstellung einer physikalischen Größe in LaTeX beispielsweise als \(10 \frac{m}{s^2}\) ist daher falsch.
* Es gibt mit ``siunitx`` ein exzellentes LaTeX-Paket, das die Formatierung übernimmt. 
* Die Dokumentation ist sehr gut und leicht mittels ``texdoc siunitx`` aufrufbar, daher an dieser Stelle nur die wesentlichen Befehle.
* Hinweis: Komma , und Punkt . werden vom siunitx-Paket als Dezimaltrenner gleich behandelt.


## Winkel 

Für Winkel bietet das Paket den ``\ang{}`` Befehl.

```latex
\documentclass[12pt,ngerman]{scrartcl}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{siunitx}

\begin{document}

\ang{10.456}

\ang{10,456}


\end{document}
```

## Zahlen


Zahlen werden mit dem ``\num{}`` Befehl ausgezeichnet.

```latex
\documentclass[12pt,ngerman]{scrartcl}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{siunitx}

\begin{document}

\num{10,456}

\num{10.456}

\num{3.1415927e23}

\end{document}
```
## Einheiten ohne Zahlen


Einheiten ohne Zahlen werden mit dem ``\si{}`` Befehl ausgezeichnet.

```latex
\documentclass[12pt,ngerman]{scrartcl}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{siunitx}

\begin{document}

\si{m^2}

\si{kg.m.s^{-1}}

\si{\kilo\gram\metre\per\square\second} 

\si{\gram\per\cubic\centi\metre} 

\si{\square\volt\cubic\lumen\per\farad}

\si{\metre\squared\per\gray\cubic\lux}

\si{\henry\second}

\end{document}
```

## Zahlen mit Einheiten

Für den Satz von Einheiten mit Zahlen gibt es den  ``\SI{}`` Befehl:

```latex
\documentclass[12pt,ngerman]{scrartcl}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{siunitx}

\begin{document}

\SI{3.1415927}{m^2}

\end{document}
```


## Listen von Zahlen und Einheiten

Für den konsistenten Satz von Listen von Zahlen/Einheiten gibt es auch verschiedene Befehle:


```latex
\documentclass[12pt,ngerman]{scrartcl}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{siunitx}

\begin{document}

\numlist{1;2;3;45;6598}

\numrange{1}{10}

\SIlist{1;2;3;45;6598}{m^2}

\SIrange{1}{10}{m^{-2}}



\end{document}
```

## Tabellensatz 

Für den Satz von Tabellen schließlich stellt das ``siunitx`` Paket noch einen speziellen Spaltentyp ``S`` bereit, der die übergebenen Zahlen am Dezimalzeichen ausrichtet.

```latex
\documentclass[12pt,ngerman]{scrartcl}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}
\usepackage{siunitx}
\usepackage{booktabs}

\begin{document}


\begin{table}
\caption{Standardverhalten des \texttt{S} Spaltentyps}
\centering
\begin{tabular}{S}
\toprule
{Some Values} \\
\midrule
2.3456 \\
34.2345 \\
-6.7835 \\
90.473 \\
5642.5 \\
1.2e3 \\
e4 \\
\bottomrule
\end{tabular}
\end{table}


\end{document}
```