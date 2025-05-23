---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python beeindruckende Diagramme erstellen und konfigurieren. Folgen Sie dieser Schritt-für-Schritt-Anleitung für eine effektive Datenvisualisierung in Präsentationen."
"title": "Erstellen von Diagrammen in Python mit Aspose.Slides – Ein umfassender Leitfaden"
"url": "/de/python-net/charts-graphs/creating-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen von Diagrammen in Python mit Aspose.Slides: Ein umfassender Leitfaden

## Einführung
Visuell ansprechende Diagramme in Ihren Präsentationen machen Daten leichter verständlich und ermöglichen Ihnen die mühelose Vermittlung komplexer Informationen. Dieses Tutorial führt Sie durch die Erstellung und Konfiguration von Diagrammen mit Aspose.Slides für Python – einer robusten Bibliothek, die die Gestaltung von Präsentationen durch leistungsstarke Funktionen zur Diagrammbearbeitung revolutioniert.

**Was Sie lernen werden:**
- So erstellen Sie ein gestapeltes Säulendiagramm in einer Präsentation
- Hinzufügen und Formatieren von Datenreihen mit benutzerdefinierten Beschriftungen
- Speichern Ihrer konfigurierten Präsentation

Am Ende dieses Tutorials haben Sie praktische Erfahrung mit Aspose.Slides Python gesammelt, um Ihre Präsentationen zu verbessern. Lassen Sie uns mit der Einrichtung Ihrer Umgebung beginnen, bevor wir mit der Erstellung beeindruckender Diagramme beginnen!

## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:

1. **Python-Umgebung:** Sie sollten Python auf Ihrem System installiert haben (Version 3.x empfohlen).
2. **Aspose.Slides für Python:** Dies kann über Pip installiert werden.
3. **Lizenzerwerb:** Obwohl eine kostenlose Testversion verfügbar ist, sollten Sie den Erwerb einer temporären oder Volllizenz in Erwägung ziehen, um alle Funktionen freizuschalten.

## Einrichten von Aspose.Slides für Python
Um Aspose.Slides in Ihren Projekten verwenden zu können, müssen Sie die Bibliothek installieren und wissen, wie Sie Ihre Umgebung einrichten:

**Installation:**
```bash
pip install aspose.slides
```

Nach der Installation können Sie Aspose.Slides initialisieren und verwenden, indem Sie es in Ihr Skript importieren. Um alle Funktionen nutzen zu können, erwerben Sie eine Lizenz. Eine kostenlose Testversion ist verfügbar. Für eine längere Nutzung können Sie eine temporäre Lizenz erwerben oder beantragen.

## Implementierungshandbuch

### Funktion 1: Erstellen und Konfigurieren einer Präsentation mit Diagrammen
**Überblick:** In diesem Abschnitt erfahren Sie, wie Sie mit Aspose.Slides Python eine Präsentationsfolie einrichten und ein Diagramm hinzufügen.

#### Schritt 1: Initialisieren der Präsentation
Erstellen Sie zunächst ein neues Präsentationsobjekt. Verwenden Sie die `with` Anweisung zur automatischen Ressourcenverwaltung:
```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Greifen Sie auf die erste Folie der Präsentation zu
    slide = presentation.slides[0]
```

#### Schritt 2: Fügen Sie der Folie ein Diagramm hinzu
Hier fügen wir an einer bestimmten Position ein gestapeltes Säulendiagramm mit definierten Abmessungen hinzu:
```python
# Hinzufügen eines gestapelten Säulendiagramms zur Folie
chart = slide.shapes.add_chart(slides.charts.ChartType.PERCENTS_STACKED_COLUMN, 20, 20, 500, 400)
```

#### Schritt 3: Diagrammachsen konfigurieren
Richten Sie das Zahlenformat der vertikalen Achse für eine bessere Datendarstellung ein:
```python
# Konfigurieren des Zahlenformats der vertikalen Achse
chart.axes.vertical_axis.is_number_format_linked_to_source = False
chart.axes.vertical_axis.number_format = "0.00%"
```

### Funktion 2: Datenreihen zum Diagramm hinzufügen und formatieren
**Überblick:** In diesem Abschnitt geht es darum, eine Datenreihe hinzuzufügen, sie mit Werten zu füllen und ihr Erscheinungsbild anzupassen.

#### Schritt 1: Definieren der Datenarbeitsmappe
Initialisieren Sie die Datenarbeitsmappe Ihres Diagramms:
```python
default_worksheet_index = 0
workbook = chart.chart_data.chart_data_workbook
```

#### Schritt 2: Datenreihen hinzufügen und füllen
Fügen Sie Ihrem Diagramm eine neue Reihe mit dem Namen „Rot“ hinzu und füllen Sie sie dann mit Datenpunkten:
```python
# Fügen Sie eine neue Reihe hinzu und füllen Sie sie mit Datenpunkten
series = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 1, "Reds"), chart.type)

for i in range(1, 5):
    series.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 1, [0.30, 0.50, 0.80, 0.65][i-1])
    )
```

