---
"description": "Lär dig hur du hämtar diagrambilder i Java Slides med hjälp av Aspose.Slides för Java. Den här steg-för-steg-guiden innehåller källkod och tips för sömlös integration."
"linktitle": "Hämta diagrambild i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Hämta diagrambild i Java Slides"
"url": "/sv/java/data-manipulation/get-chart-image-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hämta diagrambild i Java Slides


## Introduktion till att hämta diagrambild i Java-presentationer

Aspose.Slides för Java är ett kraftfullt bibliotek som låter dig arbeta med PowerPoint-presentationer programmatiskt. Med det här biblioteket kan du skapa, manipulera och extrahera olika element från presentationer, inklusive diagram. Ett vanligt krav är att hämta diagrambilder från bilder, och vi visar hur man gör just det i den här guiden.

## Förkunskapskrav

Innan vi går in i koden, se till att du har följande förutsättningar på plats:

- Java Development Kit (JDK) installerat på ditt system.
- Aspose.Slides för Java-biblioteket har laddats ner och konfigurerats i ditt projekt. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).

## Steg 1: Konfigurera ditt projekt

Börja med att skapa ett Java-projekt i din föredragna integrerade utvecklingsmiljö (IDE). Se till att du har lagt till Aspose.Slides för Java-biblioteket i projektets beroenden.

## Steg 2: Initiera presentationen

För att börja måste du initiera en PowerPoint-presentation. I det här exemplet antar vi att du har en PowerPoint-fil med namnet "test.pptx" i din dokumentkatalog.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Steg 3: Lägg till ett diagram och hämta bilden

Nästa steg är att lägga till ett diagram i en bild och hämta dess bild. I det här exemplet lägger vi till ett klustrat stapeldiagram.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

I det här kodavsnittet skapar vi ett klustrat stapeldiagram på den första bilden i presentationen och hämtar sedan dess miniatyrbild. Bilden sparas som "image.png" i den angivna katalogen.

## Komplett källkod för att hämta diagrambild i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

Att hämta diagrambilder från Java Slides med hjälp av Aspose.Slides för Java är en enkel process. Med den medföljande koden kan du enkelt integrera den här funktionen i dina Java-applikationer, så att du kan arbeta effektivt med PowerPoint-presentationer.

## Vanliga frågor

### Hur installerar jag Aspose.Slides för Java?

Det är enkelt att installera Aspose.Slides för Java. Du kan ladda ner biblioteket från [här](https://releases.aspose.com/slides/java/) och följ installationsanvisningarna som finns i dokumentationen.

### Kan jag anpassa diagrammet innan jag får bilden?

Ja, du kan anpassa diagrammets utseende, data och andra egenskaper innan du hämtar bilden. Aspose.Slides för Java erbjuder omfattande alternativ för anpassning av diagram.

### Vilka andra funktioner erbjuder Aspose.Slides för Java?

Aspose.Slides för Java erbjuder ett brett utbud av funktioner för att arbeta med PowerPoint-presentationer, inklusive att skapa bilder, textmanipulera, redigera former och mycket mer. Du kan utforska dokumentationen för detaljerad information.

### Är Aspose.Slides för Java lämpligt för kommersiellt bruk?

Ja, Aspose.Slides för Java kan användas för kommersiella ändamål. Det erbjuder licensalternativ som passar både enskilda utvecklare och företag.

### Kan jag spara diagrambilden i ett annat format?

Visst! Du kan spara diagrambilden i olika format, till exempel JPEG eller GIF, genom att ange lämplig filändelse i `ImageIO.write` metod.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}