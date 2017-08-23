# LaTeX - Einsteigerkurs

Jedes Jahr halte ich mindestens einen Einsteigerkurs für LaTeX. In diesem git-Repository sammle ich Beispiele, die mit steigender Komplexität zeigen, wie man am besten mit LaTeX arbeitet.

# Historisches

* TeX wurde seit Ende der 1970er vom Stanford-Professor Donald Knuth entwickelt
* Sein Ziel: "The Art of Computer Programming" qualitativ hochwertig setzen.
* TeX ist recht "sperrig" im Umgang, daher entwickelte Leslie Lamport eine Sammlung von Makros, mit denen man TeX leichter bedienen konnte und nannte diese "LaTeX" (gesprochen "La-Tech" oder "Le-Tech", nicht "Latex")


# Bezug

* Heute gibt es noch zwei TeX-Distributionen, die erwähnenswert sind:
	* MikTeX: nur für Windows
	* TeX Live (mit MacTeX): für alle möglichen Betriebssysteme


Persönlich nutze ich TeX Live, da ich damit _ein_ einheitliches System für alle meine Rechner bekomme. Der Fokus dieses Kurses liegt daher auch auf TeX Live.

Man erhält TeX Live:

* kostenlos per Download von [www.tug.org/texlive/acquire-netinstall.html](http://www.tug.org/texlive/acquire-netinstall.html)
* auf DVD im Rahmen der Mitgliedschaft bei Dante e.V., der deutschsprachigen Anwendervereinigung TeX, die viele TeX-Aktivitäten fördert
* auf DVD bei Lehmanns Buchhandlung

Für alles weitere nehmen wir an, dass eine LaTeX-Installation erfolgt ist, alternativ kann man auch bei ShareLaTeX oder Overleaf die Beispiele online ausprobieren.

# Editoren

Unter Windows und Mac OS X enthält TeX Live TeXworks, einen aus meiner Sicht recht brauchbaren Editor. Man kann aber jeden anderen Editor nehmen, mit speziellen TeX-Editoren ist man aber schneller und es ist ein wenig komfortabler. Die folgende Liste ist nicht vollständig, die Reihenfolge stellt keine Wertung dar:

* TeXworks
* Kile
* Texmaker
* Emacs mit AucTeX
* VIM mit LaTeX-Suite
* Gummi
* Eclipse mit TeXlipse
* TeXniccenter

# Mein erstes Dokument

Nimm den folgenden Code, speicher ihn in einer Datei mit der Endung .tex und übersetze ihn:

* mit dem entsprechenden Übersetzungsbutton im Editor
* auf der Kommandozeile mit dem Befehl `pdflatex <dateiname>.tex`

```
\documentclass{article}

\begin{document}

Hallo \LaTeX, ich bin ein \textbf{Text} in fett.

\begin{itemize}
 \item Ich bin
 \item eine 
 \item Aufzaehlung
\end{itemize}
	
\end{document}

```
 
