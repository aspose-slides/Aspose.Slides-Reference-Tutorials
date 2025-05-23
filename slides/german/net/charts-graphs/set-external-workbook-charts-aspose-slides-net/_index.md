---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mithilfe von Aspose.Slides für .NET Diagramme mit externen Excel-Arbeitsmappen einrichten und so Ihre Präsentationen und Ihr Datenmanagement verbessern."
"title": "So legen Sie eine externe Arbeitsmappe als Diagrammdatenquelle in Aspose.Slides .NET fest"
"url": "/de/net/charts-graphs/set-external-workbook-charts-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So verwenden Sie Aspose.Slides .NET, um eine externe Arbeitsmappe als Diagrammdatenquelle festzulegen
## Einführung
Die Erstellung optisch ansprechender Diagramme in Präsentationen ist entscheidend für die effektive Vermittlung datenbasierter Erkenntnisse. Die separate Verwaltung von Diagrammdaten und Präsentationsdateien kann mühsam sein. Mit Aspose.Slides für .NET können Sie eine externe Arbeitsmappe als Datenquelle für Ihre Diagramme verknüpfen, Ihren Workflow optimieren und Ihre Daten übersichtlich halten. Dieses Tutorial führt Sie durch die Implementierung der Funktion „Diagrammdaten aus externer Arbeitsmappe festlegen“ mit Aspose.Slides .NET.

**Was Sie lernen werden:**
- So verwenden Sie Aspose.Slides für .NET, um eine externe Arbeitsmappe als Datenquelle für Diagramme festzulegen.
- Schritte zum Hinzufügen und Konfigurieren eines Diagramms in Ihrer Präsentation mit externen Daten.
- Integration von Aspose.Slides-Funktionen in Ihre .NET-Projekte.

Beginnen wir mit der Schaffung der notwendigen Voraussetzungen.
## Voraussetzungen
Bevor wir beginnen, stellen Sie sicher, dass Sie über die folgende Konfiguration verfügen:
### Erforderliche Bibliotheken
- **Aspose.Slides für .NET**Diese Bibliothek unterstützt das Erstellen und Bearbeiten von PowerPoint-Präsentationen in .NET-Anwendungen. Stellen Sie die Kompatibilität mit Ihrer Entwicklungsumgebung sicher.
### Anforderungen für die Umgebungseinrichtung
- AC#-Entwicklungsumgebung wie Visual Studio.
- Eine externe Arbeitsmappe (z. B. `externalWorkbook.xlsx`), das die Diagrammdaten enthält.
### Voraussetzungen
- Grundlegende Kenntnisse der C#-Programmierung und der Konzepte des .NET-Frameworks.
- Vertrautheit mit der programmgesteuerten Arbeit an PowerPoint-Präsentationen.
## Einrichten von Aspose.Slides für .NET
Um Aspose.Slides in Ihr Projekt zu integrieren, verwenden Sie eine der folgenden Installationsmethoden:
**.NET-CLI**
```bash
dotnet add package Aspose.Slides
```
**Paketmanager**
```powershell
Install-Package Aspose.Slides
```
**NuGet-Paket-Manager-Benutzeroberfläche**
- Öffnen Sie den NuGet-Paketmanager in Ihrer IDE.
- Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.
### Lizenzerwerb
Um Aspose.Slides vollständig nutzen zu können, benötigen Sie möglicherweise eine Lizenz. So geht's:
- **Kostenlose Testversion**Beginnen Sie mit einer temporären Lizenz, um alle Funktionen ohne Einschränkungen zu erkunden.
- **Temporäre Lizenz**: Bewerben Sie sich zu Bewertungszwecken auf der Aspose-Website.
- **Kaufen**: Für die langfristige Nutzung erwerben Sie ein Abonnement.
**Grundlegende Initialisierung:**
```csharp
// Initialisieren Sie die Aspose.Slides-Lizenz, falls Sie eine haben
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("path_to_your_license.lic");
```
## Implementierungshandbuch
### Festlegen einer externen Arbeitsmappe für ein Diagramm
Mit dieser Funktion können Sie Ihre Diagrammdaten mit einer externen Excel-Arbeitsmappe verknüpfen und so sicherstellen, dass alle Aktualisierungen in der Arbeitsmappe automatisch in Ihrer Präsentation berücksichtigt werden.
#### Schritt 1: Präsentation initialisieren und Diagramm hinzufügen
Erstellen Sie eine neue Präsentationsinstanz und fügen Sie der ersten Folie ein Kreisdiagramm hinzu.
```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public class Feature_SetExternalWorkbook {
    public static void Run() {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        using (Presentation pres = new Presentation()) {
            // Fügen Sie der ersten Folie an Position 50,50 ein Kreisdiagramm mit der Größe 400x600 hinzu
            IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Pie, 50, 50, 400, 600, false);
```
#### Schritt 2: Auf Diagrammdaten zugreifen und externe Arbeitsmappe festlegen
Greifen Sie auf die Diagrammdatensammlung zu, um Ihre externe Arbeitsmappe als Datenquelle anzugeben.
```csharp
            // Zugriff auf die Diagrammdaten zur Bearbeitung.
            IChartData chartData = chart.ChartData;
            
            // Legen Sie die externe Arbeitsmappe fest, die die Diagrammdaten enthält.
            chartData.SetExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```
