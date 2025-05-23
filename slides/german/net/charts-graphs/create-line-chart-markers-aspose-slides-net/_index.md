---
"date": "2025-04-15"
"description": "Erfahren Sie, wie Sie mit Aspose.Slides für .NET Liniendiagramme mit Markierungen erstellen. Diese Schritt-für-Schritt-Anleitung behandelt die Einrichtung, Diagrammerstellung und Anpassung."
"title": "So erstellen Sie ein Liniendiagramm mit Markierungen in C# mit Aspose.Slides für .NET"
"url": "/de/net/charts-graphs/create-line-chart-markers-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# So erstellen Sie ein Liniendiagramm mit Markierungen in C# mit Aspose.Slides für .NET

## Einführung
Das Erstellen optisch ansprechender und informativer Liniendiagramme ist für eine effektive Datenpräsentation in C# unerlässlich. **Aspose.Slides für .NET** Vereinfacht das Erstellen professioneller Diagramme, auch mit Markierungen. Dieses Tutorial führt Sie durch die Erstellung eines Liniendiagramms mit Standardmarkierungen mit Aspose.Slides für .NET.

In diesem Tutorial lernen Sie:
- Einrichten Ihrer Umgebung zur Verwendung von Aspose.Slides für .NET.
- Erstellen und Anpassen einer Präsentation mit einem Liniendiagramm, das Markierungen enthält.
- Konfigurieren von Diagrammeigenschaften wie Kategorien, Reihen und Datenpunkten.
- Speichern der endgültigen Präsentationsdatei.

Beginnen wir mit der Überprüfung der Voraussetzungen, die vor der Implementierung unserer Lösung erforderlich sind.

## Voraussetzungen
Bevor Sie beginnen, stellen Sie sicher, dass Sie über Folgendes verfügen:
- **Erforderliche Bibliotheken:** Aspose.Slides für .NET über NuGet in Ihrer Entwicklungsumgebung installiert.
- **Anforderungen für die Umgebungseinrichtung:** Eine funktionierende C#-Entwicklungsumgebung wie Visual Studio und das .NET-Framework müssen auf Ihrem Computer installiert sein.
- **Erforderliche Kenntnisse:** Grundlegende Kenntnisse der C#-Programmierung und Vertrautheit mit der programmgesteuerten Erstellung von Präsentationen.

## Einrichten von Aspose.Slides für .NET
### Informationen zur Installation
Um Aspose.Slides für .NET zu verwenden, fügen Sie es Ihrem Projekt mit einer der folgenden Methoden hinzu:

**Verwenden der .NET-CLI:**
```bash
dotnet add package Aspose.Slides
```

**Über die Paket-Manager-Konsole in Visual Studio:**
```powershell
Install-Package Aspose.Slides
```

**NuGet-Paket-Manager-Benutzeroberfläche:**
- Öffnen Sie Ihre Lösung in Visual Studio.
- Gehen Sie zu „NuGet-Pakete für Lösung verwalten …“
- Suchen Sie nach „Aspose.Slides“ und installieren Sie die neueste Version.

