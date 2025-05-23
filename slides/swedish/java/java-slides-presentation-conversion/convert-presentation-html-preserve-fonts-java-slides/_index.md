---
"description": "Konvertera PowerPoint-presentationer till HTML samtidigt som du bevarar originalteckensnitt med Aspose.Slides för Java."
"linktitle": "Konvertera presentationer till HTML med bevarande av originalteckensnitt i Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Konvertera presentationer till HTML med bevarande av originalteckensnitt i Java Slides"
"url": "/sv/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Konvertera presentationer till HTML med bevarande av originalteckensnitt i Java Slides


## Introduktion till att konvertera presentationer till HTML med bevarande av originalteckensnitt i Java Slides

I den här handledningen ska vi utforska hur man konverterar en PowerPoint-presentation (PPTX) till HTML samtidigt som man bevarar de ursprungliga teckensnitten med hjälp av Aspose.Slides för Java. Detta säkerställer att den resulterande HTML-koden liknar utseendet på den ursprungliga presentationen.

## Steg 1: Konfigurera projektet
Innan vi går in i koden, låt oss se till att du har de nödvändiga inställningarna på plats:

1. Ladda ner Aspose.Slides för Java: Om du inte redan har gjort det, ladda ner och inkludera Aspose.Slides för Java-biblioteket i ditt projekt.

2. Skapa ett Java-projekt: Konfigurera ett Java-projekt i din favorit-IDE och se till att du har en "lib"-mapp där du kan placera Aspose.Slides JAR-filen.

3. Importera obligatoriska klasser: Importera de nödvändiga klasserna i början av din Java-fil:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Steg 2: Konvertera presentation till HTML med originaltypsnitt

Nu ska vi konvertera en PowerPoint-presentation till HTML samtidigt som vi bevarar de ursprungliga teckensnitten:

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";

// Ladda presentationen
Presentation pres = new Presentation("input.pptx");

try {
    // Exkludera standardpresentationsfonter som Calibri och Arial
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Skapa HTML-alternativ och ange anpassad HTML-formatering
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Spara presentationen som HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Kassera presentationsobjektet
    if (pres != null) pres.dispose();
}
```

I det här kodavsnittet:

- Vi laddar in PowerPoint-presentationen med hjälp av `Presentation`.

- Vi definierar en lista med teckensnitt (`fontNameExcludeList`) som vi vill exkludera från inbäddning i HTML-koden. Detta är användbart för att exkludera vanliga teckensnitt som Calibri och Arial för att minska filstorleken.

- Vi skapar en instans av `EmbedAllFontsHtmlController` och skicka listan över teckensnittsutestängningar till den.

- Vi skapar `HtmlOptions` och ange en anpassad HTML-formatering med hjälp av `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Slutligen sparar vi presentationen som HTML med de angivna alternativen.

## Komplett källkod för att konvertera presentationer till HTML med bevarande av originalteckensnitt i Java Slides

```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// exkludera standardpresentationsfonter
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

I den här handledningen har du lärt dig hur du konverterar en PowerPoint-presentation till HTML samtidigt som du bevarar de ursprungliga teckensnitten med hjälp av Aspose.Slides för Java. Detta är användbart när du vill behålla den visuella återgivningen av dina presentationer när du delar dem på webben.

## Vanliga frågor

### Hur laddar jag ner Aspose.Slides för Java?

Du kan ladda ner Aspose.Slides för Java från Asposes webbplats. Besök [här](https://downloads.aspose.com/slides/java/) för att få den senaste versionen.

### Kan jag anpassa listan över undantagna teckensnitt?

Ja, du kan anpassa `fontNameExcludeList` array för att inkludera eller exkludera specifika teckensnitt enligt dina krav.

### Fungerar den här metoden för äldre PowerPoint-format som PPT?

Det här kodexemplet är utformat för PPTX-filer. Om du behöver konvertera äldre PPT-filer kan du behöva justera koden.

### Hur kan jag ytterligare anpassa HTML-utdata?

Du kan utforska `HtmlOptions` klassen för att anpassa olika aspekter av HTML-utdata, såsom bildstorlek, bildkvalitet med mera.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}