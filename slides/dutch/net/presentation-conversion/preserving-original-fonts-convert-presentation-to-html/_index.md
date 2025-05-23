---
"description": "Leer hoe u originele lettertypen kunt behouden tijdens het converteren van presentaties naar HTML met Aspose.Slides voor .NET. Zorg moeiteloos voor consistente lettertypen en een visuele impact."
"linktitle": "Originele lettertypen behouden - Presentatie naar HTML converteren"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Originele lettertypen behouden - Presentatie naar HTML converteren"
"url": "/nl/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Originele lettertypen behouden - Presentatie naar HTML converteren


In deze uitgebreide handleiding leiden we je door het proces van het behouden van originele lettertypen bij het converteren van een presentatie naar HTML met Aspose.Slides voor .NET. We voorzien je van de benodigde C#-broncode en leggen elke stap in detail uit. Aan het einde van deze tutorial kun je ervoor zorgen dat de lettertypen in je geconverteerde HTML-document trouw blijven aan de originele presentatie.

## 1. Inleiding

Bij het converteren van PowerPoint-presentaties naar HTML is het cruciaal om de originele lettertypen te behouden om de visuele consistentie van uw content te garanderen. Aspose.Slides voor .NET biedt hiervoor een krachtige oplossing. In deze tutorial leiden we u door de stappen die nodig zijn om de originele lettertypen te behouden tijdens het conversieproces.

## 2. Voorwaarden

Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende voorwaarden voldoet:

- Visual Studio op uw computer geïnstalleerd.
- Aspose.Slides voor .NET-bibliotheek toegevoegd aan uw project.

## 3. Uw project instellen

Om te beginnen maakt u een nieuw project in Visual Studio en voegt u de Aspose.Slides voor .NET-bibliotheek toe als referentie.

## 4. De presentatie laden

Gebruik de volgende code om uw PowerPoint-presentatie te laden:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Uw code hier
}
```

Vervangen `"Your Document Directory"` met het pad naar uw presentatiebestand.

## 5. Standaardlettertypen uitsluiten

Om standaardlettertypen zoals Calibri en Arial uit te sluiten, gebruikt u de volgende code:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

U kunt deze lijst naar wens aanpassen.

## 6. Alle lettertypen insluiten

Vervolgens voegen we alle lettertypen toe aan het HTML-document. Zo blijven de originele lettertypen behouden. Gebruik de volgende code:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Opslaan als HTML

Sla de presentatie nu op als een HTML-document met ingesloten lettertypen:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Vervangen `"output.html"` met de gewenste naam voor het uitvoerbestand.

## 8. Conclusie

In deze tutorial hebben we laten zien hoe je originele lettertypen kunt behouden bij het converteren van een PowerPoint-presentatie naar HTML met Aspose.Slides voor .NET. Door deze stappen te volgen, zorg je ervoor dat je geconverteerde HTML-document de visuele integriteit van de originele presentatie behoudt.

## 9. Veelgestelde vragen

### V1: Kan ik de lijst met uitgesloten lettertypen aanpassen?

Ja, dat kan. Wijzig de `fontNameExcludeList` array om specifieke lettertypen op te nemen of uit te sluiten, afhankelijk van uw vereisten.

### V2: Wat als ik niet alle lettertypen wil insluiten?

Als u alleen specifieke lettertypen wilt insluiten, kunt u de code dienovereenkomstig aanpassen. Raadpleeg de documentatie van Aspose.Slides voor .NET voor meer informatie.

### V3: Zijn er licentievereisten voor het gebruik van Aspose.Slides voor .NET?

Ja, u hebt mogelijk een geldige licentie nodig om Aspose.Slides voor .NET in uw projecten te gebruiken. Raadpleeg de Aspose-website voor licentie-informatie.

### V4: Kan ik andere bestandsformaten naar HTML converteren met Aspose.Slides voor .NET?

Aspose.Slides voor .NET richt zich voornamelijk op PowerPoint-presentaties. Voor het converteren van andere bestandsformaten naar HTML kunt u mogelijk andere Aspose-producten gebruiken die specifiek voor die formaten zijn ontwikkeld.

### V5: Waar kan ik aanvullende informatie en ondersteuning krijgen?

Meer documentatie, tutorials en ondersteuning vindt u op de Aspose-website. Bezoek [Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/) voor gedetailleerde informatie.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}