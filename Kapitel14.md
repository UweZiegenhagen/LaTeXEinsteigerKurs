[Letztes Kapitel](Kapitel13.md)

# Von ``pdflatex`` zu ``lualatex``

* Neben ``pdflatex`` gibt es noch andere LaTeX-Engines, beispielsweise ``xelatex`` und ``lualatex``
* Sowohl ``xelatex`` als auch ``lualatex`` unterstützen OpenType-Schriften des Systems
* ``lualatex`` wird aktiv entwickelt, daher soll der Fokus dieses Abschnitts darauf liegen


## Was muss ich anpassen, wenn ich ``lualatex`` nutzen will

Schauen wir uns das folgende pdflatex-Dokument an:

```latex
\documentclass[12pt,ngerman]{scrartcl}

\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage{babel}

\begin{document}

Hallo Welt

\end{document}
```

Um daraus jetzt ein Dokument für ``lualatex`` zu machen, löschen wir die Zeilen für ``inputenc``  und ``fontenc`` und fügen eine Zeile für ``fontspec`` hinzu, das unter ``lualatex`` die Behandlung von Schriften übernimmt. ``inputenc`` wird nicht mehr benötigt, weil ``lualatex`` davon ausgeht, dass die Eingabedatei eh im UTF8-Encoding ist, ``fontenc`` wird intern von ``fontspec`` genutzt und muss daher nicht separat geladen werden. 

```latex
\documentclass[12pt,ngerman]{scrartcl}

\usepackage{fontspec}
\usepackage{babel}

\begin{document}

Hallo Welt

\end{document}
```

Hinweis: ``fontspec`` nutzt die Erweiterung der Computer Modern, Latin Modern Roman, während ``fontenc`` standardmäßig die Computer Modern nutzt. Möchte man ein Dokument haben, das sowohl unter ``pdflatex`` als auch ``lualatex`` gleich aussieht, dann kann man mittels ``iflualatex`` Paket eine angepasste Präambel erstellen:


```latex
\documentclass[12pt,ngerman]{scrartcl}

\usepackage{ifluatex}

\ifluatex 
    \usepackage{fontspec}
\else
    \usepackage[utf8]{inputenc}
    \usepackage[T1]{fontenc}

\usepackage{babel}

\begin{document}

Hallo Welt

\end{document}
```


Hier nun ein ``lualatex``-Beispiel, das die OpenType Schriften von MS Office nutzt. Diese müssen natürlich installiert sein.

```latex
\documentclass[parskip=half,fontsize=12pt,ngerman]{scrartcl}
 
\usepackage{babel}
\usepackage{fontspec}
\usepackage{blindtext}

\usepackage{unicode-math}
\setsansfont[ItalicFont={Cambria Italic},BoldFont={Cambria Bold},BoldItalicFont={Cambria Bold Italic}]{Cambria}
\setmainfont[ItalicFont={Calibri Italic},BoldFont={Calibri Bold},BoldItalicFont={Calibri Bold Italic}]{Calibri}
\setmonofont[ItalicFont={Consolas Italic},BoldFont={Consolas Bold},BoldItalicFont={Consolas Bold Italic}]{Consolas}
\setmathfont{Cambria Math}

\begin{document}

\section{Einleitung}

\blindtext[3]

\[
- \frac{p}{2} \pm \sqrt{ \left( \frac{p}{2}\right)^2 -q  }
\]

\texttt{Ich bin ein Satz im Mono Font}


\end{document}
```

Weiter geht es im [nächsten Kapitel](Kapitel5.md)
