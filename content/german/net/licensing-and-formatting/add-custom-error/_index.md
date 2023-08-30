---
title: Fügen Sie dem Diagramm benutzerdefinierte Fehlerbalken hinzu
linktitle: Fügen Sie dem Diagramm benutzerdefinierte Fehlerbalken hinzu
second_title: Aspose.Slides .NET PowerPoint-Verarbeitungs-API
description: Erfahren Sie, wie Sie mit Aspose.Slides für .NET benutzerdefinierte Fehlerbalken zu Diagrammen hinzufügen. Erstellen, gestalten und passen Sie Fehlerbalken für eine genaue Datenvisualisierung an.
type: docs
weight: 13
url: /de/net/licensing-and-formatting/add-custom-error/
---

## Einführung in benutzerdefinierte Fehlerbalken

Fehlerbalken sind grafische Darstellungen, mit denen die Variabilität oder Unsicherheit von Datenpunkten in einem Diagramm angezeigt wird. Sie können dabei helfen, den Bereich darzustellen, in den der wahre Wert des Datenpunkts wahrscheinlich fallen wird. Mit benutzerdefinierten Fehlerbalken können Sie spezifische Fehlerwerte für jeden Datenpunkt definieren und so mehr Kontrolle darüber haben, wie die Unsicherheit in Ihrem Diagramm angezeigt wird.

## Einrichten der Entwicklungsumgebung

 Bevor wir beginnen, stellen Sie sicher, dass Sie die Aspose.Slides für .NET-Bibliothek installiert haben. Sie können es herunterladen unter[Hier](https://releases.aspose.com/slides/net). Befolgen Sie die Installationsanweisungen in der Dokumentation.

## Erstellen eines Beispieldiagramms

Beginnen wir mit der Erstellung eines Beispieldiagramms mit Aspose.Slides für .NET. Zu Demonstrationszwecken erstellen wir ein einfaches Balkendiagramm. Stellen Sie sicher, dass Sie in Ihrem Projekt auf die Bibliothek verwiesen haben.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

// Instanziieren Sie ein Präsentationsobjekt
using Presentation presentation = new Presentation();

// Fügen Sie eine Folie hinzu
ISlide slide = presentation.Slides.AddSlide(0, presentation.SlideSize.Size);

// Fügen Sie ein Diagramm hinzu
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredBar, 100, 100, 500, 300);

// Beispieldaten hinzufügen
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, "A1"), chart.Type);
series.Values.Add(workbook.GetCell(0, "B1"));
series.Values.Add(workbook.GetCell(0, "B2"));

// Legen Sie Kategoriebezeichnungen fest
chart.ChartData.Categories.Add(workbook.GetCell(0, "A2"));
chart.ChartData.Categories.Add(workbook.GetCell(0, "A3"));

// Diagrammtitel festlegen
chart.ChartTitle.AddTextFrameForOverriding("Sample Chart");
chart.ChartTitle.TextFrameForOverriding.Text = "Sample Chart";

// Speichern Sie die Präsentation
presentation.Save("SampleChart.pptx", SaveFormat.Pptx);
```

Dieser Code erstellt eine PowerPoint-Präsentation mit einem Beispiel-Balkendiagramm.

## Fehlerbalken zum Diagramm hinzufügen

Fügen wir nun dem Diagramm Fehlerbalken hinzu. Fehlerbalken werden bestimmten Datenpunkten in einer Reihe hinzugefügt. Wir fügen dem ersten Datenpunkt in unserem Beispieldiagramm Fehlerbalken hinzu.

```csharp
// Greifen Sie auf die erste Serie zu
IChartSeries firstSeries = chart.ChartData.Series[0];

// Fehlerbalken hinzufügen
IErrorBarsFormat errorBarsFormat = firstSeries.ErrorBarsFormat.Add();
errorBarsFormat.Type = ErrorBarType.FixedValue;

// Legen Sie den Fehlerbalkenwert fest
errorBarsFormat.Value = 5; // Sie können den Wert entsprechend Ihren Daten anpassen

