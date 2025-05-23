---
"date": "2025-04-22"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python Kreisdiagramme in PowerPoint-Präsentationen erstellen und anpassen und so Ihre Fähigkeiten zur Datenvisualisierung verbessern."
"title": "So erstellen Sie ein Kreisdiagramm in PowerPoint mit Aspose.Slides für Python"
"url": "/de/python-net/charts-graphs/aspose-slides-python-pie-of-pie-chart-powerpoint/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie ein Kreisdiagramm in PowerPoint mit Aspose.Slides für Python

Visuell ansprechende Diagramme wie das Kreisdiagramm können Ihre PowerPoint-Präsentationen deutlich verbessern, indem sie komplexe Informationen verständlicher machen. Dieses Tutorial führt Sie durch die Erstellung eines Kreisdiagramms mit Aspose.Slides für Python.

## Was Sie lernen werden

- Einrichten von Aspose.Slides für Python
- Schritte zum Erstellen einer PowerPoint-Präsentation mit einem Kreisdiagramm
- Konfigurieren von Datenbeschriftungen und Seriengruppenoptionen für eine bessere Lesbarkeit
- Praktische Anwendungen des Kreisdiagramms in Präsentationen

Lassen Sie uns mit der Einrichtung Ihrer Umgebung und der Implementierung dieser Funktionen beginnen.

### Voraussetzungen

Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:

- **Python installiert**: Python 3.6 oder höher wird empfohlen.
- **Aspose.Slides für Python**: Mit pip installieren:
  ```bash
  pip install aspose.slides
  ```
- **Lizenz**: Holen Sie sich eine kostenlose Testlizenz von Aspose, um alle Funktionen ohne Einschränkungen zu erkunden.

#### Voraussetzungen

Grundlegende Kenntnisse in der Python-Programmierung und Kenntnisse in PowerPoint-Präsentationen sind von Vorteil. Wenn Sie damit noch nicht vertraut sind, sollten Sie zunächst die Einführungsmaterialien nutzen.

### Einrichten von Aspose.Slides für Python

Um mit Aspose.Slides für Python zu beginnen, befolgen Sie diese einfachen Schritte:

1. **Installation**: Verwenden Sie pip, um die Bibliothek zu installieren:
   ```bash
   pip install aspose.slides
   ```

