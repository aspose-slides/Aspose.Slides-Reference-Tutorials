---
"description": "Converteer PowerPoint-presentaties naar HTML met behoud van de originele lettertypen met Aspose.Slides voor Java."
"linktitle": "Presentatie converteren naar HTML met behoud van originele lettertypen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Presentatie converteren naar HTML met behoud van originele lettertypen in Java-dia's"
"url": "/nl/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Presentatie converteren naar HTML met behoud van originele lettertypen in Java-dia's


## Inleiding tot het converteren van presentaties naar HTML met behoud van originele lettertypen in Java-dia's

In deze tutorial laten we zien hoe je een PowerPoint-presentatie (PPTX) naar HTML converteert met behoud van de originele lettertypen met behulp van Aspose.Slides voor Java. Dit zorgt ervoor dat de resulterende HTML-code nauw aansluit bij de originele presentatie.

## Stap 1: Het project opzetten
Voordat we in de code duiken, controleren we of de benodigde instellingen aanwezig zijn:

1. Download Aspose.Slides voor Java: Als u dit nog niet hebt gedaan, download en neem dan de Aspose.Slides voor Java-bibliotheek op in uw project.

2. Maak een Java-project: stel een Java-project in uw favoriete IDE in en zorg ervoor dat u een map "lib" hebt waarin u het Aspose.Slides JAR-bestand kunt plaatsen.

3. Importeer vereiste klassen: importeer de benodigde klassen aan het begin van uw Java-bestand:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Stap 2: Presentatie converteren naar HTML met originele lettertypen

Laten we nu een PowerPoint-presentatie naar HTML converteren, waarbij we de originele lettertypen behouden:

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";

// Laad de presentatie
Presentation pres = new Presentation("input.pptx");

try {
    // Sluit standaard presentatielettertypen zoals Calibri en Arial uit
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // HTML-opties maken en de aangepaste HTML-formatter instellen
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

- We laden de invoer PowerPoint-presentatie met behulp van `Presentation`.

- We definiëren een lijst met lettertypen (`fontNameExcludeList`) die we willen uitsluiten van insluiting in de HTML. Dit is handig om veelgebruikte lettertypen zoals Calibri en Arial uit te sluiten en zo de bestandsgrootte te verkleinen.

- We maken een exemplaar van `EmbedAllFontsHtmlController` en geef de lijst met uitsluitingen voor lettertypen door aan de server.

- Wij creëren `HtmlOptions` en stel een aangepaste HTML-formatter in met behulp van `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Ten slotte slaan we de presentatie op als HTML met de opgegeven opties.

## Volledige broncode voor het converteren van presentaties naar HTML met behoud van originele lettertypen in Java-dia's

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// standaard presentatielettertypen uitsluiten
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

In deze tutorial heb je geleerd hoe je een PowerPoint-presentatie naar HTML converteert met behoud van de originele lettertypen met Aspose.Slides voor Java. Dit is handig wanneer je de visuele kwaliteit van je presentaties wilt behouden wanneer je ze deelt op internet.

## Veelgestelde vragen

### Hoe download ik Aspose.Slides voor Java?

U kunt Aspose.Slides voor Java downloaden van de Aspose-website. Bezoek [hier](https://downloads.aspose.com/slides/java/) om de nieuwste versie te krijgen.

### Kan ik de lijst met uitgesloten lettertypen aanpassen?

Ja, u kunt de `fontNameExcludeList` array om specifieke lettertypen op te nemen of uit te sluiten, afhankelijk van uw vereisten.

### Werkt deze methode voor oudere PowerPoint-formaten zoals PPT?

Dit codevoorbeeld is bedoeld voor PPTX-bestanden. Als u oudere PPT-bestanden wilt converteren, moet u mogelijk de code aanpassen.

### Hoe kan ik de HTML-uitvoer verder aanpassen?

Je kunt de `HtmlOptions` klasse om verschillende aspecten van de HTML-uitvoer aan te passen, zoals diaformaat, afbeeldingskwaliteit en meer.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}