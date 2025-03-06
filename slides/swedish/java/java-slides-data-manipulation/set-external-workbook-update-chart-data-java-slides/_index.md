---
title: Ställ in extern arbetsbok med uppdateringsdiagramdata i Java Slides
linktitle: Ställ in extern arbetsbok med uppdateringsdiagramdata i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in externa arbetsböcker och uppdaterar diagramdata i Java Slides med Aspose.Slides för Java. Förbättra dina färdigheter i PowerPoint-automatisering.
weight: 20
url: /sv/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduktion till att ställa in extern arbetsbok med uppdatering av diagramdata i Java Slides

den här omfattande guiden går vi igenom processen att ställa in en extern arbetsbok med uppdaterade diagramdata i Java Slides med hjälp av Aspose.Slides för Java API. Detta kraftfulla bibliotek låter dig manipulera PowerPoint-presentationer programmatiskt, vilket gör det enkelt att automatisera uppgifter som att uppdatera diagramdata från en extern källa. I slutet av den här handledningen har du en tydlig förståelse för hur du kan utföra denna uppgift med steg-för-steg-instruktioner och medföljande Java-kod.

## Förutsättningar

Innan vi dyker in i implementeringen, se till att du har följande förutsättningar på plats:

1.  Aspose.Slides för Java: Du bör ha Aspose.Slides för Java-biblioteket installerat. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

2. Java-utvecklingsmiljö: Se till att du har en Java-utvecklingsmiljö inställd på ditt system.

## Steg 1: Skapa en ny presentation

För att komma igång, låt oss skapa en ny PowerPoint-presentation med Aspose.Slides för Java. Här är Java-koden för att göra det:

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Steg 2: Lägg till ett diagram

Låt oss nu lägga till ett diagram till vår presentation. Vi skapar ett cirkeldiagram i det här exemplet:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Steg 3: Ställ in extern arbetsbok

Det är här vi ställer in den externa arbetsboken som datakälla för vårt diagram. Du måste ange URL:en till den externa arbetsboken, även om den inte existerar för tillfället:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://sökväg/finns inte", false);
```

## Steg 4: Spara presentationen

Spara slutligen presentationen med uppdaterade diagramdata:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Komplett källkod för inställd extern arbetsbok med uppdatering av diagramdata i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://sökväg/finns inte", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

Grattis! Du har lärt dig hur du ställer in en extern arbetsbok med uppdaterade diagramdata i Java Slides med Aspose.Slides för Java. Detta kan vara otroligt användbart för att dynamiskt uppdatera diagram i dina PowerPoint-presentationer från externa datakällor.

## FAQ's

### Hur kan jag uppdatera externa arbetsboksdata för diagrammet?

För att uppdatera den externa arbetsboksdatan för diagrammet behöver du helt enkelt ändra data i den externa arbetsboken på den angivna URL:en. Nästa gång du öppnar presentationen kommer Aspose.Slides för Java att hämta uppdaterade data från den externa arbetsboken och uppdatera diagrammet därefter.

### Kan jag använda en lokal fil som den externa arbetsboken?

Ja, du kan använda en lokal fil som den externa arbetsboken genom att ange filsökvägen istället för en URL. Se bara till att filsökvägen är korrekt och tillgänglig från din Java-applikation.

### Finns det några begränsningar för att använda externa arbetsböcker med Aspose.Slides för Java?

Även om det är en kraftfull funktion att använda externa arbetsböcker, kom ihåg att tillgängligheten för den externa arbetsbokens data beror på dess tillgänglighet på den angivna webbadressen eller sökvägen. Se till att den externa datakällan är tillgänglig när du öppnar presentationen för att undvika problem med datahämtning.

### Kan jag anpassa diagrammets utseende efter att ha ställt in den externa arbetsboken?

Ja, du kan anpassa diagrammets utseende, inklusive dess titel, etiketter, färger och mer, även efter att ha ställt in den externa arbetsboken. Aspose.Slides för Java tillhandahåller omfattande diagramformateringsalternativ för att möta dina behov.

### Var kan jag hitta mer dokumentation och resurser för Aspose.Slides för Java?

 För detaljerad dokumentation och ytterligare resurser, besök Aspose.Slides för Java-dokumentationen på[här](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
