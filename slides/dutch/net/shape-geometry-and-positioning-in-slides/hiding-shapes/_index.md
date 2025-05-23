---
"description": "Leer hoe u vormen in PowerPoint-dia's kunt verbergen met Aspose.Slides voor .NET. Pas presentaties programmatisch aan met deze stapsgewijze handleiding."
"linktitle": "Vormen verbergen in presentatieslides met Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Vormen verbergen in PowerPoint met Aspose.Slides .NET-zelfstudie"
"url": "/nl/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vormen verbergen in PowerPoint met Aspose.Slides .NET-zelfstudie

## Invoering
In de dynamische wereld van presentaties is maatwerk essentieel. Aspose.Slides voor .NET biedt een krachtige oplossing voor het programmatisch bewerken van PowerPoint-presentaties. Een veelvoorkomende vereiste is de mogelijkheid om specifieke vormen in een dia te verbergen. Deze tutorial begeleidt u bij het verbergen van vormen in presentatiedia's met Aspose.Slides voor .NET.
## Vereisten
Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Aspose.Slides voor .NET: Zorg ervoor dat je de Aspose.Slides-bibliotheek hebt geïnstalleerd. Je kunt deze downloaden. [hier](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Stel uw gewenste ontwikkelomgeving voor .NET in.
- Basiskennis van C#: Maak uzelf vertrouwd met C#, aangezien de codevoorbeelden in deze taal zijn geschreven.
## Naamruimten importeren
Om met Aspose.Slides aan de slag te gaan, importeert u de benodigde naamruimten in uw C#-project. Zo hebt u toegang tot de vereiste klassen en methoden.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Laten we de voorbeeldcode nu opsplitsen in meerdere stappen, zodat u de code duidelijk en beknopt begrijpt.
## Stap 1: Stel uw project in
Maak een nieuw C#-project en zorg ervoor dat u de Aspose.Slides-bibliotheek hierin opneemt.
## Stap 2: Een presentatie maken
Instantieer de `Presentation` klasse, die het PowerPoint-bestand vertegenwoordigt. Voeg een dia toe en ontvang een verwijzing ernaar.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Stap 3: Vormen toevoegen aan de dia
Voeg automatische vormen, zoals rechthoeken en manen, met specifieke afmetingen toe aan de dia.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Stap 4: Vormen verbergen op basis van alternatieve tekst
Geef een alternatieve tekst op en verberg vormen die bij deze tekst passen.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Stap 5: Sla de presentatie op
Sla de gewijzigde presentatie op schijf op in PPTX-formaat.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusie
Gefeliciteerd! Je hebt met succes vormen in je presentatie verborgen met Aspose.Slides voor .NET. Dit opent een wereld aan mogelijkheden voor het programmatisch maken van dynamische en aangepaste dia's.
---
## Veelgestelde vragen
### Is Aspose.Slides compatibel met .NET Core?
Ja, Aspose.Slides ondersteunt .NET Core, wat flexibiliteit biedt in uw ontwikkelomgeving.
### Kan ik vormen verbergen op basis van andere voorwaarden dan alternatieve tekst?
Absoluut! Je kunt de verberglogica aanpassen op basis van verschillende kenmerken, zoals vormtype, kleur of positie.
### Waar kan ik aanvullende Aspose.Slides-documentatie vinden?
Verken de documentatie [hier](https://reference.aspose.com/slides/net/) voor diepgaande informatie en voorbeelden.
### Zijn er tijdelijke licenties beschikbaar voor Aspose.Slides?
Ja, u kunt een tijdelijke licentie verkrijgen [hier](https://purchase.aspose.com/temporary-license/) voor testdoeleinden.
### Hoe kan ik communityondersteuning krijgen voor Aspose.Slides?
Sluit je aan bij de Aspose.Slides-community op de [forum](https://forum.aspose.com/c/slides/11) voor discussies en assistentie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}