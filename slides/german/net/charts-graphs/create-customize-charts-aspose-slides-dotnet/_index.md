---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Diagramme erstellen und anpassen, einschließlich der Anzeige von Prozentsätzen als Datenbeschriftungen. Folgen Sie dieser Schritt-für-Schritt-Anleitung."
"title": "So erstellen und passen Sie Diagramme mit Aspose.Slides .NET an&#58; Prozentsätze als Beschriftungen anzeigen"
"url": "/de/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen und passen Sie Diagramme mit Aspose.Slides .NET an: Prozentsätze als Beschriftungen anzeigen

## Einführung

Die effektive Präsentation von Daten ist in vielen Bereichen entscheidend. Diagramme spielen dabei eine wichtige Rolle, da sie komplexe Informationen anschaulich darstellen. Das Erstellen eines perfekten Diagramms erfordert Anpassungsaufgaben wie die Anzeige von Prozentwerten auf Beschriftungen – eine Aufgabe, die mit Aspose.Slides für .NET vereinfacht wird. Diese Bibliothek vereinfacht das Erstellen und Bearbeiten von Diagrammen in PowerPoint-Präsentationen.

In diesem Tutorial erfahren Sie, wie Sie mit Aspose.Slides für .NET ein gestapeltes Säulendiagramm von Grund auf neu erstellen und durch die Anzeige von Prozentwerten als Datenbeschriftungen anpassen. Mit diesen Schritten verbessern Sie Ihre Folien mit präzisen und optisch ansprechenden Datendarstellungen.

**Was Sie lernen werden:**
- Initialisieren von Aspose.Slides für .NET
- Erstellen eines gestapelten Säulendiagramms
- Berechnen und Anzeigen von Prozentsätzen auf Datenbeschriftungen
- Best Practices zur Optimierung der Diagrammleistung

Bevor wir mit der Implementierung beginnen, stellen wir sicher, dass Sie alles für den Start bereit haben.

## Voraussetzungen

Um diesem Tutorial effektiv folgen zu können, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **.NET Core SDK** auf Ihrem Computer installiert.
- Grundlegende Kenntnisse in der Anwendungsentwicklung mit C# und .NET.
- Visual Studio oder eine ähnliche IDE zum Schreiben und Ausführen von C#-Code.

Sie benötigen Aspose.Slides für .NET, um Diagramme zu erstellen. Stellen Sie daher sicher, dass es wie unten beschrieben eingerichtet ist.

## Einrichten von Aspose.Slides für .NET

Aspose.Slides für .NET ist eine leistungsstarke Bibliothek, mit der Sie programmgesteuert mit PowerPoint-Präsentationen arbeiten können. So fügen Sie sie Ihrem Projekt hinzu:

### Installation

**.NET-CLI:**
```bash
dotnet add package Aspose.Slides
```

**Paketmanager-Konsole:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche:** 
- Öffnen Sie den NuGet-Paketmanager und suchen Sie nach „Aspose.Slides“. Installieren Sie die neueste Version.

### Lizenzerwerb

