# Inhaltsverzeichnis

* [Kapitel 1: Einleitung und das erste LaTeX-Dokument](README.md)
* [Kapitel 2: Dokumentenklasse und Auswahl der LaTeX-Engine](Kapitel2.md)
* [Kapitel 3: Gliederungsbefehle und Inhaltsverzeichnis](Kapitel3.md)
* [Kapitel 4: Aufzählungen und Textauszeichnung](Kapitel4.md)
* [Kapitel 5: Bilder einbinden](Kapitel5.md)
* [Kapitel 6: Tabellen setzen](Kapitel6.md)
* [Kapitel 7: Mathematik-Satz](Kapitel7.md)
* [Kapitel 8: Literaturverzeichnisse mit ``biblatex``](Kapitel8.md)
* [Kapitel 9: Präsentationen mit dem ``beamer`` Paket](Kapitel9.md)
* [Kapitel 10: Briefe setzen mit ``scrlttr2``](Kapitel10.md)
* [Kapitel 11:Mit TikZ Zeichnungen in LaTeX erstellen](Kapitel11.md)
* [Kapitel 12: Einheitensatz mit ``siunitx``](Kapitel12.md)
* [Kapitel 13: Längere Dokumente schreiben](Kapitel13.md)
* [Kapitel 14: Von ``pdflatex`` zu ``lualatex``](Kapitel14.md)
* [Kapitel 15: Indizes und Index-Ähnliche Verzeichnisse](Kapitel15.md)
* [Kapitel 16: Mehr zu Tabellen](Kapitel16.md)

# Kapitel 1: Einleitung

Ich halte gelegentlich LaTeX-Kurse für Einsteiger und Fortgeschrittene. In diesem git-Repository sammele ich Materialien für einen mehrtägigen Einführungskurs.

Grundsätzlich nutze ich für den Kurs ``pdflatex``, da es im Vergleich zu ``lualatex`` deutlich schneller ist, in Kapitel 14 gibt es jedoch auch einen kurzen Überblick zu ``lualatex``.

Fehlermeldungen und Verbesserungsvorschläge werden gern angenommen, am besten dafür ein Issue im Bugtracker einstellen. 

## Der Name

Quelle: "A plain TeX Primer" von Malcolm Clark

* TeX ist abgeleitet von "Tau Epsilon Chi", der ersten Silbe des griechischen Wortes "tèkhne" (über das letzte 'e' kommt noch ein Querstrich), die sprachliche Basis für Wörter wie "Technologie" oder "Technik"
* wurde damals in der Bedeutung von "Kunst" oder "Kunstfertigkeit" genutzt
* Aussprache wie "teck" oder "tech" ist richtig, nicht wie in "Latex", dem Baumharz. Donald Knuth selbst hat meines Wissens nach keine Vorgaben zur Aussprache gemacht, die o.g. Aussprachen haben sich aber eingebürgert.

## Historisches

