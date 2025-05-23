---
"description": "Lär dig hur du redigerar diagramdata i en extern arbetsbok med Aspose.Slides för Java. Steg-för-steg-guide med källkod."
"linktitle": "Redigera diagramdata i extern arbetsbok i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Redigera diagramdata i extern arbetsbok i Java Slides"
"url": "/sv/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Redigera diagramdata i extern arbetsbok i Java Slides


## Introduktion till redigering av diagramdata i extern arbetsbok i Java-presentationer

I den här guiden visar vi hur man redigerar diagramdata i en extern arbetsbok med hjälp av Aspose.Slides för Java. Du lär dig hur du programmatiskt ändrar diagramdata i en PowerPoint-presentation. Se till att du har Aspose.Slides-biblioteket för Java installerat och konfigurerat i ditt projekt.

## Förkunskapskrav

- Aspose.Slides för Java
- Java-utvecklingsmiljö

## Steg 1: Ladda presentationen

Först måste vi ladda PowerPoint-presentationen som innehåller diagrammet vars data vi vill redigera. Ersätt `"Your Document Directory"` med den faktiska sökvägen till din presentationsfil.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Steg 2: Få åtkomst till diagrammet

När presentationen är laddad behöver vi komma åt diagrammet i presentationen. I det här exemplet antar vi att diagrammet finns på den första bilden och är den första formen på den bilden.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Steg 3: Ändra diagramdata

Nu ska vi ändra diagramdata. Vi fokuserar på att ändra en specifik datapunkt i diagrammet. I det här exemplet ställer vi in värdet för den första datapunkten i den första serien till 100. Du kan justera detta värde efter behov.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Steg 4: Spara presentationen

När du har gjort de nödvändiga ändringarna i diagramdata sparar du den modifierade presentationen till en ny fil. Du kan ange sökvägen och formatet för utdatafilen enligt dina behov.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Steg 5: Rengöring

Glöm inte att göra dig av med presentationsobjektet för att frigöra eventuella resurser.

```java
if (pres != null) pres.dispose();
```

Nu har du redigerat diagramdata i en extern arbetsbok i din PowerPoint-presentation med hjälp av Aspose.Slides för Java. Du kan anpassa den här koden efter dina specifika behov och integrera den i dina Java-applikationer.

## Komplett källkod

```java
        // Var uppmärksam på att sökvägen till den externa arbetsboken knappast sparas i presentationen.
        // så kopiera filen externalWorkbook.xlsx från Data/Chart-katalogen D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ innan du kör exemplet.
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

I den här omfattande guiden har vi utforskat hur man redigerar diagramdata i externa arbetsböcker i PowerPoint-presentationer med hjälp av Aspose.Slides för Java. Genom att följa steg-för-steg-instruktionerna och källkodsexemplen har du fått kunskapen och färdigheterna för att enkelt modifiera diagramdata programmatiskt.

## Vanliga frågor

### Hur anger jag ett annat diagram eller en annan bild?

För att komma åt ett annat diagram eller en annan bild, ändra lämpligt index i `getSlides().get_Item()` och `getShapes().get_Item()` metoder. Kom ihåg att indexering börjar från 0.

### Kan jag redigera data i flera diagram i samma presentation?

Ja, du kan redigera data i flera diagram i samma presentation genom att upprepa stegen för att ändra diagramdata för varje diagram.

### Vad händer om jag vill redigera data i en extern arbetsbok med ett annat format?

Du kan anpassa koden för att hantera olika externa arbetsboksformat genom att använda lämpliga Aspose.Cells-klasser och metoder för att läsa och skriva data i det formatet.

### Hur kan jag automatisera den här processen för flera presentationer?

Du kan skapa en loop för att bearbeta flera presentationer, läsa in var och en, göra önskade ändringar och spara de ändrade presentationerna en i taget.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}