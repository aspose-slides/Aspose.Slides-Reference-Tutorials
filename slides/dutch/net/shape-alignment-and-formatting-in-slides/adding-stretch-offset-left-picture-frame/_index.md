---
"description": "Leer hoe u PowerPoint-presentaties kunt verbeteren met Aspose.Slides voor .NET. Volg onze stapsgewijze handleiding om een rekverschuiving naar links toe te voegen voor afbeeldingskaders."
"linktitle": "Uitrekoffset toevoegen aan links voor een fotolijst in Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Uitrekverschuiving naar links toevoegen in PowerPoint met Aspose.Slide"
"url": "/nl/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Uitrekverschuiving naar links toevoegen in PowerPoint met Aspose.Slide

## Invoering
Aspose.Slides voor .NET is een krachtige bibliotheek waarmee ontwikkelaars eenvoudig PowerPoint-presentaties kunnen bewerken. In deze tutorial verkennen we het proces van het toevoegen van een rekverschuiving naar links voor een afbeeldingskader met Aspose.Slides voor .NET. Volg deze stapsgewijze handleiding om je vaardigheden in het werken met afbeeldingen en vormen in PowerPoint-presentaties te verbeteren.
## Vereisten
Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Aspose.Slides voor .NET: Zorg ervoor dat de bibliotheek geïnstalleerd is. Zo niet, download deze dan van de [Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/).
- Ontwikkelomgeving: Zorg voor een werkende ontwikkelomgeving met .NET-mogelijkheden.
## Naamruimten importeren
Begin met het importeren van de benodigde naamruimten in uw .NET-project:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Stap 1: Stel uw project in
Maak een nieuw project of open een bestaand project. Zorg ervoor dat de Aspose.Slides-bibliotheek in uw project is opgenomen.
## Stap 2: Presentatieobject maken
Instantieer de `Presentation` klasse, die het PPTX-bestand vertegenwoordigt:
```csharp
using (Presentation pres = new Presentation())
{
    // Hier komt uw code voor de volgende stappen te staan.
}
```
## Stap 3: Ontvang de eerste dia
Haal de eerste dia van de presentatie op:
```csharp
ISlide slide = pres.Slides[0];
```
## Stap 4: Instantieer de afbeelding
Laad de afbeelding die u wilt gebruiken:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Stap 5: Rechthoek AutoVorm toevoegen
Maak een AutoVorm van het type Rechthoek:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Stap 6: Vultype en afbeeldingvulmodus instellen
Configureer het opvultype van de vorm en de afbeeldingsopvulmodus:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Stap 7: Stel de afbeelding in om de vorm te vullen
Geef aan welke afbeelding de vorm moet vullen:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Stap 8: Specificeer rek-offsets
Definieer de afbeeldingsoffsets vanaf de overeenkomstige randen van het omsluitende kader van de vorm:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Stap 9: Sla de presentatie op
Schrijf het PPTX-bestand naar schijf:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Gefeliciteerd! U hebt met succes een rekverschuiving naar links toegevoegd voor een fotolijst met behulp van Aspose.Slides voor .NET.
## Conclusie
In deze tutorial hebben we het proces van het bewerken van afbeeldingskaders in PowerPoint-presentaties met Aspose.Slides voor .NET onderzocht. Door de stapsgewijze handleiding te volgen, hebt u inzicht gekregen in het werken met afbeeldingen, vormen en offsets.
## Veelgestelde vragen
### V: Kan ik rekverschuivingen toepassen op andere vormen dan rechthoeken?
A: Hoewel deze tutorial zich richt op rechthoeken, kunnen rekverschuivingen worden toegepast op verschillende vormen die door Aspose.Slides worden ondersteund.
### V: Hoe kan ik de rek-offsets aanpassen voor verschillende effecten?
A: Experimenteer met verschillende offsetwaarden om het gewenste visuele effect te bereiken. Pas de waarden aan uw specifieke wensen aan.
### V: Is Aspose.Slides compatibel met het nieuwste .NET Framework?
A: Aspose.Slides wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste versies van .NET Framework te garanderen.
### V: Waar kan ik aanvullende voorbeelden en bronnen voor Aspose.Slides vinden?
A: Ontdek de [Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide voorbeelden en begeleiding.
### V: Kan ik meerdere rek-offsets op één vorm toepassen?
A: Ja, u kunt meerdere stretch-offsets combineren om complexe en aangepaste visuele effecten te creëren.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}