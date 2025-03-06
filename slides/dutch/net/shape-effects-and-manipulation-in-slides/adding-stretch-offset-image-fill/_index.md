---
title: Rekverschuiving toevoegen voor afbeeldingsinvulling in PowerPoint-presentaties
linktitle: Rekverschuiving toevoegen voor invuldia's
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u PowerPoint-presentaties kunt verbeteren met Aspose.Slides voor .NET. Volg een stapsgewijze handleiding om een rekverschuiving toe te voegen voor de afbeeldingsvulling.
weight: 18
url: /nl/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rekverschuiving toevoegen voor afbeeldingsinvulling in PowerPoint-presentaties

## Invoering
In de dynamische wereld van presentaties spelen beelden een cruciale rol bij het trekken van de aandacht van het publiek. Aspose.Slides voor .NET stelt ontwikkelaars in staat hun PowerPoint-presentaties te verbeteren door een robuuste reeks functies te bieden. Eén zo'n functie is de mogelijkheid om een rekverschuiving toe te voegen voor de afbeeldingsvulling, waardoor creatieve en visueel aantrekkelijke dia's mogelijk zijn.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Aspose.Slides voor .NET Library: Download en installeer de bibliotheek van de[Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u een werkende .NET-ontwikkelomgeving hebt ingesteld.
Laten we nu aan de slag gaan met de stapsgewijze handleiding.
## Naamruimten importeren
Importeer eerst de benodigde naamruimten om de Aspose.Slides-functionaliteit binnen uw .NET-applicatie te benutten.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Stap 1: Stel uw project in
Maak een nieuw .NET-project in de ontwikkelomgeving van uw voorkeur. Zorg ervoor dat er op de juiste manier naar Aspose.Slides voor .NET wordt verwezen.
## Stap 2: Initialiseer de presentatieklasse
 Instantieer de`Presentation` klasse om het PowerPoint-bestand weer te geven.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Je code komt hier
}
```
## Stap 3: Verkrijg de eerste dia
Haal de eerste dia uit de presentatie op om mee te werken.
```csharp
ISlide sld = pres.Slides[0];
```
## Stap 4: Instantie van ImageEx-klasse
 Maak een exemplaar van de`ImageEx`klasse om de afbeelding te verwerken die u aan de dia wilt toevoegen.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Stap 5: Voeg een fotolijst toe
 Maak gebruik van de`AddPictureFrame` methode om een fotolijst aan de dia toe te voegen. Geef de afmetingen en positie van het frame op.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Stap 6: Sla de presentatie op
Sla de gewijzigde presentatie op schijf op.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
Dat is het! U hebt met succes een rekverschuiving toegevoegd voor invuldia's met afbeeldingen met behulp van Aspose.Slides voor .NET.
## Conclusie
Het verbeteren van uw PowerPoint-presentaties is nu eenvoudiger dan ooit met Aspose.Slides voor .NET. Door deze tutorial te volgen, heeft u geleerd hoe u stretch-offset kunt gebruiken voor het vullen van afbeeldingen, waardoor uw dia's een nieuw niveau van creativiteit krijgen.
## Veelgestelde vragen
### Kan ik Aspose.Slides voor .NET gebruiken in mijn webapplicaties?
Ja, Aspose.Slides voor .NET is geschikt voor zowel desktop- als webapplicaties.
### Is er een gratis proefversie beschikbaar voor Aspose.Slides voor .NET?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
 Bezoek de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) voor gemeenschapssteun.
### Waar kan ik de volledige documentatie voor Aspose.Slides voor .NET vinden?
 Verwijs naar de[documentatie](https://reference.aspose.com/slides/net/) voor gedetailleerde informatie.
### Kan ik Aspose.Slides voor .NET kopen?
 Ja, u kunt het product kopen[hier](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
