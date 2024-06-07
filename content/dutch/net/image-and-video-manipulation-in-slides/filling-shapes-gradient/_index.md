---
title: Creëer verbluffende verlopen in PowerPoint met Aspose.Slides
linktitle: Vormen vullen met verloop in presentatiedia's met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Verbeter uw presentaties met Aspose.Slides voor .NET! Leer het stapsgewijze proces van het vullen van vormen met verlopen. Download nu uw gratis proefversie!
type: docs
weight: 21
url: /nl/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---
## Invoering
Het maken van visueel boeiende presentatiedia's is essentieel om de aandacht van uw publiek te trekken en vast te houden. In deze zelfstudie begeleiden we u bij het proces van het verbeteren van uw dia's door een ellipsvorm te vullen met een verloop met behulp van Aspose.Slides voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
- Basiskennis van de programmeertaal C#.
- Visual Studio is op uw computer geïnstalleerd.
-  Aspose.Slides voor .NET-bibliotheek. Download het[hier](https://releases.aspose.com/slides/net/).
- Een projectmap om uw bestanden te ordenen.
## Naamruimten importeren
Neem in uw C#-project de vereiste naamruimten voor Aspose.Slides op:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Stap 1: Maak een presentatie
Begin met het maken van een nieuwe presentatie met behulp van de Aspose.Slides-bibliotheek:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Je code komt hier...
}
```
## Stap 2: Voeg een ellipsvorm toe
Voeg een ellipsvorm in de eerste dia van uw presentatie in:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Stap 3: Pas verloopopmaak toe
Geef op dat de vorm moet worden gevuld met een verloop en definieer de verloopkenmerken:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Stap 4: Voeg verloopstops toe
Definieer de kleuren en posities van de verloopstops:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Stap 5: Sla de presentatie op
Sla uw presentatie op met de nieuw toegevoegde, met verloop gevulde vorm:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Herhaal deze stappen in uw C#-code en zorg voor de juiste volgorde en parameterwaarden. Dit resulteert in een presentatiebestand met een visueel aantrekkelijke ellipsvorm gevuld met een verloop.
## Conclusie
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## Veelgestelde vragen
### Vraag: Kan ik verlopen toepassen op andere vormen dan ellipsen?
EEN: Zeker! Aspose.Slides voor .NET ondersteunt verloopvulling voor verschillende vormen, zoals rechthoeken, polygonen en meer.
### Vraag: Waar kan ik aanvullende voorbeelden en gedetailleerde documentatie vinden?
 A: Ontdek de[Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide handleidingen en voorbeelden.
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Slides voor .NET?
 A: Ja, u heeft toegang tot een gratis proefperiode[hier](https://releases.aspose.com/).
### Vraag: Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
A: Zoek hulp en ga in gesprek met de gemeenschap[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
### Vraag: Kan ik een tijdelijke licentie kopen voor Aspose.Slides voor .NET?
 A: Zeker, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).