#### Schritt 3: Formatieren Sie das Erscheinungsbild der Serie
Passen Sie die Füllfarbe und das Datenbeschriftungsformat an:
```python
# Serienfüllung auf Rot einstellen
series.format.fill.fill_type = slides.FillType.SOLID
series.format.fill.solid_fill_color.color = drawing.Color.red

# Konfigurieren von Datenbeschriftungen für die Prozentanzeige
series.labels.default_data_label_format.show_value = True
series.labels.default_data_label_format.number_format = "0.0%"
```

### Funktion 3: Hinzufügen und Formatieren einer zweiten Datenreihe zum Diagramm
**Überblick:** In diesem Abschnitt wird das Hinzufügen einer zweiten Datenreihe mit eigenem Stil erläutert.

#### Schritt 1: Fügen Sie die zweite Serie hinzu
Fügen Sie eine weitere Serie mit dem Namen „Blues“ hinzu:
```python
# Zweite Serie mit dem Namen „Blues“ hinzufügen
series2 = chart.chart_data.series.add(workbook.get_cell(default_worksheet_index, 0, 2, "Blues"), chart.type)
```

#### Schritt 2: Füllen und formatieren Sie die Serie
Füllen Sie es mit Datenpunkten und wenden Sie die Formatierung an:
```python
# Zweite Serie füllen
for i in range(1, 5):
    series2.data_points.add_data_point_for_bar_series(
        workbook.get_cell(default_worksheet_index, i, 2, [0.70, 0.50, 0.20, 0.35][i-1])
    )

# Füllen Sie die Farbe Blau und konfigurieren Sie die Beschriftungen
series2.format.fill.fill_type = slides.FillType.SOLID
series2.format.fill.solid_fill_color.color = drawing.Color.blue

series2.labels.default_data_label_format.show_value = True
```

### Funktion 4: Präsentation auf Festplatte speichern
**Überblick:** Sobald Ihr Diagramm konfiguriert ist, speichern Sie die Präsentation.

#### Schritt 1: Speichern Sie Ihre Arbeit
Verwenden Sie die `save` Methode zum Speichern Ihrer Datei:
```python
# Speichern Sie die Präsentation auf der Festplatte
directory = "YOUR_OUTPUT_DIRECTORY"
presentation.save(f"{directory}/charts_set_data_labels_percentage_sign_out.pptx", slides.export.SaveFormat.PPTX)
```

## Praktische Anwendungen
Mit Aspose.Slides für Python können Sie Präsentationen in verschiedenen Bereichen verbessern:
1. **Geschäftsberichte:** Erstellen Sie detaillierte Quartalsberichte mit dynamischen Diagrammen.
2. **Lehrinhalt:** Entwerfen Sie ansprechende Lehrmaterialien mit visueller Datendarstellung.
3. **Verkaufspräsentationen:** Veranschaulichen Sie Verkaufstrends und Prognosen wirkungsvoll.

Diese Beispiele zeigen, wie Aspose.Slides in bestehende Arbeitsabläufe integriert werden kann, um ausgefeilte Präsentationen zu erstellen.

## Überlegungen zur Leistung
So gewährleisten Sie eine optimale Leistung:
- Verwalten Sie den Speicher effizient, insbesondere bei der Verarbeitung großer Datensätze in Diagrammen.
- Nutzen Sie Best Practices für die Python-Ressourcenverwaltung mit Aspose.Slides.
- Aktualisieren Sie Ihre Bibliothek regelmäßig, um von Leistungsverbesserungen zu profitieren.

Wenn Sie diese Tipps befolgen, können Sie bei der Arbeit mit komplexen Präsentationen einen reibungslosen und effizienten Ablauf gewährleisten.

## Abschluss
In diesem Tutorial haben wir gezeigt, wie Sie Diagramme in Präsentationen mit Aspose.Slides für Python erstellen und konfigurieren. Sie verfügen nun über das Wissen, visuell ansprechende Datenvisualisierungen in Ihre Projekte zu integrieren. Um Ihre Fähigkeiten weiter zu vertiefen, erkunden Sie zusätzliche Funktionen der Bibliothek oder experimentieren Sie mit verschiedenen Diagrammtypen.

**Nächste Schritte:** Versuchen Sie, diese Konzepte in einem realen Projekt umzusetzen, um Ihr Verständnis zu festigen.

## FAQ-Bereich
1. **Wie installiere ich Aspose.Slides für Python?**
   - Verwenden `pip install aspose.slides` um es einfach herunterzuladen und zu installieren.
2. **Kann ich Aspose.Slides verwenden, ohne eine Lizenz zu erwerben?**
   - Ja, Sie können mit einer kostenlosen Testversion beginnen oder eine vorübergehende Lizenz beantragen.
3. **Ist es möglich, die Diagrammdatenbeschriftungen weiter anzupassen?**
   - Absolut! Sie können weitere Formatierungsoptionen erkunden, die die API der Bibliothek bietet.
4. **Welche Probleme treten häufig beim Erstellen von Diagrammen auf?**
   - Stellen Sie sicher, dass alle Datenpunkte richtig formatiert und mit der entsprechenden Reihe verknüpft sind.
5. **Wie integriere ich Aspose.Slides mit anderen Systemen?**
   - Nutzen Sie die umfassende API für eine nahtlose Integration in Ihre vorhandenen Python-Projekte.

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