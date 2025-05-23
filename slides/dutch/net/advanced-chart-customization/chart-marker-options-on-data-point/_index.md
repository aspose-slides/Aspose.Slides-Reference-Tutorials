---
"description": "Leer hoe u uw PowerPoint-grafieken kunt verbeteren met Aspose.Slides voor .NET. Pas markeringen voor datapunten aan met afbeeldingen. Maak boeiende presentaties."
"linktitle": "Grafiekmarkeringsopties op gegevenspunt"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Grafiekmarkeringsopties gebruiken op gegevenspunten in Aspose.Slides .NET"
"url": "/nl/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafiekmarkeringsopties gebruiken op gegevenspunten in Aspose.Slides .NET


Bij het werken met presentaties en datavisualisatie biedt Aspose.Slides voor .NET een breed scala aan krachtige functies om grafieken te maken, aan te passen en te bewerken. In deze tutorial onderzoeken we hoe u grafiekmarkeringsopties op datapunten kunt gebruiken om uw grafiekpresentaties te verbeteren. Deze stapsgewijze handleiding leidt u door het proces, beginnend bij de vereisten en het importeren van naamruimten, tot het opsplitsen van elk voorbeeld in meerdere stappen.

## Vereisten

Voordat we ingaan op het gebruik van grafiekmarkeringsopties voor datapunten, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

- Aspose.Slides voor .NET: Zorg ervoor dat je Aspose.Slides voor .NET hebt geïnstalleerd. Je kunt het downloaden van de [website](https://releases.aspose.com/slides/net/).

- Voorbeeldpresentatie: Voor deze tutorial gebruiken we een voorbeeldpresentatie met de naam 'Test.pptx'. Deze presentatie zou in uw documentenmap moeten staan.

Laten we beginnen met het importeren van de benodigde naamruimten.

## Naamruimten importeren

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

We hebben de vereiste naamruimten geïmporteerd en onze presentatie geïnitialiseerd. Laten we nu de opties voor diagrammarkeringen op datapunten gebruiken.

## Stap 1: De standaardgrafiek maken

```csharp

// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Het standaarddiagram maken
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

We maken een standaardgrafiek van het type 'LijnMetMarkeringen' op de dia op een bepaalde locatie en in een bepaald formaat.

## Stap 2: De standaardindex voor grafiekgegevensbladen ophalen

```csharp
// De standaardindex voor grafiekgegevens ophalen
int defaultWorksheetIndex = 0;
```

Hier verkrijgen we de index van het standaard grafiekgegevensblad.

## Stap 3: Het werkblad met grafiekgegevens ophalen

```csharp
// Het werkblad met grafiekgegevens ophalen
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

We halen de werkmap met grafiekgegevens op om met grafiekgegevens te werken.

## Stap 4: De grafiekreeks wijzigen

```csharp
// Demoserie verwijderen
chart.ChartData.Series.Clear();

// Nieuwe serie toevoegen
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

In deze stap verwijderen we alle bestaande demoseries en voegen we een nieuwe serie met de naam 'Serie 1' toe aan de grafiek.

## Stap 5: Afbeeldingsvulling voor gegevenspunten instellen

```csharp
// Stel de afbeelding in voor de markeringen
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Neem de eerste grafiekserie
IChartSeries series = chart.ChartData.Series[0];

// Nieuwe datapunten toevoegen met afbeeldingsvulling
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

We plaatsen beeldmarkeringen voor datapunten, zodat u zelf kunt bepalen hoe elk datapunt op de grafiek wordt weergegeven.

## Stap 6: De grootte van de grafiekreeksmarkering wijzigen

```csharp
// De grootte van de grafiekreeksmarkering wijzigen
series.Marker.Size = 15;
```

Hier passen we de grootte van de grafiekseriemarkering aan om deze visueel aantrekkelijk te maken.

## Stap 7: De presentatie opslaan

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Ten slotte slaan we de presentatie op met de nieuwe grafiekinstellingen.

## Conclusie

Met Aspose.Slides voor .NET kunt u verbluffende grafiekpresentaties maken met diverse aanpassingsmogelijkheden. In deze tutorial hebben we ons gericht op het gebruik van grafiekmarkeringen op datapunten om de visuele weergave van uw gegevens te verbeteren. Met Aspose.Slides voor .NET tilt u uw presentaties naar een hoger niveau en maakt u ze aantrekkelijker en informatiever.

Als u vragen hebt of hulp nodig hebt met Aspose.Slides voor .NET, kunt u gerust de website bezoeken [Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/) of neem contact op met de [Aspose-gemeenschap](https://forum.aspose.com/) voor ondersteuning.

## Veelgestelde vragen (FAQ's)

### Kan ik aangepaste afbeeldingen gebruiken als markeringen voor datapunten in Aspose.Slides voor .NET?
Ja, u kunt aangepaste afbeeldingen gebruiken als markeringen voor datapunten in Aspose.Slides voor .NET, zoals in deze tutorial wordt gedemonstreerd.

### Hoe kan ik het grafiektype in Aspose.Slides voor .NET wijzigen?
U kunt het grafiektype wijzigen door een ander type op te geven `ChartType` bij het maken van de grafiek, zoals 'Staaf', 'Cirkel' of 'Vlak'.

### Is Aspose.Slides voor .NET compatibel met de nieuwste versies van PowerPoint?
Aspose.Slides voor .NET is ontworpen om te werken met verschillende PowerPoint-indelingen en wordt regelmatig bijgewerkt om de compatibiliteit met de nieuwste PowerPoint-versies te behouden.

### Waar kan ik meer tutorials en bronnen vinden voor Aspose.Slides voor .NET?
U kunt aanvullende tutorials en bronnen bekijken in de [Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/).

### Is er een proefversie van Aspose.Slides voor .NET beschikbaar?
Ja, u kunt Aspose.Slides voor .NET uitproberen door een gratis proefversie te downloaden van [hier](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}