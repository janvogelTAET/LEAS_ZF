# LEAS Zusammenfassung (HS25) – LaTeX-Quelle

## Bauen
- **`LEAS_ZF.code-workspace` mit VS Code öffnen** (Doppelklick oder *Datei → Arbeitsbereich aus Datei öffnen*).
  Darin sind alle LaTeX-Workshop-Einstellungen: Auto-Build beim Speichern, 2× pdflatex, PDF im VS-Code-Tab.
  VS Code fragt beim ersten Öffnen, ob du dem Ordner vertraust → *Ja*. Fehlt LaTeX Workshop, schlägt VS Code die Installation vor.
- Jede Datei in `sections/` hat `% !TEX root = ../main.tex`, Speichern in einem Kapitel baut also immer das ganze Dokument.
- VS Code + Extension **LaTeX Workshop** + eine TeX-Distribution (MiKTeX oder TeX Live).
- `main.tex` öffnen und speichern → baut automatisch (2× pdflatex). PDF anzeigen: `Ctrl+Alt+V`.
- Ohne VS Code: `pdflatex main.tex` zweimal ausführen.

## Struktur
| Datei | Inhalt |
|---|---|
| `main.tex` | Layout (A4 quer, 3 Spalten), Farben, Kopf/Fuss, eigene Befehle, Titel + Inhaltsverzeichnis |
| `sections/01_grundlagen.tex` … `08_regelung.tex` | ein Kapitel pro Datei |
| `figures/` | alle Bilder (PNG) |

## Eigene Befehle (in `main.tex` definiert)
- `\begin{symtab} Symbol & Bezeichnung & [Einheit] \\ \end{symtab}` – Symboltabelle
- `\fig[0.6]{name}` – Bild aus `figures/`, Breite als Anteil der Spaltenbreite
- `\begin{achtung} ... \end{achtung}` – rote Hinweisbox
- `\ul{x}` – unterstrichen (komplexe Grösse)
- Formeln: `\begin{gather*} ... \end{gather*}` (zentriert, eine Formel pro Zeile)

## Spalten- und Seitenumbrüche
Die Umbrüche sind mit `\columnbreak` gesetzt, damit das Layout wie im Original aussieht.
Wenn du Inhalt ergänzt und eine Spalte überläuft, rutscht alles eine Spalte weiter:
dann ein `\columnbreak` entfernen oder verschieben.

## Zu prüfen (aus dem Original übernommen, mit `% TODO prüfen` markiert)
- 3.4.1: `I_1 = 1/(ü·I_2)` – korrekt wäre `I_1 = I_2/ü`
- 3.4.5: Kippmoment `M_k` – im Nenner fehlt die Wurzel `sqrt(R_1^2 + (...)^2)`
- 3.6.3: `U_E = R_E + I_E + ...` – gemeint ist `R_E · I_E`
- 3.8: `sin(s·θ)` – üblich ist `sin(2θ)`
- 4.2.1: `u_2` mit `φ_σ1` – sekundär wohl `φ_σ2`
- 5.4.3: `M · 4/π = ...` – laut Skript `M · π/4 = ...`
