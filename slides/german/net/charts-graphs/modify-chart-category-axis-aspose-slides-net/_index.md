---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Diagrammkategorieachsen in PowerPoint ändern und so die Lesbarkeit und visuelle Attraktivität Ihrer Präsentation verbessern."
"title": "So ändern Sie die Diagrammkategorieachse in PowerPoint mit Aspose.Slides .NET"
"url": "/de/net/charts-graphs/modify-chart-category-axis-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So ändern Sie die Diagrammkategorieachse in PowerPoint mit Aspose.Slides .NET

## Einführung

Verbessern Sie die visuelle Wirkung von Diagrammen in Ihren PowerPoint-Präsentationen, indem Sie die Kategorieachsen anpassen. Diese Anleitung beschreibt, wie Sie den Kategorieachsentyp eines Diagramms mit Aspose.Slides für .NET anpassen und so die Lesbarkeit der Daten und die Präsentationsqualität verbessern – insbesondere bei Zeitreihendaten.

In der heutigen datengetriebenen Welt ist die Umwandlung von Rohdaten in intuitive Grafiken unerlässlich. Mit Aspose.Slides für .NET können Entwickler PowerPoint-Diagramme effektiv bearbeiten, um eine klare Kommunikation in ihren Präsentationen zu gewährleisten.

**Was Sie lernen werden:**
- Ändern Sie den Kategorieachsentyp eines Diagramms mit Aspose.Slides für .NET.
- Konfigurieren Sie die wichtigsten Einheiteneinstellungen auf der horizontalen Achse für eine bessere Datendarstellung.
- Speichern Sie Ihre Änderungen mühelos in einer neuen PowerPoint-Datei.

## Voraussetzungen

### Erforderliche Bibliotheken, Versionen und Abhängigkeiten
Um diese Funktion zu implementieren, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Aspose.Slides für .NET**Die Kernbibliothek zur Bearbeitung von PowerPoint-Präsentationen.
- **.NET Framework oder .NET Core/5+/6+** auf Ihrem Computer installiert (überprüfen Sie die Kompatibilität mit der Dokumentation von Aspose).

### Anforderungen für die Umgebungseinrichtung
Stellen Sie sicher, dass Ihre Entwicklungsumgebung .NET-Anwendungen unterstützt, indem Sie Visual Studio oder eine gleichwertige IDE verwenden.

### Voraussetzungen
Grundkenntnisse in C# und Erfahrung mit PowerPoint-Präsentationen sind von Vorteil. Vorkenntnisse mit Aspose.Slides für .NET sind hilfreich, aber nicht erforderlich.

## Einrichten von Aspose.Slides für .NET

Installieren Sie Aspose.Slides in Ihrer Projektumgebung, um loszulegen.

**Installationsoptionen:**

**.NET-CLI**
```shell
dotnet add package Aspose.Slides
```

**Paket-Manager-Konsole**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche**
Suchen Sie nach „Aspose.Slides“ und klicken Sie auf „Installieren“, um die neueste Version zu erhalten.

### Lizenzerwerb
- **Kostenlose Testversion**: Laden Sie eine kostenlose Testversion herunter von [Asposes Veröffentlichungsseite](https://releases.aspose.com/slides/net/).
- **Temporäre Lizenz**: Erhalten Sie eine temporäre Lizenz für erweiterten Zugriff ohne Einschränkungen bei [Asposes temporäre Lizenzseite](https://purchase.aspose.com/temporary-license/).
- **Kaufen**: Erwägen Sie den Kauf einer Lizenz direkt von [Asposes Kaufseite](https://purchase.aspose.com/buy) für den Langzeitgebrauch.

**Grundlegende Initialisierung:**
```csharp
// Erstellen Sie eine Instanz der Klasse „Präsentation“ mit (Presentation presentation = new Presentation()).
{
    // Operationen mit Aspose.Slides
}
```

## Implementierungshandbuch

### Diagrammkategorieachse in „Datum“ ändern
Mit dieser Funktion können Sie den Kategorieachsentyp Ihres Diagramms ändern, ideal für Zeitreihendaten.

#### Überblick
Wir ändern die Kategorieachse eines bestehenden Diagramms in einer PowerPoint-Präsentation in das Datumsformat und konfigurieren die Haupteinheiteneinstellungen. Diese Anpassung macht Zeitleisten für Betrachter übersichtlicher und intuitiver.

#### Schritte:

**Schritt 1: Laden Sie Ihre Präsentation**
Laden Sie eine vorhandene Präsentation, die das Diagramm enthält, das Sie ändern möchten.
```csharp
string dataDir = "YOUR_DOCUMENT_DIRECTORY";
using (Presentation presentation = new Presentation(dataDir + "/ExistingChart.pptx"))
{
    // Zugriff auf die erste Form auf der ersten Folie und deren Übertragung in IChart
    IChart chart = presentation.Slides[0].Shapes[0] as IChart;
```

**Schritt 2: Kategorieachsentyp ändern**
Ändern Sie den Kategorieachsentyp in `Date`, ideal für Datensätze mit chronologischen Daten.
```csharp
    // Ändern Sie den Kategorieachsentyp in „Datum“
    chart.Axes.HorizontalAxis.CategoryAxisType = CategoryAxisType.Date;
```

**Schritt 3: Konfigurieren der Haupteinheiteneinstellungen**
Legen Sie manuelle Steuerelemente für die wichtigsten Rasterlinienintervalle fest und verbessern Sie so die Klarheit und Präzision Ihrer Präsentation.
```csharp
    // Konfigurieren Sie die wichtigsten Einheiteneinstellungen auf der horizontalen Achse
    chart.Axes.HorizontalAxis.IsAutomaticMajorUnit = false; 
    chart.Axes.HorizontalAxis.MajorUnit = 1;
    chart.Axes.HorizontalAxis.MajorUnitScale = TimeUnitType.Months;
```

**Schritt 4: Speichern Sie Ihre Änderungen**
Speichern Sie abschließend Ihre Präsentation mit dem geänderten Diagramm in einer neuen Datei.
```csharp
    // Speichern der aktualisierten Präsentation
    presentation.Save(dataDir + "/ChangeChartCategoryAxis_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}