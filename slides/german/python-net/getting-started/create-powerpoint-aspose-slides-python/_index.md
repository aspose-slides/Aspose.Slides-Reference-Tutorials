---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie PowerPoint-Präsentationen mit Aspose.Slides für Python automatisieren. Diese Anleitung behandelt die Einrichtung, das Erstellen von Folien, das Hinzufügen von Formen und das mühelose Speichern Ihrer Präsentation."
"title": "Erstellen Sie PowerPoint-Präsentationen mit Aspose.Slides für Python – Eine vollständige Anleitung"
"url": "/de/python-net/getting-started/create-powerpoint-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und speichern Sie eine PowerPoint-Präsentation mit Aspose.Slides für Python

## Einführung

Möchten Sie die Erstellung von PowerPoint-Präsentationen mit Python automatisieren? Egal, ob Sie Berichte, Diashows oder anderes Präsentationsmaterial programmgesteuert erstellen – die Beherrschung dieser Aufgabe kann Ihnen viel Zeit sparen. Dieses Tutorial führt Sie durch die Erstellung einer neuen PowerPoint-Präsentation mit Aspose.Slides für Python, das Hinzufügen einer Autoform (z. B. einer Linie) und das mühelose Speichern.

**Was Sie lernen werden:**
- So richten Sie Ihre Umgebung für die Verwendung von Aspose.Slides ein.
- Der Prozess der Erstellung einer PowerPoint-Präsentation in Python.
- Programmgesteuertes Hinzufügen von Formen zu Folien.
- Präsentationen mühelos speichern.

Lassen Sie uns zunächst die Voraussetzungen durchgehen, damit Sie mit dem Programmieren beginnen können!

## Voraussetzungen

Bevor wir beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

1. **Erforderliche Bibliotheken**: Sie benötigen die `aspose.slides` Bibliothek für dieses Tutorial.
2. **Python-Version**: Python 3.x wird empfohlen (Kompatibilität mit Aspose.Slides sicherstellen).
3. **Umgebungs-Setup**:
   - Installieren Sie Python und richten Sie bei Bedarf eine virtuelle Umgebung ein.

4. **Voraussetzungen**:
   - Grundlegende Kenntnisse der Python-Programmierung.
   - Vertrautheit mit der Dateiverwaltung in Python.

Nachdem Ihr Setup abgeschlossen ist, fahren wir mit der Installation von Aspose.Slides für Python fort.

## Einrichten von Aspose.Slides für Python

### Installation

Sie können Aspose.Slides einfach über Pip installieren:

```bash
pip install aspose.slides
```

### Schritte zum Lizenzerwerb

Aspose.Slides bietet eine kostenlose Testversion, temporäre Lizenzen und Kaufoptionen:
- **Kostenlose Testversion**: Um die Fähigkeiten der Bibliothek ohne Einschränkungen zu testen.
- **Temporäre Lizenz**: Besorgen Sie sich dies zu Evaluierungszwecken auf Ihrem lokalen Computer.
- **Kaufen**: Für den langfristigen gewerblichen Einsatz.

Besuchen [Aspose Kauf](https://purchase.aspose.com/buy) um diese Optionen zu erkunden. Nachdem Sie eine Lizenz erhalten haben, können Sie diese in Ihrem Code einrichten:

```python
import aspose.slides as slides

# Lizenz anwenden (vorausgesetzt, Sie haben die .lic-Datei)
license = slides.License()
license.set_license("path_to_your_licence_file.lic")
```

## Implementierungshandbuch

Lassen Sie uns nun durch die Erstellung und Speicherung einer Präsentation gehen.

### Erstellen einer neuen Präsentation

Der Kern dieses Tutorials besteht darin, zu zeigen, wie Sie mit Python eine PowerPoint-Präsentation von Grund auf erstellen.

#### Überblick

Wir beginnen mit der Initialisierung des `Presentation` Objekt, das unsere Präsentationsdatei darstellt.

```python
import aspose.slides as slides

# Instanziieren Sie ein Präsentationsobjekt, das eine Präsentationsdatei darstellt\mit slides.Presentation() als Präsentation:
    # Holen Sie sich die erste Folie (Standardfolie hinzugefügt von Aspose.Slides)
slide = presentation.slides[0]

    # Fügen Sie der Folie eine Autoform vom Typ Linie hinzu
slide.shapes.add_auto_shape(slides.ShapeType.LINE, 50, 150, 300, 0)

    # Speichern Sie die Präsentation im PPTX-Format
presentation.save("YOUR_OUTPUT_DIRECTORY/create_new_presentation_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}