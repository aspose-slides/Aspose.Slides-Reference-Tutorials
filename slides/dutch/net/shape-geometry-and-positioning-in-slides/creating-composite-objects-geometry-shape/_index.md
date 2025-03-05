---
title: Samengestelde geometrische vormen beheersen in presentaties
linktitle: Samengestelde objecten in geometrische vorm maken met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u verbluffende presentaties kunt maken met samengestelde geometrische vormen met behulp van Aspose.Slides voor .NET. Volg onze stapsgewijze handleiding voor indrukwekkende resultaten.
type: docs
weight: 14
url: /nl/net/shape-geometry-and-positioning-in-slides/creating-composite-objects-geometry-shape/
---
## Invoering
Ontgrendel de kracht van Aspose.Slides voor .NET om uw presentaties te verbeteren door samengestelde objecten in geometrische vormen te maken. Deze tutorial begeleidt u bij het genereren van visueel aantrekkelijke dia's met ingewikkelde geometrie met behulp van Aspose.Slides.
## Vereisten
Voordat we ingaan op de tutorial, zorg ervoor dat je aan de volgende vereisten voldoet:
- Basiskennis van de programmeertaal C#.
-  Aspose.Slides voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van de[Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/).
- Een ontwikkelomgeving opgezet met Visual Studio of een andere C#-ontwikkeltool.
## Naamruimten importeren
Zorg ervoor dat u de benodigde naamruimten in uw C#-code importeert om gebruik te kunnen maken van de functionaliteiten van Aspose.Slides. Voeg de volgende naamruimten toe aan het begin van uw code:
```csharp
using System.IO;
using Aspose.Slides.Export;
```
Laten we nu de voorbeeldcode opsplitsen in meerdere stappen om u te begeleiden bij het maken van samengestelde objecten in een geometrische vorm met behulp van Aspose.Slides voor .NET:
## Stap 1: Stel de omgeving in
```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Maak een directory aan als deze nog niet aanwezig is.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
string resultPath = Path.Combine(dataDir, "GeometryShapeCompositeObjects.pptx");
```
In deze stap initialiseren we de omgeving door de map en het resultaatpad voor onze presentatie in te stellen.
## Stap 2: Maak een presentatie- en geometrische vorm
```csharp
using (Presentation pres = new Presentation())
{
    // Creëer een nieuwe vorm
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
Hier maken we een nieuwe presentatie en voegen we een rechthoek toe als geometrische vorm.
## Stap 3: Definieer geometrische paden
```csharp
// Maak het eerste geometriepad
GeometryPath geometryPath0 = new GeometryPath();
geometryPath0.MoveTo(0, 0);
geometryPath0.LineTo(shape.Width, 0);
geometryPath0.LineTo(shape.Width, shape.Height / 3);
geometryPath0.LineTo(0, shape.Height / 3);
geometryPath0.CloseFigure();
// Maak een tweede geometriepad
GeometryPath geometryPath1 = new GeometryPath();
geometryPath1.MoveTo(0, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height / 3 * 2);
geometryPath1.LineTo(shape.Width, shape.Height);
geometryPath1.LineTo(0, shape.Height);
geometryPath1.CloseFigure();
```
In deze stap definiëren we twee geometrische paden die onze geometrische vorm zullen samenstellen.
## Stap 4: Vormgeometrie instellen
```csharp
// Stel de vormgeometrie in als samenstelling van twee geometriepaden
shape.SetGeometryPaths(new GeometryPath[] { geometryPath0, geometryPath1 });
```
Nu stellen we de geometrie van de vorm in als een samenstelling van de twee eerder gedefinieerde geometrische paden.
## Stap 5: Sla de presentatie op
```csharp
// Bewaar de presentatie
pres.Save(resultPath, SaveFormat.Pptx);
}
```
Ten slotte slaan we de presentatie op met de samengestelde geometrievorm.
## Conclusie
Gefeliciteerd! U hebt met succes samengestelde objecten in een geometrische vorm gemaakt met Aspose.Slides voor .NET. Experimenteer met verschillende vormen en paden om uw presentaties tot leven te brengen.
## Veelgestelde vragen
### Vraag: Kan ik Aspose.Slides gebruiken met andere programmeertalen?
Aspose.Slides ondersteunt verschillende programmeertalen, waaronder Java en Python. Deze tutorial richt zich echter op C#.
### Vraag: Waar kan ik meer voorbeelden en documentatie vinden?
 Ontdek de[Aspose.Slides-documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide informatie en voorbeelden.
### Vraag: Is er een gratis proefversie beschikbaar?
 Ja, je kunt Aspose.Slides voor .NET proberen met de[gratis proefperiode](https://releases.aspose.com/).
### Vraag: Hoe kan ik ondersteuning krijgen of vragen stellen?
 Bezoek de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) voor steun en hulp van de gemeenschap.
### Vraag: Kan ik een tijdelijke licentie kopen?
 Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.aspose.com/temporary-license/).