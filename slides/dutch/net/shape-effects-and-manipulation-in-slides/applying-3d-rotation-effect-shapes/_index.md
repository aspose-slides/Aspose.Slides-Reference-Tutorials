---
title: Beheersing van 3D-rotatie in presentaties met Aspose.Slides voor .NET
linktitle: 3D-rotatie-effect toepassen op vormen in presentatiedia's
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Verbeter uw presentaties met Aspose.Slides voor .NET! Leer in deze zelfstudie hoe u 3D-rotatie-effecten op vormen toepast. Creëer een dynamische en visueel verbluffende presentatie.
weight: 23
url: /nl/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheersing van 3D-rotatie in presentaties met Aspose.Slides voor .NET

## Invoering
Het creëren van boeiende en dynamische presentatiedia's is een belangrijk aspect van effectieve communicatie. Aspose.Slides voor .NET biedt een krachtige set hulpmiddelen om uw presentaties te verbeteren, inclusief de mogelijkheid om 3D-rotatie-effecten op vormen toe te passen. In deze zelfstudie doorlopen we het proces van het toepassen van een 3D-rotatie-effect op vormen in presentatiedia's met behulp van Aspose.Slides voor .NET.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
- Aspose.Slides voor .NET: Zorg ervoor dat de Aspose.Slides-bibliotheek voor .NET is geïnstalleerd. Je kunt het downloaden van de[website](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Zet een .NET-ontwikkelomgeving op, zoals Visual Studio, om uw code te schrijven en uit te voeren.
## Naamruimten importeren
Importeer in uw .NET-project de benodigde naamruimten om de functionaliteit van Aspose.Slides te benutten. Voeg de volgende naamruimten toe aan het begin van uw code:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Stap 1: Stel uw project in
Maak een nieuw project in de .NET-ontwikkelomgeving van uw voorkeur. Zorg ervoor dat u de verwijzing Aspose.Slides aan uw project hebt toegevoegd.
## Stap 2: Initialiseer de presentatie
Instantieer een presentatieklasse om met dia's te gaan werken:
```csharp
Presentation pres = new Presentation();
```
## Stap 3: Voeg AutoShape toe
Voeg een AutoVorm toe aan de dia en geef het type, de positie en de afmetingen op:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Stap 4: Stel het 3D-rotatie-effect in
Configureer het 3D-rotatie-effect voor de AutoShape:
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
## Stap 6: Herhaal dit voor andere vormen
Als u nog meer vormen heeft, herhaalt u stap 3 tot en met 5 voor elke vorm.
## Conclusie
Het toevoegen van 3D-rotatie-effecten aan vormen in uw presentatiedia's kan de visuele aantrekkingskracht ervan aanzienlijk vergroten. Met Aspose.Slides voor .NET wordt dit proces eenvoudig, waardoor u boeiende presentaties kunt maken.
## Veelgestelde vragen
### Kan ik 3D-rotatie toepassen op tekstvakken in Aspose.Slides voor .NET?
Ja, u kunt 3D-rotatie-effecten toepassen op verschillende vormen, inclusief tekstvakken, met behulp van Aspose.Slides.
### Is er een proefversie van Aspose.Slides voor .NET beschikbaar?
 Ja, u heeft toegang tot de proefversie[hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
 Bezoek de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) voor gemeenschapsondersteuning en discussies.
### Kan ik een tijdelijke licentie kopen voor Aspose.Slides voor .NET?
 Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik gedetailleerde documentatie vinden voor Aspose.Slides voor .NET?
 De documentatie is beschikbaar[hier](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
