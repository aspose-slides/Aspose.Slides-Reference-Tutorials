---
"description": "Leer hoe u video's koppelt aan PowerPoint-dia's met Aspose.Slides voor .NET. Deze stapsgewijze handleiding bevat broncode en tips voor het maken van interactieve en boeiende presentaties met gekoppelde video's."
"linktitle": "Video koppelen via ActiveX-besturingselement"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Video koppelen via een ActiveX-besturingselement in PowerPoint"
"url": "/nl/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Video koppelen via een ActiveX-besturingselement in PowerPoint

Een video koppelen via een ActiveX-besturingselement in een presentatie met Aspose.Slides voor .NET

In Aspose.Slides voor .NET kunt u een video programmatisch koppelen aan een presentatiedia met behulp van het ActiveX-besturingselement. Dit stelt u in staat om interactieve presentaties te maken waarbij de video-inhoud direct in de dia kan worden afgespeeld. In deze stapsgewijze handleiding leiden we u door het proces van het koppelen van een video aan een presentatiedia met behulp van Aspose.Slides voor .NET.

## Vereisten:
- Visual Studio (of een andere .NET-ontwikkelomgeving)
- Aspose.Slides voor .NET-bibliotheek. U kunt deze downloaden van [hier](https://releases.aspose.com/slides/net/).

## Stap 1: Een nieuw project maken
Maak een nieuw project in uw favoriete .NET-ontwikkelomgeving (bijvoorbeeld Visual Studio) en voeg verwijzingen toe naar de Aspose.Slides voor .NET-bibliotheek.

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
    // Hier komt uw code om de gelinkte video toe te voegen
}
```

## Stap 4: ActiveX-besturingselement toevoegen
Maak een exemplaar van de `IOleObjectFrame` interface om het ActiveX-besturingselement aan de dia toe te voegen:

```csharp
ISlide slide = presentation.Slides[0]; // Kies de dia waaraan u de video wilt toevoegen
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

In de bovenstaande code voegen we een ActiveX-besturingselementframe met de afmetingen 640x480 toe aan de dia. We specificeren de ProgID voor het ShockwaveFlash ActiveX-besturingselement, dat vaak wordt gebruikt voor het insluiten van video's.

## Stap 5: Eigenschappen van ActiveX-besturingselement instellen
Stel de eigenschappen van het ActiveX-besturingselement in om de gekoppelde videobron op te geven:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Vervang met het daadwerkelijke pad van het videobestand
oleObjectFrame.AlternativeText = "Linked Video";
```

Vervangen `"YourVideoPathHere"` met het daadwerkelijke pad naar uw videobestand. De `AlternativeText` eigenschap geeft een beschrijving voor de gelinkte video.

## Stap 6: Presentatie opslaan
Sla de gewijzigde presentatie op:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## Veelgestelde vragen:

### Hoe kan ik de grootte en positie van de gekoppelde video op de dia opgeven?
U kunt de afmetingen en de positie van het ActiveX-besturingselementkader aanpassen met behulp van de parameters van de `AddOleObjectFrame` methode. De vier numerieke argumenten vertegenwoordigen respectievelijk de X- en Y-coördinaten van de linkerbovenhoek en de breedte en hoogte van het kader.

### Kan ik video's in verschillende formaten met deze aanpak koppelen?
Ja, u kunt video's van verschillende formaten koppelen, zolang het juiste ActiveX-besturingselement voor dat formaat beschikbaar is. Het ShockwaveFlash ActiveX-besturingselement dat in deze handleiding wordt gebruikt, is bijvoorbeeld geschikt voor Flash-video's (SWF). Voor andere formaten moet u mogelijk andere ProgID's gebruiken.

### Is er een limiet aan de grootte van de gelinkte video?
De grootte van de gekoppelde video kan van invloed zijn op de algehele grootte en prestaties van uw presentatie. Het is raadzaam uw video's te optimaliseren voor weergave op internet voordat u ze aan de presentatie koppelt.

### Conclusie:
Door de stappen in deze handleiding te volgen, kunt u eenvoudig een video koppelen via een ActiveX-besturingselement in een presentatie met Aspose.Slides voor .NET. Met deze functie kunt u boeiende en interactieve presentaties maken die multimediacontent naadloos integreren.

Voor meer details en geavanceerde opties kunt u terecht op de [Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}