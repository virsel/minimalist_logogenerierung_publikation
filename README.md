# Minimalistische Logogenerierung Publikation

Dieses Repository enthält den LaTeX-Quellcode für die Publikation "The Minimalist Revolution: Democratizing High-Quality Design with Efficient AI".

## Voraussetzungen

Um an diesem Projekt unter Linux zu arbeiten und die PDF zu generieren, benötigst du eine LaTeX-Distribution.

### Installation (Debian/Ubuntu/Mint)

Die einfachste Möglichkeit ist die Installation von `texlive-full`, um alle Pakete verfügbar zu haben:

```bash
sudo apt update
sudo apt install texlive-full
```

Alternativ reicht oft auch eine Basis-Installation plus notwendige Pakete (empfohlen für weniger Speicherplatzverbrauch):

```bash
sudo apt install texlive-latex-base texlive-latex-extra texlive-science texlive-bibtex-extra biber latexmk
```

### Installation (Fedora/RHEL)

```bash
sudo dnf install texlive-scheme-full
```

## Bearbeiten

Die Hauptdatei ist `thesis_main.tex`. Inhaltliche Änderungen werden in den entsprechenden `.tex` Dateien vorgenommen.

Empfohlene Editoren:
- **VS Code** mit der Extension **LaTeX Workshop**. (Strg+Alt+B zum Bauen)
- **TexMaker** oder **TeXstudio**

## Kompilieren (PDF erzeugen)

### Mit `latexmk` (Empfohlen)

`latexmk` automatisiert den Build-Prozess (pdflatex -> biber -> pdflatex etc.), damit Referenzen und das Inhaltsverzeichnis korrekt sind.

```bash
latexmk -pdf thesis_main.tex
```

Um bei Änderungen automatisch neu zu bauen (Watch-Mode):

```bash
latexmk -pvc -pdf thesis_main.tex
```

### Manuell

Wenn `latexmk` nicht verfügbar ist, führe folgende Befehle nacheinander aus:

```bash
pdflatex thesis_main.tex
biber thesis_main
pdflatex thesis_main.tex
pdflatex thesis_main.tex
```

## Aufräumen

Um temporäre Dateien zu löschen:

```bash
latexmk -c
# oder manuell
rm *.aux *.bbl *.bcf *.blg *.fdb_latexmk *.fls *.log *.out *.run.xml *.synctex.gz
```





