---
"description": "Lär dig hur du manipulerar PowerPoint-presentationer programmatiskt med Aspose.Slides för Java. Bemästra Java PowerPoint-hantering med steg-för-steg-handledningar."
"linktitle": "Spara PowerPoint med standardtypsnittet Vanligt teckensnitt med Java"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Spara PowerPoint med standardtypsnittet Vanligt teckensnitt med Java"
"url": "/sv/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Spara PowerPoint med standardtypsnittet Vanligt teckensnitt med Java

## Introduktion
Inom Java-utveckling kan skapande och manipulering av PowerPoint-presentationer programmatiskt avsevärt förbättra produktiviteten och anpassningsmöjligheterna. Aspose.Slides för Java är ett robust bibliotek som ger utvecklare möjlighet att effektivt hantera PowerPoint-filer och erbjuder en omfattande uppsättning funktioner, från enkla modifieringar till komplexa presentationer.
## Förkunskapskrav
Innan du börjar använda Aspose.Slides för Java, se till att du har följande förutsättningar konfigurerade:
1. Java Development Kit (JDK): Aspose.Slides för Java kräver JDK 1.8 eller senare för att fungera korrekt.
2. Aspose.Slides för Java JAR: Ladda ner den senaste versionen av Aspose.Slides för Java från [här](https://releases.aspose.com/slides/java/).
3. Integrerad utvecklingsmiljö (IDE): Använd IntelliJ IDEA, Eclipse eller någon annan Java IDE som du väljer.
4. Grundläggande förståelse för Java: Det är nödvändigt att ha goda kunskaper i programmeringsspråket Java.

## Importera paket
För att börja använda Aspose.Slides för Java, importera nödvändiga paket:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Detta säkerställer att du har tillgång till alla klasser och metoder som tillhandahålls av Aspose.Slides för Java.
## Steg 1: Konfigurera ditt projekt
Skapa först ett nytt Java-projekt i din IDE och inkludera Aspose.Slides för Java JAR-filen i projektets byggsökväg.
## Steg 2: Initiera presentationsobjektet
Instansiera en `Presentation` objektet genom att läsa in en befintlig PowerPoint-fil (.pptx) från din lokala katalog.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Ladda presentation
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
Ersätta `"Your Document Directory"` och `"Your Output Directory"` med dina faktiska filsökvägar.
## Steg 3: Spara presentationen med vanliga standardteckensnitt
Ange standardtypsnittet för utdataformaten (HTML och PDF) med hjälp av `HtmlOptions` och `PdfOptions` respektive.
```java
try {
    // HTML-sparalternativ
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // PDF-sparalternativ
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
Se till att byta ut `"Arial Black"` och `"Lucida Console"` med dina önskade vanliga standardteckensnitt.

## Slutsats
Genom att följa dessa steg har du lärt dig hur du effektivt hanterar PowerPoint-presentationer med Aspose.Slides för Java. Den här funktionen låter dig automatisera uppgifter, anpassa presentationer och förbättra dina Java-applikationer med avancerade PowerPoint-hanteringsfunktioner.
## Vanliga frågor
### Kan Aspose.Slides för Java fungera med äldre versioner av JDK?
Aspose.Slides för Java kräver JDK 1.8 eller senare för kompatibilitet.
### Hur kan jag få en tillfällig licens för Aspose.Slides för Java?
Du kan få en tillfällig licens från [här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta mer detaljerad dokumentation om Aspose.Slides för Java?
Utforska den omfattande dokumentationen [här](https://reference.aspose.com/slides/java/).
### Finns det community-support tillgänglig för Aspose.Slides för Java?
Ja, du kan få stöd från samhället [här](https://forum.aspose.com/c/slides/11).
### Kan jag prova Aspose.Slides för Java gratis?
Ja, ladda ner en gratis testversion [här](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}