// Speichern Sie die aktualisierte Präsentation
presentation.Save("ChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Dieser Code fügt dem ersten Datenpunkt des Diagramms Fehlerbalken mit festem Wert hinzu.

## Anpassen der Fehlerbalkenwerte

Sie können die Fehlerbalkenwerte für jeden Datenpunkt individuell anpassen. Ändern wir den Code, um für jeden Datenpunkt unterschiedliche Fehlerwerte festzulegen.

```csharp
// Legen Sie benutzerdefinierte Fehlerwerte für jeden Punkt fest
double[] errorValues = { 3, 6 }; // Fehlerwerte für die beiden Datenpunkte

for (int i = 0; i < firstSeries.DataPoints.Count; i++)
{
    firstSeries.ErrorBarsFormat[i].Value = errorValues[i];
}

// Speichern Sie die aktualisierte Präsentation
presentation.Save("CustomErrorValuesChart.pptx", SaveFormat.Pptx);
```

Dieser Code legt benutzerdefinierte Fehlerwerte für jeden Datenpunkt in der Reihe fest.

## Styling-Fehlerbalken

Sie können Fehlerbalken so gestalten, dass sie besser sichtbar sind und zur Ästhetik Ihres Diagramms passen. Lassen Sie uns das Erscheinungsbild der Fehlerbalken anpassen.

```csharp
// Passen Sie das Erscheinungsbild der Fehlerleiste an
errorBarsFormat.LineFormat.Width = 2; // Linienstärke einstellen
errorBarsFormat.LineFormat.SolidFillColor.Color = Color.Red; //Linienfarbe festlegen

// Speichern Sie die aktualisierte Präsentation
presentation.Save("StyledErrorBarsChart.pptx", SaveFormat.Pptx);
```

Dieser Code passt die Linienbreite und Farbe der Fehlerbalken an.

## Aktualisieren der Kartendaten

Wenn Sie die Diagrammdaten aktualisieren müssen, können Sie dies ganz einfach mit Aspose.Slides für .NET tun. Ersetzen wir die Daten durch neue Werte.

```csharp
// Diagrammdaten aktualisieren
series.Values[0].Value = 15;
series.Values[1].Value = 20;

// Speichern Sie die aktualisierte Präsentation
presentation.Save("UpdatedChartData.pptx", SaveFormat.Pptx);
```

Dieser Code aktualisiert die Werte der Diagrammdaten.

## Fehlerbalken für mehrere Serien

Sie können Fehlerbalken zu mehreren Reihen in einem Diagramm hinzufügen. Fügen wir der zweiten Reihe in unserem Beispieldiagramm Fehlerbalken hinzu.

```csharp
// Greifen Sie auf die zweite Serie zu
IChartSeries secondSeries = chart.ChartData.Series[1];

// Fügen Sie der zweiten Serie Fehlerbalken hinzu
IErrorBarsFormat secondSeriesErrorBars = secondSeries.ErrorBarsFormat.Add();
secondSeriesErrorBars.Type = ErrorBarType.Percent;

// Legen Sie den Fehlerbalkenwert für die zweite Serie fest
secondSeriesErrorBars.Value = 10; // Sie können den Wert anpassen

// Speichern Sie die aktualisierte Präsentation
presentation.Save("MultiSeriesChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Dieser Code fügt der zweiten Reihe im Diagramm Fehlerbalken hinzu.

## Umgang mit negativen und positiven Fehlern

Fehlerbalken können sowohl positive als auch negative Fehler darstellen. Ändern wir den Code, um beide Arten von Fehlerbalken hinzuzufügen.

```csharp
// Fügen Sie positive und negative Fehlerbalken hinzu
errorBarsFormat.Type = ErrorBarType.Custom;
errorBarsFormat.PlusValue = 4; // Positiver Fehlerwert
errorBarsFormat.MinusValue = 2; // Negativer Fehlerwert

// Speichern Sie die aktualisierte Präsentation
presentation.Save("PositiveNegativeErrorBars.pptx", SaveFormat.Pptx);
```

Dieser Code fügt dem Diagramm benutzerdefinierte positive und negative Fehlerbalken hinzu.

## Speichern und Exportieren des Diagramms

Sobald Sie Fehlerbalken hinzugefügt und Ihr Diagramm angepasst haben, können Sie es speichern und zur weiteren Verwendung exportieren.

```csharp
// Speichern Sie das endgültige Diagramm
presentation.Save("FinalChart.pptx", SaveFormat.Pptx);
```

Dieser Code speichert das endgültige Diagramm mit Fehlerbalken.

## Abschluss

In diesem Tutorial haben wir untersucht, wie Sie mit Aspose.Slides für .NET benutzerdefinierte Fehlerbalken zu einem Diagramm hinzufügen. Wir haben das Erstellen eines Beispieldiagramms, das Hinzufügen von Fehlerbalken, das Anpassen von Fehlerwerten, das Formatieren von Fehlerbalken, das Aktualisieren von Diagrammdaten, das Hinzufügen von Fehlerbalken zu mehreren Serien und den Umgang mit positiven und negativen Fehlern behandelt. Mit Aspose.Slides für .NET haben Sie die Flexibilität, informative und optisch ansprechende Diagramme mit benutzerdefinierten Fehlerbalken zu erstellen, die die Variabilität Ihrer Daten effektiv kommunizieren.

## FAQs

### Wie kann ich die Dicke der Fehlerbalken anpassen?

 Sie können die Dicke der Fehlerbalken anpassen, indem Sie die ändern`LineFormat.Width` Eigentum der`ErrorBarsFormat`.

### Kann ich für jeden Datenpunkt unterschiedliche Fehlerwerte verwenden?

Ja, Sie können benutzerdefinierte Fehlerwerte für jeden Datenpunkt einzeln festlegen, indem Sie eine Schleife verwenden`Value` Eigentum von`ErrorBarsFormat`.

### Ist es möglich, Fehlerbalken zu mehreren Reihen in einem einzigen Diagramm hinzuzufügen?

Sie können auf jeden Fall Fehlerbalken zu mehreren Reihen im selben Diagramm hinzufügen. Greifen Sie einfach auf die gewünschte Serie zu und wenden Sie Fehlerbalken an, wie im Artikel gezeigt.

### Kann ich Fehlerbalken entfernen, nachdem ich sie hinzugefügt habe?

 Ja, Sie können Fehlerbalken entfernen, indem Sie die aufrufen`Clear` Methode auf der`ErrorBarsFormat` Objekt.

### Wo finde ich weitere Informationen zu Aspose.Slides für .NET?

 Eine ausführliche Dokumentation und Beispiele für Aspose.Slides für .NET finden Sie auf der[Aspose-Dokumentationswebsite](https://reference.aspose.com/slides/net/).