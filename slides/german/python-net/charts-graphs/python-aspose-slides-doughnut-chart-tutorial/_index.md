---
"date": "2025-04-22"
"description": "Erfahren Sie, wie Sie Ringdiagramme mit Python und Aspose.Slides erstellen. Diese Schritt-für-Schritt-Anleitung behandelt Einrichtung, Anpassung und bewährte Methoden zur Verbesserung Ihrer Präsentationen."
"title": "So erstellen Sie Ringdiagramme in Python mit Aspose.Slides – Eine Schritt-für-Schritt-Anleitung"
"url": "/de/python-net/charts-graphs/python-aspose-slides-doughnut-chart-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie Ringdiagramme in Python mit Aspose.Slides: Eine Schritt-für-Schritt-Anleitung

Im Bereich der Datenvisualisierung kann die effektive Darstellung von Informationen das Verständnis und die Entscheidungsfindung erheblich beeinflussen. Ob Sie eine Geschäftspräsentation erstellen oder komplexe Datensätze analysieren, Diagramme sind unverzichtbare Werkzeuge. Ringdiagramme bieten unter den verschiedenen Diagrammtypen eine ansprechende Möglichkeit, proportionale Daten mit einem intuitiven Loch in der Mitte darzustellen. Diese Schritt-für-Schritt-Anleitung führt Sie durch die Erstellung eines Ringdiagramms in Python mit Aspose.Slides – einer leistungsstarken Bibliothek zur Bearbeitung von Präsentationen.

## Was Sie lernen werden
- So richten Sie Aspose.Slides für Python ein und verwenden es
- So fügen Sie Ihren Präsentationsfolien ein Ringdiagramm hinzu
- Anpassen von Reihen und Kategorien im Diagramm
- Anpassen visueller Elemente wie Beschriftungen, Farben und Explosionseffekte
- Best Practices zur Leistungsoptimierung mit Aspose.Slides

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie über Folgendes verfügen:
- **Python-Umgebung**: Python 3.x ist auf Ihrem Computer installiert.
- **Aspose.Slides für Python**: Installieren Sie diese Bibliothek mit pip.
- **Grundlegendes Verständnis der Python-Programmierung**: Kenntnisse im Bereich Schleifen und objektorientierte Programmierung sind hilfreich.

## Einrichten von Aspose.Slides für Python
Installieren Sie zunächst die Aspose.Slides-Bibliothek über Pip:

```bash
pip install aspose.slides
```

