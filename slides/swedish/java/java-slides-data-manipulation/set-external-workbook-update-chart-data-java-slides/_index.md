---
"description": "Lär dig hur du skapar externa arbetsböcker och uppdaterar diagramdata i Java Slides med hjälp av Aspose.Slides för Java. Förbättra dina automatiseringsfärdigheter i PowerPoint."
"linktitle": "Ställ in extern arbetsbok med uppdaterade diagramdata i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Ställ in extern arbetsbok med uppdaterade diagramdata i Java Slides"
"url": "/sv/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ställ in extern arbetsbok med uppdaterade diagramdata i Java Slides


## Introduktion till att ställa in extern arbetsbok med uppdatering av diagramdata i Java-presentationer

den här omfattande guiden guidar vi dig genom processen att skapa en extern arbetsbok med uppdaterade diagramdata i Java Slides med hjälp av Aspose.Slides för Java API. Detta kraftfulla bibliotek låter dig manipulera PowerPoint-presentationer programmatiskt, vilket gör det enkelt att automatisera uppgifter som att uppdatera diagramdata från en extern källa. I slutet av den här handledningen har du en tydlig förståelse för hur du utför denna uppgift med steg-för-steg-instruktioner och tillhörande Java-kod.

## Förkunskapskrav

Innan vi går in i implementeringen, se till att du har följande förutsättningar på plats:

1. Aspose.Slides för Java: Du bör ha biblioteket Aspose.Slides för Java installerat. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).

2. Java-utvecklingsmiljö: Se till att du har en Java-utvecklingsmiljö konfigurerad på ditt system.

## Steg 1: Skapa en ny presentation

För att komma igång, låt oss skapa en ny PowerPoint-presentation med Aspose.Slides för Java. Här är Java-koden för att göra det:

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Steg 2: Lägg till ett diagram

Nu ska vi lägga till ett diagram i vår presentation. Vi skapar ett cirkeldiagram i det här exemplet:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Steg 3: Ställ in extern arbetsbok

Det är här vi ställer in den externa arbetsboken som datakälla för vårt diagram. Du måste ange URL:en till den externa arbetsboken, även om den inte finns för närvarande:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://"sökväg/finns inte/", falskt);
```

## Steg 4: Spara presentationen

Spara slutligen presentationen med den uppdaterade diagramdatan:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Komplett källkod för att ställa in extern arbetsbok med uppdatering av diagramdata i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://"sökväg/finns inte/", falskt);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

Grattis! Du har lärt dig hur du ställer in en extern arbetsbok med uppdaterade diagramdata i Java Slides med hjälp av Aspose.Slides för Java. Detta kan vara otroligt användbart för att dynamiskt uppdatera diagram i dina PowerPoint-presentationer från externa datakällor.

## Vanliga frågor

### Hur kan jag uppdatera externa arbetsboksdata för diagrammet?

För att uppdatera externa arbetsboksdata för diagrammet behöver du bara ändra data i den externa arbetsboken på den angivna URL:en. Nästa gång du öppnar presentationen kommer Aspose.Slides för Java att hämta uppdaterade data från den externa arbetsboken och uppdatera diagrammet därefter.

### Kan jag använda en lokal fil som extern arbetsbok?

Ja, du kan använda en lokal fil som extern arbetsbok genom att ange filsökvägen istället för en URL. Se bara till att filsökvägen är korrekt och tillgänglig från ditt Java-program.

### Finns det några begränsningar för att använda externa arbetsböcker med Aspose.Slides för Java?

Även om det är en kraftfull funktion att använda externa arbetsböcker, tänk på att tillgängligheten för den externa arbetsbokens data beror på dess tillgänglighet via den angivna URL:en eller filsökvägen. Se till att den externa datakällan är tillgänglig när du öppnar presentationen för att undvika problem med datahämtning.

### Kan jag anpassa diagrammets utseende efter att jag har konfigurerat den externa arbetsboken?

Ja, du kan anpassa diagrammets utseende, inklusive dess titel, etiketter, färger med mera, även efter att du har konfigurerat den externa arbetsboken. Aspose.Slides för Java erbjuder omfattande formateringsalternativ för diagram för att möta dina behov.

### Var kan jag hitta mer dokumentation och resurser för Aspose.Slides för Java?

För detaljerad dokumentation och ytterligare resurser, besök Aspose.Slides för Java-dokumentationen på [här](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}