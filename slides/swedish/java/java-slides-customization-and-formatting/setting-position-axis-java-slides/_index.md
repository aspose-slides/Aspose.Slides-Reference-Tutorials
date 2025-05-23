---
"description": "Förbättra dina diagram med Aspose.Slides för Java. Lär dig hur du ställer in positionsaxeln i Java-bilder, skapar fantastiska presentationer och anpassar diagramlayouter med lätthet."
"linktitle": "Ställa in positionsaxeln i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ställa in positionsaxeln i Java-bilder"
"url": "/sv/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ställa in positionsaxeln i Java-bilder


## Introduktion till att ställa in positionsaxeln i Aspose.Slides för Java

den här handledningen lär vi oss hur man ställer in positionsaxeln i ett diagram med hjälp av Aspose.Slides för Java. Att positionera axeln kan vara användbart när du vill anpassa utseendet och layouten på ditt diagram. Vi skapar ett klustrat stapeldiagram och justerar positionen för den horisontella axeln mellan kategorier.

## Förkunskapskrav

Innan vi börjar, se till att du har Aspose.Slides för Java-biblioteket installerat och konfigurerat i ditt Java-projekt. Du kan ladda ner biblioteket från [här](https://releases.aspose.com/slides/java/).

## Steg 1: Skapa en presentation

Först ska vi skapa en ny presentation att arbeta med:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Se till att byta ut `"Your Document Directory"` med den faktiska sökvägen till din dokumentkatalog.

## Steg 2: Lägga till ett diagram

Nästa steg är att lägga till ett klustrat stapeldiagram på bilden. Vi anger diagrammets typ, position (x-, y-koordinater) och dimensioner (bredd och höjd):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Här har vi lagt till ett klustrat stapeldiagram på position (50, 50) med en bredd på 450 och en höjd på 300. Du kan justera dessa värden efter behov.

## Steg 3: Ställa in positionsaxeln

För att ställa in positionsaxeln mellan kategorier kan du använda följande kod:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Den här koden ställer in den horisontella axeln för att visas mellan kategorier, vilket kan vara användbart för vissa diagramlayouter.

## Steg 4: Spara presentationen

Slutligen, låt oss spara presentationen med diagrammet:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

Ersätta `"AsposeClusteredColumnChart.pptx"` med ditt önskade filnamn.

Det var allt! Du har skapat ett klustrat stapeldiagram och angett positionsaxeln mellan kategorierna med hjälp av Aspose.Slides för Java.

## Komplett källkod
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

den här handledningen har vi utforskat hur man ställer in positionsaxeln i ett diagram med hjälp av Aspose.Slides för Java. Genom att följa stegen som beskrivs i den här guiden har du lärt dig hur du skapar ett klustrat stapeldiagram och anpassar dess utseende genom att placera den horisontella axeln mellan kategorier. Aspose.Slides för Java erbjuder kraftfulla funktioner för att arbeta med diagram och presentationer, vilket gör det till ett värdefullt verktyg för Java-utvecklare.

## Vanliga frågor

### Hur anpassar jag diagrammet ytterligare?

Du kan anpassa olika aspekter av diagrammet, inklusive dataserier, diagramrubrik, förklaringar med mera. Se [Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/) för detaljerade instruktioner och exempel.

### Kan jag ändra diagramtypen?

Ja, du kan ändra diagramtypen genom att modifiera `ChartType` parametern när du lägger till diagrammet. Aspose.Slides för Java stöder olika diagramtyper som stapeldiagram, linjediagram och mer.

### Var kan jag hitta fler exempel och dokumentation?

Du hittar omfattande dokumentation och fler exempel på [Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/) sida.

Kom ihåg att kassera presentationsobjektet när du är klar med det för att frigöra systemresurser:

```java
if (pres != null) pres.dispose();
```

Det var allt för den här handledningen. Du har lärt dig hur man ställer in positionsaxeln i ett diagram med hjälp av Aspose.Slides för Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}