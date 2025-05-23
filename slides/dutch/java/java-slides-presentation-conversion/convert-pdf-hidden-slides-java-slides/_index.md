---
"description": "Leer hoe je PowerPoint-presentaties converteert naar PDF met verborgen dia's met Aspose.Slides voor Java. Volg onze stapsgewijze handleiding met broncode voor naadloze PDF-generatie."
"linktitle": "Converteren naar PDF met verborgen dia's in Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Converteren naar PDF met verborgen dia's in Java Slides"
"url": "/nl/java/presentation-conversion/convert-pdf-hidden-slides-java-slides/"
"weight": 27
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Converteren naar PDF met verborgen dia's in Java Slides


## Inleiding tot het converteren van een PowerPoint-presentatie naar PDF met verborgen dia's met Aspose.Slides voor Java

In deze stapsgewijze handleiding leert u hoe u een PowerPoint-presentatie naar PDF converteert met behoud van verborgen dia's met behulp van Aspose.Slides voor Java. Verborgen dia's zijn dia's die niet worden weergegeven tijdens een reguliere presentatie, maar wel in de PDF-uitvoer kunnen worden opgenomen. We geven u de broncode en gedetailleerde instructies om deze taak uit te voeren.

## Vereisten

Voordat u begint, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:

1. Aspose.Slides voor Java-bibliotheek: Zorg ervoor dat de Aspose.Slides voor Java-bibliotheek is ingesteld in uw Java-project. U kunt deze downloaden van de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/).

2. Java-ontwikkelomgeving: er moet een Java-ontwikkelomgeving op uw systeem geïnstalleerd zijn.

## Stap 1: Aspose.Slides importeren voor Java

Importeer eerst de Aspose.Slides-bibliotheek in je Java-project. Zorg ervoor dat je de bibliotheek hebt toegevoegd aan het buildpad van je project.

```java
import com.aspose.slides.*;
```

## Stap 2: Laad de PowerPoint-presentatie

begint met het laden van de PowerPoint-presentatie die u naar PDF wilt converteren. Vervangen `"Your Document Directory"` En `"HiddingSlides.pptx"` met het juiste bestandspad.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
```

## Stap 3: PDF-opties configureren

Configureer de PDF-opties om verborgen dia's in de PDF-uitvoer op te nemen. U kunt dit doen door de `setShowHiddenSlides` eigendom van de `PdfOptions` klasse om `true`.

```java
// Instantieer de PdfOptions-klasse
PdfOptions pdfOptions = new PdfOptions();
// Geef aan dat het gegenereerde document verborgen dia's moet bevatten
pdfOptions.setShowHiddenSlides(true);
```

## Stap 4: Sla de presentatie op als PDF

Sla de presentatie nu op als een PDF-bestand met de opgegeven opties. Vervangen `"PDFWithHiddenSlides_out.pdf"` met de gewenste naam voor het uitvoerbestand.

```java
// Sla de presentatie op als PDF met de opgegeven opties
presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Stap 5: Opruimen van bronnen

Zorg ervoor dat u de bronnen die voor de presentatie zijn gebruikt, vrijgeeft wanneer u klaar bent.

```java
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Volledige broncode voor het converteren naar PDF met verborgen dia's in Java Slides

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HiddingSlides.pptx");
try
{
	// Instantieer de PdfOptions-klasse
	PdfOptions pdfOptions = new PdfOptions();
	// Geef aan dat het gegenereerde document verborgen dia's moet bevatten
	pdfOptions.setShowHiddenSlides(true);
	// Sla de presentatie op als PDF met de opgegeven opties
	presentation.save(dataDir + "PDFWithHiddenSlides_out.pdf", SaveFormat.Pdf, pdfOptions);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Conclusie

In deze uitgebreide handleiding heb je geleerd hoe je een PowerPoint-presentatie naar PDF converteert met behoud van verborgen dia's met Aspose.Slides voor Java. We hebben een stapsgewijze handleiding en de benodigde broncode toegevoegd om deze taak naadloos uit te voeren.

## Veelgestelde vragen

### Hoe kan ik dia's in een PowerPoint-presentatie verbergen?

Voer de volgende stappen uit om een dia in een PowerPoint-presentatie te verbergen:
1. Selecteer de dia die u wilt verbergen in de diasorteerderweergave.
2. Klik met de rechtermuisknop op de geselecteerde dia.
3. Kies 'Dia verbergen' in het contextmenu.

### Kan ik verborgen dia's in Aspose.Slides voor Java programmatisch zichtbaar maken?

Ja, u kunt verborgen dia's in Aspose.Slides voor Java programmatisch zichtbaar maken door de `Hidden` eigendom van de `Slide` klasse om `false`Hier is een voorbeeld:

```java
Slide slide = presentation.getSlides().get_Item(slideIndex); // Vervang slideIndex met de index van de verborgen dia
slide.setHidden(false);
```

### Hoe download ik Aspose.Slides voor Java?

U kunt Aspose.Slides voor Java downloaden van de Aspose-website. Bezoek de [Aspose.Slides voor Java downloadpagina](https://releases.aspose.com/slides/java/) om de nieuwste versie te krijgen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}