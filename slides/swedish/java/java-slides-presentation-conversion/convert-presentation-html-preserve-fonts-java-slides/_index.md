---
title: Konvertera presentation till HTML med att bevara originalteckensnitt i Java Slides
linktitle: Konvertera presentation till HTML med att bevara originalteckensnitt i Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Konvertera PowerPoint-presentationer till HTML samtidigt som de ursprungliga typsnitten bevaras med Aspose.Slides för Java.
weight: 14
url: /sv/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Introduktion till att konvertera presentation till HTML med att bevara originalteckensnitt i Java Slides

I den här handledningen kommer vi att utforska hur man konverterar en PowerPoint-presentation (PPTX) till HTML samtidigt som de ursprungliga typsnitten bevaras med Aspose.Slides för Java. Detta kommer att säkerställa att den resulterande HTML-koden liknar utseendet på den ursprungliga presentationen.

## Steg 1: Konfigurera projektet
Innan vi dyker in i koden, låt oss se till att du har de nödvändiga inställningarna på plats:

1. Ladda ner Aspose.Slides för Java: Om du inte redan har gjort det, ladda ner och inkludera Aspose.Slides for Java-biblioteket i ditt projekt.

2. Skapa ett Java-projekt: Sätt upp ett Java-projekt i din favorit-IDE och se till att du har en "lib"-mapp där du kan placera Aspose.Slides JAR-filen.

3. Importera obligatoriska klasser: Importera de nödvändiga klasserna i början av din Java-fil:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Steg 2: Konvertera presentation till HTML med originalteckensnitt

Låt oss nu konvertera en PowerPoint-presentation till HTML samtidigt som vi behåller de ursprungliga typsnitten:

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Ladda presentationen
Presentation pres = new Presentation("input.pptx");

try {
    // Uteslut standardpresentationstypsnitt som Calibri och Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Skapa HTML-alternativ och ställ in den anpassade HTML-formateraren
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Spara presentationen som HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Kassera presentationsobjektet
    if (pres != null) pres.dispose();
}
```

I detta kodavsnitt:

-  Vi laddar ingången PowerPoint-presentation med hjälp av`Presentation`.

- Vi definierar en lista med teckensnitt (`fontNameExcludeList`som vi vill utesluta från inbäddning i HTML. Detta är användbart för att utesluta vanliga typsnitt som Calibri och Arial för att minska filstorleken.

-  Vi skapar en instans av`EmbedAllFontsHtmlController` och skicka listan över teckensnittsuteslutningar till den.

-  Vi skapar`HtmlOptions` och ställ in en anpassad HTML-formaterare med`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Slutligen sparar vi presentationen som HTML med de angivna alternativen.

## Komplett källkod för att konvertera presentation till HTML med att bevara originalteckensnitt i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// exkludera standardpresentationsteckensnitt
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Slutsats

I den här handledningen har du lärt dig hur du konverterar en PowerPoint-presentation till HTML samtidigt som du bevarar de ursprungliga typsnitten med Aspose.Slides för Java. Detta är användbart när du vill bibehålla den visuella troheten i dina presentationer när du delar dem på webben.

## FAQ's

### Hur laddar jag ner Aspose.Slides för Java?

 Du kan ladda ner Aspose.Slides för Java från Asposes webbplats. Besök[här](https://downloads.aspose.com/slides/java/) för att få den senaste versionen.

### Kan jag anpassa listan över uteslutna typsnitt?

 Ja, du kan anpassa`fontNameExcludeList` array för att inkludera eller utesluta specifika typsnitt enligt dina krav.

### Fungerar den här metoden för äldre PowerPoint-format som PPT?

Detta kodexempel är designat för PPTX-filer. Om du behöver konvertera äldre PPT-filer kan du behöva göra justeringar i koden.

### Hur kan jag anpassa HTML-utdata ytterligare?

 Du kan utforska`HtmlOptions` klass för att anpassa olika aspekter av HTML-utdata, såsom bildstorlek, bildkvalitet och mer.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
