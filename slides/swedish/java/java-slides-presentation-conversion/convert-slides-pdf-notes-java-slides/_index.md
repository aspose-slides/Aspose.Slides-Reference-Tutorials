---
"description": "Lär dig hur du konverterar PowerPoint-bilder till PDF med anteckningar i Java med hjälp av Aspose.Slides för Java. Steg-för-steg-guide för Java-utvecklare. Förbättra din presentationsdelning."
"linktitle": "Konvertera bilder till PDF med anteckningar i Java-bilder"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Konvertera bilder till PDF med anteckningar i Java-bilder"
"url": "/sv/java/presentation-conversion/convert-slides-pdf-notes-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera bilder till PDF med anteckningar i Java-bilder


## Introduktion till att konvertera bilder till PDF med anteckningar i Java

I den digitala presentationsvärlden är möjligheten att konvertera bilder till PDF med tillhörande anteckningar en värdefull funktion. Java-utvecklare kan uppnå detta med hjälp av biblioteket Aspose.Slides för Java, som tillhandahåller en robust uppsättning verktyg för att arbeta med PowerPoint-presentationer programmatiskt. I den här steg-för-steg-guiden kommer vi att utforska hur man konverterar bilder till PDF med anteckningar med hjälp av Java och Aspose.Slides för Java.

## Förkunskapskrav

Innan vi går in i koden, se till att du har följande förutsättningar på plats:

- Java Development Kit (JDK) installerat på ditt system.
- Aspose.Slides för Java-biblioteket. Du kan ladda ner det från [här](https://releases.aspose.com/slides/java/).

Nu när vi har vår disposition, låt oss dyka in i implementeringen steg för steg.
## Steg 1: Konfigurera projektet

Skapa först ett Java-projekt och lägg till Aspose.Slides för Java-biblioteket i projektets beroenden.

## Steg 2: Ladda presentationen

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

## Steg 5: Justera bildstorlek

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
// Instansiera ett presentationsobjekt som representerar en presentationsfil 
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

den här handledningen lärde vi oss hur man konverterar bilder till PDF med anteckningar i Java med hjälp av Aspose.Slides för Java. Vi gick igenom hur man konfigurerar projektet, laddar presentationen, skapar en ny presentation, kopierar bilder, justerar bildstorlek, konfigurerar PDF-alternativ och slutligen sparar presentationen som en PDF med anteckningar.

## Vanliga frågor

### Hur installerar jag Aspose.Slides för Java?

För att installera Aspose.Slides för Java, följ dessa steg:
1. Ladda ner biblioteket från [här](https://releases.aspose.com/slides/java/).
2. Lägg till JAR-filen i ditt Java-projekts klassväg.

### Kan jag anpassa anteckningarnas placering i den genererade PDF-filen?

Ja, du kan anpassa anteckningarnas position genom att ändra `NotesPositions` enum i PDF-alternativen. I den här handledningen ställer vi in den på `BottomFull`, men du kan även utforska andra alternativ.

### Finns det några licenskrav för att använda Aspose.Slides för Java?

Ja, Aspose.Slides för Java är ett kommersiellt bibliotek, och du kan behöva skaffa en licens för att använda det i produktion. Besök Asposes webbplats för licensinformation.

### Kan jag konvertera flera bilder samtidigt?

Absolut! Du kan loopa igenom bilderna i din presentation och klona dem till den nya presentationen, vilket gör att du kan konvertera flera bilder till PDF med anteckningar på en gång.

### Var kan jag hitta mer dokumentation för Aspose.Slides för Java?

Du hittar detaljerad dokumentation för Aspose.Slides för Java på webbplatsen: [Aspose.Slides för Java API-referens](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}