---
title: Lägg till anpassat fel i Java Slides
linktitle: Lägg till anpassat fel i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till anpassade felstaplar till PowerPoint-diagram i Java Slides med Aspose.Slides. Steg-för-steg guide med källkod för exakt datavisualisering.
type: docs
weight: 11
url: /sv/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Introduktion till att lägga till anpassade felfält i Java Slides med Aspose.Slides

I den här handledningen kommer du att lära dig hur du lägger till anpassade felstaplar till ett diagram i en PowerPoint-presentation med Aspose.Slides för Java. Felstaplar är användbara för att visa variabilitet eller osäkerhet i datapunkter i ett diagram.

## Förutsättningar

Innan du börjar, se till att du har följande:

- Aspose.Slides för Java-bibliotek installerat och konfigurerat i ditt projekt.
- En Java-utvecklingsmiljö inrättad.

## Steg 1: Skapa en tom presentation

Skapa först en tom PowerPoint-presentation.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar tom presentation
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till ett bubbeldiagram

Därefter lägger vi till ett bubbeldiagram till presentationen.

```java
// Skapa ett bubbeldiagram
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Steg 3: Lägg till anpassade felfält

Låt oss nu lägga till anpassade felstaplar till diagramserien.

```java
// Lägga till anpassade felfält och ställa in deras format
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Steg 4: Ställ in felfältsdata

I det här steget kommer vi åt diagramseriens datapunkter och ställer in de anpassade felstaplarnas värden för varje punkt.

```java
// Åtkomst till diagramseriedatapunkter och inställning av felstapelvärden för enskilda punkter
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Inställning av felstaplar för diagramseriepunkter
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Steg 5: Spara presentationen

Slutligen sparar du presentationen med de anpassade felfälten.

```java
// Sparar presentation
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Det är allt! Du har framgångsrikt lagt till anpassade felstaplar till ett diagram i en PowerPoint-presentation med Aspose.Slides för Java.

## Komplett källkod för Lägg till anpassat fel i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar tom presentation
Presentation presentation = new Presentation();
try
{
	// Skapa ett bubbeldiagram
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Lägger till anpassade felfält och ställer in dess format
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Åtkomst till diagramseriedatapunkt och inställning av felstapelvärden för individuell punkt
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Inställning av felstaplar för diagramseriepunkter
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Sparar presentation
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här omfattande handledningen har du lärt dig hur du förbättrar dina PowerPoint-presentationer genom att lägga till anpassade felstaplar till diagram med Aspose.Slides för Java. Felstaplar ger värdefulla insikter om datavariabilitet och osäkerhet, vilket gör dina diagram mer informativa och visuellt tilltalande.

## FAQ's

### Hur anpassar jag utseendet på felfält?

 Du kan anpassa utseendet på felstaplar genom att ändra egenskaperna för`IErrorBarsFormat` objekt, som linjestil, linjefärg och felfältets bredd.

### Kan jag lägga till felstaplar till andra diagramtyper?

Ja, du kan lägga till felstaplar till olika diagramtyper som stöds av Aspose.Slides för Java, inklusive stapeldiagram, linjediagram och punktdiagram.

### Hur ställer jag in olika felstapelvärden för varje datapunkt?

Du kan gå igenom datapunkterna och ställa in anpassade felstapelvärden för varje punkt, som visas i koden ovan.

### Är det möjligt att dölja felstaplar för specifika datapunkter?

 Ja, du kan kontrollera synligheten för felstaplar för enskilda datapunkter genom att ställa in`setVisible` egendom av`IErrorBarsFormat` objekt.