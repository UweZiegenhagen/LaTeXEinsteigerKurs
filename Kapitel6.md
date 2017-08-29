[Letztes Kapitel](Kapitel5.md)

# Kapitel 6: Tabellen

## Allgemeines

* Tabellen können sehr komplex werden, hier nur die Grundlagen
* Von Herbert Voß gibt es ein eigenes Buch zu diesem Thema, das ich -- wie alle Bücher aus Lehmanns Dante-Edition -- empfehlen kann.

## Meine erste Tabelle

* Für Tabellen nutzt man die `tabular` Umgebung
* Es gibt vier grundsätzliche Spaltentypen:
	* **l** für linksbündig
	* **r** für rechtsbündig
	* **c** für zentriert
	* **p{Breite}** für eine Spalte mit _n_ Zentimetern Breite, die automatisch umgebrochen wird
* Zeilen beendet man mit `\\`
* Zellen trennt man voneinander mit `&`
* Vertikale Linien könnte man mit `|` zwischen den Spalten setzen, aber vertikale Linien sind typografisch böse und schlecht, sollten daher nicht eingesetzt werden.


```latex
\documentclass[12pt]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

\begin{tabular}{lrcp{5cm}}
linksbündig & rechtsbündig & zentriert & linksbündig mit automatischem Umbruch \\
links & rechts & zentrierte Spalte & linksbündig mit Umbruch \\
\end{tabular}

\end{document}
```

## Float-Tabellen

Wie bei Bildern kann -- oder sollte man -- LaTeX selbst entscheiden lassen, wo die Tabelle am besten hinpasst. Dazu packt man die `tabular`-Umgebung in eine `table` Umgebung. Dann lässt sich auch der normale `\caption{}` Befehl nutzen, der im Gegensatz zu Bildern überhalb der Tabelle gesetzt wird. 

Wie bei Bildern kann man der entsprechenden Gleitumgebung noch die Option für die vertikale Ausrichtung mitgeben:

* **t** (top), oben auf der Seite
* **b** (bottom), unten auf der Seite
* **h** (here), an der Stelle des Befehls

Hier nun ein vollständiges Beispiel mit `\listoftables`

```latex
\documentclass[12pt]{scrartcl}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}


\begin{document}

\listoftables

\begin{center}
\begin{table}
\caption{Ich bin eine fließende Tabelle}\label{tab:ersteTabelle}
\begin{tabular}{lrcp{5cm}}
linksbündig & rechtsbündig & zentriert & linksbündig mit automatischem Umbruch \\
links & rechts & zentrierte Spalte & linksbündig mit Umbruch \\
\end{tabular}
\end{table}
\end{center}

Siehe Tabelle \ref{tab:ersteTabelle} auf Seite \pageref{tab:ersteTabelle}.

\end{document}
```

## Nicht-gleitende Bilder im Abbildungsverzeichnis

Es gibt einen Trick, um Abbildungen, die nicht gleiten, in das Inhaltsverzeichnis zu bekommen. Dieser besteht darin, den Befehl `\captionof` zu nutzen, der die Gleitumgebung umgeht. 

Hinweis: bei Verwendung einer KOMA-Script-Klasse (was ich jedem nur empfehlen kann) oder des `caption` Pakets wird das Paket `capt-of` nicht benötigt, da diese die Anweisung `\captionof` bereits intern selbst zur Verfügung stellen. 

Weiter geht es im [nächsten Kapitel](Kapitel7.md) mit 
