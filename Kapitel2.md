# Kapitel 2: Unser erstes richtiges Dokument

Nachdem wir in [Kapitel 1](Readme.md) ein erstes kleines Dokument erstellt und hoffentlich sauber übersetzen konnten, schauen wir uns jetzt an, wie man ein Dokument _richtig_ aufsetzt. Mit _richtig_ meine ich damit die Auswahl der passenden TeX-Engine, die Wahl der richtigen Pakete und Einstellungen.

## Die richtige Dokumentenklasse

Im ersten Kapitel hatten wir ein Beispiel gesehen, das die Dokumentenklasse `article` benutzt hat. Diese Klasse, sowie auch `book` und `report` sind für typografische Gewohnheiten im US-amerikanischen bzw. angelsächsischen Raum erstellt worden. Für deutsche bzw. europäische Texte sind sie aus typografischer Sicht nicht geeignet, da gibt es bessere!

Ganz klar zu empfehlen sind die Klassen aus dem KOMA-Script Paket von Markus Kohm. Sie ersetzen die ursprünglichen Klassen perfekt und produzieren wohlfeile Dokumente. Es gilt also:

* Lass article, report und book weg, wenn es keinen spezifischen Grund dafür gibt.
* Vergiss am besten, dass es sie gibt.
* Ersetze:
	* `article` durch `scrartcl`
	* `report` durch  `scrreprt`
	* `book` durch `scrbook`

## Die richtige TeX-Engine

Es gibt mehr als einen Weg, ein TeX-Dokument zu übersetzen. Im ersten Kapitel hatten wir noch `pdflatex` benutzt, es gibt aber Alternativen.

* **pdflatex**: die schnellste Engine, sehr ausgereift. Kann aber nicht mit OpenType-Fonts umgehen, die Integration von Schriften ist sehr komplex und wird keinem Anfänger empfohlen
* **xelatex**: kann mit den Systemschriften umgehen, ist aber m.E. nicht mehr aktiv in der Entwicklung
* **lualatex**: aktiv in der Entwicklung, die langsamste der Engines. Wie xelatex kann luaLaTeX mit Systemfonts im OTF-Format umgehen. Ein Hauptvorteil ist die integrierte Lua-Engine, die vieles in der Arbeit mit dem TeX-Kern leichter macht.

Welche TeX-Engine solltet ihr nehmen? Hängt davon ab, aber mit `pdflatex` macht man als Anfänger nichts falsch. Im folgenden werden wir uns daher auf `pdflatex` konzentrieren. Gegebenenfalls werde ich wichtige Punkte erwähnen, die in xelatex/lualatex anders sind.

## Unser erstes 'richtiges' Dokument

Im folgenden bauen wir Schritt für Schritt ein komplettes Dokument auf: