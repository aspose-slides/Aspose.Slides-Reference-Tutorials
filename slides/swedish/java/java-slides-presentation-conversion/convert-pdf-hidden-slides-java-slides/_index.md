---
title: Konvertera till PDF med dolda bilder i Java Slides
linktitle: Konvertera till PDF med dolda bilder i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du konverterar PowerPoint-presentationer till PDF med dolda bilder med Aspose.Slides för Java. Följ vår steg-för-steg-guide med källkod för sömlös PDF-generering.
weight: 27
url: /sv/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduktion till att konvertera PowerPoint-presentationer till PDF med dolda bilder med Aspose.Slides för Java

den här steg-för-steg-guiden får du lära dig hur du konverterar en PowerPoint-presentation till PDF samtidigt som du bevarar dolda bilder med Aspose.Slides för Java. Dolda bilder är de som inte visas under en vanlig presentation men som kan inkluderas i PDF-utdata. Vi kommer att förse dig med källkoden och detaljerade instruktioner för att utföra denna uppgift.

## Förutsättningar

Innan du börjar, se till att du har följande förutsättningar på plats:

1.  Aspose.Slides for Java Library: Se till att du har konfigurerat Aspose.Slides for Java-biblioteket i ditt Java-projekt. Du kan ladda ner den från[Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/).

2. Java-utvecklingsmiljö: Du bör ha en Java-utvecklingsmiljö installerad på ditt system.

## Steg 1: Importera Aspose.Slides för Java

Först måste du importera Aspose.Slides-biblioteket till ditt Java-projekt. Se till att du har lagt till biblioteket i projektets byggväg.

```java
import com.aspose.slides.*;
```

## Steg 2: Ladda PowerPoint-presentationen

 Du börjar med att ladda PowerPoint-presentationen som du vill konvertera till PDF. Byta ut`"Your Document Directory"` och`"HiddingSlides.pptx"` med lämplig sökväg.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Steg 3: Konfigurera PDF-alternativ

Konfigurera PDF-alternativen för att inkludera dolda bilder i PDF-utdata. Du kan göra detta genom att ställa in`setShowHiddenSlides` egendom av`PdfOptions` klass till`true`.

```java
// Instantiera klassen PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Ange att det genererade dokumentet ska innehålla dolda bilder
pdfOptions.setShowHiddenSlides(true);
```

## Steg 4: Spara presentationen som PDF

 Spara nu presentationen till en PDF-fil med de angivna alternativen. Byta ut`"PDFWithHiddenSlides_out.pdf"` med önskat utdatafilnamn.

```java
// Spara presentationen till PDF med angivna alternativ
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Steg 5: Rensningsresurser

Se till att frigöra resurserna som används av presentationen när du är klar med den.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Komplett källkod för konvertering till PDF med dolda bilder i Java-bilder

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Instantiera klassen PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Ange att det genererade dokumentet ska innehålla dolda bilder
	pdfOptions.setShowHiddenSlides(true);
	// Spara presentationen till PDF med angivna alternativ
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här omfattande guiden har du lärt dig hur du konverterar en PowerPoint-presentation till PDF samtidigt som du bevarar dolda bilder med Aspose.Slides för Java. Vi har försett dig med en steg-för-steg handledning tillsammans med den nödvändiga källkoden för att utföra denna uppgift sömlöst.

## FAQ's

### Hur kan jag dölja bilder i en PowerPoint-presentation?

Följ dessa steg för att dölja en bild i en PowerPoint-presentation:
1. Välj den bild som du vill dölja i bildsorteringsvyn.
2. Högerklicka på den valda bilden.
3. Välj "Dölj bild" från snabbmenyn.

### Kan jag programmatiskt visa dolda bilder i Aspose.Slides för Java?

 Ja, du kan programmatiskt visa dolda bilder i Aspose.Slides för Java genom att ställa in`Hidden` egendom av`Slide` klass till`false`. Här är ett exempel:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Ersätt slideIndex med indexet för den dolda bilden
slide.setHidden(false);
```

### Hur laddar jag ner Aspose.Slides för Java?

 Du kan ladda ner Aspose.Slides för Java från Asposes webbplats. Besök[Aspose.Slides för Java nedladdningssida](https://releases.aspose.com/slides/java/) för att få den senaste versionen.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