Um Aspose.Slides vollständig zu nutzen, starten Sie mit einer kostenlosen Testversion. Für eine längere Nutzung können Sie eine temporäre Lizenz erwerben oder eine von [Aspose](https://purchase.aspose.com/buy)Befolgen Sie deren Richtlinien, um Ihre Lizenz in Ihrer Projektumgebung einzurichten.

### Grundlegende Initialisierung

Nach der Installation initialisieren Sie die `Presentation` Klasse, um mit der Erstellung von Folien zu beginnen:
```csharp
using Aspose.Slides;

// Initialisieren Sie die Instanz der Präsentationsklasse
tPresentation presentation = new Presentation();
```

Fahren wir nun mit der Implementierung unserer Funktion zur Diagrammerstellung und -anpassung mit Aspose.Slides für .NET fort.

## Implementierungshandbuch

### Erstellen eines gestapelten Säulendiagramms

Unser Ziel ist es, ein gestapeltes Säulendiagramm zu erstellen und es durch die Anzeige von Prozentsätzen als Datenbeschriftungen anzupassen. So geht's:

#### Initialisieren der Präsentation

Beginnen Sie mit der Erstellung einer Instanz von `Presentation`:
```csharp
using Aspose.Slides;

// Initialisieren Sie die Instanz der Präsentationsklasse
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Hinzufügen eines Diagramms zur Folie

Fügen Sie Ihrer ersten Folie an den angegebenen Koordinaten und in den angegebenen Abmessungen ein gestapeltes Säulendiagramm hinzu:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Diese Linie erzeugt eine `StackedColumn` Diagramm an Position (20, 20) mit einer Breite und Höhe von 400.

#### Gesamtwerte für die Prozentberechnung berechnen

Um Prozentsätze anzuzeigen, berechnen Sie den Gesamtwert für jede Kategorie über alle Reihen hinweg:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Summieren Sie die Werte aller Serien für jede Kategorie
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Passen Sie Datenbeschriftungen an, um Prozentwerte anzuzeigen

Als nächstes durchlaufen Sie jede Reihe und passen die Datenbeschriftungen an:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Prozentsatz berechnen
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Klartext zur Vermeidung von Überschneidungen
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Konfigurieren Sie das Beschriftungsformat, um Standarddatenbeschriftungen auszublenden
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

In diesem Abschnitt wird der Prozentsatz für jeden Datenpunkt berechnet und als benutzerdefinierte Bezeichnung festgelegt. Dabei wird sichergestellt, dass es zu keiner Überschneidung mit Standardbezeichnungen kommt.

#### Speichern der Präsentation

Speichern Sie abschließend Ihre Präsentation, um das Ergebnis anzuzeigen:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Praktische Anwendungen

Die Anzeige von Prozentsätzen in Diagrammen kann insbesondere in folgenden Szenarien nützlich sein:
1. **Finanzberichterstattung:** Zeigen Sie Portfolioverteilungen oder Anlagerenditen als Prozentsätze an.
2. **Verkaufsanalyse:** Stellen Sie Marktanteilsdaten in Prozent dar, um die Leistung in verschiedenen Regionen hervorzuheben.
3. **Umfrageergebnisse:** Zeigen Sie die Umfrageantworten als Prozentsätze an, um einen besseren visuellen Vergleich zu ermöglichen.
4. **Projektmanagement:** Verwenden Sie Kreisdiagramme mit Prozentsätzen, um die Ressourcenzuweisung zu veranschaulichen.
5. **Ausbildung:** Erklären Sie statistische Konzepte anhand klarer, prozentualer Darstellungen.

Durch die Integration dieser benutzerdefinierten Diagramme in Systeme wie CRM oder ERP können Dashboards und Berichte verbessert und so Entscheidungsprozesse unterstützt werden.

## Überlegungen zur Leistung

Beim Arbeiten mit Aspose.Slides für .NET, insbesondere bei großen Datensätzen:
- **Speicherverwaltung:** Entsorgen Sie Präsentationsobjekte ordnungsgemäß, um Speicherplatz freizugeben. Verwenden Sie `using` Aussagen, sofern zutreffend.
- **Effiziente Datenverarbeitung:** Führen Sie Berechnungen nach Möglichkeit außerhalb von Schleifen durch, um den Rechenaufwand zu reduzieren.
- **Lastenausgleich:** Stellen Sie bei Webanwendungen sicher, dass ausreichend Serverressourcen für gleichzeitige Anforderungen zur Diagrammgenerierung bereitgestellt werden.

## Abschluss

Dieses Tutorial behandelte das Erstellen und Anpassen von Diagrammen mit Aspose.Slides für .NET durch die Anzeige von Prozentwerten als Beschriftungen. Die Beherrschung dieser Techniken ermöglicht es Ihnen, Ihre Präsentationen mit detaillierten und optisch ansprechenden Datendarstellungen zu verbessern.

Entdecken Sie im nächsten Schritt die anderen Diagrammtypen und Anpassungsmöglichkeiten von Aspose.Slides. Experimentieren Sie mit verschiedenen Datensätzen, um sie in aussagekräftige Visualisierungen zu verwandeln, die Erkenntnisse klar vermitteln.

## FAQ-Bereich

**F1: Wie gehe ich mit großen Datensätzen um, wenn ich Diagramme mit Aspose.Slides für .NET erstelle?**
A1: Optimieren Sie bei großen Datensätzen die Berechnungen und nutzen Sie effiziente Speicherverwaltungstechniken. Teilen Sie die Verarbeitungsaufgaben auf, um eine Speicherüberlastung zu vermeiden.

**F2: Kann ich Aspose.Slides für .NET in einer Webanwendung verwenden?**
A2: Ja, es kann in ASP.NET-Anwendungen integriert werden. Stellen Sie für optimale Leistung eine angemessene Serverressourcenzuweisung sicher.

**F3: Ist es möglich, mit Aspose.Slides erstellte Diagramme in andere Formate zu exportieren?**
A3: Auf jeden Fall! Sie können Präsentationen mit Ihren benutzerdefinierten Diagrammen mithilfe der Bibliothek in verschiedene Formate wie PDF und Bilddateien exportieren.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}