---
title: Converteer dia's naar PDF met notities in Java-dia's
linktitle: Converteer dia's naar PDF met notities in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u PowerPoint-dia's naar PDF kunt converteren met notities in Java met behulp van Aspose.Slides voor Java. Stapsgewijze handleiding voor Java-ontwikkelaars. Verbeter het delen van uw presentaties.
type: docs
weight: 19
url: /nl/java/presentation-conversion/convert-slides-pdf-notes-java-slides/
---

## Inleiding tot het converteren van dia's naar PDF met notities in Java

In de wereld van digitale presentaties is de mogelijkheid om dia's met bijbehorende notities naar PDF te converteren een waardevolle functie. Java-ontwikkelaars kunnen dit bereiken met behulp van de Aspose.Slides voor Java-bibliotheek, die een robuuste set hulpmiddelen biedt voor het programmatisch werken met PowerPoint-presentaties. In deze stapsgewijze handleiding onderzoeken we hoe u dia's met notities naar PDF kunt converteren met behulp van Java en Aspose.Slides voor Java.

## Vereisten

Voordat we in de code duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:

- Java Development Kit (JDK) op uw systeem geïnstalleerd.
-  Aspose.Slides voor Java-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/java/).

Nu we ons overzicht hebben, gaan we stap voor stap in de implementatie duiken.
## Stap 1: Het project opzetten

Maak eerst een Java-project en voeg de Aspose.Slides voor Java-bibliotheek toe aan de afhankelijkheden van uw project.

## Stap 2: De presentatie laden

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
```

## Stap 3: Een nieuwe presentatie maken

```java
Presentation auxPresentation = new Presentation();
```

## Stap 4: Dia's kopiëren

```java
ISlide slide = presentation.getSlides().get_Item(0);
auxPresentation.getSlides().insertClone(0, slide);
```

## Stap 5: Diagrootte aanpassen

```java
auxPresentation.getSlideSize().setSize(612F, 792F, SlideSizeScaleType.EnsureFit);
```

## Stap 6: PDF-opties configureren

```java
PdfOptions pdfOptions = new PdfOptions();
INotesCommentsLayoutingOptions options = pdfOptions.getNotesCommentsLayouting();
options.setNotesPosition(NotesPositions.BottomFull);
```

## Stap 7: Opslaan als PDF

```java
auxPresentation.save(dataDir + "PDFnotes_out.pdf", SaveFormat.Pdf, pdfOptions);
```

## Volledige broncode voor het converteren van dia's naar PDF met notities in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Instantieer een presentatieobject dat een presentatiebestand vertegenwoordigt
Presentation presentation = new Presentation(dataDir + "SelectedSlides.pptx");
try
{
	Presentation auxPresentation = new Presentation();
	try
	{
		ISlide slide = presentation.getSlides().get_Item(0);
		auxPresentation.getSlides().insertClone(0, slide);
		// Diatype en -grootte instellen
		//auxPresentation.getSlideSize().setSize(presentatie.getSlideSize().getSize().getWidth(), presentatie.getSlideSize().getSize().getHeight(),SlideSizeScaleType.EnsureFit);
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

## Conclusie

In deze zelfstudie hebben we geleerd hoe u dia's naar PDF kunt converteren met notities in Java met behulp van Aspose.Slides voor Java. We behandelden het opzetten van het project, het laden van de presentatie, het maken van een nieuwe presentatie, het kopiëren van dia's, het aanpassen van de diagrootte, het configureren van PDF-opties en ten slotte het opslaan van de presentatie als een PDF met notities.

## Veelgestelde vragen

### Hoe installeer ik Aspose.Slides voor Java?

Volg deze stappen om Aspose.Slides voor Java te installeren:
1.  Download de bibliotheek van[hier](https://releases.aspose.com/slides/java/).
2. Voeg het JAR-bestand toe aan het klassenpad van uw Java-project.

### Kan ik de notitiepositie in de gegenereerde PDF aanpassen?

 Ja, u kunt de positie van de notities aanpassen door de`NotesPositions` enum in de PDF-opties. In deze zelfstudie hebben we dit ingesteld op`BottomFull`, maar u kunt ook andere opties verkennen.

### Zijn er licentievereisten voor het gebruik van Aspose.Slides voor Java?

Ja, Aspose.Slides voor Java is een commerciële bibliotheek en mogelijk moet u een licentie aanschaffen om deze in productie te kunnen gebruiken. Bezoek de Aspose-website voor licentiegegevens.

### Kan ik meerdere dia's tegelijk converteren?

Zeker! U kunt de dia's in uw presentatie doorlopen en ze naar de nieuwe presentatie klonen, zodat u meerdere dia's in één keer naar PDF met notities kunt converteren.

### Waar kan ik meer documentatie vinden voor Aspose.Slides voor Java?

 U kunt gedetailleerde documentatie voor Aspose.Slides voor Java vinden op de site:[Aspose.Slides voor Java API-referentie](https://reference.aspose.com/slides/java/).