### Lizenzerwerb
Aspose bietet eine kostenlose Testversion an, mit der Sie Funktionen für einen begrenzten Zeitraum ohne Einschränkungen testen können. So erhalten Sie diese:
1. Besuchen Sie die [Kostenlose Testversion](https://releases.aspose.com/slides/python-net/) Seite.
2. Befolgen Sie die Anweisungen zum Herunterladen und Anwenden Ihrer temporären Lizenz.

Für die weitere Nutzung sollten Sie den Kauf eines Abonnements von der [Kaufseite](https://purchase.aspose.com/buy).

### Grundlegende Initialisierung
Nachdem Sie Aspose.Slides eingerichtet haben, initialisieren Sie es wie folgt:

```python
import aspose.slides as slides

# Erstellen Sie eine Instanz der Präsentationsklasse.
with slides.Presentation() as pres:
    # Ihr Code zum Bearbeiten von Präsentationen kommt hierhin.

# Speichern Sie die Präsentation, nachdem Sie Änderungen vorgenommen haben.
pres.save("output.pptx", slides.export.SaveFormat.PPTX)
```

## Implementierungshandbuch
Nachdem Sie Aspose.Slides eingerichtet haben, befolgen Sie diese Schritte, um Ihrer Präsentation Folie für Folie ein Ringdiagramm hinzuzufügen.

### Erstellen einer neuen Präsentation und Hinzufügen einer Folie
Beginnen Sie mit der Erstellung einer Instanz des `Presentation` Klasse:

```python
import aspose.slides as slides

with slides.Presentation() as pres:
    # Greifen Sie in diesem Kontext auf Folien zu oder erstellen Sie diese.
```

### Hinzufügen eines Ringdiagramms zur ersten Folie
Rufen Sie die erste Folie auf und verwenden Sie die `add_chart` Methode. Geben Sie den Diagrammtyp als `DOUGHNUT`, zusammen mit Position und Größe:

```python
slide = pres.slides[0]
chart = slide.shapes.add_chart(slides.charts.ChartType.DOUGHNUT, 10, 10, 500, 500, False)
```

### Konfigurieren von Diagrammdaten
Löschen Sie vorhandene Daten und konfigurieren Sie Einstellungen wie das Ausblenden der Legende:

```python
workbook = chart.chart_data.chart_data_workbook
chart.chart_data.series.clear()
chart.chart_data.categories.clear()
chart.has_legend = False
```

### Hinzufügen von Serien und Kategorien
Fügen Sie mehrere Reihen und Kategorien für ein Ringdiagramm hinzu. So erstellen Sie 15 Reihen mit spezifischen Eigenschaften:

```python
series_index = 0
while series_index < 15:
    series = chart.chart_data.series.add(
        workbook.get_cell(0, 0, series_index + 1, f"SERIES {series_index}"),
        chart.type
    )
    series.explosion = 0
    series.parent_series_group.doughnut_hole_size = 20
    series.parent_series_group.first_slice_angle = 351
    series_index += 1
```

Fügen Sie Kategorien auf ähnliche Weise hinzu:

```python
category_index = 0
while category_index < 15:
    chart.chart_data.categories.add(
        workbook.get_cell(0, category_index + 1, 0, f"CATEGORY {category_index}")
    )
    # Fügen Sie für jede Reihe Datenpunkte hinzu.
    i = 0
    while i < len(chart.chart_data.series):
        i_cs = chart.chart_data.series[i]
        data_point = i_cs.data_points.add_data_point_for_doughnut_series(
            workbook.get_cell(0, category_index + 1, i + 1, 1)
        )
        
        # Passen Sie das Erscheinungsbild jedes Datenpunkts an.
        data_point.format.fill.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.fill_type = slides.FillType.SOLID
        data_point.format.line.fill_format.solid_fill_color.color = drawing.Color.white
        data_point.format.line.width = 1
        
        # Konfigurieren Sie die Etiketteneinstellungen für die letzte Serie.
        if i == len(chart.chart_data.series) - 1:
            lbl = data_point.label
            lbl.text_format.text_block_format.autofit_type = slides.TextAutofitType.SHAPE
            lbl.data_label_format.text_format.portion_format.font_bold = slides.NullableBool.TRUE
            lbl.data_label_format.text_format.portion_format.latin_font = slides.FontData("DINPro-Bold")
            lbl.data_label_format.text_format.portion_format.font_height = 12
            lbl.data_label_format.show_value = False
            lbl.data_label_format.show_category_name = True
        
        i += 1
    category_index += 1
```

### Speichern der Präsentation
Speichern Sie Ihre Präsentation abschließend in einem angegebenen Verzeichnis:

```python
pres.save("YOUR_OUTPUT_DIRECTORY/chart_add_doughnut_callout_out.pptx", slides.export.SaveFormat.PPTX)
```

## Praktische Anwendungen
Ringdiagramme sind vielseitig und können in verschiedenen Szenarien verwendet werden, beispielsweise:
1. **Budgetzuweisung**: Anzeige, wie verschiedene Abteilungen ihre zugewiesenen Mittel verwenden.
2. **Marktanteilsanalyse**: Vergleich der Marktanteile konkurrierender Produkte oder Unternehmen.
3. **Umfrageergebnisse**: Visualisieren von Antworten auf Umfragefragen zu Präferenzen oder Zufriedenheitsgraden.

## Überlegungen zur Leistung
So gewährleisten Sie eine optimale Leistung bei der Verwendung von Aspose.Slides:
- Minimieren Sie die Speichernutzung, indem Sie Objekte nach der Verwendung ordnungsgemäß entsorgen.
- Laden Sie Präsentationen nur bei Bedarf in den Speicher und schließen Sie sie so schnell wie möglich.
- Wenn Sie mit einer großen Anzahl von Diagrammen arbeiten, sollten Sie die Stapelverarbeitung von Folien in Betracht ziehen.

## Abschluss
In dieser Anleitung haben Sie gelernt, wie Sie mit Aspose.Slides für Python dynamische Ringdiagramme erstellen. Diese Visualisierungen verbessern Ihre Präsentationen, indem sie Daten verständlicher und ansprechender gestalten. Entdecken Sie die Funktionen der Bibliothek, um Ihre Diagramme weiter anzupassen und zu optimieren.

## FAQ-Bereich
1. **Kann ich Aspose.Slides verwenden, ohne eine Lizenz zu erwerben?**
   - Ja, Sie können zu Evaluierungszwecken mit einer kostenlosen Testlizenz beginnen.
2. **Wie ändere ich die Diagrammfarben in Aspose.Slides?**
   - Verwenden Sie die `fill_format` -Eigenschaft, um die gewünschte Farbe für Ihre Diagrammelemente festzulegen.
3. **Ist es möglich, Diagramme als Bilder zu exportieren?**
   - Ja, Sie können Folien mit Diagrammen mithilfe der Rendering-Funktionen der Bibliothek in Bildformate rendern.
4. **Welche Probleme treten häufig beim Hinzufügen von Diagrammen auf?**
   - Stellen Sie sicher, dass alle Datenpunkte und Kategorien ordnungsgemäß hinzugefügt wurden, bevor Sie versuchen, Ihr Diagramm zu speichern oder anzuzeigen.
5. **Kann ich Aspose.Slides in andere Python-Bibliotheken integrieren?**
   - Absolut! Sie können es zusammen mit Bibliotheken wie Pandas verwenden, um erweiterte Datenmanipulationsmöglichkeiten zu erhalten.

## Ressourcen
- [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/python-net/)
- [Laden Sie Aspose.Slides herunter](https://releases.aspose.com/slides/python-net/)
- [Erwerben Sie eine Lizenz](https://purchase.aspose.com/buy)
- [Kostenlose Testversion und temporäre Lizenz](https://releases.aspose.com/slides/python-net/)
- [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}