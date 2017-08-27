[Letztes Kapitel](Kapitel3.md)

# Kapitel 4: Aufzählungen und Textauszeichnung

## Aufzählungen

Schauen wir uns in diesem Kapitel einmal an, wie man verschiedene Aufzählungen setzt.

Das folgende Beispiel zeigt, wie man die Standard-Aufzählungen in LaTeX nutzen kann. Man kann die Umgebungen auch verschachteln, siehe dazu das darauffolgende Beispiel

**dateiname.tex**

```latex
\documentclass[12pt]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

\begin{itemize}
	\item Ich bin
	\item eine einfache
	\item Aufzählung
\end{itemize}

\begin{enumerate}
	\item Ich bin
	\item eine nummerierte
	\item Aufzählung
\end{enumerate}

\begin{description}
\item[Rosen] sind Blumen
\item[Affen] sind Tiere
\item[Mars] ist ein Planet
\end{description}

\end{document}
```

**dateiname.tex**

```latex
\documentclass[12pt]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

\begin{itemize}
	\item Ich bin
	\begin{itemize}
		\item Ich bin
		\item eine einfache
		\item Aufzählung
    \end{itemize}

	\item eine einfache
	\begin{itemize}
		\item Ich bin
		\item eine einfache
		\item Aufzählung
	\end{itemize}	

	\item Aufzählung
	\begin{itemize}
		\item Ich bin
		\item eine einfache
		\item Aufzählung
	\end{itemize}

\end{itemize}

\end{document}
```

## Textauszeichnung


```latex
\documentclass[12pt]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

Dies ist ein \textbf{fettgedrucktes} Wort.

Dies ist ein \textit{kursives} Wort.

Dies ist ein \textsl{geneigtes} Wort, also eine falsche Kursive.

Dies ist ein \textbf{\textit{fett-kursives}} Wort.

\end{description}

\end{document}
```

Für Unterstreichungen gilt: sie sind böse und sollten nicht genutzt werden, schon gar nicht im Zusammenhang mit Überschriften! Mehr dazu unter [http://www.typovia.at/index.php/typografie/grundlagen/goldene-regel-der-typografie](http://www.typovia.at/index.php/typografie/grundlagen/goldene-regel-der-typografie)


Weiter geht es im [nächsten Kapitel](Kapitel5.md) mit dem Einbinden von Bildern.