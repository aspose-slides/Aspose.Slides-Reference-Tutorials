---
title: Redigera diagramdata i extern arbetsbok i Java Slides
linktitle: Redigera diagramdata i extern arbetsbok i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du redigerar diagramdata i en extern arbetsbok med Aspose.Slides för Java. Steg-för-steg guide med källkod.
weight: 17
url: /sv/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduktion till redigering av diagramdata i extern arbetsbok i Java Slides

I den här guiden kommer vi att visa hur man redigerar diagramdata i en extern arbetsbok med Aspose.Slides för Java. Du lär dig hur du ändrar diagramdata i en PowerPoint-presentation programmatiskt. Se till att du har Aspose.Slides-biblioteket för Java installerat och konfigurerat i ditt projekt.

## Förutsättningar

- Aspose.Slides för Java
- Java utvecklingsmiljö

## Steg 1: Ladda presentationen

 Först måste vi ladda PowerPoint-presentationen som innehåller diagrammet vars data vi vill redigera. Byta ut`"Your Document Directory"` med den faktiska sökvägen till din presentationsfil.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Steg 2: Öppna diagrammet

När presentationen har laddats måste vi komma åt diagrammet i presentationen. I det här exemplet antar vi att diagrammet är på den första bilden och är den första formen på den bilden.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Steg 3: Ändra sjökortsdata

Låt oss nu ändra diagramdata. Vi kommer att fokusera på att ändra en specifik datapunkt i diagrammet. I det här exemplet ställer vi in värdet för den första datapunkten i den första serien till 100. Du kan justera detta värde efter behov.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Steg 4: Spara presentationen

Efter att ha gjort de nödvändiga ändringarna i diagramdata, spara den ändrade presentationen i en ny fil. Du kan ange sökväg och format för utdatafilen enligt dina krav.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Steg 5: Rengöring

Glöm inte att kassera presentationsobjektet för att frigöra eventuella resurser.

```java
if (pres != null) pres.dispose();
```

Nu har du framgångsrikt redigerat diagramdata i en extern arbetsbok i din PowerPoint-presentation med Aspose.Slides för Java. Du kan anpassa den här koden för att passa dina specifika behov och integrera den i dina Java-applikationer.

## Komplett källkod

```java
        // Var uppmärksam på att sökvägen till extern arbetsbok knappast sparas i presentationen
        // så kopiera filen externalWorkbook.xlsx från Data/Chart-katalogen D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ innan du kör exemplet
        // Sökvägen till dokumentkatalogen.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Slutsats

I den här omfattande guiden har vi utforskat hur man redigerar diagramdata i externa arbetsböcker i PowerPoint-presentationer med Aspose.Slides för Java. Genom att följa steg-för-steg-instruktionerna och källkodsexemplen har du fått kunskap och färdigheter för att programmässigt ändra diagramdata med lätthet.

## FAQ's

### Hur anger jag ett annat diagram eller en annan bild?

 För att komma åt ett annat diagram eller diabild, ändra lämpligt index i`getSlides().get_Item()` och`getShapes().get_Item()`metoder. Kom ihåg att indexering börjar från 0.

### Kan jag redigera data i flera diagram inom samma presentation?

Ja, du kan redigera data i flera diagram inom samma presentation genom att upprepa stegen för ändring av diagramdata för varje diagram.

### Vad händer om jag vill redigera data i en extern arbetsbok med ett annat format?

Du kan anpassa koden för att hantera olika externa arbetsboksformat genom att använda lämpliga Aspose.Cells-klasser och metoder för att läsa och skriva data i det formatet.

### Hur kan jag automatisera den här processen för flera presentationer?

Du kan skapa en loop för att bearbeta flera presentationer, ladda var och en, göra önskade ändringar och spara de modifierade presentationerna en efter en.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
