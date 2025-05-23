---
"description": "Leer hoe u de afmetingen van een grafiekgebied in Java Slides kunt ophalen met Aspose.Slides voor Java. Verbeter uw vaardigheden in PowerPoint-automatisering."
"linktitle": "Breedte en hoogte ophalen uit grafiekgebied in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Breedte en hoogte ophalen uit grafiekgebied in Java-dia's"
"url": "/nl/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Breedte en hoogte ophalen uit grafiekgebied in Java-dia's


## Invoering

Grafieken zijn een krachtige manier om gegevens in PowerPoint-presentaties te visualiseren. Soms moet u om verschillende redenen de afmetingen van het tekengebied van een grafiek weten, bijvoorbeeld om de grootte of positie van elementen in de grafiek aan te passen. Deze handleiding laat zien hoe u de breedte en hoogte van het tekengebied kunt bepalen met behulp van Java en Aspose.Slides voor Java.

## Vereisten

Voordat we in de code duiken, moet je ervoor zorgen dat je de Aspose.Slides voor Java-bibliotheek hebt geïnstalleerd en ingesteld in je Java-project. Je kunt de bibliotheek downloaden van de Aspose-website. [hier](https://releases.aspose.com/slides/java/).

## Stap 1: De omgeving instellen

Zorg ervoor dat de Aspose.Slides voor Java-bibliotheek aan je Java-project is toegevoegd. Je kunt dit doen door de bibliotheek op te nemen in de afhankelijkheden van je project of door het JAR-bestand handmatig toe te voegen.

## Stap 2: Een PowerPoint-presentatie maken

Laten we beginnen met het maken van een PowerPoint-presentatie en er een dia aan toevoegen. Deze dient als container voor onze grafiek.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Vervangen `"Your Document Directory"` met het pad naar uw documentenmap.

## Stap 3: Een grafiek toevoegen

Laten we nu een geclusterde kolomgrafiek aan de dia toevoegen. We zullen ook de lay-out van de grafiek valideren.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Deze code maakt een geclusterde kolomgrafiek op positie (100, 100) met dimensies (500, 350).

## Stap 4: De afmetingen van het perceel verkrijgen

Om de breedte en hoogte van het grafiekgebied op te halen, kunnen we de volgende code gebruiken:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Nu, de variabelen `x`, `y`, `w`, En `h` bevatten de respectievelijke waarden voor de X-coördinaat, Y-coördinaat, breedte en hoogte van het plotgebied.

## Stap 5: De presentatie opslaan

Sla ten slotte de presentatie met de grafiek op.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Zorg ervoor dat u vervangt `"Chart_out.pptx"` met de gewenste naam voor het uitvoerbestand.

## Volledige broncode voor het verkrijgen van breedte en hoogte uit het grafiekgebied in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Presentatie met grafiek opslaan
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In dit artikel hebben we besproken hoe u de breedte en hoogte van het tekengebied van een grafiek in Java Slides kunt bepalen met behulp van de Aspose.Slides voor Java API. Deze informatie kan nuttig zijn wanneer u de lay-out van uw grafieken in PowerPoint-presentaties dynamisch wilt aanpassen.

## Veelgestelde vragen

### Hoe kan ik het grafiektype wijzigen naar iets anders dan geclusterde kolommen?

U kunt het grafiektype wijzigen door `ChartType.ClusteredColumn` met de gewenste grafiektype-opsomming, zoals `ChartType.Line` of `ChartType.Pie`.

### Kan ik andere eigenschappen van de grafiek wijzigen?

Ja, u kunt verschillende eigenschappen van de grafiek, zoals gegevens, labels en opmaak, wijzigen met de Aspose.Slides voor Java API. Raadpleeg de documentatie voor meer informatie.

### Is Aspose.Slides voor Java geschikt voor professionele PowerPoint-automatisering?

Ja, Aspose.Slides voor Java is een krachtige bibliotheek voor het automatiseren van PowerPoint-taken in Java-applicaties. Het biedt uitgebreide functies voor het werken met presentaties, dia's, vormen, grafieken en meer.

### Hoe kan ik meer te weten komen over Aspose.Slides voor Java?

Uitgebreide documentatie en voorbeelden vindt u op de Aspose.Slides voor Java-documentatiepagina [hier](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}