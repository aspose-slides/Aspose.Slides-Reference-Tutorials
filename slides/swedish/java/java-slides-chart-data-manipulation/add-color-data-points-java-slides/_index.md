---
"description": "Lär dig hur du lägger till färg till datapunkter i Java-bilder med hjälp av Aspose.Slides för Java."
"linktitle": "Lägg till färg till datapunkter i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägg till färg till datapunkter i Java-bilder"
"url": "/sv/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till färg till datapunkter i Java-bilder


## Introduktion till att lägga till färg till datapunkter i Java-bilder

I den här handledningen visar vi hur man lägger till färg till datapunkter i Java-bilder med hjälp av Aspose.Slides för Java. Den här steg-för-steg-guiden innehåller exempel på källkod som hjälper dig att utföra denna uppgift.

## Förkunskapskrav

Innan du börjar, se till att du har följande förutsättningar på plats:

- Java-utvecklingsmiljö
- Aspose.Slides för Java-biblioteket

## Steg 1: Skapa en ny presentation

Först skapar vi en ny presentation med Aspose.Slides för Java. Denna presentation kommer att fungera som behållare för vårt diagram.

```java
Presentation pres = new Presentation();
```

## Steg 2: Lägg till ett solstrålediagram

Nu ska vi lägga till ett Sunburst-diagram i presentationen. Vi anger diagrammets typ, position och storlek.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Steg 3: Åtkomst till datapunkter

För att ändra datapunkter i diagrammet behöver vi komma åt `IChartDataPointCollection` objekt.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Steg 4: Anpassa datapunkter

I det här steget anpassar vi specifika datapunkter. Här ändrar vi färgen på datapunkterna och konfigurerar etikettinställningar.

```java
// Anpassa datapunkt 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Anpassa datapunkt 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Steg 5: Spara presentationen

Spara slutligen presentationen med det anpassade diagrammet.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Det var allt! Du har lyckats lägga till färg till specifika datapunkter i en Java-bild med hjälp av Aspose.Slides för Java.

## Komplett källkod för att lägga till färg till datapunkter i Java-bilder

```java
Presentation pres = new Presentation();
try
{
	// Sökvägen till dokumentkatalogen.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//ATT GÖRA
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

I den här handledningen lärde du dig hur du lägger till färg till datapunkter i Java-bilder med hjälp av Aspose.Slides för Java. Du kan ytterligare anpassa dina diagram och presentationer baserat på dina specifika behov.

## Vanliga frågor

### Hur kan jag ändra färgen på andra datapunkter?

För att ändra färgen på andra datapunkter kan du följa en liknande metod som visas i steg 4. Gå till den datapunkt du vill anpassa och ändra dess färg- och etikettinställningar.

### Kan jag anpassa andra aspekter av diagrammet?

Ja, du kan anpassa olika aspekter av diagrammet, inklusive teckensnitt, etiketter, titlar med mera. Se [Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/) för detaljerade anpassningsalternativ.

### Var kan jag hitta fler exempel och dokumentation?

Du hittar fler exempel och detaljerad dokumentation om hur du använder Aspose.Slides för Java på [Aspose.Slides-dokumentation](https://reference.aspose.com/slides/java/) webbplats.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}