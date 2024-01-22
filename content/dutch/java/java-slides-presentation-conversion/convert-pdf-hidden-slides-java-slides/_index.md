---
title: Converteren naar PDF met verborgen dia's in Java-dia's
linktitle: Converteren naar PDF met verborgen dia's in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u PowerPoint-presentaties naar PDF kunt converteren met verborgen dia's met behulp van Aspose.Slides voor Java. Volg onze stapsgewijze handleiding met broncode voor het naadloos genereren van PDF's.
type: docs
weight: 27
url: /nl/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/
---

## Inleiding tot het converteren van PowerPoint-presentaties naar PDF met verborgen dia's met behulp van Aspose.Slides voor Java

In deze stapsgewijze handleiding leert u hoe u een PowerPoint-presentatie naar PDF kunt converteren terwijl u verborgen dia's behoudt met behulp van Aspose.Slides voor Java. Verborgen dia's zijn dia's die niet worden weergegeven tijdens een gewone presentatie, maar die kunnen worden opgenomen in de PDF-uitvoer. Wij voorzien u van de broncode en gedetailleerde instructies om deze taak te volbrengen.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1.  Aspose.Slides voor Java-bibliotheek: Zorg ervoor dat u de Aspose.Slides voor Java-bibliotheek hebt ingesteld in uw Java-project. Je kunt het downloaden van de[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

2. Java-ontwikkelomgeving: Er moet een Java-ontwikkelomgeving op uw systeem zijn geïnstalleerd.

## Stap 1: Importeer Aspose.Slides voor Java

Eerst moet u de Aspose.Slides-bibliotheek in uw Java-project importeren. Zorg ervoor dat u de bibliotheek aan het buildpad van uw project hebt toegevoegd.

```java
import com.aspose.slides.*;
```

## Stap 2: Laad de PowerPoint-presentatie

 U begint met het laden van de PowerPoint-presentatie die u naar PDF wilt converteren. Vervangen`"Your Document Directory"` En`"HiddingSlides.pptx"` met het juiste bestandspad.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Stap 3: Configureer PDF-opties

 Configureer de PDF-opties om verborgen dia's op te nemen in de PDF-uitvoer. Dit kunt u doen door het instellen van de`setShowHiddenSlides` eigendom van de`PdfOptions` klasse aan`true`.

```java
// Instantieer de klasse PdfOptions
PdfOptions pdfOptions = new PdfOptions();
// Geef op dat het gegenereerde document verborgen dia's moet bevatten
pdfOptions.setShowHiddenSlides(true);
```

## Stap 4: Sla de presentatie op als PDF

 Sla de presentatie nu op in een PDF-bestand met de opgegeven opties. Vervangen`"PDFWithHiddenSlides_out.pdf"` met de gewenste uitvoerbestandsnaam.

```java
// Sla de presentatie op in PDF met gespecificeerde opties
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Stap 5: Hulpbronnen opruimen

Zorg ervoor dat u de bronnen die door de presentatie worden gebruikt, vrijgeeft als u klaar bent.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Volledige broncode voor conversie naar PDF met verborgen dia's in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Instantieer de klasse PdfOptions
	PdfOptions pdfOptions = new PdfOptions();
	// Geef op dat het gegenereerde document verborgen dia's moet bevatten
	pdfOptions.setShowHiddenSlides(true);
	// Sla de presentatie op in PDF met gespecificeerde opties
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze uitgebreide handleiding hebt u geleerd hoe u een PowerPoint-presentatie naar PDF kunt converteren terwijl u verborgen dia's behoudt met Aspose.Slides voor Java. We hebben u een stapsgewijze zelfstudie gegeven, samen met de benodigde broncode, om deze taak naadloos uit te voeren.

## Veelgestelde vragen

### Hoe kan ik dia's verbergen in een PowerPoint-presentatie?

Volg deze stappen om een dia in een PowerPoint-presentatie te verbergen:
1. Selecteer de dia die u wilt verbergen in de diasorteerderweergave.
2. Klik met de rechtermuisknop op de geselecteerde dia.
3. Kies "Dia verbergen" in het contextmenu.

### Kan ik verborgen dia's programmatisch zichtbaar maken in Aspose.Slides voor Java?

 Ja, u kunt verborgen dia's programmatisch zichtbaar maken in Aspose.Slides voor Java door de`Hidden` eigendom van de`Slide` klasse aan`false`. Hier is een voorbeeld:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Vervang slideIndex door de index van de verborgen dia
slide.setHidden(false);
```

### Hoe download ik Aspose.Slides voor Java?

 kunt Aspose.Slides voor Java downloaden van de Aspose-website. Bezoek de[Aspose.Slides voor Java-downloadpagina](https://releases.aspose.com/slides/java/) om de nieuwste versie te krijgen.