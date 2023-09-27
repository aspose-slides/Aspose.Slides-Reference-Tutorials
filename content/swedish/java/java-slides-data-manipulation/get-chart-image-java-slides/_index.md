---
title: Få diagrambild i Java Slides
linktitle: Få diagrambild i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du skaffar diagrambilder i Java Slides med Aspose.Slides för Java. Den här steg-för-steg-guiden ger källkod och tips för sömlös integration.
type: docs
weight: 19
url: /sv/java/data-manipulation/get-chart-image-java-slides/
---

## Introduktion till Hämta diagrambild i Java Slides

Aspose.Slides för Java är ett kraftfullt bibliotek som låter dig arbeta med PowerPoint-presentationer programmatiskt. Med det här biblioteket kan du skapa, manipulera och extrahera olika element från presentationer, inklusive diagram. Ett vanligt krav är att skaffa diagrambilder från bilder, och vi kommer att visa hur man gör just det i den här guiden.

## Förutsättningar

Innan vi dyker in i koden, se till att du har följande förutsättningar på plats:

- Java Development Kit (JDK) installerat på ditt system.
-  Aspose.Slides för Java-bibliotek nedladdade och konfigurerade i ditt projekt. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

## Steg 1: Konfigurera ditt projekt

Börja med att skapa ett Java-projekt i din föredragna Integrated Development Environment (IDE). Se till att du har lagt till Aspose.Slides för Java-biblioteket till ditt projekts beroenden.

## Steg 2: Initiera presentationen

För att börja måste du initiera en PowerPoint-presentation. I det här exemplet antar vi att du har en PowerPoint-fil med namnet "test.pptx" i din dokumentkatalog.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Steg 3: Lägg till ett diagram och hämta bilden

Därefter kan du lägga till ett diagram till en bild och få dess bild. I det här exemplet lägger vi till ett klustrat kolumndiagram.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

I det här kodavsnittet skapar vi ett klustrat kolumndiagram på den första bilden av presentationen och får sedan dess miniatyrbild. Bilden sparas som "image.png" i den angivna katalogen.

## Komplett källkod för få diagrambild i Java Slides

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

Att skaffa diagrambilder från Java Slides med Aspose.Slides för Java är en enkel process. Med den medföljande koden kan du enkelt integrera den här funktionen i dina Java-applikationer, så att du kan arbeta effektivt med PowerPoint-presentationer.

## FAQ's

### Hur installerar jag Aspose.Slides för Java?

 Att installera Aspose.Slides för Java är enkelt. Du kan ladda ner biblioteket från[här](https://releases.aspose.com/slides/java/)och följ installationsinstruktionerna i dokumentationen.

### Kan jag anpassa diagrammet innan jag får dess bild?

Ja, du kan anpassa diagrammets utseende, data och andra egenskaper innan du får dess bild. Aspose.Slides för Java ger omfattande alternativ för diagramanpassning.

### Vilka andra funktioner erbjuder Aspose.Slides för Java?

Aspose.Slides för Java erbjuder ett brett utbud av funktioner för att arbeta med PowerPoint-presentationer, inklusive bildskapande, textmanipulering, formredigering och mycket mer. Du kan utforska dokumentationen för detaljerad information.

### Är Aspose.Slides för Java lämplig för kommersiellt bruk?

Ja, Aspose.Slides för Java kan användas för kommersiella ändamål. Det ger licensalternativ som vänder sig till både enskilda utvecklare och företag.

### Kan jag spara diagrambilden i ett annat format?

Säkert! Du kan spara diagrambilden i olika format, till exempel JPEG eller GIF, genom att ange lämplig filtillägg i`ImageIO.write` metod.