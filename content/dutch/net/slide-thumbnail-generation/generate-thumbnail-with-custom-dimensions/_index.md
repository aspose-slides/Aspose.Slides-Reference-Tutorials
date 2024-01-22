---
title: Genereer miniatuurweergaven in dia's met aangepaste afmetingen
linktitle: Genereer een miniatuur met aangepaste afmetingen
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u aangepaste miniatuurafbeeldingen kunt genereren uit PowerPoint-presentaties met Aspose.Slides voor .NET. Verbeter de gebruikerservaring en functionaliteit.
type: docs
weight: 13
url: /nl/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

Het maken van aangepaste miniatuurafbeeldingen van uw PowerPoint-presentaties kan een waardevol bezit zijn, of u nu een interactieve toepassing bouwt, de gebruikerservaring verbetert of inhoud voor verschillende platforms optimaliseert. In deze zelfstudie begeleiden we u bij het genereren van aangepaste miniatuurafbeeldingen uit PowerPoint-presentaties met behulp van de Aspose.Slides voor .NET-bibliotheek. Met deze krachtige bibliotheek kunt u PowerPoint-bestanden programmatisch manipuleren, converteren en verbeteren in .NET-toepassingen.

## Vereisten

Voordat we ingaan op het genereren van aangepaste miniatuurafbeeldingen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

### 1. Aspose.Slides voor .NET

 U moet de Aspose.Slides voor .NET-bibliotheek in uw project hebben geïnstalleerd. Als u dat nog niet heeft gedaan, kunt u hier de benodigde documentatie en downloadlinks vinden[hier](https://reference.aspose.com/slides/net/).

### 2. Een PowerPoint-presentatie

Zorg ervoor dat u de PowerPoint-presentatie hebt waarvan u een aangepaste miniatuurafbeelding wilt genereren. Deze presentatie zou toegankelijk moeten zijn binnen uw projectmap.

### 3. Ontwikkelomgeving

Om deze zelfstudie te volgen, moet u praktische kennis hebben van .NET-programmeren met C# en een ontwikkelomgeving hebben, zoals Visual Studio.

Nu we de vereisten hebben besproken, gaan we het proces van het genereren van aangepaste miniaturen opsplitsen in stapsgewijze instructies.

## Naamruimten importeren

Eerst moet u de vereiste naamruimten in uw C#-code opnemen. Met deze naamruimten kunt u met Aspose.Slides werken en PowerPoint-presentaties manipuleren.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Stap 1: Laad de presentatie

Laad om te beginnen de PowerPoint-presentatie waaruit u een aangepaste miniatuurafbeelding wilt genereren. Dit wordt bereikt met behulp van de Aspose.Slides-bibliotheek.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instantieer een Presentation-klasse die het presentatiebestand vertegenwoordigt
using (Presentation pres = new Presentation(srcFileName))
{
    // Uw code voor het genereren van miniaturen komt hier terecht
}
```

## Stap 2: Toegang tot de dia

Binnen de geladen presentatie moet u toegang krijgen tot de specifieke dia waarvan u de aangepaste miniatuurafbeelding wilt genereren. U kunt de dia kiezen op basis van de index.

```csharp
// Toegang tot de eerste dia (u kunt de index indien nodig wijzigen)
ISlide sld = pres.Slides[0];
```

## Stap 3: Definieer aangepaste miniatuurafmetingen

Geef de gewenste afmetingen op voor uw aangepaste miniatuurafbeelding. U kunt de breedte en hoogte in pixels definiëren, afhankelijk van de vereisten van uw toepassing.

```csharp
int desiredX = 1200; // Breedte
int desiredY = 800;  // Hoogte
```

## Stap 4: Bereken schaalfactoren

Om de beeldverhouding van de dia te behouden, berekent u de schaalfactoren voor de X- en Y-afmetingen op basis van de grootte van de dia en de gewenste afmetingen.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Stap 5: Genereer de miniatuurafbeelding

Maak een afbeelding op volledige schaal van de dia met de opgegeven aangepaste afmetingen en sla deze op schijf op in JPEG-indeling.

```csharp
// Maak een afbeelding op volledige schaal
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Sla de afbeelding op schijf op in JPEG-formaat
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Nu u deze stappen heeft gevolgd, zou u met succes een aangepaste miniatuurafbeelding uit uw PowerPoint-presentatie moeten hebben gegenereerd.

## Conclusie

Het genereren van aangepaste miniatuurafbeeldingen uit PowerPoint-presentaties met Aspose.Slides voor .NET is een waardevolle vaardigheid die de gebruikerservaring en functionaliteit van uw toepassingen kan verbeteren. Door de stappen in deze zelfstudie te volgen, kunt u eenvoudig aangepaste miniaturen maken die aan uw specifieke vereisten voldoen.

---

## Veelgestelde vragen (veelgestelde vragen)

### Wat is Aspose.Slides voor .NET?
Aspose.Slides voor .NET is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met PowerPoint-presentaties kunnen werken in .NET-toepassingen.

### Waar kan ik de documentatie voor Aspose.Slides voor .NET vinden?
 U kunt de documentatie vinden[hier](https://reference.aspose.com/slides/net/).

### Is Aspose.Slides voor .NET gratis te gebruiken?
 Aspose.Slides voor .NET is een commerciële bibliotheek. U kunt informatie over prijzen en licenties vinden[hier](https://purchase.aspose.com/buy).

### Heb ik geavanceerde programmeervaardigheden nodig om Aspose.Slides voor .NET te gebruiken?
Hoewel enige kennis van .NET-programmering nuttig is, biedt Aspose.Slides voor .NET een gebruiksvriendelijke API die het werken met PowerPoint-presentaties vereenvoudigt.

### Is er technische ondersteuning beschikbaar voor Aspose.Slides voor .NET?
 Ja, u heeft toegang tot technische ondersteuning en communityforums[hier](https://forum.aspose.com/).