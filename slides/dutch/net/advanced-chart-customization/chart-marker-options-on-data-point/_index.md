---
title: Grafiekmarkeringsopties gebruiken op gegevenspunten in Aspose.Slides .NET
linktitle: Grafiekmarkeringsopties op gegevenspunt
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u uw PowerPoint-grafieken kunt verbeteren met Aspose.Slides voor .NET. Pas datapuntmarkeringen aan met afbeeldingen. Maak boeiende presentaties.
weight: 11
url: /nl/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Bij het werken met presentaties en gegevensvisualisatie biedt Aspose.Slides voor .NET een breed scala aan krachtige functies voor het maken, aanpassen en manipuleren van diagrammen. In deze zelfstudie onderzoeken we hoe u diagrammarkeringsopties op gegevenspunten kunt gebruiken om uw diagrampresentaties te verbeteren. Deze stapsgewijze handleiding leidt u door het proces, beginnend bij de vereisten en het importeren van naamruimten, tot het opsplitsen van elk voorbeeld in meerdere stappen.

## Vereisten

Voordat we dieper ingaan op het gebruik van kaartmarkeringsopties voor gegevenspunten, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

-  Aspose.Slides voor .NET: Zorg ervoor dat Aspose.Slides voor .NET is geïnstalleerd. Je kunt het downloaden van de[website](https://releases.aspose.com/slides/net/).

- Voorbeeldpresentatie: voor deze zelfstudie gebruiken we een voorbeeldpresentatie met de naam 'Test.pptx'. U zou deze presentatie in uw documentmap moeten hebben.

Laten we nu beginnen met het importeren van de benodigde naamruimten.

## Naamruimten importeren

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

We hebben de vereiste naamruimten geïmporteerd en onze presentatie geïnitialiseerd. Laten we nu verder gaan met het gebruiken van diagrammarkeringsopties voor gegevenspunten.

## Stap 1: Het standaarddiagram maken

```csharp

// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Het standaarddiagram maken
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

We maken een standaarddiagram van het type "LineWithMarkers" op de dia op een opgegeven locatie en grootte.

## Stap 2: De standaard werkbladindex voor diagramgegevens verkrijgen

```csharp
// De standaard werkbladindex voor diagramgegevens ophalen
int defaultWorksheetIndex = 0;
```

Hier verkrijgen we de index van het standaard werkblad met grafiekgegevens.

## Stap 3: Het werkblad met grafiekgegevens ophalen

```csharp
// Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

We halen de werkmap met diagramgegevens op om met diagramgegevens te werken.

## Stap 4: De kaartreeks wijzigen

```csharp
// Demoserie verwijderen
chart.ChartData.Series.Clear();

// Nieuwe serie toevoegen
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

In deze stap verwijderen we alle bestaande demoseries en voegen we een nieuwe serie met de naam 'Serie 1' toe aan het diagram.

## Stap 5: Afbeeldingsvulling voor gegevenspunten instellen

```csharp
// Stel de afbeelding voor de markeringen in
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Neem de eerste kaartenserie
IChartSeries series = chart.ChartData.Series[0];

// Voeg nieuwe gegevenspunten toe met afbeeldingsvulling
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

We stellen afbeeldingsmarkeringen in voor gegevenspunten, zodat u kunt aanpassen hoe elk gegevenspunt in de grafiek wordt weergegeven.

## Stap 6: De maat van de markering van de kaartserie wijzigen

```csharp
// De grootte van de markering van de kaartserie wijzigen
series.Marker.Size = 15;
```

Hier passen we de grootte van de kaartseriemarkering aan om deze visueel aantrekkelijk te maken.

## Stap 7: De presentatie opslaan

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Ten slotte slaan we de presentatie op met de nieuwe grafiekinstellingen.

## Conclusie

Met Aspose.Slides voor .NET kunt u verbluffende grafiekpresentaties maken met verschillende aanpassingsopties. In deze zelfstudie hebben we ons gericht op het gebruik van diagrammarkeringsopties op gegevenspunten om de visuele weergave van uw gegevens te verbeteren. Met Aspose.Slides voor .NET kunt u uw presentaties naar een hoger niveau tillen, waardoor ze aantrekkelijker en informatiever worden.

Als u vragen heeft of hulp nodig heeft met Aspose.Slides voor .NET, bezoek dan gerust de[Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/) of neem contact op met de[Stel gemeenschap](https://forum.aspose.com/) Voor ondersteuning.

## Veelgestelde vragen (FAQ's)

### Kan ik aangepaste afbeeldingen gebruiken als markeringen voor gegevenspunten in Aspose.Slides voor .NET?
Ja, u kunt aangepaste afbeeldingen gebruiken als markeringen voor gegevenspunten in Aspose.Slides voor .NET, zoals gedemonstreerd in deze zelfstudie.

### Hoe kan ik het diagramtype in Aspose.Slides voor .NET wijzigen?
 U kunt het diagramtype wijzigen door een ander diagramtype op te geven`ChartType` bij het maken van het diagram, zoals 'Bar', 'Taart' of 'Gebied'.

### Is Aspose.Slides voor .NET compatibel met de nieuwste versies van PowerPoint?
Aspose.Slides voor .NET is ontworpen om met verschillende PowerPoint-formaten te werken en wordt regelmatig bijgewerkt om de compatibiliteit met de nieuwste PowerPoint-versies te behouden.

### Waar kan ik meer tutorials en bronnen vinden voor Aspose.Slides voor .NET?
 U kunt aanvullende zelfstudies en bronnen verkennen in de[Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/).

### Is er een proefversie van Aspose.Slides voor .NET beschikbaar?
 Ja, u kunt Aspose.Slides voor .NET uitproberen door een gratis proefversie te downloaden van[hier](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
