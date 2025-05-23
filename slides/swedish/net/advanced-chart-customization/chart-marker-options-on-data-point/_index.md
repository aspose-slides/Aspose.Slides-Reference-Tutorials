---
"description": "Lär dig hur du förbättrar dina PowerPoint-diagram med Aspose.Slides för .NET. Anpassa datapunktmarkörer med bilder. Skapa engagerande presentationer."
"linktitle": "Alternativ för diagrammarkörer på datapunkt"
"second_title": "Aspose.Slides .NET PowerPoint-bearbetnings-API"
"title": "Använda diagrammarköralternativ på datapunkt i Aspose.Slides .NET"
"url": "/sv/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Använda diagrammarköralternativ på datapunkt i Aspose.Slides .NET


När du arbetar med presentationer och datavisualisering erbjuder Aspose.Slides för .NET ett brett utbud av kraftfulla funktioner för att skapa, anpassa och manipulera diagram. I den här handledningen kommer vi att utforska hur du använder diagrammarköralternativ på datapunkter för att förbättra dina diagrampresentationer. Den här steg-för-steg-guiden guidar dig genom processen, från förutsättningarna och import av namnrymder till att dela upp varje exempel i flera steg.

## Förkunskapskrav

Innan vi går in på att använda diagrammarköralternativ på datapunkter, se till att du har följande förutsättningar på plats:

- Aspose.Slides för .NET: Se till att du har Aspose.Slides för .NET installerat. Du kan ladda ner det från [webbplats](https://releases.aspose.com/slides/net/).

- Exempelpresentation: I den här handledningen använder vi en exempelpresentation med namnet "Test.pptx". Du bör ha den här presentationen i din dokumentkatalog.

Nu börjar vi med att importera de nödvändiga namnrymderna.

## Importera namnrymder

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Vi har importerat de namnrymder som krävs och initierat vår presentation. Nu ska vi fortsätta med att använda diagrammarköralternativ på datapunkter.

## Steg 1: Skapa standarddiagrammet

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Skapa standarddiagrammet
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Vi skapar ett standarddiagram av typen "LineWithMarkers" på bilden på en angiven plats och i en angiven storlek.

## Steg 2: Hämta standardindex för diagramdata

```csharp
// Hämta standardindex för diagramdatakalkylblad
int defaultWorksheetIndex = 0;
```

Här hämtar vi indexet för standarddiagramdataarket.

## Steg 3: Hämta diagramdataarket

```csharp
// Hämta diagramdataarbetsbladet
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Vi hämtar arbetsboken för diagramdata för att arbeta med diagramdata.

## Steg 4: Ändra diagramserien

```csharp
// Ta bort demoserien
chart.ChartData.Series.Clear();

// Lägg till ny serie
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

I det här steget tar vi bort alla befintliga demoserier och lägger till en ny serie med namnet "Serie 1" i diagrammet.

## Steg 5: Ställa in bildfyllning för datapunkter

```csharp
// Ställ in bilden för markörerna
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Ta den första diagramserien
IChartSeries series = chart.ChartData.Series[0];

// Lägg till nya datapunkter med bildfyllning
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Vi ställer in bildmarkörer för datapunkter, så att du kan anpassa hur varje datapunkt visas i diagrammet.

## Steg 6: Ändra storleken på markören för diagramserien

```csharp
// Ändra storleken på markören för diagramserien
series.Marker.Size = 15;
```

Här justerar vi storleken på diagramseriemarkören för att göra den visuellt tilltalande.

## Steg 7: Spara presentationen

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Slutligen sparar vi presentationen med de nya diagraminställningarna.

## Slutsats

Aspose.Slides för .NET ger dig möjlighet att skapa fantastiska diagrampresentationer med olika anpassningsalternativ. I den här handledningen fokuserade vi på att använda diagrammarkörer på datapunkter för att förbättra den visuella representationen av dina data. Med Aspose.Slides för .NET kan du ta dina presentationer till nästa nivå och göra dem mer engagerande och informativa.

Om du har några frågor eller behöver hjälp med Aspose.Slides för .NET, besök gärna [Aspose.Slides-dokumentation](https://reference.aspose.com/slides/net/) eller kontakta [Aspose-gemenskapen](https://forum.aspose.com/) för stöd.

## Vanliga frågor (FAQ)

### Kan jag använda anpassade bilder som markörer för datapunkter i Aspose.Slides för .NET?
Ja, du kan använda anpassade bilder som markörer för datapunkter i Aspose.Slides för .NET, vilket visas i den här handledningen.

### Hur kan jag ändra diagramtypen i Aspose.Slides för .NET?
Du kan ändra diagramtypen genom att ange en annan `ChartType` när du skapar diagrammet, till exempel "Stapel", "Cirkel" eller "Area".

### Är Aspose.Slides för .NET kompatibelt med de senaste versionerna av PowerPoint?
Aspose.Slides för .NET är utformat för att fungera med olika PowerPoint-format och uppdateras regelbundet för att bibehålla kompatibilitet med de senaste PowerPoint-versionerna.

### Var kan jag hitta fler handledningar och resurser för Aspose.Slides för .NET?
Du kan utforska ytterligare handledningar och resurser i [Aspose.Slides-dokumentation](https://reference.aspose.com/slides/net/).

### Finns det en testversion av Aspose.Slides för .NET tillgänglig?
Ja, du kan prova Aspose.Slides för .NET genom att ladda ner en gratis testversion från [här](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}