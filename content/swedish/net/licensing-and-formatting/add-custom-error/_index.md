---
title: Lägg till anpassade felstaplar till diagrammet
linktitle: Lägg till anpassade felstaplar till diagrammet
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du lägger till anpassade felstaplar till diagram med Aspose.Slides för .NET. Skapa, stil och anpassa felfält för korrekt datavisualisering.
type: docs
weight: 13
url: /sv/net/licensing-and-formatting/add-custom-error/
---

## Introduktion till anpassade felfält

Felstaplar är grafiska representationer som används för att indikera variationen eller osäkerheten hos datapunkter i ett diagram. De kan hjälpa till att skildra intervallet inom vilket det sanna värdet av datapunkten sannolikt kommer att falla. Med anpassade felstaplar kan du definiera specifika felvärden för varje datapunkt, vilket ger mer kontroll över hur osäkerheten visas i ditt diagram.

## Ställa in utvecklingsmiljön

 Innan vi börjar, se till att du har Aspose.Slides för .NET-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/slides/net). Följ installationsinstruktionerna i dokumentationen.

## Skapa ett exempeldiagram

Låt oss börja med att skapa ett exempeldiagram med Aspose.Slides för .NET. Vi kommer att skapa ett grundläggande stapeldiagram för demonstrationsändamål. Se till att du har refererat till biblioteket i ditt projekt.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

// Instantiera presentationsobjekt
using Presentation presentation = new Presentation();

// Lägg till en bild
ISlide slide = presentation.Slides.AddSlide(0, presentation.SlideSize.Size);

// Lägg till ett diagram
IChart chart = slide.Shapes.AddChart(ChartType.ClusteredBar, 100, 100, 500, 300);

// Lägg till exempeldata
IChartDataWorkbook workbook = chart.ChartData.ChartDataWorkbook;
IChartSeries series = chart.ChartData.Series.Add(workbook.GetCell(0, "A1"), chart.Type);
series.Values.Add(workbook.GetCell(0, "B1"));
series.Values.Add(workbook.GetCell(0, "B2"));

// Ställ in kategorietiketter
chart.ChartData.Categories.Add(workbook.GetCell(0, "A2"));
chart.ChartData.Categories.Add(workbook.GetCell(0, "A3"));

// Ange diagramtitel
chart.ChartTitle.AddTextFrameForOverriding("Sample Chart");
chart.ChartTitle.TextFrameForOverriding.Text = "Sample Chart";

// Spara presentationen
presentation.Save("SampleChart.pptx", SaveFormat.Pptx);
```

Den här koden skapar en PowerPoint-presentation med ett exempel på stapeldiagram.

## Lägga till felstaplar till diagrammet

Låt oss nu lägga till felstaplar i diagrammet. Felstaplar läggs till specifika datapunkter i en serie. Vi lägger till felstaplar till den första datapunkten i vårt exempeldiagram.

```csharp
// Få tillgång till den första serien
IChartSeries firstSeries = chart.ChartData.Series[0];

// Lägg till felfält
IErrorBarsFormat errorBarsFormat = firstSeries.ErrorBarsFormat.Add();
errorBarsFormat.Type = ErrorBarType.FixedValue;

// Ställ in felstapelvärde
errorBarsFormat.Value = 5; // Du kan justera värdet efter dina data

