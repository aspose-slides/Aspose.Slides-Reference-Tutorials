---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie die Erstellung von SmartArt-Grafiken in PowerPoint-Präsentationen mit Aspose.Slides für Python automatisieren, einschließlich des effizienten Extrahierens und Speicherns von Miniaturansichten."
"title": "So erstellen und rufen Sie SmartArt-Miniaturansichten mit Aspose.Slides für Python ab"
"url": "/de/python-net/smart-art-diagrams/aspose-slides-python-smartart-thumbnails/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und rufen Sie SmartArt-Miniaturansichten mit Aspose.Slides für Python ab

## Einführung

Visuell ansprechende Präsentationen sind entscheidend, um die Aufmerksamkeit Ihres Publikums zu fesseln. Eine effektive Möglichkeit, Foliensätze zu verbessern, ist die Einbindung dynamischer Grafiken wie SmartArt in PowerPoint-Präsentationen. Wenn Sie nach einer automatisierten Methode zum Generieren dieser Grafiken und zum Extrahieren von Miniaturansichten suchen, ist diese Anleitung zu „Aspose.Slides Python“ von unschätzbarem Wert.

Mit Aspose.Slides für Python können Sie mühelos SmartArt-Grafiken erstellen, auf bestimmte Knoten innerhalb der Grafik zugreifen, Miniaturansichten dieser Knoten abrufen und diese Bilder für Ihre Projekte speichern. Dieses Tutorial führt Sie detailliert durch jeden Schritt.

**Was Sie lernen werden:**
- So installieren und richten Sie Aspose.Slides für Python ein.
- Erstellen einer SmartArt-Grafik in einer PowerPoint-Präsentation.
- Zugriff auf Knoten innerhalb einer SmartArt-Grafik.
- Extrahieren und Speichern einer Miniaturansicht eines Bilds aus einem bestimmten Knoten.

Lassen Sie uns zunächst auf die Voraussetzungen eingehen.

## Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie Folgendes bereit haben:

- **Erforderliche Bibliotheken:** Sie benötigen Aspose.Slides für Python. Stellen Sie sicher, dass Ihre Umgebung Python 3.x unterstützt.
- **Anforderungen für die Umgebungseinrichtung:** Eine funktionierende Python-Installation und eine geeignete IDE oder ein geeigneter Texteditor wie VSCode oder PyCharm.
- **Erforderliche Kenntnisse:** Grundlegende Kenntnisse der Python-Programmierung, einschließlich Funktionsdefinitionen und Dateioperationen.

## Einrichten von Aspose.Slides für Python

Zunächst müssen Sie die Aspose.Slides-Bibliothek installieren. Dies lässt sich ganz einfach mit pip erledigen:

```bash
pip install aspose.slides
```

Nach der Installation benötigen Sie eine Lizenz, um alle Funktionen uneingeschränkt nutzen zu können. Sie können mit einer kostenlosen Testversion beginnen, eine temporäre Lizenz beantragen oder die Software für die langfristige Nutzung erwerben.

Um Aspose.Slides in Ihrer Python-Umgebung zu initialisieren, importieren Sie die Bibliothek am Anfang Ihres Skripts:

```python
import aspose.slides as slides
```

## Implementierungshandbuch

Lassen Sie uns den Vorgang zum Erstellen und Abrufen einer SmartArt-Miniaturansicht in klare Schritte unterteilen.

### Schritt 1: Erstellen einer neuen Präsentationsinstanz

Erstellen Sie zunächst eine Instanz einer Präsentation. Dies ist der Container, in den Sie Ihre SmartArt-Grafik einfügen.

```python
with slides.Presentation() as pres:
```

Verwenden `with` stellt sicher, dass die Ressourcen ordnungsgemäß verwaltet werden, und speichert und schließt die Datei beim Beenden automatisch.

### Schritt 2: SmartArt zur ersten Folie hinzufügen

Als Nächstes fügen wir unserer ersten Folie eine SmartArt-Grafik hinzu. So geht's:

```python
smart = pres.slides[0].shapes.add_smart_art(10, 10, 400, 300,
    slides.smartart.SmartArtLayoutType.BASIC_CYCLE)
```

Dadurch wird ein grundlegendes Zykluslayout für die SmartArt-Grafik an Position (10, 10) mit den Abmessungen 400 x 300 Pixel hinzugefügt.

### Schritt 3: Zugriff auf den zweiten Knoten

Greifen Sie auf bestimmte Knoten in Ihrem SmartArt zu. In diesem Beispiel greifen wir auf den zweiten Knoten zu:

```python
node = smart.nodes[1]
```

Knoten werden beginnend bei Null indiziert. Daher `nodes[1]` bezieht sich auf den zweiten Knoten in der Liste.

### Schritt 4: Abrufen der Miniaturansicht

So erhalten Sie eine Miniaturansicht der Form innerhalb des ausgewählten Knotens:

```python
image = node.shapes[0].get_image()
```

Dadurch wird das Bild der ersten Form als Miniaturansicht vom angegebenen SmartArt-Knoten abgerufen.

### Schritt 5: Speichern Sie das abgerufene Bild

Speichern Sie dieses Miniaturbild abschließend im JPEG-Format am gewünschten Speicherort:

```python
image.save("YOUR_OUTPUT_DIRECTORY/shapes_create_smartart_thumbnail_out.jpeg\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}