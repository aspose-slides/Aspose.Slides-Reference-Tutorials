---
title: Originele lettertypen behouden - Presentatie naar HTML converteren
linktitle: Originele lettertypen behouden - Presentatie naar HTML converteren
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u originele lettertypen kunt behouden terwijl u presentaties naar HTML converteert met Aspose.Slides voor .NET. Zorg moeiteloos voor lettertypeconsistentie en visuele impact.
type: docs
weight: 14
url: /nl/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

In deze uitgebreide handleiding begeleiden we u door het proces van het behouden van originele lettertypen bij het converteren van een presentatie naar HTML met Aspose.Slides voor .NET. Wij voorzien u van de benodigde C#-broncode en leggen elke stap gedetailleerd uit. Aan het einde van deze zelfstudie kunt u ervoor zorgen dat de lettertypen in uw geconverteerde HTML-document trouw blijven aan de oorspronkelijke presentatie.

## 1. Inleiding

Bij het converteren van PowerPoint-presentaties naar HTML is het van cruciaal belang dat u de originele lettertypen behoudt om de visuele consistentie van uw inhoud te garanderen. Aspose.Slides voor .NET biedt een krachtige oplossing om dit te bereiken. In deze zelfstudie begeleiden we u door de stappen die nodig zijn om de originele lettertypen te behouden tijdens het conversieproces.

## 2. Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

- Visual Studio is op uw computer geïnstalleerd.
- Aspose.Slides voor .NET-bibliotheek toegevoegd aan uw project.

## 3. Uw project opzetten

Om aan de slag te gaan, maakt u een nieuw project in Visual Studio en voegt u de Aspose.Slides voor .NET-bibliotheek toe als referentie.

## 4. De presentatie laden

Gebruik de volgende code om uw PowerPoint-presentatie te laden:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Jouw code hier
}
```

 Vervangen`"Your Document Directory"` met het pad naar uw presentatiebestand.

## 5. Exclusief standaardlettertypen

Gebruik de volgende code om standaardlettertypen zoals Calibri en Arial uit te sluiten:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

U kunt deze lijst indien nodig aanpassen.

## 6. Alle lettertypen insluiten

Vervolgens sluiten we alle lettertypen in het HTML-document in. Dit zorgt ervoor dat de originele lettertypen behouden blijven. Gebruik de volgende code:

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

 Vervangen`"output.html"` met de gewenste uitvoerbestandsnaam.

## 8. Conclusie

In deze zelfstudie hebben we gedemonstreerd hoe u originele lettertypen kunt behouden bij het converteren van een PowerPoint-presentatie naar HTML met Aspose.Slides voor .NET. Door deze stappen te volgen, kunt u ervoor zorgen dat uw geconverteerde HTML-document de visuele integriteit van de originele presentatie behoudt.

## 9. Veelgestelde vragen

### V1: Kan ik de lijst met uitgesloten lettertypen aanpassen?

 Ja, dat kan. Wijzig de`fontNameExcludeList` array om specifieke lettertypen op te nemen of uit te sluiten volgens uw vereisten.

### Vraag 2: Wat moet ik doen als ik niet alle lettertypen wil insluiten?

Als u alleen specifieke lettertypen wilt insluiten, kunt u de code dienovereenkomstig aanpassen. Raadpleeg de Aspose.Slides voor .NET-documentatie voor meer details.

### V3: Zijn er licentievereisten voor het gebruik van Aspose.Slides voor .NET?

Ja, u heeft mogelijk een geldige licentie nodig om Aspose.Slides voor .NET in uw projecten te gebruiken. Raadpleeg de Aspose-website voor licentie-informatie.

### V4: Kan ik andere bestandsindelingen naar HTML converteren met Aspose.Slides voor .NET?

Aspose.Slides voor .NET richt zich voornamelijk op PowerPoint-presentaties. Voor het converteren van andere bestandsformaten naar HTML moet u mogelijk andere Aspose-producten verkennen die op maat zijn gemaakt voor die formaten.

### Vraag 5: Waar kan ik toegang krijgen tot aanvullende bronnen en ondersteuning?

 Meer documentatie, tutorials en ondersteuning vindt u op de Aspose-website. Bezoek[Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/) voor gedetailleerde informatie.