2. **Lizenzerwerb**: 
   - Besuchen [Asposes Kaufseite](https://purchase.aspose.com/buy) um eine Lizenz zu erwerben oder eine vorübergehende kostenlose Testversion zu erhalten.
   - Wenden Sie Ihre Lizenz mit dem folgenden Codeausschnitt in Ihrem Projekt an:
     ```python
     import aspose.slides as slides

     # Laden Sie die Lizenzdatei
     license = slides.License()
     license.set_license("path_to_your_license.lic")
     ```

3. **Grundlegende Initialisierung**:
   Beginnen Sie mit dem Importieren von Aspose.Slides und dem Initiieren eines Präsentationsobjekts.

### Implementierungshandbuch

#### Funktion 1: Präsentation mit Diagramm erstellen

Diese Funktion zeigt, wie Sie eine PowerPoint-Präsentation erstellen und der ersten Folie ein Kreisdiagramm hinzufügen.

##### Hinzufügen des Diagramms

Beginnen Sie, indem Sie eine neue Präsentation erstellen und an Position (50, 50) auf der ersten Folie ein Kreisdiagramm hinzufügen:

```python
import aspose.slides as slides

with slides.Presentation() as presentation:
    # Fügen Sie ein Kreisdiagramm mit den angegebenen Abmessungen hinzu
    chart = presentation.slides[0].shapes.add_chart(
        slides.charts.ChartType.PIE_OF_PIE, 50, 50, 500, 400)
```

##### Konfigurieren von Datenbeschriftungen

Um die Lesbarkeit zu verbessern, konfigurieren Sie die Datenbeschriftungen so, dass Werte angezeigt werden:

```python
# Aktivieren Sie die Wertanzeige in Datenbeschriftungen für mehr Übersichtlichkeit
chart.chart_data.series[0].labels.default_data_label_format.show_value = True
```

##### Festlegen von Pie-of-Pie-Optionen

Konfigurieren Sie bestimmte Eigenschaften für das Kreisdiagramm, z. B. die Größe des zweiten Kreises und die Teilungsposition:

```python
# Legen Sie die Größe und Aufteilungseigenschaften des zweiten Kreises fest
chart.chart_data.series[0].parent_series_group.second_pie_size = 149
chart.chart_data.series[0].parent_series_group.pie_split_by = slides.charts.PieSplitType.BY_PERCENTAGE
chart.chart_data.series[0].parent_series_group.pie_split_position = 53
```

##### Speichern der Präsentation

Speichern Sie Ihre Präsentation abschließend in einem gewünschten Verzeichnis:

```python
# Speichern Sie die Präsentation mit dem Diagramm
presentation.save("YOUR_OUTPUT_DIRECTORY/charts_second_plot_options_out.pptx", slides.export.SaveFormat.PPTX)
```

### Praktische Anwendungen

Das Kreisdiagramm ist vielseitig und kann in verschiedenen Szenarien verwendet werden:

1. **Geschäftsberichte**: Visualisieren Sie die Datenverteilung über verschiedene Abteilungen oder Produkte hinweg.
2. **Akademische Projekte**: Präsentieren Sie Umfrageergebnisse, die neben weniger bedeutenden Erkenntnissen auch wichtige Themen zeigen.
3. **Finanzanalyse**Vergleichen Sie in einem Budgetbericht Primärausgaben mit Sekundärkosten.

### Überlegungen zur Leistung

Für optimale Leistung bei der Verwendung von Aspose.Slides:

- Minimieren Sie nach Möglichkeit die Anzahl der Folien und Diagramme, um den Speicherverbrauch zu reduzieren.
- Bereinigen Sie Ihren Code regelmäßig, wenn nicht verwendete Ressourcen oder Referenzen vorhanden sind.
- Verwenden Sie die integrierte Garbage Collection von Python (`gc` Modul), um den Speicher effektiv zu verwalten.

### Abschluss

Sie haben gelernt, wie Sie mit Aspose.Slides für Python eine PowerPoint-Präsentation mit einem Kreisdiagramm erstellen. Diese Fähigkeit kann die visuelle Attraktivität und Effektivität Ihrer Präsentationen deutlich steigern. Entdecken Sie weitere Funktionen von Aspose.Slides, wie z. B. das Hinzufügen von Animationen oder die Integration von Multimedia-Elementen.

### Nächste Schritte

- Experimentieren Sie mit verschiedenen Diagrammtypen, die in Aspose.Slides verfügbar sind.
- Integrieren Sie diese Funktion in einen größeren Workflow zur Präsentationsautomatisierung.

### FAQ-Bereich

**F: Kann ich die Farben des Kreisdiagramms anpassen?**
A: Ja, Sie können die Diagrammfarben anpassen, indem Sie `fill_format` Eigenschaft für jedes Segment.

**F: Wie verarbeite ich große Datensätze mit Aspose.Slides?**
A: Optimieren Sie Ihre Dateneingabe und erwägen Sie, sie in kleinere Teile aufzuteilen, um die Leistung aufrechtzuerhalten.

**F: Gibt es eine Möglichkeit, das Hinzufügen mehrerer Diagramme auf einmal zu automatisieren?**
A: Ja, durchlaufen Sie Ihre Datensätze und verwenden Sie die `add_chart` Methode innerhalb eines einzelnen Präsentationskontexts.

### Ressourcen

- **Dokumentation**: Entdecken Sie detaillierte Anleitungen unter [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/python-net/).
- **Herunterladen**: Holen Sie sich die neueste Version von [Veröffentlichungen](https://releases.aspose.com/slides/python-net/).
- **Kauf und kostenlose Testversion**: Zugriff auf Lizenzoptionen unter [Aspose Kauf](https://purchase.aspose.com/buy) oder versuchen Sie eine [Kostenlose Testversion](https://releases.aspose.com/slides/python-net/).
- **Unterstützung**: Diskutieren Sie mit auf [Aspose Forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}