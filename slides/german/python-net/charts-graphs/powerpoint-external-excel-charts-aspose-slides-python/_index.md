---
"date": "2025-04-23"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für Python dynamische Excel-Diagramme in Ihre PowerPoint-Präsentationen integrieren. Erstellen Sie nahtlos datenbasierte Folien für Unternehmen und Bildung."
"title": "Erstellen Sie PowerPoint-Präsentationen mit externen Excel-Diagrammen mit Aspose.Slides für Python"
"url": "/de/python-net/charts-graphs/powerpoint-external-excel-charts-aspose-slides-python/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Erstellen Sie PowerPoint mit externen Excel-Diagrammen mithilfe von Aspose.Slides für Python

## So integrieren Sie Excel-Diagramme in PowerPoint-Präsentationen mit Aspose.Slides für Python

### Einführung
Dynamische Präsentationen sind für Geschäftstreffen, Lehrveranstaltungen und persönliche Projekte unerlässlich. Entwickler stehen häufig vor der Herausforderung, externe Datenquellen wie Excel-Dateien nahtlos in Präsentationen zu integrieren. Dieses Tutorial behandelt dieses Problem und zeigt, wie man **Aspose.Slides für Python** um PowerPoint-Präsentationen mit Diagrammen aus einer externen Arbeitsmappe zu erstellen.

Am Ende dieses Handbuchs werden Sie Folgendes erfahren:
- So kopieren Sie externe Arbeitsmappendateien mit Python
- So erstellen und konfigurieren Sie eine Präsentation in Aspose.Slides
- So richten Sie Diagramme ein, die Daten direkt aus Excel-Arbeitsmappen abrufen

Lassen Sie uns zunächst auf die Voraussetzungen eingehen!

## Voraussetzungen

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
Um diesem Tutorial folgen zu können, benötigen Sie:
- **Python** auf Ihrem Computer installiert (Version 3.6 oder höher)
- Der `shutil` Bibliothek für Dateioperationen (in Python integriert)
- **Aspose.Slides für Python**eine leistungsstarke Bibliothek zum Erstellen und Ändern von PowerPoint-Präsentationen

### Anforderungen für die Umgebungseinrichtung
Stellen Sie sicher, dass Sie die erforderlichen Verzeichnisse eingerichtet haben:
1. Ein Quellverzeichnis, das Ihre Excel-Arbeitsmappe enthält (`charts_external_workbook.xlsx`)
2. Ein Ausgabeverzeichnis, in dem die kopierten Dateien und die erstellte Präsentation gespeichert werden

### Voraussetzungen
Sie sollten über Grundkenntnisse der Python-Programmierung verfügen, einschließlich Dateiverwaltung und Arbeit mit Bibliotheken.

## Einrichten von Aspose.Slides für Python
Um mit Aspose.Slides zu beginnen, müssen Sie es über Pip installieren:
```bash
pip install aspose.slides
```