#### Schritt 3: Hinzufügen von Reihen und Datenpunkten aus einer externen Arbeitsmappe
Fügen Sie Ihrem Diagramm eine neue Reihe hinzu und verknüpfen Sie sie sowohl für Kategorien als auch für Werte mit bestimmten Zellen in der externen Arbeitsmappe.
```csharp
            // Fügen Sie eine neue Reihe mit Daten aus Zelle B1 in der externen Arbeitsmappe hinzu
            chartData.Series.Add(chartData.ChartDataWorkbook.GetCell(0, "B1"), ChartType.Pie);

            // Fügen Sie Datenpunkte für die Reihe aus den Zellen B2, B3 und B4 hinzu
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B2"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B3"));
            chartData.Series[0].DataPoints.AddDataPointForPieSeries(
                chartData.ChartDataWorkbook.GetCell(0, "B4"));

            // Definieren Sie Kategorien für die Reihe anhand der Daten aus den Zellen A2, A3 und A4
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A2"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A3"));
            chartData.Categories.Add(chartData.ChartDataWorkbook.GetCell(0, "A4"));

            // Speichern Sie die Präsentation unter dem angegebenen Dateinamen
            pres.Save(dataDir + "Presentation_with_externalWorkbook.pptx");
        }
    }
}
```
### Tipps zur Fehlerbehebung
- Stellen Sie sicher, dass der Pfad der externen Arbeitsmappe korrekt und zugänglich ist.
- Überprüfen Sie, ob die Zellbezüge in Ihrem Code mit denen in Ihrer Excel-Datei übereinstimmen.
## Praktische Anwendungen
Hier sind einige Szenarien, in denen das Einrichten einer externen Arbeitsmappe für ein Diagramm äußerst nützlich sein kann:
1. **Finanzberichte**: Diagramme automatisch aktualisieren, wenn sich Finanzdaten in Tabellen ändern.
2. **Projektmanagement-Dashboards**Verknüpfen Sie in separaten Arbeitsmappen gespeicherte Fortschrittsmetriken mit Präsentationsfolien.
3. **Marketinganalyse**: Halten Sie Präsentationen mit den neuesten Kampagnenleistungsdaten auf dem neuesten Stand.
## Überlegungen zur Leistung
Beachten Sie beim Arbeiten mit Aspose.Slides diese Tipps für eine optimale Leistung:
- Minimieren Sie externe Arbeitsmappenaufrufe, indem Sie die erforderlichen Daten nach Möglichkeit vorab laden.
- Verwenden Sie effiziente Speicherverwaltungsverfahren in .NET, um große Präsentationen zu verarbeiten.
- Aktualisieren Sie Ihre Aspose.Slides-Bibliothek regelmäßig, um von Optimierungen und Fehlerbehebungen zu profitieren.
## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für .NET eine externe Arbeitsmappe als Quelle für Diagrammdaten festlegen. Diese Funktion verbessert die Datenverwaltung und stellt sicher, dass Ihre Präsentationen bei allen zugrunde liegenden Datenänderungen aktuell bleiben.
**Nächste Schritte:**
- Entdecken Sie zusätzliche Funktionen von Aspose.Slides, um Ihre Präsentationen weiter zu verbessern.
- Experimentieren Sie mit verschiedenen Diagrammtypen und Datenkonfigurationen.
Wir empfehlen Ihnen, diese Techniken in Ihren Projekten zu implementieren. Für weitere Informationen lesen Sie bitte die [Aspose.Slides-Dokumentation](https://reference.aspose.com/slides/net/) oder erkunden Sie ihre Foren für Community-Support.
## FAQ-Bereich
1. **Wie verknüpfe ich eine externe Arbeitsmappe, die sich auf einem Netzlaufwerk befindet?**
   - Stellen Sie sicher, dass für den Zugriff aus Ihrer Anwendungsumgebung die richtigen Berechtigungen und Pfade festgelegt sind.
2. **Kann ich Diagrammdaten in Echtzeit aktualisieren?**
   - Obwohl Aspose.Slides Echtzeitaktualisierungen nicht direkt unterstützt, können häufige Aktualisierungen diesen Effekt simulieren.
3. **Gibt es eine Begrenzung für die Anzahl externer Arbeitsmappen, die ich verknüpfen kann?**
   - Es gibt keine inhärente Begrenzung, aber die Leistung kann je nach Leistungsfähigkeit Ihres Systems und Komplexität der Arbeitsmappe variieren.
4. **Wie behebe ich das Problem, wenn mein Diagramm die Daten nicht richtig anzeigt?**
   - Überprüfen Sie die Zellreferenzen in Ihrem Code auf Richtigkeit im Vergleich zu Ihrer Excel-Datei.
5. **Welche Formate werden für externe Arbeitsmappen unterstützt?**
   - Aspose.Slides unterstützt in erster Linie `.xlsx` Dateien, stellen Sie jedoch die Kompatibilität basierend auf Ihren spezifischen Arbeitsmappeneinstellungen sicher.
## Ressourcen
- [Aspose.Slides Dokumentation](https://reference.aspose.com/slides/net/)
- [Laden Sie Aspose.Slides herunter](https://releases.aspose.com/slides/net/)
- [Erwerben Sie eine Aspose.Slides-Lizenz](https://purchase.aspose.com/buy)
- [Kostenlose Testversion zur Evaluierung](https://releases.aspose.com/slides/net/)
- [Temporäre Lizenz anfordern](https://purchase.aspose.com/temporary-license/)
- [Aspose Support Forum](https://forum.aspose.com/c/slides/14)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}