### TeX
* TeX wurde seit Ende der 1970er vom Stanford-Professor Donald Knuth entwickelt
* Knuth ist bekannt für sein Werk "The Art of Computer Programming" zur theoretischen Informatik
* 1973 stand die Neu-Auflage der bisher erschienenen Bände an, die Satz-Industrie wechselte zu dieser Zeit von Bleisatz auf Fotosatz
* Die Ergebnisse des Satzes waren für Knuth nicht gut genug
* Ab dem 5. Mai 1977 begann die Entwicklung von TeX
* Auch Knuth hat nicht auf der grünen Wiese angefangen, damals gab es beispielsweise schon [troff](https://de.wikipedia.org/wiki/Troff) und mit [eqn](https://en.wikipedia.org/wiki/Eqn_(software)) sogar einen Formel-Editor

### LaTeX

* TeX ist recht "kompliziert" im Umgang, Knuth selbst nutzte diverse Makros für seine Bücher 
* Leslie Lamport (heute bei Microsoft Research) entwickelte eine Makro-Sammlung, mit denen man TeX leichter bedienen konnte und nannte diese "LaTeX" (gesprochen "La-Tech" oder "Le-Tech", nicht "Latex"). LaTeX ist der gebräuchlichste Weg, um mit TeX zu interagieren. 

## Warum sollte ich LaTeX nutzen?

Microsoft Word hat in den letzten Jahren qualitativ zugelegt, auch LibreOffice und OpenOffice sind für die meisten Anwendungszwecke sehr gut benutzbar. In diesen Programmen ist es aber immer noch recht einfach, etwas zu produzieren, was -- nach typografischen und damit ästhetischen Gesichtspunkten -- schlecht aussieht und dadurch schlecht lesbar ist. LaTeX im Gegensatz dazu macht es dem Nutzer üblicherweise schwer, richtig typografischen Mist zu produzieren.

LaTeX ist auch perfekt dafür gemacht, längere Dokumente effizient zu produzieren, wobei man sagen kann: "längere Dokumente" bedeutet: mehr als 50 Seiten. Die Fähigkeiten von LaTeX, helfen einem dann maßgeblich, Zeit zu sparen.

Hier einige Beispiele aus Projekten, an denen ich TeXnisch beteiligt war:

* In einem Dissertationsprojekt sollte ein Werkskatalog angefertigt werden, der dann als PDF per DVD beigelegt werden sollte. Im Werkskatalog wurde in der mehrzeiligen Bildunterschrift auf die Seite der Dissertation verlinkt, in der das Werk besprochen wurde. In der Dissertation wiederum wurde auf die Seite im Werkskatalog verwiesen (verlinkt), auf der das Bild abgebildet war. Alles war dynamisch, bei Anpassungen im Dissertationstext bzw. Werkskatalog wurde einfach alles mehrfach neu übersetzt, die Referenzen wurden dann alle automatisch aktualisiert.
* Viele Bilder verwalten: In dem genannten Dissertationsprojekt waren hunderte Bilder inkludiert. Diese manuell in das Dokument einzufügen wäre zeitlich nicht sinnvoll und sehr fehleranfällig gewesen. Also wurden die einzelnen Punkte der Unterschrift in Excel-Spalten nach und nach ergänzt, dann wurde mit Hilfe von Excel-Formeln der `\includegraphics` Befehl für LaTeX zusammengebaut. Alle so erzeugten Befehle wurden dann 1:1 nach LaTeX kopiert.

Ich nehme LaTeX für alle Dokumente, die ordentlich aussehen sollen.

## Wann sollte ich bei meiner herkömmlichen Textverarbeitung bleiben?

Nicht in jedem Fall empfehle ich das Lernen von LaTeX. Insbesondere bei studentischen Abschlussarbeiten, die weder lang noch sonderlich komplex sind, rate ich, bei Word oder LibreOffice zu bleiben. Wenn der Studentin oder die Studentin nicht im akademischen Bereich bleiben will, dann ist es oft besser, nicht mit LaTeX noch eine weitere "Baustelle" aufzumachen.

## Bezug

* Heute gibt es noch zwei TeX-Distributionen, die erwähnenswert sind:  MikTeX und TeX Live. Beide sind für mindestens Windows, Linux und Mac OS X erhältlich.

Persönlich nutze ich TeX Live, da ich damit einheitliche Umgebung für alle meine Rechner bekomme, vom Windows PC bis hin zum Raspberry Pi, außerdem betreue ich auch die deutsche TeX Live Installationsanleitung, da liegt es nahe.

Der Fokus dieses Kurses liegt daher auch auf TeX Live.

Man erhält TeX Live:

* kostenlos per Download von [www.tug.org/texlive/acquire-netinstall.html](https://www.tug.org/texlive/acquire-netinstall.html)
* auf DVD im Rahmen der Mitgliedschaft bei [Dante e.V.](https://www.dante.de), der deutschsprachigen Anwendervereinigung TeX, die viele TeX-Aktivitäten fördert und bei der ich auch schon lange Mitglied bin
* auf DVD bei der Lehmanns Buchhandlung

Für alles weitere nehmen wir an, dass eine lokale LaTeX-Installation erfolgt ist, alternativ kann man auch bei ShareLaTeX oder Overleaf die Beispiele online ausprobieren.

## Editoren

Unter Windows und Mac OS X enthält TeX Live TeXworks, einen aus meiner Sicht sehr guten Editor. Ich nutze ihn zusammen mit in [https://www.autohotkey.com/](Autohotkey) erstellten Tastatur-Shortcuts, mehr dazu in meinem Blog unter [uweziegenhagen.de](https://www.uweziegenhagen.de). Man kann grundsätzlich auch jeden anderen Editor nehmen, mit speziellen TeX-Editoren ist man aber oft ein wenig komfortabler unterwegs.

Die einzig sinnvolle Bedingung ist aber, dass der Editor UTF-8 Unicode unterstützen sollte, da es sonst insbesondere beim Austausch mit Anderen nur zu Problemen führt. Die folgende Liste ist nicht vollständig, die Reihenfolge stellt keine Wertung dar:

* TeXworks
* Kile
* Texmaker
* Emacs mit AucTeX
* VIM mit LaTeX-Suite
* Gummi
* Eclipse mit TeXlipse
* TeXniccenter

## Mein erstes Dokument

Nimm den folgenden Code, speichere ihn in einer Datei mit der Endung ``.tex´´ und übersetze ihn:

* mit dem entsprechenden Übersetzungsbutton im Editor
* auf der Kommandozeile mit dem Befehl `pdflatex <dateiname>.tex`

Wenn TeX Live installiert wurde, der `pdflatex` Befehl aber nicht gefunden wurde, dann muss vermutlich die PATH-Variable noch um den Pfad zur `pdflatex.exe` erweitert werden.  


**code/document-00.tex**

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

![document-00.png](./code/document-00.png)

Achtung: Wenn dieses Dokument beim Übersetzen Fehler produziert, dann ist die Installation fehlerhaft. Such jemanden, der LaTeX-Erfahrung hat oder frage nett in einem LaTeX-Forum.
 
Jetzt zur Erklärung, was dieses Dokument macht:

* Die `\documentclass` legt fest, was wir eigentlich schreiben wollen. Jede Dokumentenklasse ist letztlich nichts anderes als eine Vorlage. Und da sich ein kurzer Artikel von zwei Seiten, eine Präsentation und ein 2000-Seiten-Buch im Aussehen stark voneinander unterscheiden, gibt es unterschiedliche Dokumentenklassen.
* [12pt] ist ein optionaler globaler Parameter und legt die Höhe der Grundschrift fest, also der Schrift, die im Fließtext genutzt wird. Alle weiteren Größen, von Überschriften bis zu den Fußnoten, werden von dieser Schriftgröße abgeleitet. "Global" wird der Parameter genannt, weil er auf der Ebene der Dokumentenklasse definiert wird. Pakete, die wir später laden, können grundsätzlich diese globalen Optionen auswerten.
* Den Teil vor `\begin{document}` nennt man Präambel. Hier kommen alle Definitionen und ähnliches rein, die das Aussehen unseres Dokuments bestimmen.
* Die Kombination aus `\begin{<irgendwas>}` und `\end{<irgendwas>}` ist  eine _Umgebung_, den Begriff werden wir öfter hören.
* `\LaTeX` ist ein _Befehl_, auch dieser Begriff wird öfter fallen.
* Befehle und Umgebungen können Parameter haben, wie zum Beispiel der `\textbf{}` Befehl, der den Text in geschweiften Klammern fett druckt. Pflichtparameter stehen dabei immer in geschweiften Klammern, optionale Parameter in eckigen Klammern.
* die folgenden Zeilen definieren eine _itemize_ Umgebung, eine nicht nummerierte Aufzählung mit Bulletpoints.
* `\end{document}` beendet das Dokument. Alles dahinter wird vom LaTeX-Compiler ignoriert.

So, weiter geht es in der [nächsten Datei](Kapitel2.md) mit Dokumentenklassen und der Auswahl der passenden LaTeX-Engine.