### Schritte zum Lizenzerwerb
Aspose bietet verschiedene Lizenzoptionen an, von einer kostenlosen Testversion bis hin zu temporären und Volllizenzen. Sie können beginnen, indem Sie eine [kostenlose Testlizenz](https://purchase.aspose.com/temporary-license/) um seine Funktionen zu erkunden.

#### Grundlegende Initialisierung und Einrichtung
Nach der Installation können Sie Aspose.Slides in Ihr Skript importieren:
```python
import aspose.slides as slides
```

Dies schafft die Voraussetzung für die nahtlose Integration externer Datenquellen in Präsentationen.

## Implementierungshandbuch

### Funktion: Externe Arbeitsmappe kopieren
**Überblick:**
Zunächst zeigen wir, wie man eine externe Arbeitsmappendatei aus einem Quellverzeichnis in ein Zielausgabeverzeichnis kopiert, und zwar mit Pythons `shutil` Damit stellen Sie sicher, dass Ihre Präsentation auf die notwendigen Daten zugreifen kann.

#### Schritt 1: Erforderliche Bibliotheken importieren
```python
import shutil
```

#### Schritt 2: Dateipfade definieren und Arbeitsmappe kopieren
```python
external_workbook_file_name = "charts_external_workbook.xlsx"
source_path = "YOUR_DOCUMENT_DIRECTORY/" + external_workbook_file_name
output_path = "YOUR_OUTPUT_DIRECTORY/" + external_workbook_file_name
shutil.copyfile(source_path, output_path)
```
Dieses Snippet kopiert `charts_external_workbook.xlsx` von Ihrem Dokumentverzeichnis in das Ausgabeverzeichnis.

### Funktion: Präsentation erstellen und externe Arbeitsmappe für Diagrammdaten festlegen
**Überblick:**
Als Nächstes erstellen wir eine Präsentation und legen mithilfe von Aspose.Slides eine externe Arbeitsmappe als Datenquelle für ein Diagramm fest. So können Sie Excel-Daten direkt in PowerPoint-Folien visualisieren.

#### Schritt 1: Aspose.Slides importieren
```python
import aspose.slides as slides
```

#### Schritt 2: Funktion zur Präsentationserstellung definieren
```python
def create_presentation_with_external_chart():
    with slides.Presentation() as pres:
        chart = pres.slides[0].shapes.add_chart(
            slides.charts.ChartType.PIE, 50, 50, 400, 600, False)
        
        chart_data = chart.chart_data
        chart_data.set_external_workbook("YOUR_OUTPUT_DIRECTORY/charts_external_workbook.xlsx")
        
        series = chart_data.series.add(chart_data.chart_data_workbook.get_cell(0, "B1"), slides.charts.ChartType.PIE)
        
        # Hinzufügen von Datenpunkten für die Kreisdatenreihe aus externen Arbeitsmappenzellen
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B2"))
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B3"))
        series.data_points.add_data_point_for_pie_series(chart_data.chart_data_workbook.get_cell(0, "B4"))

        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A2"))
        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A3"))
        chart_data.categories.add(chart_data.chart_data_workbook.get_cell(0, "A4"))
        
        pres.save("YOUR_OUTPUT_DIRECTORY/charts_set_external_workbook_out.pptx", slides.export.SaveFormat.PPTX)
```

#### Erläuterung:
- **Erstellen einer Präsentation**Wir beginnen mit dem Öffnen eines neuen Präsentationsobjekts.
- **Diagramm hinzufügen**: Der ersten Folie wird an den angegebenen Koordinaten und mit den angegebenen Abmessungen ein Kreisdiagramm hinzugefügt.
- **Externe Arbeitsmappe festlegen**: Der Arbeitsmappenpfad ist so festgelegt, dass Aspose.Slides weiß, woher die Daten abgerufen werden sollen.
- **Serien und Datenpunkte hinzufügen**: Wir konfigurieren Reihen mit bestimmten Zellen aus der externen Arbeitsmappe und ermöglichen so dynamische Aktualisierungen.

#### Tipps zur Fehlerbehebung:
- Stellen Sie sicher, dass die Dateipfade richtig sind. Andernfalls wird die Fehlermeldung „Datei nicht gefunden“ angezeigt.
- Überprüfen Sie, ob die Zellreferenzen in Ihrer Excel-Datei mit denen in Ihrem Code übereinstimmen, um Probleme mit der Datenausrichtung zu vermeiden.

## Praktische Anwendungen
Hier sind einige praktische Anwendungen zur Integration von Aspose.Slides mit externen Arbeitsmappen:
1. **Finanzberichte**: Aktualisieren Sie Diagramme in vierteljährlichen Präsentationen automatisch auf Grundlage der neuesten Finanztabellen.
2. **Datenbasierte Präsentationen**: Integrieren Sie Echtzeitanalysen nahtlos in Verkaufsgespräche oder Projektaktualisierungen.
3. **Lehrmaterialien**: Lehrer können aktualisierte Leistungsdaten der Schüler verwenden, um personalisierte Berichte zu erstellen.
4. **Automatisierte Berichtssysteme**: Implementieren Sie automatisierte Systeme, die Präsentationen auf der Grundlage neuer Dateneinträge generieren und verteilen.

## Überlegungen zur Leistung
### Leistungsoptimierung
- Verwenden Sie effiziente Dateipfade und stellen Sie sicher, dass Ihre Arbeitsmappe nicht zu groß ist, um schnellere Zugriffszeiten zu gewährleisten.
- Begrenzen Sie die Anzahl der Folien mit externen Datenquellen, um die Verarbeitungszeit zu verkürzen.

### Richtlinien zur Ressourcennutzung
- Überwachen Sie regelmäßig die Speichernutzung, insbesondere wenn Sie mit großen Datensätzen oder mehreren Präsentationen gleichzeitig arbeiten.

### Best Practices für die Speicherverwaltung
- Entsorgen Sie Objekte ordnungsgemäß mithilfe von Kontextmanagern (`with` Anweisungen), um Ressourcen nach der Verwendung umgehend freizugeben.

## Abschluss
Durch die Integration von Aspose.Slides für Python in Ihren Workflow erstellen Sie mühelos dynamische und datenbasierte PowerPoint-Präsentationen. Dieses Tutorial behandelt die Grundlagen des Kopierens externer Arbeitsmappen und der Konfiguration von Diagrammen mit Live-Datenquellen. Um Ihre Kenntnisse weiter zu vertiefen, können Sie zusätzliche Funktionen von Aspose.Slides erkunden, wie z. B. Folienübergänge und Animationseffekte.

Bereit, einen Schritt weiterzugehen? Versuchen Sie, diese Techniken in Ihrem nächsten Projekt umzusetzen!

## FAQ-Bereich
1. **Wie installiere ich Aspose.Slides für Python?**
   - Verwenden Sie den Pip-Befehl: `pip install aspose.slides`.
2. **Kann ich Aspose.Slides mit anderen Datenquellen außer Excel verwenden?**
   - Ja, Aspose.Slides unterstützt verschiedene Datenformate, dieses Tutorial konzentriert sich jedoch auf Excel-Arbeitsmappen.
3. **Was ist, wenn mein Diagramm in der Präsentation nicht richtig angezeigt wird?**
   - Überprüfen Sie Ihre Zellreferenzen noch einmal und stellen Sie sicher, dass zur Laufzeit auf die externe Arbeitsmappe zugegriffen werden kann.
4. **Wie kann ich eine temporäre Lizenz für Aspose.Slides erhalten?**
   - Besuchen [Lizenzierungsseite von Aspose](https://purchase.aspose.com/temporary-license/) um eine vorläufige Lizenz anzufordern.
5. **Gibt es Einschränkungen bei der Nutzung der kostenlosen Testfunktionen von Aspose.Slides?**
   - Die kostenlose Testversion unterliegt möglicherweise einigen Nutzungseinschränkungen, beispielsweise der Einfügen von Wasserzeichen in exportierte Dateien.

## Ressourcen
- [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/python-net/)
- [Laden Sie Aspose.Slides für Python herunter](https://releases.aspose.com/slides/python-net/)
- [Erwerben Sie eine Lizenz](https://purchase.aspose.com/slides)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}