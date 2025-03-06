---
title: Använda diagrammarkeringsalternativ på datapunkt i Aspose.Slides .NET
linktitle: Kartmarköralternativ på datapunkt
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Lär dig hur du förbättrar dina PowerPoint-diagram med Aspose.Slides för .NET. Anpassa datapunktsmarkörer med bilder. Skapa engagerande presentationer.
weight: 11
url: /sv/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Använda diagrammarkeringsalternativ på datapunkt i Aspose.Slides .NET


När du arbetar med presentationer och datavisualisering erbjuder Aspose.Slides för .NET ett brett utbud av kraftfulla funktioner för att skapa, anpassa och manipulera diagram. I den här självstudien kommer vi att utforska hur du använder diagrammarkeringsalternativ på datapunkter för att förbättra dina diagrampresentationer. Den här steg-för-steg-guiden leder dig genom processen, med början från förutsättningarna och import av namnrymder, till att dela upp varje exempel i flera steg.

## Förutsättningar

Innan vi dyker in i att använda diagrammarkeringsalternativ på datapunkter, se till att du har följande förutsättningar på plats:

-  Aspose.Slides för .NET: Se till att du har Aspose.Slides för .NET installerat. Du kan ladda ner den från[hemsida](https://releases.aspose.com/slides/net/).

- Exempelpresentation: För den här handledningen använder vi en exempelpresentation med namnet "Test.pptx." Du bör ha denna presentation i din dokumentkatalog.

Låt oss nu börja med att importera de nödvändiga namnrymden.

## Importera namnområden

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Vi har importerat de nödvändiga namnrymden och initierat vår presentation. Låt oss nu fortsätta att använda diagrammarkeringsalternativ på datapunkter.

## Steg 1: Skapa standarddiagrammet

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Skapar standarddiagrammet
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Vi skapar ett standarddiagram av typen "LineWithMarkers" på bilden på en angiven plats och storlek.

## Steg 2: Hämta standarddiagrammets kalkylbladsindex

```csharp
// Hämta standarddiagrammets kalkylbladsindex
int defaultWorksheetIndex = 0;
```

Här får vi indexet för standarddiagramdatakalkylbladet.

## Steg 3: Skaffa arbetsbladet för diagramdata

```csharp
// Hämta arbetsbladet för diagramdata
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Vi hämtar arbetsboken för diagramdata för att arbeta med diagramdata.

## Steg 4: Ändra sjökortsserien

```csharp
// Ta bort demoserier
chart.ChartData.Series.Clear();

// Lägg till nya serier
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

I det här steget tar vi bort alla befintliga demoserier och lägger till en ny serie med namnet "Serie 1" till diagrammet.

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

## Steg 6: Ändra storleken på diagramseriens markör

```csharp
// Ändra storleken på kartseriens markör
series.Marker.Size = 15;
```

Här justerar vi storleken på diagramseriemarkören för att göra den visuellt tilltalande.

## Steg 7: Spara presentationen

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Slutligen sparar vi presentationen med de nya diagraminställningarna.

## Slutsats

Aspose.Slides för .NET ger dig möjlighet att skapa fantastiska diagrampresentationer med olika anpassningsalternativ. I den här handledningen fokuserade vi på att använda diagrammarkeringsalternativ på datapunkter för att förbättra den visuella representationen av dina data. Med Aspose.Slides för .NET kan du ta dina presentationer till nästa nivå och göra dem mer engagerande och informativa.

Om du har några frågor eller behöver hjälp med Aspose.Slides för .NET, besök gärna[Aspose.Slides dokumentation](https://reference.aspose.com/slides/net/) eller nå ut till[Aspose gemenskap](https://forum.aspose.com/) för support.

## Vanliga frågor (FAQs)

### Kan jag använda anpassade bilder som markörer för datapunkter i Aspose.Slides för .NET?
Ja, du kan använda anpassade bilder som markörer för datapunkter i Aspose.Slides för .NET, som visas i denna handledning.

### Hur kan jag ändra diagramtypen i Aspose.Slides för .NET?
 Du kan ändra diagramtypen genom att ange en annan`ChartType` när du skapar diagrammet, t.ex. "Bar", "Pair" eller "Area".

### Är Aspose.Slides för .NET kompatibelt med de senaste versionerna av PowerPoint?
Aspose.Slides för .NET är utformad för att fungera med olika PowerPoint-format och uppdateras regelbundet för att bibehålla kompatibiliteten med de senaste PowerPoint-versionerna.

### Var kan jag hitta fler handledningar och resurser för Aspose.Slides för .NET?
 Du kan utforska ytterligare handledningar och resurser i[Aspose.Slides dokumentation](https://reference.aspose.com/slides/net/).

### Finns det en testversion av Aspose.Slides för .NET tillgänglig?
 Ja, du kan prova Aspose.Slides för .NET genom att ladda ner en gratis testversion från[här](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
