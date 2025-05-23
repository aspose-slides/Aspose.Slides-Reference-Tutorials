---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python das Erstellen und Formatieren von Rechteckformen in PowerPoint automatisieren. Verbessern Sie mühelos Ihre Präsentationsfähigkeiten."
"title": "Automatisieren Sie rechteckige Formen in PowerPoint mit Aspose.Slides für Python"
"url": "/de/python-net/shapes-text/automate-rectangle-shapes-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und formatieren Sie eine rechteckige Form in PowerPoint mit Aspose.Slides für Python
## Einführung
Mussten Sie Ihren PowerPoint-Präsentationen schon einmal schnell benutzerdefinierte Formen hinzufügen, hatten aber Probleme mit der fehlenden Automatisierung? Wenn Sie es satt haben, Rechtecke Folie für Folie manuell zu formatieren, hilft Ihnen dieses Tutorial weiter. Mit „Aspose.Slides für Python“ automatisieren wir das Hinzufügen und Gestalten einer Rechteckform mit nur wenigen Codezeilen. Am Ende dieses Leitfadens beherrschen Sie:
- Programmgesteuertes Erstellen einer Rechteckform
- Anwenden von Formatierungsoptionen wie Farbe und Linienstil
- Speichern Sie Ihre Präsentation ganz einfach
Lassen Sie uns einen Blick darauf werfen, wie Sie Ihren Folienerstellungsprozess umgestalten können!
### Voraussetzungen
Bevor wir mit der Codierung beginnen, stellen Sie sicher, dass Sie Folgendes bereit haben:
- **Python** auf Ihrem Computer installiert (Version 3.6 oder höher wird empfohlen)
- **Aspose.Slides für Python** Bibliothek, die es uns ermöglicht, PowerPoint-Präsentationen zu bearbeiten
- Grundlegende Kenntnisse der Python-Programmierkonzepte und Vertrautheit mit der Installation von Paketen mithilfe von pip
## Einrichten von Aspose.Slides für Python
### Installation
Um das Aspose.Slides-Paket zu installieren, öffnen Sie Ihr Terminal oder Ihre Eingabeaufforderung und führen Sie Folgendes aus:
```bash
pip install aspose.slides
```
Dieser Befehl ruft die neueste Version von Aspose.Slides für Python von PyPI ab und installiert sie.
### Lizenzerwerb
Aspose.Slides ist ein kommerzielles Produkt, Sie können es jedoch mit einer kostenlosen Testlizenz nutzen. So erhalten Sie eine:
1. **Kostenlose Testversion:** Besuchen [Kostenlose Aspose-Testversion](https://releases.aspose.com/slides/python-net/) und melden Sie sich für eine Bewertung an.
2. **Temporäre Lizenz:** Für umfangreichere Tests ohne Einschränkungen fordern Sie eine temporäre Lizenz an unter [Seite „Temporäre Lizenz“](https://purchase.aspose.com/temporary-license/).
3. **Kaufen:** Wenn Sie bereit sind, live zu gehen, erwerben Sie eine Lizenz über die [Aspose-Kaufseite](https://purchase.aspose.com/buy).
Befolgen Sie nach dem Erwerb die Dokumentation, um Ihre Lizenz in Ihrem Projekt anzuwenden.
### Grundlegende Initialisierung
So können Sie Aspose.Slides für Python initialisieren:
```python
import aspose.slides as slides
\# Präsentationsklasse initialisieren
with slides.Presentation() as pres:
    print("Presentation is ready!")
```
Dieses Snippet richtet eine neue Präsentation ein und bestätigt, dass sie zur Bearbeitung bereit ist.
## Implementierungshandbuch
### Erstellen der Rechteckform
#### Überblick
In diesem Abschnitt konzentrieren wir uns auf das Hinzufügen einer rechteckigen Form zu einer PowerPoint-Folie mithilfe von Aspose.Slides für Python.
#### Schritte zum Erstellen der Form
1. **Öffnen oder erstellen Sie eine Präsentation:**
   ```python
   import aspose.slides as slides
   
   with slides.Presentation() as pres:
       # Wir werden hier unser Rechteck hinzufügen
   ```
2. **Zugriff auf die Folie:**
   Rufen Sie die erste Folie ab, der wir die Form hinzufügen möchten.
   ```python
   slide = pres.slides[0]
   ```
3. **Rechteckige Form hinzufügen:**
   Verwenden Sie die `add_auto_shape` Methode zum Erstellen eines Rechtecks auf der Folie.
   ```python
   shape = slide.shapes.add_auto_shape(slides.ShapeType.RECTANGLE, 50, 150, 150, 50)
   ```
   - Parameter: `ShapeType.RECTANGLE`, x-Position (50), y-Position (150), Breite (150), Höhe (50).
### Formatieren des Rechtecks
#### Überblick
Als Nächstes wenden wir eine Formatierung auf unsere Rechteckform an, einschließlich Füllfarbe und Linienstil.
#### Schritte zum Formatieren
1. **Füllfarbe:**
   Legen Sie für den Hintergrund des Rechtecks eine Volltonfüllung mit einer bestimmten Farbe fest.
   ```python
   shape.fill_format.fill_type = slides.FillType.SOLID
   shape.fill_format.solid_fill_color.color = drawing.Color.chocolate
   ```
2. **Linienstil:**
   Passen Sie die Linie des Rechtecks an, einschließlich Farbe und Breite.
   ```python
   shape.line_format.fill_format.fill_type = slides.FillType.SOLID
   shape.line_format.fill_format.solid_fill_color.color = drawing.Color.black
   shape.line_format.width = 5
   ```
3. **Präsentation speichern:**
   Speichern Sie die Präsentation abschließend in einer Datei.
   ```python
   pres.save("YOUR_OUTPUT_DIRECTORY/shapes_formatted_rectangle_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}