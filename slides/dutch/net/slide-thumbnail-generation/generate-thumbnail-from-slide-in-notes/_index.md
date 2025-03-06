---
title: Genereer een miniatuur uit een dia in notities
linktitle: Genereer een miniatuur uit een dia in notities
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u miniaturen kunt genereren van dia's in het notitiegedeelte van uw presentatie met behulp van Aspose.Slides voor .NET. Verbeter uw visuele inhoud!
type: docs
weight: 12
url: /nl/net/slide-thumbnail-generation/generate-thumbnail-from-slide-in-notes/
---

In de wereld van moderne presentaties is visuele inhoud koning. Het maken van aantrekkelijke slides is essentieel voor effectieve communicatie. Eén manier om uw presentaties te verbeteren is door miniaturen van dia's te genereren, vooral als u specifieke details wilt benadrukken of een overzicht wilt delen. Aspose.Slides voor .NET is een krachtige tool waarmee u dit naadloos kunt bereiken. In deze stapsgewijze handleiding leiden we u door het proces van het genereren van miniaturen van dia's in het notitiegedeelte van een presentatie met behulp van Aspose.Slides voor .NET.

## Vereisten

Voordat we ingaan op de details, moet u aan de volgende vereisten voldoen:

### 1. Aspose.Slides voor .NET

 Zorg ervoor dat Aspose.Slides voor .NET is geïnstalleerd en ingesteld. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/net/).

### 2. .NET-omgeving

Er moet een .NET-ontwikkelomgeving op uw systeem aanwezig zijn.

### 3. Een presentatiebestand

 Zorg voor een presentatiebestand (bijv.`ThumbnailFromSlideInNotes.pptx`) waarvan u miniaturen wilt genereren.

Laten we het proces nu in stappen opsplitsen:

## Stap 1: Naamruimten importeren

Eerst moet u de benodigde naamruimten importeren om met Aspose.Slides te kunnen werken. Voeg de volgende code toe aan het begin van uw C#-script:

```csharp
using Aspose.Slides;
using System.Drawing;
```

## Stap 2: Laad de presentatie

 Vervolgens moet u het presentatiebestand laden dat de dia's met notities bevat. Gebruik de volgende code om een`Presentation` klas:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "ThumbnailFromSlideInNotes.pptx"))
{
    // Je code komt hier
}
```

## Stap 3: Toegang tot de dia

U kunt kiezen voor welke dia in de presentatie u een miniatuur wilt genereren. In dit voorbeeld hebben we toegang tot de eerste dia:

```csharp
ISlide sld = pres.Slides[0];
```

## Stap 4: Definieer de gewenste afmetingen

Geef de afmetingen (breedte en hoogte) op voor de miniatuur die u wilt genereren. Bijvoorbeeld:

```csharp
int desiredX = 1200; // Breedte
int desiredY = 800;  // Hoogte
```

## Stap 5: Bereken schaalfactoren

Om er zeker van te zijn dat de thumbnail de gewenste afmetingen heeft, berekent u de schaalfactoren als volgt:

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## Stap 6: Maak een miniatuur

Maak nu een miniatuur van een afbeelding op volledige schaal met behulp van de berekende schaalfactoren:

```csharp
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);
```

## Stap 7: Bewaar de miniatuur

Sla ten slotte de gegenereerde miniatuur op als een JPEG-afbeelding:

```csharp
bmp.Save(dataDir + "Notes_tnail_out.jpg", System.Drawing.Imaging.ImageFormat.Jpeg);
```

Dat is het! U hebt met succes een miniatuur gegenereerd van een dia in het notitiegedeelte van uw presentatie met behulp van Aspose.Slides voor .NET.

## Conclusie

Het opnemen van miniaturen in uw presentaties kan de visuele aantrekkingskracht en effectiviteit ervan aanzienlijk verbeteren. Aspose.Slides voor .NET maakt dit proces eenvoudig, waardoor u eenvoudig aangepaste miniaturen van uw dia's kunt maken.

## Veelgestelde vragen (veelgestelde vragen)

### In welke formaten kan ik de gegenereerde thumbnails opslaan?
U kunt de miniaturen in verschillende formaten opslaan, waaronder JPEG, PNG en meer, afhankelijk van uw vereisten.

### Kan ik miniaturen voor meerdere dia's tegelijk genereren?
Ja, u kunt de dia's in uw presentatie doorlopen en voor elke dia miniatuurweergaven genereren.

### Is Aspose.Slides voor .NET compatibel met verschillende .NET-frameworks?
Ja, Aspose.Slides voor .NET is compatibel met verschillende .NET-frameworks, waaronder .NET Core en .NET Framework.

### Kan ik het uiterlijk van de gegenereerde miniaturen aanpassen?
Absoluut! Aspose.Slides voor .NET biedt opties voor het aanpassen van het uiterlijk van de miniaturen, zoals afmetingen, kwaliteit en meer.

### Waar kan ik ondersteuning of verdere hulp krijgen met Aspose.Slides voor .NET?
 U kunt hulp vinden en in contact komen met de Aspose-gemeenschap op de[Aspose-ondersteuningsforum](https://forum.aspose.com/).