---
"description": "Lär dig hur du lägger till anpassade felstaplar i PowerPoint-diagram i Java Slides med hjälp av Aspose.Slides. Steg-för-steg-guide med källkod för exakt datavisualisering."
"linktitle": "Lägg till anpassat fel i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägg till anpassat fel i Java-bilder"
"url": "/sv/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till anpassat fel i Java-bilder


## Introduktion till att lägga till anpassade felstaplar i Java Slides med hjälp av Aspose.Slides

I den här handledningen lär du dig hur du lägger till anpassade felstaplar i ett diagram i en PowerPoint-presentation med hjälp av Aspose.Slides för Java. Felstaplar är användbara för att visa variation eller osäkerhet i datapunkter i ett diagram.

## Förkunskapskrav

Innan du börjar, se till att du har följande:

- Aspose.Slides för Java-biblioteket är installerat och konfigurerat i ditt projekt.
- En Java-utvecklingsmiljö konfigurerad.

## Steg 1: Skapa en tom presentation

Skapa först en tom PowerPoint-presentation.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar en tom presentation
Presentation presentation = new Presentation();
```

## Steg 2: Lägg till ett bubbeldiagram

Nästa steg är att lägga till ett bubbeldiagram i presentationen.

```java
// Skapa ett bubbeldiagram
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Steg 3: Lägg till anpassade felstaplar

Nu ska vi lägga till anpassade felstaplar i diagramserien.

```java
// Lägga till anpassade felstaplar och ställa in deras format
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Steg 4: Ställ in felstapeldata

det här steget kommer vi åt diagramseriens datapunkter och anger anpassade felstaplarsvärden för varje punkt.

```java
// Åtkomst till datapunkter i diagramserier och inställning av felstaplar för enskilda punkter
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Ställa in felstaplar för punkter i diagramserien
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Steg 5: Spara presentationen

Spara slutligen presentationen med de anpassade felstaplarna.

```java
// Sparar presentation
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Det var allt! Du har lagt till anpassade felstaplar i ett diagram i en PowerPoint-presentation med Aspose.Slides för Java.

## Komplett källkod för att lägga till anpassat fel i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar en tom presentation
Presentation presentation = new Presentation();
try
{
	// Skapa ett bubbeldiagram
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Lägga till anpassade felstaplar och ställa in deras format
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Åtkomst till datapunkter i diagramserier och inställning av felstaplar för enskilda punkter
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Ställa in felstaplar för punkter i diagramserien
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

den här omfattande handledningen har du lärt dig hur du förbättrar dina PowerPoint-presentationer genom att lägga till anpassade felstaplar i diagram med hjälp av Aspose.Slides för Java. Felstaplar ger värdefulla insikter i datavariabilitet och osäkerhet, vilket gör dina diagram mer informativa och visuellt tilltalande.

## Vanliga frågor

### Hur anpassar jag utseendet på felstaplar?

Du kan anpassa utseendet på felstaplar genom att ändra egenskaperna för `IErrorBarsFormat` objekt, såsom linjestil, linjefärg och felstapelbredd.

### Kan jag lägga till felstaplar i andra diagramtyper?

Ja, du kan lägga till felstaplar till olika diagramtyper som stöds av Aspose.Slides för Java, inklusive stapeldiagram, linjediagram och punktdiagram.

### Hur ställer jag in olika felstapelvärden för varje datapunkt?

Du kan loopa igenom datapunkterna och ange anpassade felstapelvärden för varje punkt, som visas i koden ovan.

### Är det möjligt att dölja felstaplar för specifika datapunkter?

Ja, du kan styra synligheten av felstaplar för enskilda datapunkter genom att ställa in `setVisible` egendomen tillhörande `IErrorBarsFormat` objekt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}