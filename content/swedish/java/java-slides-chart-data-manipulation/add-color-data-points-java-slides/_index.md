---
title: Lägg till färg till datapunkter i Java Slides
linktitle: Lägg till färg till datapunkter i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till färg på datapunkter i Java-bilder med Aspose.Slides för Java.
type: docs
weight: 10
url: /sv/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Introduktion till att lägga till färg till datapunkter i Java Slides

I den här handledningen kommer vi att visa hur man lägger till färg till datapunkter i Java-bilder med Aspose.Slides för Java. Den här steg-för-steg-guiden innehåller källkodsexempel som hjälper dig att utföra denna uppgift.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

- Java utvecklingsmiljö
- Aspose.Slides för Java-bibliotek

## Steg 1: Skapa en ny presentation

Först skapar vi en ny presentation med Aspose.Slides för Java. Denna presentation kommer att fungera som behållaren för vårt diagram.

```java
Presentation pres = new Presentation();
```

## Steg 2: Lägg till ett Sunburst-diagram

Låt oss nu lägga till ett Sunburst-diagram till presentationen. Vi anger diagramtyp, position och storlek.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Steg 3: Få åtkomst till datapunkter

 För att ändra datapunkter i diagrammet måste vi komma åt`IChartDataPointCollection` objekt.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Steg 4: Anpassa datapunkter

I det här steget kommer vi att anpassa specifika datapunkter. Här ändrar vi färgen på datapunkter och konfigurerar etikettinställningar.

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

Slutligen, spara presentationen med det anpassade diagrammet.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Det är allt! Du har framgångsrikt lagt till färg till specifika datapunkter i en Java-bild med Aspose.Slides för Java.

## Komplett källkod för att lägga till färg till datapunkter i Java Slides

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

I den här handledningen lärde du dig hur du lägger till färg på datapunkter i Java-bilder med Aspose.Slides för Java. Du kan ytterligare anpassa dina diagram och presentationer baserat på dina specifika krav.

## FAQ's

### Hur kan jag ändra färgen på andra datapunkter?

För att ändra färgen på andra datapunkter kan du följa ett liknande tillvägagångssätt som visas i steg 4. Gå till den datapunkt som du vill anpassa och ändra dess färg- och etikettinställningar.

### Kan jag anpassa andra aspekter av diagrammet?

 Ja, du kan anpassa olika aspekter av diagrammet, inklusive typsnitt, etiketter, titlar och mer. Referera till[Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/) för detaljerade anpassningsalternativ.

### Var kan jag hitta fler exempel och dokumentation?

 Du kan hitta fler exempel och detaljerad dokumentation om hur du använder Aspose.Slides för Java på[Aspose.Slides dokumentation](https://reference.aspose.com/slides/java/) hemsida.