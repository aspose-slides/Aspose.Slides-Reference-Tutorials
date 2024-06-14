---
title: Presentatiedia's opnieuw vormgeven met Aspose.Slides voor .NET
linktitle: De volgorde van vormen in presentatiedia's wijzigen met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u presentatiedia's een nieuwe vorm kunt geven met Aspose.Slides voor .NET. Volg deze stapsgewijze handleiding om vormen opnieuw te ordenen en de visuele aantrekkingskracht te verbeteren.
type: docs
weight: 26
url: /nl/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---
## Invoering
Het maken van visueel aantrekkelijke presentatiedia's is een cruciaal aspect van effectieve communicatie. Aspose.Slides voor .NET stelt ontwikkelaars in staat dia's programmatisch te manipuleren en biedt een breed scala aan functionaliteiten. In deze zelfstudie verdiepen we ons in het proces van het wijzigen van de volgorde van vormen in presentatiedia's met behulp van Aspose.Slides voor .NET.
## Vereisten
Voordat we aan deze reis beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.Slides voor .NET: Zorg ervoor dat de Aspose.Slides-bibliotheek in uw .NET-project is geïntegreerd. Als dit niet het geval is, kunt u deze downloaden van de[releases pagina](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Zet een werkende ontwikkelomgeving op met Visual Studio of een andere .NET-ontwikkeltool.
- Basiskennis van C#: maak uzelf vertrouwd met de basisprincipes van de programmeertaal C#.
## Naamruimten importeren
Neem in uw C#-project de benodigde naamruimten op om toegang te krijgen tot de Aspose.Slides-functionaliteit:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Stap 1: Stel uw project in
Maak een nieuw project in Visual Studio of uw favoriete .NET-ontwikkelomgeving. Zorg ervoor dat er in uw project naar Aspose.Slides voor .NET wordt verwezen.
## Stap 2: Laad de presentatie
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Stap 3: Toegang tot de dia en vormen
```csharp
ISlide slide = presentation.Slides[0];
```
## Stap 4: Voeg een nieuwe vorm toe
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Stap 5: Wijzig de tekst in de vorm
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Stap 6: Voeg nog een vorm toe
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Stap 7: Wijzig de volgorde van vormen
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Stap 8: Sla de aangepaste presentatie op
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
Hiermee is de stapsgewijze handleiding voltooid voor het wijzigen van de volgorde van vormen in presentatiedia's met Aspose.Slides voor .NET.
## Conclusie
Aspose.Slides voor .NET vereenvoudigt de taak van het programmatisch manipuleren van presentatiedia's. Door deze tutorial te volgen, heeft u geleerd hoe u vormen opnieuw kunt ordenen, zodat u de visuele aantrekkingskracht van uw presentaties kunt vergroten.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Slides voor .NET gebruiken in zowel Windows- als Linux-omgevingen?
A: Ja, Aspose.Slides voor .NET is compatibel met zowel Windows- als Linux-omgevingen.
### Vraag: Zijn er licentieoverwegingen voor het gebruik van Aspose.Slides in een commercieel project?
 A: Ja, u kunt licentiegegevens en aankoopopties vinden op de website[Aspose.Slides-aankooppagina](https://purchase.aspose.com/buy).
### Vraag: Is er een gratis proefversie beschikbaar voor Aspose.Slides voor .NET?
 A: Ja, u kunt de functies verkennen met de[gratis proefperiode](https://releases.aspose.com/) beschikbaar op de Aspose.Slides-website.
### Vraag: Waar kan ik ondersteuning vinden of vragen stellen met betrekking tot Aspose.Slides voor .NET?
 A: Bezoek de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) om steun te krijgen en betrokken te raken bij de gemeenschap.
### Vraag: Hoe kan ik een tijdelijke licentie verkrijgen voor Aspose.Slides voor .NET?
 A: U kunt een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor evaluatiedoeleinden.