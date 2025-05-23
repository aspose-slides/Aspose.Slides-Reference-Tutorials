---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie Hyperlinkfarben in PowerPoint-Präsentationen mit Aspose.Slides für Python anpassen. Optimieren Sie Ihre Folien effizient mit personalisierten Linkstilen."
"title": "So legen Sie Hyperlinkfarben in PowerPoint mit Aspose.Slides für Python fest"
"url": "/de/python-net/formatting-styles/aspose-slides-python-hyperlink-colors-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So legen Sie Hyperlinkfarben in PowerPoint mit Aspose.Slides für Python fest

## Einführung

Mit Aspose.Slides für Python können Sie die visuelle Attraktivität Ihrer PowerPoint-Präsentationen durch die Anpassung der Hyperlinkfarben ganz einfach steigern. Diese Anleitung führt Sie durch das Einrichten von Hyperlinks mit bestimmten Farben in Ihren Folien mit Python.

**Was Sie lernen werden:**
- So legen Sie in PowerPoint eine Hyperlinkfarbe innerhalb von Textformen fest.
- Schritte zum Erstellen einer optisch ansprechenden Präsentation.
- Hauptfunktionen von Aspose.Slides für Python, die diese Anpassung erleichtern.

Lassen Sie uns zunächst einen Blick auf die erforderlichen Voraussetzungen werfen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Ihre Umgebung wie folgt bereit ist:
- **Bibliotheken und Versionen:** Installieren `aspose.slides` Bibliothek. Stellen Sie sicher, dass Python auf Ihrem Computer installiert ist.
- **Anforderungen für die Umgebungseinrichtung:** Dieses Tutorial setzt eine grundlegende Einrichtung von Python unter Windows, Mac oder Linux voraus.
- **Erforderliche Kenntnisse:** Kenntnisse in der Python-Programmierung sind von Vorteil.

## Einrichten von Aspose.Slides für Python

Um Aspose.Slides für Python zu verwenden, installieren Sie das Paket über pip:

```bash
pip install aspose.slides
```

**Schritte zum Lizenzerwerb:**
- **Kostenlose Testversion:** Laden Sie eine Testversion herunter von [Asposes Release-Seite](https://releases.aspose.com/slides/python-net/).
- **Temporäre Lizenz:** Fordern Sie eine temporäre Lizenz an auf der [Kaufseite](https://purchase.aspose.com/temporary-license/) für erweiterten Zugriff.
- **Kaufen:** Um alle Funktionen ohne Einschränkungen freizuschalten, sollten Sie eine Lizenz von erwerben [Asposes Kaufseite](https://purchase.aspose.com/buy).

**Grundlegende Initialisierung:**
Nach der Installation und Lizenzierung importieren Sie Aspose.Slides in Ihr Skript:

```python
import aspose.slides as slides
```

## Implementierungshandbuch

Dieser Abschnitt führt Sie durch das Festlegen von Hyperlinkfarben in einer PowerPoint-Präsentation.

### Hyperlink-Farbfunktion festlegen

#### Überblick

Passen Sie die Farbe von in Textformen eingebetteten Hyperlinks mit Aspose.Slides für Python an. Dies verbessert die Lesbarkeit und die visuelle Attraktivität.

##### Schritt 1: Erstellen Sie eine neue Präsentation

Erstellen Sie eine Instanz einer Präsentation:

```python
with slides.Presentation() as presentation:
    # Ihr Code hier
```

##### Schritt 2: Fügen Sie eine Form mit Text hinzu

Fügen Sie der ersten Folie eine rechteckige Form hinzu und fügen Sie Text ein, der einen Hyperlink enthält.

```python
shape1 = presentation.slides[0].shapes.add_auto_shape(
    slides.ShapeType.RECTANGLE, 100, 100, 450, 50, False)

shape1.add_text_frame("This is a sample of colored hyperlink.")
```

##### Schritt 3: Hyperlink-Eigenschaften festlegen

Weisen Sie den Hyperlink zu und legen Sie seine Farbe fest. `hyperlink_click` Die Eigenschaft gibt an, wohin der Link beim Anklicken navigieren soll.

```python
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click = slides.Hyperlink(
    "https://www.aspose.com/")
# Legen Sie die Farbquelle für den Hyperlink auf das Teilformat fest und definieren Sie Fülltyp und Farbe.
shape1.text_frame.paragraphs[0].portions[0].portion_format.hyperlink_click.color_source = slides.HyperlinkColorSource.PORTION_FORMAT
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.fill_type = slides.FillType.SOLID
shape1.text_frame.paragraphs[0].portions[0].portion_format.fill_format.solid_fill_color.color = drawing.Color.red
```

##### Schritt 4: Speichern Sie die Präsentation

Speichern Sie Ihre Präsentation in einem angegebenen Verzeichnis:

```python\presentation.save("YOUR_OUTPUT_DIRECTORY/hyperlink_set_color_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}