---
title: Haal de breedte en hoogte uit het diagramplotgebied in Java-dia's
linktitle: Haal de breedte en hoogte uit het diagramplotgebied in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u de dimensies van het diagramplotgebied kunt ophalen in Java Slides met behulp van Aspose.Slides voor Java. Verbeter uw PowerPoint-automatiseringsvaardigheden.
weight: 21
url: /nl/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Haal de breedte en hoogte uit het diagramplotgebied in Java-dia's


## Invoering

Grafieken zijn een krachtige manier om gegevens in PowerPoint-presentaties te visualiseren. Soms moet u om verschillende redenen de afmetingen van het plotgebied van een diagram weten, zoals het wijzigen van de grootte of het verplaatsen van elementen in het diagram. In deze handleiding wordt gedemonstreerd hoe u de breedte en hoogte van het plotgebied kunt verkrijgen met behulp van Java en Aspose.Slides voor Java.

## Vereisten

 Voordat we in de code duiken, moet u ervoor zorgen dat de Aspose.Slides voor Java-bibliotheek is geïnstalleerd en ingesteld in uw Java-project. U kunt de bibliotheek downloaden van de Aspose-website[hier](https://releases.aspose.com/slides/java/).

## Stap 1: De omgeving instellen

Zorg ervoor dat de Aspose.Slides voor Java-bibliotheek aan uw Java-project is toegevoegd. U kunt dit doen door de bibliotheek op te nemen in de afhankelijkheden van uw project of door het JAR-bestand handmatig toe te voegen.

## Stap 2: Een PowerPoint-presentatie maken

Laten we beginnen met het maken van een PowerPoint-presentatie en het toevoegen van een dia eraan. Dit zal dienen als de container voor onze kaart.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Vervangen`"Your Document Directory"` met het pad naar uw documentmap.

## Stap 3: Een diagram toevoegen

Laten we nu een geclusterd kolomdiagram aan de dia toevoegen. We zullen ook de kaartindeling valideren.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Met deze code wordt een geclusterd kolomdiagram gemaakt op positie (100, 100) met dimensies (500, 350).

## Stap 4: De afmetingen van het plotgebied verkrijgen

Om de breedte en hoogte van het plotgebied van de grafiek op te halen, kunnen we de volgende code gebruiken:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Nu de variabelen`x`, `y`, `w` , En`h` bevatten de respectieve waarden voor de X-coördinaat, Y-coördinaat, breedte en hoogte van het plotgebied.

## Stap 5: De presentatie opslaan

Sla ten slotte de presentatie op met het diagram.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Zorg ervoor dat u vervangt`"Chart_out.pptx"` met de gewenste uitvoerbestandsnaam.

## Volledige broncode voor het verkrijgen van breedte en hoogte uit het diagramplotgebied in Java-dia's

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
	// Presentatie opslaan met grafiek
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In dit artikel hebben we besproken hoe u de breedte en hoogte van het plotgebied van een diagram in Java Slides kunt verkrijgen met behulp van de Aspose.Slides voor Java API. Deze informatie kan waardevol zijn wanneer u de lay-out van uw diagrammen binnen PowerPoint-presentaties dynamisch moet aanpassen.

## Veelgestelde vragen

### Hoe kan ik het diagramtype wijzigen in iets anders dan geclusterde kolommen?

 U kunt het diagramtype wijzigen door te vervangen`ChartType.ClusteredColumn` met de gewenste opsomming van het diagramtype, zoals`ChartType.Line` of`ChartType.Pie`.

### Kan ik andere eigenschappen van het diagram wijzigen?

Ja, u kunt verschillende eigenschappen van het diagram wijzigen, zoals gegevens, labels en opmaak, met behulp van de Aspose.Slides voor Java API. Raadpleeg de documentatie voor meer details.

### Is Aspose.Slides voor Java geschikt voor professionele PowerPoint-automatisering?

Ja, Aspose.Slides voor Java is een krachtige bibliotheek voor het automatiseren van PowerPoint-taken in Java-toepassingen. Het biedt uitgebreide functies voor het werken met presentaties, dia's, vormen, grafieken en meer.

### Hoe kan ik meer te weten komen over Aspose.Slides voor Java?

 Uitgebreide documentatie en voorbeelden vindt u op de documentatiepagina Aspose.Slides voor Java[hier](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
