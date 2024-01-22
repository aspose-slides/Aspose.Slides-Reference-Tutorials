---
title: Stretch Offset naar links toevoegen in PowerPoint met Aspose.Slide
linktitle: Stretch-offset naar links toevoegen voor afbeeldingsframe in Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u PowerPoint-presentaties kunt verbeteren met Aspose.Slides voor .NET. Volg onze stapsgewijze handleiding om rekverschuiving naar links toe te voegen voor fotolijsten.
type: docs
weight: 14
url: /nl/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## Invoering
Aspose.Slides voor .NET is een krachtige bibliotheek waarmee ontwikkelaars PowerPoint-presentaties gemakkelijk kunnen manipuleren. In deze zelfstudie verkennen we het proces van het toevoegen van een rekverschuiving aan de linkerkant voor een fotolijst met behulp van Aspose.Slides voor .NET. Volg deze stapsgewijze handleiding om uw vaardigheden in het werken met afbeeldingen en vormen in PowerPoint-presentaties te verbeteren.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Aspose.Slides voor .NET: Zorg ervoor dat de bibliotheek is geïnstalleerd. Als dit niet het geval is, downloadt u deze van de[Aspose.Slides voor .NET-documentatie](https://reference.aspose.com/slides/net/).
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
Maak een nieuw project aan of open een bestaand project. Zorg ervoor dat er in uw project naar de Aspose.Slides-bibliotheek wordt verwezen.
## Stap 2: Maak een presentatieobject
 Instantieer de`Presentation` klasse, die het PPTX-bestand vertegenwoordigt:
```csharp
using (Presentation pres = new Presentation())
{
    // Uw code voor de volgende stappen komt hier terecht.
}
```
## Stap 3: Verkrijg de eerste dia
Haal de eerste dia uit de presentatie op:
```csharp
ISlide slide = pres.Slides[0];
```
## Stap 4: Instantie van de afbeelding
Laad de afbeelding die u wilt gebruiken:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Stap 5: Voeg Rechthoek AutoShape toe
Maak een AutoVorm van het type Rechthoek:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Stap 6: Stel het vultype en de afbeeldingsvulmodus in
Configureer het opvultype en de afbeeldingsopvulmodus van de vorm:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Stap 7: Stel de afbeelding in om de vorm te vullen
Geef de afbeelding op om de vorm te vullen:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Stap 8: Specificeer rek-offsets
Definieer de afbeeldingsverschuivingen ten opzichte van de overeenkomstige randen van het omsluitende kader van de vorm:
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
Gefeliciteerd! U hebt met succes een rekverschuiving aan de linkerkant toegevoegd voor een fotolijst met Aspose.Slides voor .NET.
## Conclusie
In deze zelfstudie hebben we het proces van het manipuleren van afbeeldingsframes in PowerPoint-presentaties onderzocht met behulp van Aspose.Slides voor .NET. Door de stapsgewijze handleiding te volgen, heeft u inzicht gekregen in het werken met afbeeldingen, vormen en offsets.
## Veel Gestelde Vragen
### Vraag: Kan ik rekverschuivingen toepassen op andere vormen dan rechthoeken?
A: Hoewel deze tutorial zich richt op rechthoeken, kunnen rekverschuivingen worden toegepast op verschillende vormen die worden ondersteund door Aspose.Slides.
### Vraag: Hoe kan ik de rek-offsets voor verschillende effecten aanpassen?
A: Experimenteer met verschillende offsetwaarden om de gewenste visuele impact te bereiken. Stem de waarden af op uw specifieke vereisten.
### Vraag: Is Aspose.Slides compatibel met het nieuwste .NET-framework?
A: Aspose.Slides wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste .NET-frameworkversies te garanderen.
### Vraag: Waar kan ik aanvullende voorbeelden en bronnen voor Aspose.Slides vinden?
 A: Ontdek de[Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide voorbeelden en begeleiding.
### Vraag: Kan ik meerdere rekverschuivingen op één vorm toepassen?
A: Ja, u kunt meerdere rek-offsets combineren om complexe en aangepaste visuele effecten te bereiken.