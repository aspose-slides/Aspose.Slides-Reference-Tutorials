---
title: Spara PowerPoint med standardtypsnitt med Java
linktitle: Spara PowerPoint med standardtypsnitt med Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du manipulerar PowerPoint-presentationer programmatiskt med Aspose.Slides för Java. Bemästra Java PowerPoint-hantering med steg-för-steg handledning.
weight: 12
url: /sv/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Spara PowerPoint med standardtypsnitt med Java

## Introduktion
Inom Java-utveckling kan skapa och manipulera PowerPoint-presentationer programmatiskt avsevärt förbättra produktiviteten och anpassningsalternativen. Aspose.Slides för Java är ett robust bibliotek som ger utvecklare möjlighet att effektivt hantera PowerPoint-filer, och erbjuder en omfattande uppsättning funktioner från enkla modifieringar till komplexa presentationer.
## Förutsättningar
Innan du börjar använda Aspose.Slides för Java, se till att du har ställt in följande förutsättningar:
1. Java Development Kit (JDK): Aspose.Slides för Java kräver JDK 1.8 eller högre för att fungera korrekt.
2. Aspose.Slides för Java JAR: Ladda ner den senaste versionen av Aspose.Slides för Java från[här](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Använd IntelliJ IDEA, Eclipse eller annan valfri Java IDE.
4. Grundläggande förståelse för Java: Bekantskap med grunderna i Java programmeringsspråk är nödvändig.

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
Skapa först ett nytt Java-projekt i din IDE och inkludera Aspose.Slides for Java JAR-filen i ditt projekts byggsökväg.
## Steg 2: Initiera presentationsobjekt
 Instantiera en`Presentation` objekt genom att ladda en befintlig PowerPoint-fil (.pptx) från din lokala katalog.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Ladda presentationen
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Byta ut`"Your Document Directory"` och`"Your Output Directory"` med dina faktiska filsökvägar.
## Steg 3: Spara presentationen med vanliga vanliga teckensnitt
 Ange standardtypsnittet för utdataformaten (HTML och PDF) med hjälp av`HtmlOptions` och`PdfOptions` respektive.
```java
try {
    // HTML spara alternativ
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // Alternativ för att spara PDF
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Se till att byta ut`"Arial Black"` och`"Lucida Console"` med önskade standardtypsnitt.

## Slutsats
Genom att följa dessa steg har du lärt dig hur du effektivt manipulerar PowerPoint-presentationer med Aspose.Slides för Java. Denna funktion låter dig automatisera uppgifter, anpassa presentationer och förbättra dina Java-applikationer med avancerade PowerPoint-hanteringsfunktioner.
## FAQ's
### Kan Aspose.Slides för Java fungera med äldre versioner av JDK?
Aspose.Slides för Java kräver JDK 1.8 eller högre för kompatibilitet.
### Hur kan jag få tillfällig licens för Aspose.Slides för Java?
 Du kan få en tillfällig licens från[här](https://purchase.aspose.com/temporary-license/).
### Var kan jag hitta mer detaljerad dokumentation om Aspose.Slides för Java?
 Utforska den omfattande dokumentationen[här](https://reference.aspose.com/slides/java/).
### Finns det gemenskapsstöd tillgängligt för Aspose.Slides för Java?
 Ja, du kan få stöd från samhället[här](https://forum.aspose.com/c/slides/11).
### Kan jag prova Aspose.Slides för Java gratis?
 Ja, ladda ner en gratis testversion[här](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
