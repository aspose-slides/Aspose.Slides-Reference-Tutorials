---
"date": "2025-04-22"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python Ringdiagramme in PowerPoint erstellen und anpassen. Dieses Tutorial behandelt das Festlegen der Lochgröße, das Speichern von Präsentationen und bewährte Vorgehensweisen."
"title": "So erstellen Sie ein Ringdiagramm in PowerPoint mit benutzerdefinierter Lochgröße mit Aspose.Slides für Python"
"url": "/de/python-net/charts-graphs/create-doughnut-chart-aspose-python-custom-hole-size/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie ein Ringdiagramm in PowerPoint mit benutzerdefinierter Lochgröße mit Aspose.Slides für Python

## Einführung
Visuell ansprechende Diagramme in PowerPoint machen Ihre Daten ansprechender und verständlicher. Ein häufiges Problem sind fehlende Anpassungsmöglichkeiten bei der programmgesteuerten Erstellung dieser Diagramme. Dieses Tutorial löst dieses Problem, indem es zeigt, wie Sie mit Aspose.Slides für Python ein Ringdiagramm mit benutzerdefinierter Lochgröße erstellen.

**Schlüsselwörter:** Aspose.Slides Python, Donut-Diagramm, benutzerdefinierte Lochgröße

### Was Sie lernen werden:
- Einrichten und Verwenden von Aspose.Slides für Python
- Erstellen eines Ringdiagramms in PowerPoint
- Anpassen der Lochgröße Ihres Ringdiagramms
- Best Practices zum Speichern und Exportieren von Präsentationen

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie über Folgendes verfügen:
- **Python 3.x** auf Ihrem System installiert.
- Grundkenntnisse der Python-Programmierkonzepte.
- Der `aspose.slides` Bibliothek (Installationsanweisungen finden Sie unten).

## Einrichten von Aspose.Slides für Python
Installieren Sie zunächst Aspose.Slides für Python mit pip:

```bash
pip install aspose.slides
```

### Lizenzerwerb
Aspose bietet eine kostenlose Testversion an, mit der Sie die Funktionen ohne Einschränkungen hinsichtlich der Anzahl der Dokumente oder der Nutzungsdauer erkunden können:
- **Kostenlose Testversion:** Beginnen Sie mit einer temporären Lizenz, um alle Funktionen zu testen.
- **Temporäre Lizenz:** Für Evaluierungszwecke verfügbar.
- **Kaufen:** Für eine langfristige Nutzung sollten Sie den Erwerb einer Lizenz in Erwägung ziehen.

Nach der Installation und Einrichtung können Sie mit der programmgesteuerten Erstellung von Präsentationen beginnen. So initialisieren Sie Aspose.Slides:

```python
import aspose.slides as slides

# Initialisieren eines Präsentationsobjekts
class PresentationCreator:
    def create_presentation(self):
        with slides.Presentation() as presentation:
            # Ihr Code kommt hier hin
```

## Implementierungshandbuch
In diesem Abschnitt werden die erforderlichen Schritte zum Erstellen und Anpassen eines Ringdiagramms in PowerPoint mit Aspose.Slides erläutert.

### Schritt 1: Auf eine Folie zugreifen und sie ändern
Rufen Sie zunächst die erste Folie Ihrer Präsentation auf. Fügen Sie dort Ihr benutzerdefiniertes Ringdiagramm hinzu.

```python
# Greifen Sie auf die erste Folie zu
class SlideModifier:
    def modify_slide(self, presentation):
        first_slide = presentation.slides[0]
```

### Schritt 2: Hinzufügen eines Ringdiagramms
Sie können jeder Folie ein Ringdiagramm hinzufügen, indem Sie dessen Position und Größe angeben. Hier platzieren wir es an den Koordinaten (50, 50) mit den Abmessungen 400 x 400.

```python
class ChartAdder:
    def add_doughnut_chart(self, first_slide):
        # Hinzufügen eines Ringdiagramms
        chart = first_slide.shapes.add_chart(
            slides.charts.ChartType.DOUGHNUT,
            50, 50, 400, 400
        )
```

