---
title: Spara som fördefinierad vytyp i Java Slides
linktitle: Spara som fördefinierad vytyp i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du ställer in fördefinierade vytyper i Java Slides med Aspose.Slides för Java. Steg-för-steg guide med kodexempel och vanliga frågor.
weight: 10
url: /sv/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Introduktion till Spara som fördefinierad vytyp i Java Slides

I denna steg-för-steg-guide kommer vi att utforska hur man sparar en presentation med en fördefinierad vytyp med Aspose.Slides för Java. Vi kommer att förse dig med nödvändig kod och förklaringar för att utföra denna uppgift framgångsrikt.

## Förutsättningar

Innan vi börjar, se till att du har följande:

- Grundläggande kunskaper i Java-programmering.
- Aspose.Slides för Java-biblioteket installerat.
- Integrerad utvecklingsmiljö (IDE) efter eget val.

## Ställa in din miljö

För att komma igång, följ dessa steg för att konfigurera din utvecklingsmiljö:

1. Skapa ett nytt Java-projekt i din IDE.
2. Lägg till Aspose.Slides för Java-biblioteket till ditt projekt som ett beroende.

Nu när din miljö är inställd, låt oss fortsätta med koden.

## Steg 1: Skapa en presentation

För att visa hur du sparar en presentation med en fördefinierad vytyp skapar vi först en ny presentation. Här är koden för att skapa en presentation:

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Öppnar presentationsfilen
Presentation presentation = new Presentation();
```

 I den här koden skapar vi en ny`Presentation` objekt, som representerar vår PowerPoint-presentation.

## Steg 2: Ställa in vytyp

Därefter ställer vi in vytypen för vår presentation. Vytyper definierar hur presentationen visas när den öppnas. I det här exemplet ställer vi in den på "Slide Master View". Här är koden:

```java
// Ställa in vytyp
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 I koden ovan använder vi`setLastView` metod för`ViewProperties` klass för att ställa in vytypen till`SlideMasterView`. Du kan välja andra vytyper efter behov.

## Steg 3: Spara presentationen

Nu när vi har skapat vår presentation och ställt in vytypen är det dags att spara presentationen. Vi sparar det i PPTX-format. Här är koden:

```java
// Sparar presentationen
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 I den här koden använder vi`save` metod för`Presentation` klass för att spara presentationen med angivet filnamn och format.

## Komplett källkod för Spara som fördefinierad vytyp i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Öppnar presentationsfilen
Presentation presentation = new Presentation();
try
{
	// Ställa in vytyp
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Sparar presentationen
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här handledningen har vi lärt oss hur man sparar en presentation med en fördefinierad vytyp i Java med Aspose.Slides för Java. Genom att följa den medföljande koden och stegen kan du enkelt ställa in visningstypen för dina presentationer och spara dem i önskat format.

## FAQ's

### Hur ändrar jag vytypen till något annat än "Slide Master View"?

 För att ändra vytypen till något annat än "Slide Master View", byt bara ut`ViewType.SlideMasterView` med önskad vytyp, som t.ex`ViewType.NormalView` eller`ViewType.SlideSorterView`, i koden där vi ställer in vytypen.

### Kan jag ställa in vyegenskaper för enskilda bilder i presentationen?

Ja, du kan ställa in vyegenskaper för enskilda bilder med Aspose.Slides för Java. Du kan komma åt och manipulera egenskaper för varje bild separat genom att iterera genom bilderna i presentationen.

### Vilka andra format kan jag spara min presentation i?

Aspose.Slides för Java stöder olika utdataformat, inklusive PPTX, PDF, TIFF, HTML och mer. Du kan ange önskat format när du sparar din presentation genom att använda lämpligt`SaveFormat` uppräkningsvärde.

### Är Aspose.Slides för Java lämplig för batchbearbetning av presentationer?

Ja, Aspose.Slides för Java är väl lämpad för batchbearbetningsuppgifter. Du kan automatisera behandlingen av flera presentationer, tillämpa ändringar och spara dem samtidigt med Java-kod.

### Var kan jag hitta mer information och dokumentation för Aspose.Slides för Java?

 För omfattande dokumentation och referenser relaterade till Aspose.Slides för Java, besök dokumentationswebbplatsen:[Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
