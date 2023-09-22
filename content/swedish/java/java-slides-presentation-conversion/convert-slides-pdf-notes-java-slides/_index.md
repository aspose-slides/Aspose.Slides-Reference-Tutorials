---
title: Konvertera bilder till PDF med Notes i Java Slides
linktitle: Konvertera bilder till PDF med Notes i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du konverterar PowerPoint-bilder till PDF med anteckningar i Java med Aspose.Slides för Java. Steg-för-steg-guide för Java-utvecklare. Förbättra din presentationsdelning.
type: docs
weight: 19
url: /sv/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## Introduktion till att konvertera bilder till PDF med Notes i Java

I en värld av digitala presentationer är möjligheten att konvertera bilder till PDF med tillhörande anteckningar en värdefull funktion. Java-utvecklare kan uppnå detta med Aspose.Slides for Java-biblioteket, som tillhandahåller en robust uppsättning verktyg för att arbeta med PowerPoint-presentationer programmatiskt. I den här steg-för-steg-guiden kommer vi att utforska hur man konverterar bilder till PDF med anteckningar med Java och Aspose.Slides för Java.

## Förutsättningar

Innan vi dyker in i koden, se till att du har följande förutsättningar på plats:

- Java Development Kit (JDK) installerat på ditt system.
-  Aspose.Slides för Java-bibliotek. Du kan ladda ner den från[här](https://releases.aspose.com/slides/java/).

Nu när vi har vår disposition, låt oss dyka in i implementeringen steg för steg.
## Steg 1: Konfigurera projektet

Skapa först ett Java-projekt och lägg till Aspose.Slides for Java-biblioteket till ditt projekts beroenden.

## Steg 2: Laddar presentationen

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Steg 3: Skapa en ny presentation

```java
Presentation auxPresentation = new Presentation();
```

## Steg 4: Kopiera bilder

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Steg 5: Justera bildens storlek

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Steg 6: Konfigurera PDF-alternativ

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Steg 7: Spara som PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Komplett källkod för att konvertera bilder till PDF med anteckningar i Java-bilder

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
// Instantiera ett presentationsobjekt som representerar en presentationsfil
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Ställa in bildtyp och storlek
		//auxPresentation.getSlideSize().setSize(presentation.getSlideSize().getSize().getWidth(), presentation.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
		auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
		PdfOptions pdfOptions = new PdfOptions();
		INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
		options.setNotesPosition(NotesPositions.BottomFull);
		auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
	}
	finally
	{
		if (auxPresentation != null) auxPresentation.dispose();
	}
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Slutsats

I den här handledningen lärde vi oss hur man konverterar bilder till PDF med anteckningar i Java med Aspose.Slides för Java. Vi täckte inställningen av projektet, laddade presentationen, skapa en ny presentation, kopiera bilder, justera bildstorleken, konfigurera PDF-alternativ och slutligen spara presentationen som en PDF med anteckningar.

## FAQ's

### Hur installerar jag Aspose.Slides för Java?

För att installera Aspose.Slides för Java, följ dessa steg:
1.  Ladda ner biblioteket från[här](https://releases.aspose.com/slides/java/).
2. Lägg till JAR-filen i ditt Java-projekts klassväg.

### Kan jag anpassa anteckningarnas position i den genererade PDF-filen?

 Ja, du kan anpassa anteckningarnas position genom att ändra`NotesPositions` enum i PDF-alternativen. I den här handledningen ställer vi in den till`BottomFull`, men du kan också utforska andra alternativ.

### Finns det några licenskrav för att använda Aspose.Slides för Java?

Ja, Aspose.Slides för Java är ett kommersiellt bibliotek, och du kan behöva skaffa en licens för att använda det i produktionen. Besök Asposes webbplats för licensinformation.

### Kan jag konvertera flera bilder samtidigt?

Säkert! Du kan gå igenom bilderna i din presentation och klona dem till den nya presentationen, så att du kan konvertera flera bilder till PDF med anteckningar på en gång.

### Var kan jag hitta mer dokumentation för Aspose.Slides för Java?

 Du kan hitta detaljerad dokumentation för Aspose.Slides för Java på webbplatsen:[Aspose.Slides för Java API Referens](https://reference.aspose.com/slides/java/).