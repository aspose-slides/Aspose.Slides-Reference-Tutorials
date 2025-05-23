---
"description": "Leer hoe je fotolijsten met relatieve schaalhoogte toevoegt in Aspose.Slides voor .NET. Volg deze stapsgewijze handleiding voor naadloze presentaties."
"linktitle": "Fotolijsten toevoegen met relatieve schaalhoogte in Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Tutorial voor het toevoegen van fotolijsten met Aspose.Slides .NET"
"url": "/nl/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tutorial voor het toevoegen van fotolijsten met Aspose.Slides .NET

## Invoering
Aspose.Slides voor .NET is een krachtige bibliotheek waarmee ontwikkelaars moeiteloos PowerPoint-presentaties kunnen maken, bewerken en converteren in hun .NET-applicaties. In deze tutorial duiken we in het proces van het toevoegen van afbeeldingskaders met relatieve schaalhoogte met behulp van Aspose.Slides voor .NET. Volg deze stapsgewijze handleiding om je presentatievaardigheden te verbeteren.
## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft:
- Basiskennis van de programmeertaal C#.
- Visual Studio of een andere gewenste C#-ontwikkelomgeving geïnstalleerd.
- Aspose.Slides voor .NET-bibliotheek toegevoegd aan uw project.
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in je C#-code. Deze stap zorgt ervoor dat je toegang hebt tot de klassen en functionaliteiten van de Aspose.Slides-bibliotheek.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Stap 1: Stel uw project in
Begin met het aanmaken van een nieuw C#-project in je favoriete ontwikkelomgeving. Zorg ervoor dat je de Aspose.Slides voor .NET-bibliotheek aan je project toevoegt door ernaar te verwijzen.
## Stap 2: Presentatie en afbeelding laden
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Afbeelding laden die moet worden toegevoegd aan de presentatieafbeeldingenverzameling
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
In deze stap maken we een nieuw presentatieobject en laden we de afbeelding die we aan de presentatie willen toevoegen.
## Stap 3: Voeg een fotolijst toe aan de dia
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Voeg nu een fotokader toe aan de eerste dia van de presentatie. Pas parameters zoals vormtype, positie en afmetingen naar wens aan.
## Stap 4: Stel de relatieve schaalbreedte en -hoogte in
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Stel de relatieve schaalhoogte en -breedte van het fotolijstje in om het gewenste schaaleffect te bereiken.
## Stap 5: Presentatie opslaan
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Sla ten slotte de presentatie met het toegevoegde fotokader op in het opgegeven uitvoerformaat.
## Conclusie
Gefeliciteerd! Je hebt succesvol geleerd hoe je fotolijsten met relatieve schaalhoogte kunt toevoegen met Aspose.Slides voor .NET. Experimenteer met verschillende afbeeldingen, posities en schalen om visueel aantrekkelijke presentaties te maken die zijn afgestemd op jouw behoeften.
## Veelgestelde vragen
### Kan ik Aspose.Slides voor .NET gebruiken met andere programmeertalen?
Aspose.Slides ondersteunt voornamelijk .NET-talen, maar u kunt ook andere Aspose-producten bekijken om te zien of deze compatibel zijn met andere platforms.
### Waar kan ik gedetailleerde documentatie vinden voor Aspose.Slides voor .NET?
Raadpleeg de [documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide informatie en voorbeelden.
### Is er een gratis proefversie beschikbaar voor Aspose.Slides voor .NET?
Ja, je kunt een [gratis proefperiode](https://releases.aspose.com/) om de mogelijkheden van de bibliotheek te evalueren.
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
Bezoek de [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) om hulp te vragen aan de community en Aspose-experts.
### Waar kan ik Aspose.Slides voor .NET kopen?
U kunt Aspose.Slides voor .NET kopen bij de [aankooppagina](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}