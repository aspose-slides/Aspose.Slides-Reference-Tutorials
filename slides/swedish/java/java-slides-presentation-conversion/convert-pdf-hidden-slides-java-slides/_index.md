---
"description": "Lär dig hur du konverterar PowerPoint-presentationer till PDF med dolda bilder med hjälp av Aspose.Slides för Java. Följ vår steg-för-steg-guide med källkod för sömlös PDF-generering."
"linktitle": "Konvertera till PDF med dolda bilder i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Konvertera till PDF med dolda bilder i Java-bilder"
"url": "/sv/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera till PDF med dolda bilder i Java-bilder


## Introduktion till att konvertera PowerPoint-presentationer till PDF med dolda bilder med Aspose.Slides för Java

den här steg-för-steg-guiden lär du dig hur du konverterar en PowerPoint-presentation till PDF samtidigt som du bevarar dolda bilder med hjälp av Aspose.Slides för Java. Dolda bilder är de som inte visas under en vanlig presentation men som kan inkluderas i PDF-utdata. Vi förser dig med källkoden och detaljerade instruktioner för att utföra denna uppgift.

## Förkunskapskrav

Innan du börjar, se till att du har följande förutsättningar på plats:

1. Aspose.Slides för Java-biblioteket: Se till att du har konfigurerat Aspose.Slides för Java-biblioteket i ditt Java-projekt. Du kan ladda ner det från [Aspose.Slides för Java-dokumentation](https://reference.aspose.com/slides/java/).

2. Java-utvecklingsmiljö: Du bör ha en Java-utvecklingsmiljö installerad på ditt system.

## Steg 1: Importera Aspose.Slides för Java

Först måste du importera Aspose.Slides-biblioteket till ditt Java-projekt. Se till att du har lagt till biblioteket i projektets byggsökväg.

```java
import com.aspose.slides.*;
```

## Steg 2: Ladda PowerPoint-presentationen

Du börjar med att ladda PowerPoint-presentationen som du vill konvertera till PDF. Ersätt `"Your Document Directory"` och `"HiddingSlides.pptx"` med rätt filsökväg.

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Steg 3: Konfigurera PDF-alternativ

Konfigurera PDF-alternativen för att inkludera dolda bilder i PDF-utdata. Du kan göra detta genom att ställa in `setShowHiddenSlides` egendomen tillhörande `PdfOptions` klass till `true`.

```java
// Instansiera PdfOptions-klassen
PdfOptions pdfOptions = new PdfOptions();
// Ange att det genererade dokumentet ska innehålla dolda bilder
pdfOptions.setShowHiddenSlides(true);
```

## Steg 4: Spara presentationen som PDF

Spara nu presentationen till en PDF-fil med de angivna alternativen. Ersätt `"PDFWithHiddenSlides_out.pdf"` med ditt önskade utdatafilnamn.

```java
// Spara presentationen som PDF med angivna alternativ
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Steg 5: Rengöringsresurser

Se till att frigöra de resurser som används av presentationen när du är klar med den.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Komplett källkod för att konvertera till PDF med dolda bilder i Java-bilder

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Instansiera PdfOptions-klassen
	PdfOptions pdfOptions = new PdfOptions();
	// Ange att det genererade dokumentet ska innehålla dolda bilder
	pdfOptions.setShowHiddenSlides(true);
	// Spara presentationen som PDF med angivna alternativ
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här omfattande guiden har du lärt dig hur du konverterar en PowerPoint-presentation till PDF samtidigt som du bevarar dolda bilder med hjälp av Aspose.Slides för Java. Vi har försett dig med en steg-för-steg-handledning tillsammans med nödvändig källkod för att utföra denna uppgift smidigt.

## Vanliga frågor

### Hur kan jag dölja bilder i en PowerPoint-presentation?

Så här döljer du en bild i en PowerPoint-presentation:
1. Markera den bild du vill dölja i bildsorteringsvyn.
2. Högerklicka på den valda bilden.
3. Välj "Dölj bild" från kontextmenyn.

### Kan jag programmatiskt visa dolda bilder i Aspose.Slides för Java?

Ja, du kan programmatiskt visa dolda bilder i Aspose.Slides för Java genom att ställa in `Hidden` egendomen tillhörande `Slide` klass till `false`Här är ett exempel:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Ersätt slideIndex med indexet för den dolda bilden
slide.setHidden(false);
```

### Hur laddar jag ner Aspose.Slides för Java?

Du kan ladda ner Aspose.Slides för Java från Asposes webbplats. Besök [Nedladdningssida för Aspose.Slides för Java](https://releases.aspose.com/slides/java/) för att få den senaste versionen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}