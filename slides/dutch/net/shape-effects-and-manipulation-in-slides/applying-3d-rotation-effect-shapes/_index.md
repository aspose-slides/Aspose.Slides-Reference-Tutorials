---
"description": "Verbeter je presentaties met Aspose.Slides voor .NET! Leer in deze tutorial hoe je 3D-rotatie-effecten op vormen toepast. Creëer dynamische en visueel verbluffende presentaties."
"linktitle": "Het 3D-rotatie-effect toepassen op vormen in presentatieslides"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "3D-rotatie in presentaties onder de knie krijgen met Aspose.Slides voor .NET"
"url": "/nl/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 3D-rotatie in presentaties onder de knie krijgen met Aspose.Slides voor .NET

## Invoering
Het creëren van boeiende en dynamische presentatieslides is een essentieel onderdeel van effectieve communicatie. Aspose.Slides voor .NET biedt een krachtige set tools om uw presentaties te verbeteren, inclusief de mogelijkheid om 3D-rotatie-effecten toe te passen op vormen. In deze tutorial laten we zien hoe u een 3D-rotatie-effect kunt toepassen op vormen in presentatieslides met Aspose.Slides voor .NET.
## Vereisten
Voordat we met de tutorial beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Aspose.Slides voor .NET: Zorg ervoor dat u de Aspose.Slides-bibliotheek voor .NET hebt geïnstalleerd. U kunt deze downloaden van de [website](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Stel een .NET-ontwikkelomgeving in, zoals Visual Studio, om uw code te schrijven en uit te voeren.
## Naamruimten importeren
Importeer in uw .NET-project de benodigde naamruimten om de functionaliteit van Aspose.Slides te benutten. Voeg de volgende naamruimten toe aan het begin van uw code:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Stap 1: Stel uw project in
Maak een nieuw project in uw favoriete .NET-ontwikkelomgeving. Zorg ervoor dat u de Aspose.Slides-referentie aan uw project hebt toegevoegd.
## Stap 2: Presentatie initialiseren
Maak een Presentation-klasse om met dia's te beginnen werken:
```csharp
Presentation pres = new Presentation();
```
## Stap 3: AutoVorm toevoegen
Voeg een AutoVorm toe aan de dia en geef het type, de positie en de afmetingen op:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Stap 4: 3D-rotatie-effect instellen
Configureer het 3D-rotatie-effect voor de AutoVorm:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Stap 5: Sla de presentatie op
Sla de gewijzigde presentatie op met het toegepaste 3D-rotatie-effect:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Stap 6: Herhaal voor andere vormen
Als u nog meer vormen hebt, herhaalt u stap 3 tot en met 5 voor elke vorm.
## Conclusie
Het toevoegen van 3D-rotatie-effecten aan vormen in uw presentatieslides kan de visuele aantrekkingskracht ervan aanzienlijk vergroten. Met Aspose.Slides voor .NET wordt dit proces eenvoudig, waardoor u boeiende presentaties kunt maken.
## Veelgestelde vragen
### Kan ik 3D-rotatie toepassen op tekstvakken in Aspose.Slides voor .NET?
Ja, u kunt 3D-rotatie-effecten toepassen op verschillende vormen, waaronder tekstvakken, met behulp van Aspose.Slides.
### Is er een proefversie van Aspose.Slides voor .NET beschikbaar?
Ja, u kunt de proefversie gebruiken [hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
Bezoek de [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) voor ondersteuning en discussies vanuit de gemeenschap.
### Kan ik een tijdelijke licentie voor Aspose.Slides voor .NET kopen?
Ja, u kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik gedetailleerde documentatie vinden voor Aspose.Slides voor .NET?
De documentatie is beschikbaar [hier](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}