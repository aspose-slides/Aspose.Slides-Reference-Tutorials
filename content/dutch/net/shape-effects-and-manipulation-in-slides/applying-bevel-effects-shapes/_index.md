---
title: Afschuiningseffecten beheersen in Aspose.Slides - Stapsgewijze zelfstudie
linktitle: Afschuiningseffecten toepassen op vormen in presentatiedia's met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Verbeter uw presentatiedia's met Aspose.Slides voor .NET! Leer boeiende schuine effecten toepassen in deze stapsgewijze handleiding.
type: docs
weight: 24
url: /nl/net/shape-effects-and-manipulation-in-slides/applying-bevel-effects-shapes/
---
## Invoering
In de dynamische wereld van presentaties kan het toevoegen van visuele aantrekkingskracht aan uw dia's de impact van uw boodschap aanzienlijk vergroten. Aspose.Slides voor .NET biedt een krachtige toolkit om uw presentatiedia's programmatisch te manipuleren en te verfraaien. Een van die intrigerende functies is de mogelijkheid om schuine effecten op vormen toe te passen, waardoor diepte en dimensie aan uw beelden wordt toegevoegd.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.Slides voor .NET: Zorg ervoor dat de Aspose.Slides-bibliotheek is geïnstalleerd. Je kunt het downloaden van de[website](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Zet uw .NET-ontwikkelomgeving op en zorg voor een basiskennis van C#.
- Documentmap: maak een map voor uw documenten waarin de gegenereerde presentatiebestanden worden opgeslagen.
## Naamruimten importeren
Neem in uw C#-code de benodigde naamruimten op om toegang te krijgen tot de Aspose.Slides-functionaliteiten.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Stap 1: Stel uw documentenmap in
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Zorg ervoor dat de documentmap bestaat en maak deze aan als deze nog niet aanwezig is.
## Stap 2: Maak een presentatie-instantie
```csharp
Presentation pres = new Presentation();
ISlide slide = pres.Slides[0];
```
Initialiseer een presentatie-exemplaar en voeg een dia toe om mee te werken.
## Stap 3: Voeg een vorm toe aan de dia
```csharp
IAutoShape shape = slide.Shapes.AddAutoShape(ShapeType.Ellipse, 30, 30, 100, 100);
shape.FillFormat.FillType = FillType.Solid;
shape.FillFormat.SolidFillColor.Color = Color.Green;
ILineFillFormat format = shape.LineFormat.FillFormat;
format.FillType = FillType.Solid;
format.SolidFillColor.Color = Color.Orange;
shape.LineFormat.Width = 2.0;
```
Maak een automatische vorm (ellips in dit voorbeeld) en pas de vul- en lijneigenschappen ervan aan.
## Stap 4: Stel ThreeDFormat-eigenschappen in
```csharp
shape.ThreeDFormat.Depth = 4;
shape.ThreeDFormat.BevelTop.BevelType = BevelPresetType.Circle;
shape.ThreeDFormat.BevelTop.Height = 6;
shape.ThreeDFormat.BevelTop.Width = 6;
shape.ThreeDFormat.Camera.CameraType = CameraPresetType.OrthographicFront;
shape.ThreeDFormat.LightRig.LightType = LightRigPresetType.ThreePt;
shape.ThreeDFormat.LightRig.Direction = LightingDirection.Top;
```
Geef de driedimensionale eigenschappen op, waaronder het type afschuining, hoogte, breedte, cameratype, lichttype en richting.
## Stap 5: Sla de presentatie op
```csharp
pres.Save(dataDir + "Bevel_out.pptx", SaveFormat.Pptx);
```
Sla de presentatie met de toegepaste schuine effecten op in een PPTX-bestand.
## Conclusie
Gefeliciteerd! U hebt met succes schuine effecten toegepast op een vorm in uw presentatie met Aspose.Slides voor .NET. Experimenteer met verschillende parameters om het volledige potentieel van visuele verbeteringen in uw dia's te benutten.
## Veel Gestelde Vragen
### 1. Kan ik schuine randen op andere vormen toepassen?
Ja, u kunt schuine effecten op verschillende vormen toepassen door het vormtype en de eigenschappen dienovereenkomstig aan te passen.
### 2. Hoe kan ik de kleur van de schuine kant veranderen?
 Wijzig de`SolidFillColor.Color` eigendom binnen de`BevelTop` eigenschap om de kleur van de schuine kant te wijzigen.
### 3. Is Aspose.Slides compatibel met het nieuwste .NET-framework?
Ja, Aspose.Slides wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste .NET-frameworks te garanderen.
### 4. Kan ik meerdere schuine effecten op één vorm toepassen?
Hoewel dit niet gebruikelijk is, kunt u experimenteren met het stapelen van meerdere vormen of het manipuleren van de schuine eigenschappen om een soortgelijk effect te bereiken.
### 5. Zijn er andere 3D-effecten beschikbaar in Aspose.Slides?
Absoluut! Aspose.Slides biedt een verscheidenheid aan 3D-effecten om diepte en realisme aan uw presentatie-elementen toe te voegen.