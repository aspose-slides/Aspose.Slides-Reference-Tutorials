---
title: Sla PowerPoint op met het standaard reguliere lettertype met behulp van Java
linktitle: Sla PowerPoint op met het standaard reguliere lettertype met behulp van Java
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u PowerPoint-presentaties programmatisch kunt manipuleren met Aspose.Slides voor Java. Beheers het omgaan met Java PowerPoint met stapsgewijze zelfstudies.
type: docs
weight: 12
url: /nl/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---
## Invoering
Op het gebied van Java-ontwikkeling kan het programmatisch maken en manipuleren van PowerPoint-presentaties de productiviteit en aanpassingsmogelijkheden aanzienlijk verbeteren. Aspose.Slides voor Java is een robuuste bibliotheek waarmee ontwikkelaars PowerPoint-bestanden efficiënt kunnen verwerken en een uitgebreide reeks functies biedt, van eenvoudige aanpassingen tot complexe presentaties.
## Vereisten
Voordat u Aspose.Slides voor Java gaat gebruiken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Aspose.Slides voor Java vereist JDK 1.8 of hoger om correct te functioneren.
2. Aspose.Slides voor Java JAR: Download de nieuwste versie van Aspose.Slides voor Java van[hier](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Gebruik IntelliJ IDEA, Eclipse of een andere Java IDE naar keuze.
4. Basiskennis van Java: Bekendheid met de grondbeginselen van de Java-programmeertaal is noodzakelijk.

## Pakketten importeren
Importeer de benodigde pakketten om Aspose.Slides voor Java te gaan gebruiken:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Dit zorgt ervoor dat u toegang heeft tot alle klassen en methoden die door Aspose.Slides voor Java worden aangeboden.
## Stap 1: Stel uw project in
Maak eerst een nieuw Java-project in uw IDE en neem het Aspose.Slides for Java JAR-bestand op in het buildpad van uw project.
## Stap 2: Initialiseer het presentatieobject
 Instantieer een`Presentation` object door een bestaand PowerPoint-bestand (.pptx) vanuit uw lokale map te laden.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Presentatie laden
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Vervangen`"Your Document Directory"` En`"Your Output Directory"` met uw daadwerkelijke bestandspaden.
## Stap 3: Presentatie opslaan met standaard reguliere lettertypen
 Geef het standaard reguliere lettertype op voor de uitvoerformaten (HTML en PDF).`HtmlOptions` En`PdfOptions` respectievelijk.
```java
try {
    // HTML-opslagopties
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // PDF-opslagopties
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Zorg ervoor dat u deze vervangt`"Arial Black"` En`"Lucida Console"` met uw gewenste standaard reguliere lettertypen.

## Conclusie
Door deze stappen te volgen, hebt u geleerd hoe u PowerPoint-presentaties effectief kunt manipuleren met Aspose.Slides voor Java. Met deze mogelijkheid kunt u taken automatiseren, presentaties aanpassen en uw Java-toepassingen uitbreiden met geavanceerde PowerPoint-verwerkingsfunctionaliteiten.
## Veelgestelde vragen
### Kan Aspose.Slides voor Java werken met oudere versies van JDK?
Aspose.Slides voor Java vereist JDK 1.8 of hoger voor compatibiliteit.
### Hoe kan ik tijdelijke licenties krijgen voor Aspose.Slides voor Java?
 Een tijdelijke licentie kunt u verkrijgen bij[hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik meer gedetailleerde documentatie vinden over Aspose.Slides voor Java?
 Ontdek de uitgebreide documentatie[hier](https://reference.aspose.com/slides/java/).
### Is er community-ondersteuning beschikbaar voor Aspose.Slides voor Java?
 Ja, u kunt gemeenschapssteun krijgen[hier](https://forum.aspose.com/c/slides/11).
### Kan ik Aspose.Slides voor Java gratis uitproberen?
 Ja, download een gratis proefversie[hier](https://releases.aspose.com/).