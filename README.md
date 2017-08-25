# Kapitel 1 des LaTeX - Einsteigerkurses

Jedes Jahr halte ich mindestens einen Einsteigerkurs für LaTeX. In diesem git-Repository sammle ich Beispiele, die mit steigender Komplexität zeigen, wie man am besten mit LaTeX arbeitet. In erster Linie werde ich sie selbst nutzen, bin aber für eine Kooperation offen. Fehlermeldungen und Verbesserungsvorschläge werden gern angenommen.


## Historisches

* TeX wurde seit Ende der 1970er vom Stanford-Professor Donald Knuth entwickelt
* Sein Ziel: "The Art of Computer Programming" qualitativ hochwertig setzen.
* TeX ist recht "sperrig" im Umgang, daher entwickelte Leslie Lamport eine Sammlung von Makros, mit denen man TeX leichter bedienen konnte und nannte diese "LaTeX" (gesprochen "La-Tech" oder "Le-Tech", nicht "Latex")

## Warum sollte ich LaTeX nutzen?

Ich bin da recht pragmatisch. Word hat in den letzten Jahren an Qualität sehr zugelegt, auch LibreOffice/OpenOffice taugen für viele Anwendungszwecke schon was. In diesen Programmen ist es aber recht einfach, etwas zu produzieren, was -- nach typografischen und ästetischen Gesichtspunkten -- schlecht aussieht. LaTeX im Gegensatz dazu macht es dem Nutzer recht schwer, richtig typografischen Mist zu produzieren. 

LaTeX ist auch dazu gemacht, längere Dokumente effizient zu produzieren, wobei ich nicht von Dokumenten mit 20 oder 30 Seiten spreche. Die lassen sich noch mit einem Schreibprogramm erstellen, da lohnt sich der Einarbeitungsaufwand in LaTeX nicht in jedem Fall. Hier geht es eher um Doktorarbeiten, Masterarbeiten oder Bücher. Die Fähigkeiten von LaTeX, Textsatz effizient zu gestalten, helfen einem dort maßgeblich, Zeit zu sparen.


## Bezug

* Heute gibt es noch zwei TeX-Distributionen, die erwähnenswert sind:
	* MikTeX: nur für Windows
	* TeX Live (mit MacTeX): für alle möglichen Betriebssysteme


Persönlich nutze ich TeX Live, da ich damit _ein_ einheitlichen Editor für alle meine Rechner bekomme. Der Fokus dieses Kurses liegt daher auch auf TeX Live.

Man erhält TeX Live:

* kostenlos per Download von [www.tug.org/texlive/acquire-netinstall.html](http://www.tug.org/texlive/acquire-netinstall.html)
* auf DVD im Rahmen der Mitgliedschaft bei Dante e.V., der deutschsprachigen Anwendervereinigung TeX, die viele TeX-Aktivitäten fördert
* auf DVD bei Lehmanns Buchhandlung

Für alles weitere nehmen wir an, dass eine LaTeX-Installation erfolgt ist, alternativ kann man auch bei ShareLaTeX oder Overleaf die Beispiele online ausprobieren.

## Editoren

Unter Windows und Mac OS X enthält TeX Live TeXworks, einen aus meiner Sicht sehr guten Editor. Ich nutze ihn zusammen mit in Autohotkey erstellten Tastatur-Shortcuts, mehr dazu in meinem Blog. Man kann aber jeden anderen Editor nehmen, mit speziellen TeX-Editoren ist man aber schneller und es ist ein wenig komfortabler. Die einzig sinnvolle Bedingung ist aber, dass der Editor UTF-8 Unicode unterstützen sollte, da es sonst insbesondere beim Austausch mit anderen nur zu Problemen führt. Die folgende Liste ist nicht vollständig, die Reihenfolge stellt keine Wertung dar:

* TeXworks
* Kile
* Texmaker
* Emacs mit AucTeX
* VIM mit LaTeX-Suite
* Gummi
* Eclipse mit TeXlipse
* TeXniccenter

## Mein erstes Dokument

Nimm den folgenden Code, speichere ihn in einer Datei mit der Endung .tex und übersetze ihn:

* mit dem entsprechenden Übersetzungsbutton im Editor
* auf der Kommandozeile mit dem Befehl `pdflatex <dateiname>.tex`

```latex
\documentclass[12pt]{article}

\begin{document}

Hallo \LaTeX, ich bin ein \textbf{Text} in fett.

\begin{itemize}
 \item Ich bin
 \item eine 
 \item Aufzaehlung
\end{itemize}
	
\end{document}

```

Achtung: Wenn dieses Dokument beim Übersetzen Fehler produziert, dann ist was faul. Such jemanden, der LaTeX-Erfahrung hat oder frage nett in einem LaTeX-Forum.
 
Jetzt zur Erklärung, was dieses Dokument macht:

* Die `\documentclass` legt fest, was wir eigentlich schreiben wollen. Jede Dokumentenklasse ist letztlich nichts anderes als eine Vorlage. Und da sich ein kurzer Artikel von fünf Seiten und ein 2000-Seiten-Buch voneinander unterscheiden, gibt es da unterschiedliche.
* [12pt] ist ein optionaler Parameter und legt die Höhe der Grundschrift fest, also dem Fließtext. Alle weiteren Größen, von Überschriften bis zu den Fußnoten, wird von dieser Schriftgröße abgeleitet
* Den Teil vor `\begin{document}` nennt man Präambel. Hier kommen alle Definitionen und ähnliches rein, die das Aussehen unseres Dokuments bestimmen.
* Die Kombination aus `\begin{document}` und `\end{document}` ist dabei eine _Umgebung_, den Begriff werden wir öfter hören.
* `\LaTeX` ist ein _Befehl_, auch dieser Begriff wird öfter fallen.
* Befehle können Parameter haben, wie zum Beispiel der `\textbf{}` Befehl, der den Text in geschweiften Klammern fett druckt.
* die folgenden Zeilen definieren eine _itemize_ Umgebung, eine nicht nummerierte Aufzählung mit Bulletpoints.
* `\end{document}` beendet das Dokument. Alles dahinter wird ignoriert.

So, weiter geht es in der [nächsten Datei](Kapitel2.md).