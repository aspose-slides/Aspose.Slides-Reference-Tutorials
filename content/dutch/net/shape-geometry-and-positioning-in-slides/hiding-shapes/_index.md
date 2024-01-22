---
title: Vormen verbergen in PowerPoint met Aspose.Slides .NET Tutorial
linktitle: Vormen verbergen in presentatiedia's met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u vormen in PowerPoint-dia's kunt verbergen met Aspose.Slides voor .NET. Pas presentaties programmatisch aan met deze stapsgewijze handleiding.
type: docs
weight: 21
url: /nl/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## Invoering
In de dynamische wereld van presentaties is maatwerk essentieel. Aspose.Slides voor .NET biedt een krachtige oplossing voor het programmatisch manipuleren van PowerPoint-presentaties. Een veel voorkomende vereiste is de mogelijkheid om specifieke vormen binnen een dia te verbergen. Deze tutorial leidt u door het proces van het verbergen van vormen in presentatiedia's met behulp van Aspose.Slides voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
-  Aspose.Slides voor .NET: Zorg ervoor dat de Aspose.Slides-bibliotheek is geïnstalleerd. Je kunt het downloaden[hier](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Stel uw favoriete ontwikkelomgeving voor .NET in.
- Basiskennis van C#: Maak uzelf vertrouwd met C#, aangezien de gegeven codevoorbeelden in deze taal zijn.
## Naamruimten importeren
Om met Aspose.Slides te gaan werken, importeert u de benodigde naamruimten in uw C#-project. Dit zorgt ervoor dat u toegang heeft tot de vereiste klassen en methoden.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Laten we nu de voorbeeldcode in meerdere stappen opsplitsen voor een duidelijk en beknopt begrip.
## Stap 1: Stel uw project in
Maak een nieuw C#-project en zorg ervoor dat u de Aspose.Slides-bibliotheek opneemt.
## Stap 2: Maak een presentatie
 Instantieer de`Presentation` klasse, die het PowerPoint-bestand vertegenwoordigt. Voeg een dia toe en verkrijg een verwijzing ernaar.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Stap 3: Vormen toevoegen aan de dia
Voeg autovormen toe aan de dia, zoals rechthoeken en manen, met specifieke afmetingen.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Stap 4: vormen verbergen op basis van alternatieve tekst
Geef een alternatieve tekst op en verberg vormen die overeenkomen met deze tekst.
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
Sla de gewijzigde presentatie op schijf op in PPTX-indeling.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Conclusie
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## Veelgestelde vragen
### Is Aspose.Slides compatibel met .NET Core?
Ja, Aspose.Slides ondersteunt .NET Core en biedt flexibiliteit in uw ontwikkelomgeving.
### Kan ik vormen verbergen op basis van andere voorwaarden dan alternatieve tekst?
Absoluut! U kunt de verberglogica aanpassen op basis van verschillende kenmerken, zoals vormtype, kleur of positie.
### Waar kan ik aanvullende Aspose.Slides-documentatie vinden?
 Verken de documentatie[hier](https://reference.aspose.com/slides/net/) voor uitgebreide informatie en voorbeelden.
### Zijn er tijdelijke licenties beschikbaar voor Aspose.Slides?
 Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/) voor testdoeleinden.
### Hoe kan ik community-ondersteuning krijgen voor Aspose.Slides?
 Sluit u aan bij de Aspose.Slides-community op de[forum](https://forum.aspose.com/c/slides/11) voor discussies en hulp.