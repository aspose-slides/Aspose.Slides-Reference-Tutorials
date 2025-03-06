---
title: Grafiekmarkeringsopties op gegevenspunt in Java-dia's
linktitle: Grafiekmarkeringsopties op gegevenspunt in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Optimaliseer uw Java-dia's met aangepaste diagrammarkeringsopties. Leer hoe u datapunten visueel kunt verbeteren met Aspose.Slides voor Java. Ontdek stapsgewijze begeleiding en veelgestelde vragen.
weight: 14
url: /nl/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Inleiding tot opties voor diagrammarkeringen op gegevenspunten in Java-dia's

Als het gaat om het maken van indrukwekkende presentaties, kan de mogelijkheid om diagrammarkeringen op gegevenspunten aan te passen en te manipuleren het verschil maken. Met Aspose.Slides voor Java beschikt u over de mogelijkheid om uw diagrammen om te zetten in dynamische en visueel aantrekkelijke elementen.

## Vereisten

Voordat we ingaan op het codeergedeelte, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

- Java-ontwikkelomgeving
- Aspose.Slides voor Java-bibliotheek
- Een Java Integrated Development Environment (IDE)
- Voorbeeldpresentatiedocument (bijvoorbeeld "Test.pptx")

## Stap 1: De omgeving instellen

Zorg er eerst voor dat u de benodigde tools geïnstalleerd en gereed hebt. Maak een Java-project in uw IDE en importeer de Aspose.Slides voor Java-bibliotheek.

## Stap 2: De presentatie laden

Laad uw voorbeeldpresentatiedocument om aan de slag te gaan. In de opgegeven code gaan we ervan uit dat het document de naam 'Test.pptx' heeft.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## Stap 3: Een diagram maken

Laten we nu een diagram in de presentatie maken. In dit voorbeeld gebruiken we een lijndiagram met markeringen.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## Stap 4: Werken met grafiekgegevens

Om diagramgegevens te manipuleren, moeten we toegang hebben tot de diagramgegevenswerkmap en de gegevensreeksen voorbereiden. We wissen de standaardreeksen en voegen onze aangepaste gegevens toe.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## Stap 5: Aangepaste markeringen toevoegen

Hier komt het spannende gedeelte: het aanpassen van de markeringen op datapunten. In dit voorbeeld gebruiken we afbeeldingen als markeringen.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Aangepaste markeringen toevoegen aan gegevenspunten
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Herhaal dit voor andere gegevenspunten
// ...

// De grootte van de markering van de kaartserie wijzigen
series.getMarker().setSize(15);
```

## Stap 6: De presentatie opslaan

Nadat u uw kaartmarkeringen heeft aangepast, slaat u de presentatie op om de wijzigingen in actie te zien.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Volledige broncode voor diagrammarkeringsopties op gegevenspunt in Java-dia's

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Het standaarddiagram maken
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//De standaard werkbladindex voor diagramgegevens ophalen
int defaultWorksheetIndex = 0;
//Het werkblad met diagramgegevens ophalen
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Demoserie verwijderen
chart.getChartData().getSeries().clear();
//Nieuwe serie toevoegen
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Stel de afbeelding in
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Stel de afbeelding in
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Neem de eerste kaartenserie
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Voeg daar een nieuw punt (1:3) toe.
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//De kaartreeksmarkering wijzigen
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Conclusie

Met Aspose.Slides voor Java kunt u uw presentaties naar een hoger niveau tillen door diagrammarkeringen op gegevenspunten aan te passen. Hierdoor kunt u visueel verbluffende en informatieve dia's maken die uw publiek boeien.

## Veelgestelde vragen

### Hoe kan ik de markeringsgrootte voor gegevenspunten wijzigen?

 Om de markeringsgrootte voor gegevenspunten te wijzigen, gebruikt u de`series.getMarker().setSize()` methode en geef de gewenste grootte op als argument.

### Kan ik afbeeldingen gebruiken als aangepaste markeringen?

 Ja, u kunt afbeeldingen gebruiken als aangepaste markeringen voor gegevenspunten. Stel het vultype in op`FillType.Picture` en geef de afbeelding op die u wilt gebruiken.

### Is Aspose.Slides voor Java geschikt voor het maken van dynamische grafieken?

Absoluut! Aspose.Slides voor Java biedt uitgebreide mogelijkheden voor het maken van dynamische en interactieve grafieken in uw presentaties.

### Kan ik andere aspecten van het diagram aanpassen met Aspose.Slides?

Ja, u kunt verschillende aspecten van het diagram aanpassen, waaronder titels, assen, gegevenslabels en meer, met behulp van Aspose.Slides voor Java.

### Waar kan ik toegang krijgen tot de Aspose.Slides voor Java-documentatie en -downloads?

 U kunt de documentatie vinden op[hier](https://reference.aspose.com/slides/java/) en download de bibliotheek op[hier](https://releases.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