### Lizenzerwerb
Bevor Sie Aspose.Slides verwenden, besorgen Sie sich eine Test- oder Kauflizenz:
1. **Kostenlose Testversion:** Besuchen [Kostenlose Testseite von Aspose](https://releases.aspose.com/slides/net/) um schnell zu starten.
2. **Temporäre Lizenz:** Für erweiterten Zugriff besuchen Sie die [Seite „Temporäre Lizenz“](https://purchase.aspose.com/temporary-license/).
3. **Kaufen:** Um Aspose.Slides in der Produktion zu verwenden, erwerben Sie eine Lizenz bei [Aspose Kauf](https://purchase.aspose.com/buy).

### Grundlegende Initialisierung
Nachdem Sie Ihr Projekt eingerichtet und die erforderlichen Lizenzen erhalten haben, initialisieren Sie Aspose.Slides wie folgt:
```csharp
using Aspose.Slides;
// Erstellen Sie eine Instanz der Präsentationsklasse
Presentation pres = new Presentation();
```
Nachdem wir nun unsere Umgebung eingerichtet haben, können wir mit der Erstellung eines Liniendiagramms mit Markierungen fortfahren.

## Implementierungshandbuch
### Erstellen des Liniendiagramms mit Markierungen
In diesem Abschnitt lernen Sie jeden Schritt kennen, der zum Erstellen und Konfigurieren eines Liniendiagramms mit Standardmarkierungen in Ihrer Präsentation mithilfe von Aspose.Slides für .NET erforderlich ist.

#### Schritt 1: Erstellen Sie ein Präsentationsobjekt
Beginnen Sie mit der Erstellung einer Instanz des `Presentation` Klasse:
```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
```
Hier greifen wir auf die erste Folie einer neu erstellten Präsentation zu.

#### Schritt 2: Fügen Sie ein Liniendiagramm mit Markierungen hinzu
Fügen Sie als Nächstes ein Liniendiagramm mit Markierungen zu Ihrer Folie hinzu:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
```
Dieser Code fügt ein neues Diagramm vom Typ hinzu `LineWithMarkers` an den Koordinaten `(10, 10)` mit Abmessungen `400x400`.

#### Schritt 3: Vorhandene Serien und Kategorien löschen
Löschen Sie vor dem Hinzufügen von Daten alle vorhandenen Reihen oder Kategorien:
```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```
Dadurch wird sichergestellt, dass unser Diagramm mit einem leeren Blatt beginnt.

#### Schritt 4: Konfigurieren der Diagrammdaten-Arbeitsmappe
Zugriff auf die `ChartDataWorkbook` So verwalten Sie die Daten Ihres Diagramms:
```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```
Dieses Objekt ist für die Verwaltung von Zellen mit Serien- und Kategoriedaten von entscheidender Bedeutung.

#### Schritt 5: Serien und Kategorien hinzufügen
Fügen Sie dem Diagramm eine neue Reihe hinzu und füllen Sie sie mit Datenpunkten:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
IChartSeries series = chart.ChartData.Series[0];

// Definieren Sie Kategorien und entsprechende Datenpunkte
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "C1"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 1, 24));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "C2"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 1, 23));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "C3"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 1, -10));
chart.ChartData.Categories.Add(fact.GetCell(0, 4, 0, "C4"));

// Fügen Sie einen Null-Datenpunkt hinzu, um den Umgang mit fehlenden Werten zu demonstrieren
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 1, (double?)null));
```
Hier füllen wir das Diagramm mit Kategorien und entsprechenden Seriendaten. Beachten Sie, wie ein `null` Der Wert dient lediglich der Demonstration.

#### Schritt 6: Eine weitere Serie hinzufügen
Wiederholen Sie den Vorgang, um eine weitere Serie hinzuzufügen:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 2, "Series 2"), chart.Type);
IChartSeries series2 = chart.ChartData.Series[1];

series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 2, 30));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 2, 10));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 2, 60));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 2, 40));
```

#### Schritt 7: Aktivieren und Konfigurieren der Legende
Aktivieren Sie die Diagrammlegende, um die Lesbarkeit zu verbessern:
```csharp
chart.HasLegend = true;
chart.Legend.Overlay = false;
```
Dadurch wird sichergestellt, dass die Legende sichtbar ist und nicht das Diagramm überlagert.

#### Schritt 8: Speichern Sie die Präsentation
Speichern Sie abschließend Ihre Präsentation mit dem neu hinzugefügten Diagramm:
```csharp
pres.Save("DefaultMarkersInChart.pptx");
}
```
### Tipps zur Fehlerbehebung
- **Datenbindungsfehler:** Stellen Sie sicher, dass die Datenpunkte den Kategorien korrekt entsprechen.
- **Diagramm wird nicht angezeigt:** Überprüfen Sie, ob `chart.HasLegend` und andere Eigenschaften entsprechend eingestellt sind.

## Praktische Anwendungen
1. **Geschäftsberichte:** Verwenden Sie Liniendiagramme mit Markierungen, um die Verkaufsleistung im Zeitverlauf zu verfolgen und Trends beim monatlichen Umsatz anzuzeigen.
2. **Finanzanalyse:** Visualisieren Sie Aktienkursbewegungen mit Standardmarkierungen, um Spitzen und Tiefpunkte hervorzuheben.
3. **Wissenschaftliche Forschung:** Präsentieren Sie experimentelle Ergebnisse, bei denen Datenpunkte für die Analyse klar abgegrenzt werden müssen.

## Überlegungen zur Leistung
- Optimieren Sie, indem Sie bei großen Datensätzen die Anzahl der Datenreihen und Kategorien begrenzen.
- Verwenden Sie Speicherverwaltungstechniken wie das sofortige Entsorgen von Objekten in .NET, um die Ressourcennutzung zu reduzieren.

## Abschluss
In diesem Tutorial haben Sie gelernt, wie Sie mit Aspose.Slides für .NET ein Liniendiagramm mit Markierungen erstellen. Mit diesen Schritten können Sie Ihre Präsentationen mit detaillierten und professionellen Diagrammen optimieren. Entdecken Sie weitere Funktionen von Aspose.Slides, um Ihre Präsentationen noch weiter zu bereichern.

### Nächste Schritte
- Experimentieren Sie mit verschiedenen Diagrammtypen, die in Aspose.Slides verfügbar sind.
- Passen Sie die Darstellung von Diagrammen an, um eine bessere visuelle Wirkung zu erzielen.
- Entdecken Sie die zusätzliche Dokumentation zu Aspose.Slides für erweiterte Funktionen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}