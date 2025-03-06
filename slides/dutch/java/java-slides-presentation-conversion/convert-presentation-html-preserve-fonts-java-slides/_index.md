---
title: Presentatie naar HTML converteren met behoud van originele lettertypen in Java-dia's
linktitle: Presentatie naar HTML converteren met behoud van originele lettertypen in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Converteer PowerPoint-presentaties naar HTML met behoud van originele lettertypen met Aspose.Slides voor Java.
weight: 14
url: /nl/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Presentatie naar HTML converteren met behoud van originele lettertypen in Java-dia's


## Inleiding tot het converteren van een presentatie naar HTML met behoud van originele lettertypen in Java-dia's

In deze zelfstudie onderzoeken we hoe u een PowerPoint-presentatie (PPTX) naar HTML kunt converteren met behoud van de originele lettertypen met behulp van Aspose.Slides voor Java. Dit zorgt ervoor dat de resulterende HTML sterk lijkt op het uiterlijk van de originele presentatie.

## Stap 1: Het project opzetten
Voordat we in de code duiken, moeten we ervoor zorgen dat u over de benodigde instellingen beschikt:

1. Aspose.Slides voor Java downloaden: Als u dat nog niet heeft gedaan, downloadt u de Aspose.Slides voor Java-bibliotheek en neemt u deze op in uw project.

2. Maak een Java-project: stel een Java-project in uw favoriete IDE in en zorg ervoor dat u een "lib"-map hebt waarin u het JAR-bestand Aspose.Slides kunt plaatsen.

3. Importeer vereiste klassen: importeer de benodigde klassen aan het begin van uw Java-bestand:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Stap 2: Presentatie converteren naar HTML met originele lettertypen

Laten we nu een PowerPoint-presentatie naar HTML converteren met behoud van de originele lettertypen:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Laad de presentatie
Presentation pres = new Presentation("input.pptx");

try {
    // Sluit standaardpresentatielettertypen zoals Calibri en Arial uit
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Maak HTML-opties en stel de aangepaste HTML-formatter in
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Sla de presentatie op als HTML
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Gooi het presentatieobject weg
    if (pres != null) pres.dispose();
}
```

In dit codefragment:

-  We laden de ingevoerde PowerPoint-presentatie met behulp van`Presentation`.

- We definiëren een lijst met lettertypen (`fontNameExcludeList`die we willen uitsluiten van insluiten in de HTML. Dit is handig voor het uitsluiten van veelgebruikte lettertypen zoals Calibri en Arial om de bestandsgrootte te verkleinen.

-  We maken een exemplaar van`EmbedAllFontsHtmlController` en geef de lijst met lettertype-uitsluitingen eraan door.

-  We creëren`HtmlOptions` en stel een aangepaste HTML-formatter in met behulp van`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Ten slotte slaan we de presentatie op als HTML met de opgegeven opties.

## Volledige broncode voor het converteren van presentatie naar HTML met behoud van originele lettertypen in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// standaardpresentatielettertypen uitsluiten
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

## Conclusie

In deze zelfstudie hebt u geleerd hoe u een PowerPoint-presentatie naar HTML kunt converteren met behoud van de originele lettertypen met behulp van Aspose.Slides voor Java. Dit is handig als u de visuele getrouwheid van uw presentaties wilt behouden wanneer u deze op internet deelt.

## Veelgestelde vragen

### Hoe download ik Aspose.Slides voor Java?

 U kunt Aspose.Slides voor Java downloaden van de Aspose-website. Bezoek[hier](https://downloads.aspose.com/slides/java/) om de nieuwste versie te krijgen.

### Kan ik de lijst met uitgesloten lettertypen aanpassen?

 Ja, u kunt de`fontNameExcludeList` array om specifieke lettertypen op te nemen of uit te sluiten volgens uw vereisten.

### Werkt deze methode voor oudere PowerPoint-formaten zoals PPT?

Dit codevoorbeeld is ontworpen voor PPTX-bestanden. Als u oudere PPT-bestanden moet converteren, moet u mogelijk de code aanpassen.

### Hoe kan ik de HTML-uitvoer verder aanpassen?

 Je kunt de`HtmlOptions` class om verschillende aspecten van de HTML-uitvoer aan te passen, zoals diagrootte, afbeeldingskwaliteit en meer.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
