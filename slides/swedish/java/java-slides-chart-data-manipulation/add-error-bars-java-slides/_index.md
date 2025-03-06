---
title: Lägg till felfält i Java Slides
linktitle: Lägg till felfält i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du lägger till felstaplar till PowerPoint-diagram i Java med Aspose.Slides. Steg-för-steg-guide med källkod för att anpassa felfält.
type: docs
weight: 13
url: /sv/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Introduktion till att lägga till felfält i Java Slides med Aspose.Slides

I den här handledningen kommer vi att visa hur man lägger till felstaplar till ett diagram i en PowerPoint-bild med Aspose.Slides för Java. Felstaplar ger värdefull information om variabiliteten eller osäkerheten hos datapunkter i ett diagram. Vi kommer att skapa ett bubbeldiagram och lägga till felstaplar till det. Låt oss börja!

## Förutsättningar

Innan du börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från[Aspose hemsida](https://downloads.aspose.com/slides/java).

## Steg 1: Skapa en tom presentation

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar tom presentation
Presentation presentation = new Presentation();
```

I det här steget skapar vi en tom presentation där vi lägger till vårt diagram med felstaplar.

## Steg 2: Skapa ett bubbeldiagram

```java
// Skapa ett bubbeldiagram
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Här skapar vi ett bubbeldiagram och anger dess position och dimensioner på bilden.

## Steg 3: Lägga till felfält och ställa in format

```java
// Lägger till felfält och ställer in dess format
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

I det här steget lägger vi till felstaplar i diagrammet och ställer in deras format. Du kan anpassa felstaplar genom att ändra värden, typer och andra egenskaper.

- `errBarX` representerar felstaplar längs X-axeln.
- `errBarY` representerar felstaplar längs Y-axeln.
- Vi gör både X- och Y-felstaplar synliga.
- `setValueType` anger värdetypen för felstaplar (t.ex. Fast eller Procent).
- `setValue` anger värdet för felstaplar.
- `setType` definierar typen av felstaplar (t.ex. plus eller minus).
-  Vi ställer in bredden på felfältslinjerna med hjälp av`getFormat().getLine().setWidth(2)`.
- `setEndCap`anger om ändkapslar ska inkluderas på felstaplarna.

## Steg 4: Spara presentationen

```java
// Sparar presentationen
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Slutligen sparar vi presentationen med de tillagda felfälten till en angiven plats.

Det är allt! Du har framgångsrikt lagt till felstaplar till ett diagram i en PowerPoint-bild med Aspose.Slides för Java.

## Komplett källkod för att lägga till felfält i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Skapar tom presentation
Presentation presentation = new Presentation();
try
{
	// Skapa ett bubbeldiagram
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Lägger till felfält och ställer in dess format
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
	// Sparar presentationen
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här handledningen har vi utforskat hur du kan förbättra dina PowerPoint-presentationer genom att lägga till felstaplar i diagram med Aspose.Slides för Java. Felstaplar ger värdefulla insikter om datavariabilitet och osäkerheter, vilket gör dina presentationer mer informativa och visuellt tilltalande.

## FAQ's

### Hur kan jag anpassa utseendet på felfält ytterligare?

Du kan anpassa felstaplar genom att ändra deras egenskaper, såsom linjestil, färg och bredd, som visas i steg 3.

### Kan jag lägga till felstaplar till olika diagramtyper?

Ja, du kan lägga till felstaplar till olika diagramtyper som stöds av Aspose.Slides för Java. Skapa helt enkelt önskad diagramtyp och följ samma felfältsanpassningssteg.

### Hur kan jag justera positionen och storleken på diagrammet på bilden?

 Du kan styra diagrammets position och dimensioner genom att justera parametrarna i`addChart` metod, som visas i steg 2.

### Var kan jag hitta mer information om Aspose.Slides för Java?

 Du kan hänvisa till[Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/) för detaljerad information om hur du använder biblioteket.