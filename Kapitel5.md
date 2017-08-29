[Letztes Kapitel](Kapitel4.md)

# Kapitel 5: Bilder einbinden

## Allgemeines

* Zum Einbinden von externen Bilder nutz man das Paket `graphicx`
* Das Paket `graphics` ist veraltet und sollte nicht mehr genutzt werden
* Es sollte nur `graphicx` geladen werden, das zusätzliche Laden von `graphics` bringt nix
* Die drei erwähnten LaTeX-Engines können mit den folgenden Bildformaten umgehen: PNG, JPG und PDF. Mehr geht nur über zusätzliche Pakete oder Tricks wie der On-the-fly-Umwandlung. 

## Mein erstes Bild

Annahme: Im selben Verzeichnis wie die LaTeX-Datei liegt auch das Bild `hallowelt.jpg`.

```latex
\documentclass[12pt]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\usepackage{graphicx}


\begin{document}

\includegraphics{hallowelt.jpg}

\end{document}
```

## Maße anpassen

Der  `\includegraphics` Befehl hat diverse Optionen zur Transformation der Bilder. Ich nutze persönlich nur die `width`-Option, um die Breite des Bildes anzupassen. Dies kann in absoluten Maßen geschehen oder relativ wie der halben Textbreite. Eine zusätzliche Höhe muss nicht angegeben werden, LaTeX skaliert diese entsprechend des Seitenverhältnisses. Im folgenden Beispiel sind beide Versionen gezeigt, gleichzeitig werden beide Bilder zentriert.

```latex
\documentclass[12pt]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\usepackage{graphicx}


\begin{document}

\begin{center}
\includegraphics[width=4cm]{dateiname.jpg}
\end{center}


\begin{center}
\includegraphics[width=0.5\textwidth]{dateiname.jpg}
\end{center}

\end{document}
```

## Bilder für das Abbildungsverzeichnis

LaTeX nutzt bei Bildern und Tabellen, die in den jeweiligen Verzeichnissen auftauchen sollen, standardmäßig sogenannte _Gleitumgebungen_.

Das bedeutet, dass LaTeX selbst entscheidet, ob auch der Seite mit dem entsprechenden Befehl genug Platz ist oder nicht.

Das klappt üblicherweise ganz gut, jedoch nicht perfekt. Aus diesem Grund kann man der entsprechenden Gleitumgebung noch die Option mitgeben:

* **t** (top), oben auf der Seite
* **b** (bottom), unten auf der Seite
* **h** (here), an der Stelle des Befehls

Wenn LaTeX aber meint, dass an dieser Stelle es nicht passt, dann werden diese Optionen unter Umständen ignoriert. Grundsätzlich ist es aber so, dass eh auf **alle** Grafiken und Tabellen im Text Bezug genommen werden muss, daher kann man damit eigentlich ganz gut leben.

Als nächstes ein vollständiges Beispiel. Der  `label`-Befehl setzt einen Anker an das Bild, auf dieses kann dann mittels `\ref{fig:hallo}` verwiesen werden. Auch hier braucht LaTeX zwei Compiler-Läufe, um a) die Referenzen und b) Einträge im Abbildungsverzeichnis korrekt zu setzen.

```latex
\documentclass[12pt]{scrartcl}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\usepackage{graphicx}

\begin{document}

\listoffigures

\begin{center}
\begin{figure}
\includegraphics[width=4cm]{dateiname.jpg}
\caption{Hallo, ich bin ein Bild}\label{fig:hallo}
\end{figure}
\end{center}

Siehe Abbildung \ref{fig:hallo} auf Seite \pageref{fig:hallo}.

\end{document}
```

## Nicht-gleitende Bilder im Abbildungsverzeichnis

Es gibt einen Trick, um Abbildungen, die nicht gleiten, in das Inhaltsverzeichnis zu bekommen. Dieser besteht darin, den Befehl `\captionof` zu nutzen, der die Gleitumgebung umgeht. 

Hinweis: bei Verwendung einer KOMA-Script-Klasse (was ich jedem nur empfehlen kann) oder des `caption` Pakets wird das Paket `capt-of` nicht benötigt, da diese die Anweisung `\captionof` bereits intern selbst zur Verfügung stellen. 



Weiter geht es im [nächsten Kapitel](Kapitel6.md) mit dem Satz von Tabellen. 
