---
"date": "2025-04-23"
"description": "Erfahren Sie anhand detaillierter Schritte und Codebeispiele, wie Sie die Achsenskalen von Diagrammen mit Aspose.Slides in Python anpassen."
"title": "So legen Sie die Achsenskala des Diagramms in Aspose.Slides für Python (Diagramme und Grafiken) auf KEINE fest"
"url": "/de/python-net/charts-graphs/aspose-slides-python-chart-axis-scale-none/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So setzen Sie die Diagrammachsenskala mit Aspose.Slides Python auf KEINE
## Einführung
Für die Erstellung optisch ansprechender Diagramme ist oft eine Feinabstimmung der Achsenskalen erforderlich. Dieses Tutorial zeigt, wie Sie die Haupteinheitsskala der horizontalen Achse auf `NONE` für ein Diagramm mit Aspose.Slides in Python, perfekt zum Anpassen der Datenvisualisierung in Ihren Präsentationen.
**Was Sie lernen werden:**
- Richten Sie Aspose.Slides für Python ein.
- Erstellen und passen Sie Diagramme mit spezifischen Achsenkonfigurationen an.
- Speichern Sie Präsentationen programmgesteuert.
- Beheben Sie häufige Probleme beim Arbeiten mit Diagrammachsen.

## Voraussetzungen
Stellen Sie vor dem Start sicher, dass Sie über Folgendes verfügen:
### Erforderliche Bibliotheken
- **Aspose.Slides für Python**: Installation über Pip. Erfordert Python 3.x oder höher.
### Umgebungs-Setup
- Installieren Sie Python von [python.org](https://www.python.org/).
- Verwenden Sie einen Code-Editor wie VSCode oder PyCharm.
### Voraussetzungen
- Grundlegende Kenntnisse der Python-Programmierung.
- Kenntnisse im Umgang mit Präsentationen und Diagrammen sind hilfreich, aber nicht zwingend erforderlich.

## Einrichten von Aspose.Slides für Python
So verwenden Sie Aspose.Slides in Ihren Projekten:
**Installation:**
```bash
pip install aspose.slides
```
### Schritte zum Lizenzerwerb
- **Kostenlose Testversion**: Laden Sie die Testversion herunter, um die Funktionen zu testen.
- **Temporäre Lizenz**: Erwerben Sie eine temporäre Lizenz für erweiterte Tests.
- **Kaufen**: Kaufen Sie eine Vollversion für langfristigen Zugriff.

**Grundlegende Initialisierung:**
```python
import aspose.slides as slides
```
Dadurch werden alle Aspose.Slides-Funktionen importiert.

## Implementierungshandbuch
### Erstellen eines Diagramms mit benutzerdefinierter Achsenskala
#### Überblick
Wir erstellen ein Diagramm vom Typ FLÄCHE und setzen die Haupteinheitsskala der horizontalen Achse auf `NONE`.
**Schritt 1: Initialisieren der Präsentation**
Beginnen Sie mit der Erstellung einer neuen Präsentationsinstanz:
```python
with slides.Presentation() as pres:
    # Hier werden die weiteren Operationen durchgeführt.
```
Dieser Kontextmanager sorgt für eine effiziente Ressourcenverwaltung.
#### Schritt 2: Diagramm hinzufügen
Fügen Sie Ihrer Folie an bestimmten Koordinaten und mit bestimmten Abmessungen ein Diagramm vom Typ „FLÄCHE“ hinzu:
```python
chart = pres.slides[0].shapes.add_chart(slides.charts.ChartType.AREA, 10, 10, 400, 300, True)
```
Dadurch wird an der Position (10, 10) auf der ersten Folie ein Diagramm der Größe 400 x 300 Pixel hinzugefügt.
#### Schritt 3: Achsenskala auf KEINE setzen
Ändern Sie die Haupteinheitenskala der horizontalen Achse:
```python
chart.axes.horizontal_axis.major_unit_scale = slides.charts.TimeUnitType.NONE
```
Durch Festlegen dieser Eigenschaft werden vordefinierte Skalierungsintervalle entlang der X-Achse entfernt.
#### Schritt 4: Speichern Sie die Präsentation
Speichern Sie Ihre Änderungen in einer Datei im PPTX-Format:
```python
pres.save("YOUR_OUTPUT_DIRECTORY/charts_time_unit_type_enum_out.pptx", slides.export.SaveFormat.PPTX)
```
Dadurch wird Ihr benutzerdefiniertes Diagramm in einer neuen Präsentationsdatei gespeichert.
### Tipps zur Fehlerbehebung
- Stellen Sie sicher, dass `aspose.slides` Paket ist korrekt installiert. Verwenden Sie `pip show aspose.slides` zu überprüfen.
- Überprüfen Sie, ob das Ausgabeverzeichnis vorhanden ist und über die entsprechenden Schreibberechtigungen verfügt.

## Praktische Anwendungen
Das Festlegen von Achsenskalen kann in folgenden Fällen hilfreich sein:
1. **Finanzberichte**: Konzentrieren Sie sich auf bestimmte Zeitrahmen oder Datenpunkte ohne vordefinierte Intervalle.
2. **Wissenschaftliche Vorträge**: Präzise Kontrolle über die Datenvisualisierung für Forschungsergebnisse.
3. **Marketinganalyse**: Heben Sie wichtige Kennzahlen hervor, indem Sie störende Skalierungen entfernen.

## Überlegungen zur Leistung
Bei der Arbeit mit Aspose.Slides:
- Verwenden Sie Kontextmanager (`with` Aussagen), um Ressourcen effizient zu verwalten.
- Verarbeiten Sie Daten effizient in Python, um den Speicherverbrauch zu minimieren.
- Aktualisieren Sie die Bibliotheksversionen regelmäßig, um Leistungsverbesserungen und Fehlerbehebungen zu erzielen.

## Abschluss
Sie haben gelernt, wie Sie die Achsenskalen von Diagrammen mit Aspose.Slides für Python anpassen und so die Übersichtlichkeit Ihrer Präsentation verbessern. Entdecken Sie weitere Funktionen wie Animationssteuerungen, um Ihre Präsentationen noch weiter zu verbessern.
**Nächste Schritte:**
Implementieren Sie diese Lösung in einem Projekt zur Verbesserung der Datenpräsentation!

## FAQ-Bereich
1. **Wie aktualisiere ich Aspose.Slides?**
   - Verwenden `pip install --upgrade aspose.slides`.
2. **Kann ich sowohl die horizontalen als auch die vertikalen Achsenskalen auf KEINE setzen?**
   - Ja, verwenden `chart.axes.vertical_axis.major_unit_scale = slides.charts.TimeUnitType.NONE`.
3. **Was passiert, wenn mein Diagramm nicht richtig gespeichert wird?**
   - Überprüfen Sie die Dateipfade und stellen Sie sicher, dass Ihr Ausgabeverzeichnis beschreibbar ist.
4. **Gibt es eine Möglichkeit, Änderungen vor dem Speichern in der Vorschau anzuzeigen?**
   - Aspose.Slides bietet keine direkte Vorschau, sondern iteriert mit kleineren Skripten, bis es zufrieden ist.
5. **Wie gehe ich mit unterschiedlichen Diagrammtypen um?**
   - Ersetzen `ChartType.AREA` mit anderen Typen wie `Bar`, `Line`, usw., je nach Bedarf.

## Ressourcen
- [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/python-net/)
- [Laden Sie Aspose.Slides für Python herunter](https://releases.aspose.com/slides/python-net/)
- [Erwerben Sie eine Lizenz](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/slides/python-net/)
- [Temporäre Lizenz](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}