### Schritt 3: Anpassen der Lochgröße
Die Lochgröße Ihres Ringdiagramms lässt sich ganz einfach anpassen. Für einen ausgeprägten Effekt stellen Sie sie auf 90 % ein.

```python
class ChartCustomizer:
    def customize_hole_size(self, chart):
        # Benutzerdefinierte Lochgröße festlegen
        chart.chart_data.series_groups[0].doughnut_hole_size = 90
```

### Schritt 4: Speichern Ihrer Präsentation
Speichern Sie Ihre Präsentation abschließend unter dem gewählten Dateinamen am gewünschten Ort.

```python
class PresentationSaver:
    def save_presentation(self, presentation):
        # Speichern der Präsentation
        presentation.save(
            "charts_doughnut_chart_hole_out.pptx",
            slides.export.SaveFormat.PPTX
        )
```

## Praktische Anwendungen
Das Erstellen benutzerdefinierter Ringdiagramme kann in verschiedenen Szenarien nützlich sein, darunter:
- **Geschäftsberichte:** Hervorhebung wichtiger Leistungsindikatoren durch optisch unterscheidbare Segmente.
- **Lehrinhalt:** Veranschaulichen statistischer Daten für Studenten oder Kollegen.
- **Marketingmaterialien:** Präsentation von Produktaufschlüsselungen oder Kundendemografien.

Integrationen mit anderen Systemen sind möglich, indem die Diagramme als Bilder exportiert oder mithilfe der umfassenden API von Aspose in Webanwendungen eingebettet werden.

## Überlegungen zur Leistung
Beachten Sie beim Arbeiten mit Aspose.Slides diese Tipps für eine optimale Leistung:
- Minimieren Sie die Ressourcennutzung, indem Sie nur die erforderlichen Folien laden.
- Verwalten Sie Ihren Speicher effektiv, indem Sie Präsentationen nach der Verwendung umgehend schließen.
- Nutzen Sie die Stapelverarbeitung, um mehrere Diagramme gleichzeitig zu erstellen.

Durch die Einhaltung bewährter Methoden wird sichergestellt, dass Ihre Anwendung reibungslos und effizient läuft.

## Abschluss
In dieser Anleitung erfahren Sie, wie Sie mit Aspose.Slides für Python ein Ringdiagramm mit benutzerdefinierter Lochgröße in PowerPoint erstellen. Dies verbessert nicht nur die visuelle Attraktivität Ihrer Präsentationen, sondern ermöglicht auch eine flexiblere Datendarstellung.

Um die Möglichkeiten von Aspose.Slides weiter zu erkunden, experimentieren Sie mit anderen Diagrammtypen und Präsentationsfunktionen. Viel Spaß beim Programmieren!

## FAQ-Bereich
1. **Welche maximale Lochgröße kann ich für ein Ringdiagramm festlegen?**
   - Sie können es für ein vollständiges Kreisdiagramm auf bis zu 100 % einstellen.
2. **Kann ich mit Aspose.Slides vorhandene Diagramme in einer PowerPoint-Datei ändern?**
   - Ja, Sie können vorhandene Präsentationen laden und bearbeiten.
3. **Wie gehe ich mit Fehlern beim Speichern von Präsentationen um?**
   - Stellen Sie sicher, dass der Ausgabepfad beschreibbar ist, und prüfen Sie, ob Berechtigungsprobleme vorliegen.
4. **Gibt es Unterstützung für andere Diagrammtypen außer Ringdiagrammen?**
   - Absolut, Aspose.Slides unterstützt eine Vielzahl von Diagrammtypen.
5. **Kann Aspose.Slides mit Webanwendungen verwendet werden?**
   - Ja, die API kann in Backend-Systeme integriert und über Webdienste bereitgestellt werden.

## Ressourcen
- [Dokumentation](https://reference.aspose.com/slides/python-net/)
- [Herunterladen](https://releases.aspose.com/slides/python-net/)
- [Kaufen](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/slides/python-net/)
- [Temporäre Lizenz](https://purchase.aspose.com/temporary-license/)
- [Support-Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}