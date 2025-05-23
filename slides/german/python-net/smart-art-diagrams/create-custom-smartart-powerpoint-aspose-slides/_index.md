---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python SmartArt-Grafiken in PowerPoint erstellen und anpassen und Ihre Präsentationen mit dynamischen Organigrammen verbessern."
"title": "So erstellen und passen Sie SmartArt in PowerPoint mit Aspose.Slides für Python an"
"url": "/de/python-net/smart-art-diagrams/create-custom-smartart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und passen Sie SmartArt in PowerPoint mit Aspose.Slides für Python an

## Einführung

Präsentationen sind ein wichtiges Werkzeug für die visuelle Darstellung von Organisationsstrukturen oder Brainstorming-Sitzungen. Mit Aspose.Slides für Python erstellen und individualisieren Sie mühelos SmartArt-Grafiken. Dieses Tutorial führt Sie durch das Hinzufügen einer SmartArt-Grafik mit Organigramm zu Ihren PowerPoint-Folien.

**Was Sie lernen werden:**
- Hinzufügen einer SmartArt-Grafik in PowerPoint mit Aspose.Slides für Python.
- Anpassen des Layouts Ihres SmartArt-Knotens.
- Präsentationen effizient speichern und exportieren.

Beginnen wir mit der Einrichtung Ihrer Umgebung!

## Voraussetzungen

Bevor Sie mit der Erstellung von SmartArt-Grafiken beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

### Erforderliche Bibliotheken
- **Aspose.Slides für Python**: Installieren Sie diese Bibliothek mit pip, falls dies noch nicht geschehen ist.

### Anforderungen für die Umgebungseinrichtung
- Eine funktionierende Python-Installation (3.x empfohlen).
- Grundlegende Kenntnisse der Python-Programmierung.
- Kenntnisse in Microsoft PowerPoint sind hilfreich, aber nicht erforderlich.

## Einrichten von Aspose.Slides für Python

Richten Sie zunächst die Aspose.Slides-Bibliothek in Ihrer Python-Umgebung ein:

**Pip-Installation:**
```bash
pip install aspose.slides
```

### Schritte zum Lizenzerwerb
Aspose bietet verschiedene Lizenzierungsoptionen:
- **Kostenlose Testversion**: Laden Sie eine temporäre Lizenz herunter, um alle Funktionen zu testen.
- **Temporäre Lizenz**: Erhalten Sie eine kostenlose temporäre Lizenz für die kurzfristige Nutzung.
- **Kaufen**: Erwägen Sie den Kauf eines Abonnements für langfristige Projekte.

### Grundlegende Initialisierung und Einrichtung

Initialisieren Sie nach der Installation Ihr Python-Skript mit Aspose.Slides wie folgt:

```python
import aspose.slides as slides

# Initialisieren Sie die Klasse „Präsentation“ mit slides.Presentation() als Präsentation:
    # Ihr Code zum Hinzufügen von SmartArt wird hier eingefügt
```

## Implementierungshandbuch

Lassen Sie uns nun den Vorgang des Hinzufügens und Anpassens von SmartArt in PowerPoint mithilfe von Aspose.Slides für Python aufschlüsseln.

### Hinzufügen einer SmartArt-Grafik

#### Überblick
Erstellen Sie eine neue Folie und fügen Sie ihr eine SmartArt-Grafik im Typ „Organigramm“ hinzu:

```python
import aspose.slides as slides

# Erstellen Sie eine Präsentationsinstanz mit slides.Presentation() als Präsentation:
    # SmartArt mit angegebenen Abmessungen an Position (10, 10) hinzufügen
    smart = presentation.slides[0].shapes.add_smart_art(
        x=10,
        y=10,
        width=400,
        height=300,
        layout_type=slides.smartart.SmartArtLayoutType.ORGANIZATION_CHART
    )
```

#### Parameter und Methodenzweck
- **x, y**: Position der SmartArt-Grafik auf der Folie.
- **Breite, Höhe**: Abmessungen für gute Sichtbarkeit.
- **Layouttyp**: Gibt den Typ des SmartArt-Layouts an, in diesem Fall ein Organigramm.

### Anpassen des Organigramm-Layouts

#### Überblick
Passen Sie den ersten Knoten in unserer SmartArt-Grafik an, indem Sie sein Layout auf LEFT_HANGING setzen:

```python
# Stellen Sie den ersten Knoten auf das linkshängende Layout ein
smart.nodes[0].organization_chart_layout = slides.smartart.OrganizationChartLayoutType.LEFT_HANGING
```

#### Erläuterung der wichtigsten Konfigurationsoptionen
- **OrganizationChartLayoutType**Bestimmt, wie Knoten angezeigt werden, und verbessert so die Lesbarkeit und Ästhetik.

### Speichern der Präsentation

Speichern Sie Ihre Präsentation abschließend in einem angegebenen Verzeichnis:

```python
# Speichern Sie die Präsentation mit SmartArt\presentation.save("IHR_AUSGABEVERZEICHNIS/smart_art_organization_chart_layout_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}