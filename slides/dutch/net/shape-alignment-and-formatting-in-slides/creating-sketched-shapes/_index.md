---
title: Creëer prachtige geschetste vormen met Aspose.Slides
linktitle: Geschetste vormen maken in presentatiedia's met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u creatief geschetste vormen aan uw presentatiedia's kunt toevoegen met Aspose.Slides voor .NET. Verbeter de visuele aantrekkingskracht moeiteloos!
weight: 13
url: /nl/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Invoering
Welkom bij onze stapsgewijze handleiding voor het maken van geschetste vormen in presentatiedia's met Aspose.Slides voor .NET. Als u een vleugje creativiteit aan uw presentaties wilt toevoegen, zorgen geschetste vormen voor een unieke en handgetekende esthetiek. In deze zelfstudie leiden we u door het proces en splitsen het op in eenvoudige stappen om een soepele ervaring te garanderen.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
-  Aspose.Slides voor .NET: Zorg ervoor dat de Aspose.Slides-bibliotheek voor .NET is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Zet een .NET-ontwikkelomgeving op met de IDE van uw voorkeur.
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw .NET-project. Deze stap zorgt ervoor dat u toegang heeft tot de klassen en functionaliteiten die nodig zijn om met Aspose.Slides te werken.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Stap 1: Stel het project in
Begin met het maken van een nieuw .NET-project of het openen van een bestaand project. Zorg ervoor dat u Aspose.Slides opneemt in uw projectreferenties.
## Stap 2: Initialiseer Aspose.Slides
Initialiseer Aspose.Slides door het volgende codefragment toe te voegen. Hiermee wordt de presentatie ingesteld en worden de uitvoerpaden voor het presentatiebestand en de miniatuurafbeelding opgegeven.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Ga door naar de volgende stappen...
}
```
## Stap 3: Voeg een geschetste vorm toe
Laten we nu een geschetste vorm aan de dia toevoegen. In dit voorbeeld voegen we een rechthoek toe met een schetseffect uit de vrije hand.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transformeer de vorm naar een schets van een stijl uit de vrije hand
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Stap 4: Genereer een miniatuur
Genereer een miniatuur van de dia om de geschetste vorm te visualiseren. Sla de miniatuur op als een PNG-bestand.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Stap 5: Presentatie opslaan
Sla het presentatiebestand op met de geschetste vorm.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Dat is het! U hebt met succes een presentatie met geschetste vormen gemaakt met Aspose.Slides voor .NET.
## Conclusie
Het toevoegen van geschetste vormen aan uw presentatiedia's kan de visuele aantrekkingskracht vergroten en uw publiek betrekken. Met Aspose.Slides voor .NET wordt het proces eenvoudig, zodat u uw creativiteit moeiteloos de vrije loop kunt laten.
## Veelgestelde vragen
### 1. Kan ik het geschetste effect aanpassen?
 Ja, Aspose.Slides voor .NET biedt verschillende aanpassingsopties voor geschetste effecten. Verwijs naar de[documentatie](https://reference.aspose.com/slides/net/) voor gedetailleerde informatie.
### 2. Is er een gratis proefperiode beschikbaar?
 Zeker! U kunt een gratis proefversie van Aspose.Slides voor .NET verkennen[hier](https://releases.aspose.com/).
### 3. Waar kan ik ondersteuning krijgen?
 Voor hulp of vragen kunt u terecht op de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
### 4. Hoe kan ik Aspose.Slides voor .NET kopen?
 Om Aspose.Slides voor .NET te kopen, gaat u naar de[aankooppagina](https://purchase.aspose.com/buy).
### 5. Bieden jullie tijdelijke licenties aan?
 Ja, er zijn tijdelijke licenties beschikbaar[hier](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
