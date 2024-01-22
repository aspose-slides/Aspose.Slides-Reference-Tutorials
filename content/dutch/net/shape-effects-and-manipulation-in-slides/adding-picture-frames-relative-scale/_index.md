---
title: Zelfstudie fotolijsten toevoegen met Aspose.Slides .NET
linktitle: Afbeeldingsframes met relatieve schaalhoogte toevoegen in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u afbeeldingsframes met relatieve schaalhoogte toevoegt in Aspose.Slides voor .NET. Volg deze stapsgewijze handleiding voor naadloze presentaties.
type: docs
weight: 17
url: /nl/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---
## Invoering
Aspose.Slides voor .NET is een krachtige bibliotheek waarmee ontwikkelaars moeiteloos PowerPoint-presentaties in hun .NET-toepassingen kunnen maken, manipuleren en converteren. In deze zelfstudie duiken we in het proces van het toevoegen van afbeeldingsframes met relatieve schaalhoogte met behulp van Aspose.Slides voor .NET. Volg deze stapsgewijze handleiding om uw vaardigheden op het gebied van presentatieopbouw te verbeteren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
- Basiskennis van de programmeertaal C#.
- Visual Studio of een andere C#-ontwikkelomgeving van uw voorkeur geïnstalleerd.
- Aspose.Slides voor .NET-bibliotheek toegevoegd aan uw project.
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw C#-code. Deze stap zorgt ervoor dat u toegang heeft tot de klassen en functionaliteiten van de Aspose.Slides-bibliotheek.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Stap 1: Stel uw project in
Begin met het maken van een nieuw C#-project in de ontwikkelomgeving van uw voorkeur. Zorg ervoor dat u de Aspose.Slides voor .NET-bibliotheek aan uw project toevoegt door ernaar te verwijzen.
## Stap 2: Presentatie en afbeelding laden
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Laad de afbeelding die moet worden toegevoegd aan de presentatieafbeeldingscollectie
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
In deze stap maken we een nieuw presentatieobject aan en laden we de afbeelding die we aan de presentatie willen toevoegen.
## Stap 3: Voeg een fotolijst toe aan de dia
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Voeg nu een fotolijst toe aan de eerste dia van de presentatie. Pas de parameters zoals vormtype, positie en afmetingen aan volgens uw vereisten.
## Stap 4: Stel de relatieve schaalbreedte en -hoogte in
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Stel de relatieve schaalhoogte en -breedte voor de fotolijst in om het gewenste schaaleffect te bereiken.
## Stap 5: Presentatie opslaan
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Sla ten slotte de presentatie op met het toegevoegde fotolijstje in het opgegeven uitvoerformaat.
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u afbeeldingsframes met relatieve schaalhoogte kunt toevoegen met behulp van Aspose.Slides voor .NET. Experimenteer met verschillende afbeeldingen, posities en schalen om visueel aantrekkelijke presentaties te creëren die zijn afgestemd op uw behoeften.
## Veel Gestelde Vragen
### Kan ik Aspose.Slides voor .NET gebruiken met andere programmeertalen?
Aspose.Slides ondersteunt voornamelijk .NET-talen, maar u kunt andere Aspose-producten verkennen op compatibiliteit met verschillende platforms.
### Waar kan ik gedetailleerde documentatie vinden voor Aspose.Slides voor .NET?
 Verwijs naar de[documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide informatie en voorbeelden.
### Is er een gratis proefversie beschikbaar voor Aspose.Slides voor .NET?
 Ja, je kunt een[gratis proefperiode](https://releases.aspose.com/) om de mogelijkheden van de bibliotheek te evalueren.
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
 Bezoek de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) om hulp te zoeken bij de gemeenschap en Aspose-experts.
### Waar kan ik Aspose.Slides voor .NET kopen?
 U kunt Aspose.Slides voor .NET kopen bij de[aankooppagina](https://purchase.aspose.com/buy).