// Spara den uppdaterade presentationen
presentation.Save("ChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Den här koden lägger till felstaplar med fasta värden till den första datapunkten i diagrammet.

## Anpassa felfältsvärden

Du kan anpassa felfältsvärdena för varje datapunkt individuellt. Låt oss modifiera koden för att ställa in olika felvärden för varje datapunkt.

```csharp
// Ställ in anpassade felvärden för varje punkt
double[] errorValues = { 3, 6 }; // Felvärden för de två datapunkterna

for (int i = 0; i < firstSeries.DataPoints.Count; i++)
{
    firstSeries.ErrorBarsFormat[i].Value = errorValues[i];
}

// Spara den uppdaterade presentationen
presentation.Save("CustomErrorValuesChart.pptx", SaveFormat.Pptx);
```

Den här koden ställer in anpassade felvärden för varje datapunkt i serien.

## Styling felfält

Du kan utforma felstaplar för att förbättra deras synlighet och matcha ditt diagrams estetik. Låt oss anpassa utseendet på felfälten.

```csharp
// Anpassa felfältets utseende
errorBarsFormat.LineFormat.Width = 2; // Ställ in linjebredd
errorBarsFormat.LineFormat.SolidFillColor.Color = Color.Red; //Ställ in linjefärg

// Spara den uppdaterade presentationen
presentation.Save("StyledErrorBarsChart.pptx", SaveFormat.Pptx);
```

Den här koden justerar linjebredden och färgen på felfälten.

## Uppdatering av diagramdata

Om du behöver uppdatera sjökortsdata kan du göra det enkelt med Aspose.Slides för .NET. Låt oss ersätta data med nya värden.

```csharp
// Uppdatera diagramdata
series.Values[0].Value = 15;
series.Values[1].Value = 20;

// Spara den uppdaterade presentationen
presentation.Save("UpdatedChartData.pptx", SaveFormat.Pptx);
```

Denna kod uppdaterar värdena för diagramdata.

## Felstaplar för flera serier

Du kan lägga till felstaplar till flera serier i ett diagram. Låt oss lägga till felstaplar till den andra serien i vårt exempeldiagram.

```csharp
// Gå till den andra serien
IChartSeries secondSeries = chart.ChartData.Series[1];

// Lägg till felstaplar i den andra serien
IErrorBarsFormat secondSeriesErrorBars = secondSeries.ErrorBarsFormat.Add();
secondSeriesErrorBars.Type = ErrorBarType.Percent;

// Ställ in felstapelvärde för den andra serien
secondSeriesErrorBars.Value = 10; // Du kan justera värdet

// Spara den uppdaterade presentationen
presentation.Save("MultiSeriesChartWithErrorBars.pptx", SaveFormat.Pptx);
```

Denna kod lägger till felstaplar till den andra serien i diagrammet.

## Hantera negativa och positiva fel

Felstaplar kan representera både positiva och negativa fel. Låt oss ändra koden för att lägga till båda typerna av felstaplar.

```csharp
// Lägg till positiva och negativa felstaplar
errorBarsFormat.Type = ErrorBarType.Custom;
errorBarsFormat.PlusValue = 4; // Positivt felvärde
errorBarsFormat.MinusValue = 2; // Negativt felvärde

// Spara den uppdaterade presentationen
presentation.Save("PositiveNegativeErrorBars.pptx", SaveFormat.Pptx);
```

Den här koden lägger till anpassade positiva och negativa felstaplar till diagrammet.

## Spara och exportera diagrammet

När du har lagt till felstaplar och anpassat ditt diagram kan du spara och exportera det för vidare användning.

```csharp
// Spara det sista diagrammet
presentation.Save("FinalChart.pptx", SaveFormat.Pptx);
```

Denna kod sparar det slutliga diagrammet med felstaplar.

## Slutsats

I den här handledningen undersökte vi hur man lägger till anpassade felstaplar till ett diagram med Aspose.Slides för .NET. Vi täckte att skapa ett exempeldiagram, lägga till felstaplar, anpassa felvärden, utforma felstaplar, uppdatera diagramdata, lägga till felstaplar i flera serier och hantera positiva och negativa fel. Med Aspose.Slides för .NET har du flexibiliteten att skapa informativa och visuellt tilltalande diagram med anpassade felstaplar som effektivt kommunicerar dina datas variabilitet.

## FAQ's

### Hur kan jag justera tjockleken på felstaplar?

 Du kan justera tjockleken på felstaplar genom att ändra`LineFormat.Width` egendom av`ErrorBarsFormat`.

### Kan jag använda olika felvärden för varje datapunkt?

Ja, du kan ställa in anpassade felvärden för varje datapunkt individuellt med hjälp av en loop och`Value` egendom av`ErrorBarsFormat`.

### Är det möjligt att lägga till felstaplar till flera serier i ett enda diagram?

Absolut, du kan lägga till felstaplar till flera serier i samma diagram. Gå bara till önskad serie och använd felfält som visas i artikeln.

### Kan jag ta bort felfält efter att ha lagt till dem?

 Ja, du kan ta bort felfält genom att anropa`Clear` metod på`ErrorBarsFormat` objekt.

### Var kan jag hitta mer information om Aspose.Slides för .NET?

 Du kan hitta detaljerad dokumentation och exempel för Aspose.Slides för .NET på[Aspose dokumentation webbplats](https://reference.aspose.com/slides/net/).