---
"description": "Lär dig hur du lägger till felstaplar i PowerPoint-diagram i Java med Aspose.Slides. Steg-för-steg-guide med källkod för att anpassa felstaplar."
"linktitle": "Lägg till felstaplar i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägg till felstaplar i Java Slides"
"url": "/sv/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till felstaplar i Java Slides


## Introduktion till att lägga till felstaplar i Java Slides med hjälp av Aspose.Slides

I den här handledningen visar vi hur man lägger till felstaplar i ett diagram i en PowerPoint-bild med hjälp av Aspose.Slides för Java. Felstaplar ger värdefull information om variabiliteten eller osäkerheten hos datapunkter i ett diagram. Vi skapar ett bubbeldiagram och lägger till felstaplar i det. Nu sätter vi igång!

## Förkunskapskrav

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från [Asposes webbplats](https://downloads.aspose.com/slides/java).

## Steg 1: Skapa en tom presentation

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar en tom presentation
Presentation presentation = new Presentation();
```

I det här steget skapar vi en tom presentation där vi lägger till vårt diagram med felstaplar.

## Steg 2: Skapa ett bubbeldiagram

```java
// Skapa ett bubbeldiagram
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Här skapar vi ett bubbeldiagram och anger dess position och dimensioner på bilden.

## Steg 3: Lägga till felstaplar och ställa in format

```java
// Lägga till felstaplar och ställa in deras format
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

I det här steget lägger vi till felstaplar i diagrammet och ställer in deras format. Du kan anpassa felstaplarna genom att ändra värden, typer och andra egenskaper.

- `errBarX` representerar felstaplar längs X-axeln.
- `errBarY` representerar felstaplar längs Y-axeln.
- Vi gör både X- och Y-felstaplarna synliga.
- `setValueType` anger värdetypen för felstaplar (t.ex. Fast eller Procentuell).
- `setValue` anger värdet för felstaplar.
- `setType` definierar typen av felstaplar (t.ex. Plus eller Minus).
- Vi ställer in bredden på felstrecklinjerna med hjälp av `getFormat().getLine().setWidth(2)`.
- `setEndCap` anger om ändkåpor ska inkluderas på felstaplarna.

## Steg 4: Spara presentationen

```java
// Sparar presentation
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Slutligen sparar vi presentationen med de tillagda felstaplarna på en angiven plats.

Det var allt! Du har lagt till felstaplar i ett diagram i en PowerPoint-bild med hjälp av Aspose.Slides för Java.

## Komplett källkod för att lägga till felstaplar i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar en tom presentation
Presentation presentation = new Presentation();
try
{
	// Skapa ett bubbeldiagram
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Lägga till felstaplar och ställa in deras format
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Sparar presentation
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här handledningen har vi utforskat hur du kan förbättra dina PowerPoint-presentationer genom att lägga till felstaplar i diagram med hjälp av Aspose.Slides för Java. Felstaplar ger värdefulla insikter i datavariabilitet och osäkerheter, vilket gör dina presentationer mer informativa och visuellt tilltalande.

## Vanliga frågor

### Hur kan jag anpassa utseendet på felstaplar ytterligare?

Du kan anpassa felstaplar genom att ändra deras egenskaper, till exempel linjestil, färg och bredd, som visas i steg 3.

### Kan jag lägga till felstaplar i olika diagramtyper?

Ja, du kan lägga till felstaplar till olika diagramtyper som stöds av Aspose.Slides för Java. Skapa bara önskad diagramtyp och följ samma anpassningssteg för felstaplar.

### Hur kan jag justera diagrammets position och storlek på bilden?

Du kan styra diagrammets position och dimensioner genom att justera parametrarna i `addChart` metod, som visas i steg 2.

### Var kan jag hitta mer information om Aspose.Slides för Java?

Du kan hänvisa till [Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/) för detaljerad information om hur man använder biblioteket.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}