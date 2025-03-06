---
title: Video koppelen via ActiveX-besturingselement in PowerPoint
linktitle: Video koppelen via ActiveX-besturing
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u video's aan PowerPoint-dia's kunt koppelen met Aspose.Slides voor .NET. Deze stapsgewijze handleiding bevat broncode en tips voor het maken van interactieve en boeiende presentaties met gekoppelde video's.
weight: 12
url: /nl/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

Een video koppelen via ActiveX-besturingselement in een presentatie met Aspose.Slides voor .NET

In Aspose.Slides voor .NET kunt u een video programmatisch aan een presentatiedia koppelen met behulp van het ActiveX-besturingselement. Hiermee kunt u interactieve presentaties maken waarbij de video-inhoud direct binnen de dia kan worden afgespeeld. In deze stapsgewijze handleiding leiden we u door het proces van het koppelen van een video aan een presentatiedia met behulp van Aspose.Slides voor .NET.

## Vereisten:
- Visual Studio (of een andere .NET-ontwikkelomgeving)
-  Aspose.Slides voor .NET-bibliotheek. Je kunt het downloaden van[hier](https://releases.aspose.com/slides/net/).

## Stap 1: Maak een nieuw project
Maak een nieuw project in de .NET-ontwikkelomgeving van uw voorkeur (bijvoorbeeld Visual Studio) en voeg verwijzingen toe naar de Aspose.Slides voor .NET-bibliotheek.

## Stap 2: Importeer de benodigde naamruimten
Importeer in uw project de benodigde naamruimten voor het werken met Aspose.Slides:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## Stap 3: Presentatie laden
Laad de PowerPoint-presentatie waaraan u de gekoppelde video wilt toevoegen:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Uw code om de gekoppelde video toe te voegen, komt hier terecht
}
```

## Stap 4: ActiveX-besturingselement toevoegen
 Maak een exemplaar van de`IOleObjectFrame` interface om het ActiveX-besturingselement aan de dia toe te voegen:

```csharp
ISlide slide = presentation.Slides[0]; // Kies de dia waaraan u de video wilt toevoegen
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

In de bovenstaande code voegen we een ActiveX-besturingsframe met de afmetingen 640x480 toe aan de dia. We specificeren de ProgID voor het ShockwaveFlash ActiveX-besturingselement, dat vaak wordt gebruikt voor het insluiten van video's.

## Stap 5: Stel eigenschappen van ActiveX-besturingselement in
Stel de eigenschappen van het ActiveX-besturingselement in om de gekoppelde videobron op te geven:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Vervang door het daadwerkelijke videobestandspad
oleObjectFrame.AlternativeText = "Linked Video";
```

 Vervangen`"YourVideoPathHere"` met het daadwerkelijke pad naar uw videobestand. De`AlternativeText` eigenschap geeft een beschrijving voor de gekoppelde video.

## Stap 6: Presentatie opslaan
Sla de gewijzigde presentatie op:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Veelgestelde vragen:

### Hoe kan ik de grootte en positie van de gekoppelde video op de dia opgeven?
 kunt de afmetingen en positie van het ActiveX-controleframe aanpassen met behulp van de parameters van de`AddOleObjectFrame` methode. De vier numerieke argumenten vertegenwoordigen respectievelijk de X- en Y-coördinaten van de linkerbovenhoek en de breedte en hoogte van het frame.

### Kan ik op deze manier video's van verschillende formaten aan elkaar koppelen?
Ja, u kunt video's van verschillende formaten koppelen, zolang het juiste ActiveX-besturingselement beschikbaar is voor dat formaat. Het ShockwaveFlash ActiveX-besturingselement dat in deze handleiding wordt gebruikt, is bijvoorbeeld geschikt voor Flash-video's (SWF). Voor andere formaten moet u mogelijk andere ProgID's gebruiken.

### Is er een limiet aan de grootte van de gekoppelde video?
De grootte van de gekoppelde video kan van invloed zijn op de algehele grootte en prestaties van uw presentatie. Het wordt aanbevolen om uw video's te optimaliseren voor weergave op internet voordat u ze aan de presentatie koppelt.

### Conclusie:
Door de stappen in deze handleiding te volgen, kunt u eenvoudig een video via ActiveX-besturingselement koppelen in een presentatie met behulp van Aspose.Slides voor .NET. Met deze functie kunt u boeiende en interactieve presentaties maken waarin multimedia-inhoud naadloos is opgenomen.

 Voor meer details en geavanceerde opties kunt u de[Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
