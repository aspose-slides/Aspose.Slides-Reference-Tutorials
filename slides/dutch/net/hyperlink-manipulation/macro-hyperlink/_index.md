---
title: Macro-hyperlinkklikken instellen in Aspose.Slides voor .NET
linktitle: Hyperlinkbeheer met behulp van macro's
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u macro-hyperlinks in uw presentaties instelt met Aspose.Slides voor .NET. Verbeter de interactiviteit en betrek uw publiek.
type: docs
weight: 13
url: /nl/net/hyperlink-manipulation/macro-hyperlink/
---

In de wereld van moderne softwareontwikkeling is het creëren van dynamische en interactieve presentaties een belangrijk aspect. Aspose.Slides voor .NET is een krachtige bibliotheek waarmee u naadloos met presentaties kunt werken. Of u nu een bedrijfspresentatie of een educatieve diavoorstelling maakt, de mogelijkheid om klikken op macro-hyperlinks in te stellen kan de gebruikerservaring aanzienlijk verbeteren. In deze stapsgewijze handleiding leiden we u door het proces van het instellen van een macro-hyperlinkklik met Aspose.Slides voor .NET. 

## Vereisten

Voordat we ingaan op de stapsgewijze zelfstudie, zijn er een aantal vereisten waaraan u moet voldoen:

1.Visual Studio: Zorg ervoor dat Visual Studio op uw computer is geïnstalleerd, aangezien dit onze ontwikkelomgeving is.

 2.Aspose.Slides voor .NET: De Aspose.Slides voor .NET-bibliotheek moet geïnstalleerd zijn. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/net/).

3.Basiskennis van C#: Bekendheid met de programmeertaal C# is essentieel om deze tutorial te volgen.

## Naamruimten importeren

Laten we in de eerste stap de benodigde naamruimten importeren om met Aspose.Slides te werken:

### Stap 1: Naamruimten importeren

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;
```

 We hebben de`Aspose.Slides` naamruimte, de kernnaamruimte voor het werken met presentaties, en de`Aspose.Slides.Export` naamruimte.

## Macro-hyperlinkklikken instellen

Laten we nu verder gaan met het hoofdgedeelte van deze zelfstudie: het instellen van een macro-hyperlinkklik in uw presentatie.

### Stap 2: Initialiseer de presentatie

Eerst moeten we een nieuwe presentatie initialiseren.

```csharp
using (Presentation presentation = new Presentation())
{
    // Je code komt hier terecht.
}
```

Binnen deze gebruiksinstructie maakt u een nieuw presentatieobject en voert u daarin al uw bewerkingen uit.

### Stap 3: Voeg een AutoShape toe

Om een macro-hyperlinkklik in te stellen, heeft u een object nodig waarop de gebruiker kan klikken. In dit voorbeeld gebruiken we een AutoVorm als klikbaar element.

```csharp
IAutoShape shape = presentation.Slides[0].Shapes.AddAutoShape(ShapeType.BlankButton, 20, 20, 80, 30);
```

Hier maken we een AutoShape met het type "BlankButton" op specifieke coördinaten (20, 20) en met afmetingen van 80x30. U kunt deze waarden aanpassen aan de lay-out van uw presentatie.

### Stap 4: Macro-hyperlinkklikken instellen

Nu komt het gedeelte waar u de macro-hyperlinkklik instelt. U moet een macronaam als parameter opgeven.

```csharp
string macroName = "TestMacro";
shape.HyperlinkManager.SetMacroHyperlinkClick(macroName);
```

In dit voorbeeld hebben we de macro-hyperlinkklik ingesteld op de "TestMacro". Wanneer de gebruiker op de AutoVorm klikt, wordt deze macro geactiveerd.

### Stap 5: Informatie ophalen

Ook kunt u informatie opvragen over de hyperlink die u heeft ingesteld.

```csharp
Console.WriteLine("External URL is {0}", shape.HyperlinkClick.ExternalUrl);
Console.WriteLine("Shape action type is {0}", shape.HyperlinkClick.ActionType);
```

Met deze coderegels kunt u de externe URL en het actietype van de hyperlink afdrukken.

En dat is het! U hebt met succes een macro-hyperlinkklik in uw presentatie ingesteld met Aspose.Slides voor .NET.

## Conclusie

In deze zelfstudie hebben we geleerd hoe u een macro-hyperlinkklik in uw presentatie kunt instellen met behulp van Aspose.Slides voor .NET. Dit kan een waardevolle functie zijn om interactieve en dynamische presentaties te maken die uw publiek boeien. Met Aspose.Slides voor .NET beschikt u over een krachtig hulpmiddel om uw presentatieontwikkeling naar een hoger niveau te tillen.

 Nu is het tijd om te experimenteren en boeiende presentaties te maken met aangepaste macro-hyperlinks. Ontdek gerust de[Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/) voor meer diepgaande informatie en mogelijkheden.

## Veelgestelde vragen (veelgestelde vragen)

### Kan ik Aspose.Slides voor .NET gebruiken met andere programmeertalen?
Aspose.Slides is voornamelijk ontworpen voor .NET, maar Aspose biedt vergelijkbare bibliotheken voor andere programmeertalen, zoals Java.

### Is Aspose.Slides voor .NET een gratis bibliotheek?
Aspose.Slides voor .NET is een commerciële bibliotheek met een gratis proefversie. Je kunt het downloaden van[hier](https://releases.aspose.com/).

### Zijn er beperkingen voor het gebruik van macro's in presentaties gemaakt met Aspose.Slides voor .NET?
Met Aspose.Slides voor .NET kunt u met macro's werken, maar u moet rekening houden met beveiligings- en compatibiliteitsoverwegingen wanneer u macro's in presentaties gebruikt.

### Kan ik het uiterlijk van de AutoVorm die voor de hyperlink wordt gebruikt, aanpassen?
Ja, u kunt het uiterlijk van de AutoVorm aanpassen door de eigenschappen ervan aan te passen, zoals grootte, kleur en lettertype.

### Waar kan ik hulp of ondersteuning krijgen voor Aspose.Slides voor .NET?
 Als u problemen ondervindt of vragen heeft, kunt u hulp zoeken op het Aspose-ondersteuningsforum[hier](https://forum.aspose.com/).