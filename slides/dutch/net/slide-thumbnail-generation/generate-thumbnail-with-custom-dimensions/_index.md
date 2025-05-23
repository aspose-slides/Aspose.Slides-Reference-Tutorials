---
"description": "Leer hoe u aangepaste miniatuurafbeeldingen van PowerPoint-presentaties kunt genereren met Aspose.Slides voor .NET. Verbeter de gebruikerservaring en functionaliteit."
"linktitle": "Genereer een miniatuur met aangepaste afmetingen"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Genereer miniaturen in dia's met aangepaste afmetingen"
"url": "/nl/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Genereer miniaturen in dia's met aangepaste afmetingen


Het maken van aangepaste miniatuurafbeeldingen van uw PowerPoint-presentaties kan een waardevolle toevoeging zijn, of u nu een interactieve applicatie bouwt, de gebruikerservaring verbetert of content optimaliseert voor verschillende platforms. In deze tutorial begeleiden we u bij het genereren van aangepaste miniatuurafbeeldingen van PowerPoint-presentaties met behulp van de Aspose.Slides voor .NET-bibliotheek. Met deze krachtige bibliotheek kunt u PowerPoint-bestanden programmatisch bewerken, converteren en verbeteren in .NET-applicaties.

## Vereisten

Voordat we beginnen met het genereren van aangepaste miniatuurafbeeldingen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

### 1. Aspose.Slides voor .NET

De Aspose.Slides voor .NET-bibliotheek moet in uw project geïnstalleerd zijn. Als u dat nog niet gedaan hebt, vindt u hier de benodigde documentatie en downloadlinks. [hier](https://reference.aspose.com/slides/net/).

### 2. Een PowerPoint-presentatie

Zorg ervoor dat u de PowerPoint-presentatie hebt waarvan u een aangepaste miniatuurafbeelding wilt genereren. Deze presentatie moet toegankelijk zijn in uw projectmap.

### 3. Ontwikkelomgeving

Om deze tutorial te kunnen volgen, hebt u een praktische kennis van .NET-programmering met C# nodig en moet u over een ontwikkelomgeving beschikken, zoals Visual Studio.

Nu we de vereisten hebben besproken, gaan we het proces voor het genereren van aangepaste miniaturen opsplitsen in stapsgewijze instructies.

## Naamruimten importeren

Ten eerste moet je de vereiste naamruimten in je C#-code opnemen. Deze naamruimten stellen je in staat om met Aspose.Slides te werken en PowerPoint-presentaties te bewerken.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Stap 1: Laad de presentatie

Om te beginnen laadt u de PowerPoint-presentatie waarvan u een aangepaste miniatuurafbeelding wilt genereren. Dit doet u met behulp van de Aspose.Slides-bibliotheek.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Instantieer een presentatieklasse die het presentatiebestand vertegenwoordigt
using (Presentation pres = new Presentation(srcFileName))
{
    // Hier komt uw code voor het genereren van miniaturen
}
```

## Stap 2: Toegang tot de dia

Binnen de geladen presentatie moet u de specifieke dia openen waarvan u de aangepaste miniatuurafbeelding wilt genereren. U kunt de dia selecteren op basis van de index.

```csharp
// Toegang tot de eerste dia (u kunt de index indien nodig wijzigen)
ISlide sld = pres.Slides[0];
```

## Stap 3: Definieer aangepaste miniatuurafmetingen

Geef de gewenste afmetingen op voor uw aangepaste miniatuurafbeelding. U kunt de breedte en hoogte in pixels definiëren op basis van de vereisten van uw toepassing.

```csharp
int desiredX = 1200; // Breedte
int desiredY = 800;  // Hoogte
```

## Stap 4: Schaalfactoren berekenen

Om de beeldverhouding van de dia te behouden, berekent u de schaalfactoren voor de X- en Y-afmetingen op basis van de grootte van de dia en de gewenste afmetingen.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Stap 5: Genereer de miniatuurafbeelding

Maak een afbeelding op ware grootte van de dia met de opgegeven afmetingen en sla deze op schijf op in JPEG-formaat.

```csharp
// Maak een afbeelding op ware grootte
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Sla de afbeelding op schijf op in JPEG-formaat
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Nu u deze stappen hebt gevolgd, zou u met succes een aangepaste miniatuurafbeelding van uw PowerPoint-presentatie moeten hebben gegenereerd.

## Conclusie

Het genereren van aangepaste miniatuurafbeeldingen van PowerPoint-presentaties met Aspose.Slides voor .NET is een waardevolle vaardigheid die de gebruikerservaring en functionaliteit van uw applicaties kan verbeteren. Door de stappen in deze tutorial te volgen, kunt u eenvoudig aangepaste miniaturen maken die aan uw specifieke eisen voldoen.

---

## Veelgestelde vragen (FAQ)

### Wat is Aspose.Slides voor .NET?
Aspose.Slides voor .NET is een krachtige bibliotheek waarmee ontwikkelaars programmatisch met PowerPoint-presentaties kunnen werken in .NET-toepassingen.

### Waar kan ik de documentatie voor Aspose.Slides voor .NET vinden?
De documentatie vindt u hier [hier](https://reference.aspose.com/slides/net/).

### Is Aspose.Slides voor .NET gratis te gebruiken?
Aspose.Slides voor .NET is een commerciële bibliotheek. U kunt hier informatie vinden over prijzen en licenties. [hier](https://purchase.aspose.com/buy).

### Heb ik geavanceerde programmeervaardigheden nodig om Aspose.Slides voor .NET te gebruiken?
Hoewel enige kennis van .NET-programmering nuttig is, biedt Aspose.Slides voor .NET een gebruiksvriendelijke API waarmee u eenvoudiger met PowerPoint-presentaties kunt werken.

### Is er technische ondersteuning beschikbaar voor Aspose.Slides voor .NET?
Ja, u hebt toegang tot technische ondersteuning en communityforums [hier](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}