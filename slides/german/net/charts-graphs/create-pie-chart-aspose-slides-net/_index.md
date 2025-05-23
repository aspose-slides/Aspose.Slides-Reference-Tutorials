---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET programmgesteuert Kreisdiagramme zu Ihren Präsentationen hinzufügen und so die Datenvisualisierung mühelos verbessern."
"title": "Erstellen Sie ein Kreisdiagramm in PowerPoint mit Aspose.Slides für .NET"
"url": "/de/net/charts-graphs/create-pie-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und fügen Sie mit Aspose.Slides für .NET ein Kreisdiagramm zu einer Präsentation hinzu
## Einführung
Für überzeugende Präsentationen reicht oft nicht nur Text; visuelle Elemente wie Diagramme können die Wirkung Ihrer Datendarstellung deutlich steigern. Wenn Sie Ihren PowerPoint-Präsentationen programmgesteuert dynamische Kreisdiagramme hinzufügen möchten, **Aspose.Slides für .NET** ist ein leistungsstarkes Tool, das diese Aufgabe nahtlos und effizient macht. Dieses Tutorial führt Sie durch das Hinzufügen eines Kreisdiagramms zu einer Präsentationsfolie und dessen Konfiguration mit externen Datenquellen.

### Was Sie lernen werden
- So erstellen Sie eine neue Präsentation mit Aspose.Slides für .NET
- Hinzufügen eines Kreisdiagramms zur ersten Folie
- Festlegen einer externen Arbeitsmappen-URL als Datenquelle für Ihr Diagramm
- Speichern Ihrer Präsentation im PPTX-Format
Lassen Sie uns einen Blick darauf werfen, wie Sie dies mühelos erreichen können, beginnend mit den Voraussetzungen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie Folgendes bereit haben:
- **Aspose.Slides für .NET** Bibliothek installiert. Sie benötigen eine Version, die mit .NET Framework oder .NET Core/.NET 5+ kompatibel ist.
- Grundkenntnisse der C#-Programmierung und Vertrautheit mit der Visual Studio IDE.
- Eine auf Ihrem Computer eingerichtete Entwicklungsumgebung (Windows, macOS oder Linux).
## Einrichten von Aspose.Slides für .NET
### Installationsanweisungen
Aspose.Slides für .NET kann Ihrem Projekt mit verschiedenen Methoden hinzugefügt werden:
**.NET-CLI**
```shell
dotnet add package Aspose.Slides
```
**Paket-Manager-Konsole**
```powershell
Install-Package Aspose.Slides
```
**NuGet-Paket-Manager-Benutzeroberfläche**
1. Öffnen Sie den NuGet-Paket-Manager in Visual Studio.
2. Suchen Sie nach „Aspose.Slides“.
3. Installieren Sie die neueste Version.
### Lizenzerwerb
Um Aspose.Slides zu nutzen, können Sie mit einer kostenlosen Testlizenz beginnen und die Funktionen uneingeschränkt nutzen. Für Produktionsumgebungen empfiehlt sich der Erwerb einer kommerziellen Lizenz oder einer temporären Lizenz für längere Tests. Besuchen Sie [Asposes Kaufseite](https://purchase.aspose.com/buy) für weitere Details.
### Grundlegende Initialisierung
Um Aspose.Slides in Ihrem Projekt zu verwenden, müssen Sie es mit Ihrer Lizenz initialisieren, falls verfügbar:
```csharp
// Initialisieren der Bibliothek
License license = new License();
license.SetLicense("path/to/your/license.lic");
```
## Implementierungshandbuch
Nachdem Sie nun eingerichtet sind, gehen wir die einzelnen Funktionen Schritt für Schritt durch.
### Erstellen und Hinzufügen eines Diagramms zur Präsentation
#### Überblick
Wir beginnen mit der Erstellung einer Präsentation und fügen der ersten Folie ein Kreisdiagramm hinzu.
#### Schritte:
1. **Initialisieren der Präsentation**
   Beginnen Sie mit der Erstellung einer Instanz des `Presentation` Klasse, die Ihre PowerPoint-Datei darstellt.
   ```csharp
   using Aspose.Slides;
   
   string dataDir = "YOUR_DOCUMENT_DIRECTORY";
   
   using (Presentation pres = new Presentation())
   {
       // Hier fügen wir unser Diagramm hinzu.
   }
   ```
2. **Hinzufügen eines Kreisdiagramms**
   Verwenden Sie die `Shapes.AddChart` Methode zum Einfügen eines Kreisdiagramms an bestimmten Koordinaten auf Ihrer Folie.
   ```csharp
   IChart chart = pres.Slides[0].Shapes.AddChart(
       ChartType.Pie, 50, 50, 400, 600, true);
   ```
### Externe Arbeitsmappe für Diagrammdaten festlegen
#### Überblick
Konfigurieren wir nun das Kreisdiagramm so, dass es Daten aus einer externen Arbeitsmappe verwendet.
#### Schritte:
1. **Zugriff auf Diagrammdaten**
   Rufen Sie die Diagrammdatenschnittstelle ab, in der Sie die URL Ihrer externen Datenquelle angeben.
   ```csharp
   IChartData chartData = chart.ChartData;
   ```
2. **Festlegen der URL der externen Arbeitsmappe**
   Legen Sie die URL für Ihre Datenquelle fest mit `SetExternalWorkbook`. In diesem Beispiel wird eine Platzhalter-URL verwendet, die durch den tatsächlichen Datenquellenpfad ersetzt werden sollte.
   ```csharp
   (chartData as ChartData).SetExternalWorkbook("http://Pfad/existiert/nicht", false);
   ```
### Präsentation in Datei speichern
#### Überblick
Speichern Sie die Präsentation abschließend im PPTX-Format am gewünschten Speicherort.
#### Schritte:
1. **Speichern der Präsentation**
   Verwenden Sie die `Save` Methode der `Presentation` Klasse, um die Datei auf die Festplatte zu schreiben.
   ```csharp
   pres.Save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
   ```
## Praktische Anwendungen
- **Geschäftsberichte**: Erstellen Sie automatisch Diagramme für vierteljährliche Leistungsbeurteilungen.
- **Daten-Dashboards**: Integrieren Sie Datenquellen, um visuelle Berichte in Echtzeit zu aktualisieren.
- **Bildungsinhalte**: Erstellen Sie dynamische Präsentationen, die die neuesten Daten aus externen Studien oder Forschungsarbeiten enthalten.
Durch die Integration von Aspose.Slides können Sie Ihren Präsentationserstellungsprozess in verschiedenen Bereichen automatisieren und verbessern.
## Überlegungen zur Leistung
Beim Arbeiten mit großen Datensätzen oder zahlreichen Diagrammen:
- Optimieren Sie die Ressourcennutzung, indem Sie den Speicher innerhalb von .NET effektiv verwalten.
- Entsorgen `Presentation` Objekte ordnungsgemäß, um Ressourcen freizugeben.
- Verwenden Sie nach Möglichkeit asynchrone Vorgänge, um die Reaktionsfähigkeit der Anwendung zu verbessern.
## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für .NET programmgesteuert Präsentationen mit Kreisdiagrammen erstellen. Sie verfügen nun über die Tools, um die Diagrammerstellung zu automatisieren und externe Datenquellen effizient zu verwalten.
### Nächste Schritte
Erkunden Sie die Möglichkeiten noch weiter, indem Sie Diagrammstile anpassen, weitere Diagrammtypen hinzufügen oder andere Aspose-Komponenten wie Aspose.Cells integrieren, um die Datenbearbeitungsfunktionen zu verbessern.
## FAQ-Bereich
1. **Was ist Aspose.Slides?**  
   Eine robuste Bibliothek zur programmgesteuerten Bearbeitung von PowerPoint-Präsentationen in .NET.
2. **Kann ich Aspose.Slides ohne Lizenz verwenden?**  
   Ja, allerdings mit Einschränkungen. Erwägen Sie die Nutzung einer kostenlosen Testversion oder den Erwerb einer Lizenz für den vollen Funktionsumfang.
3. **Wie aktualisiere ich Diagrammdaten dynamisch?**  
   Nutzen Sie externe Arbeitsmappen und legen Sie deren URLs in der `SetExternalWorkbook` Verfahren.
4. **Kann Aspose.Slides auf mehreren Plattformen verwendet werden?**  
   Ja, es unterstützt .NET Framework und .NET Core/.NET 5+ unter Windows, macOS und Linux.
5. **Welche anderen Diagrammtypen werden unterstützt?**  
   Zusätzlich zu Kreisdiagrammen können Sie mit Aspose.Slides Balkendiagramme, Liniendiagramme und mehr erstellen.
## Ressourcen
- [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/net/)
- [Lade die neueste Version herunter](https://releases.aspose.com/slides/net/)
- [Lizenz erwerben](https://purchase.aspose.com/buy)
- [Kostenlose Testversion](https://releases.aspose.com/slides/net/)
- [Temporäre Lizenz](https://purchase.aspose.com/temporary-license/)
- [Support-Forum](https://forum.aspose.com/c/slides/11)
Beginnen Sie noch heute mit der Integration von Aspose.Slides in Ihre Projekte, um Ihre PowerPoint-Präsentationen zu verbessern und zu automatisieren!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}