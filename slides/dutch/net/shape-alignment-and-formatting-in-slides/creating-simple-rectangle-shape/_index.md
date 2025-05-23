---
"description": "Ontdek de wereld van dynamische PowerPoint-presentaties met Aspose.Slides voor .NET. Leer hoe je aantrekkelijke rechthoekige vormen in dia's maakt met deze stapsgewijze handleiding."
"linktitle": "Eenvoudige rechthoekige vormen maken in presentatieslides met Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Rechthoekige vormen maken met Aspose.Slides voor .NET"
"url": "/nl/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Rechthoekige vormen maken met Aspose.Slides voor .NET

## Invoering
Als u uw .NET-applicaties wilt verbeteren met dynamische en visueel aantrekkelijke PowerPoint-presentaties, is Aspose.Slides voor .NET dé oplossing. In deze tutorial begeleiden we u bij het maken van een eenvoudige rechthoekige vorm in presentatieslides met Aspose.Slides voor .NET.
## Vereisten
Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Visual Studio: Zorg ervoor dat Visual Studio op uw ontwikkelcomputer is geïnstalleerd.
- Aspose.Slides voor .NET: Download en installeer de Aspose.Slides voor .NET-bibliotheek van [hier](https://releases.aspose.com/slides/net/).
- Basiskennis van C#: Kennis van de programmeertaal C# is essentieel.
## Naamruimten importeren
Begin in uw C#-project met het importeren van de benodigde naamruimten om toegang te krijgen tot de Aspose.Slides-functionaliteiten:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Stap 1: Het project instellen
Begin met het maken van een nieuw C#-project in Visual Studio. Zorg ervoor dat Aspose.Slides voor .NET correct wordt gerefereerd in uw project.
## Stap 2: Presentatieobject initialiseren
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Hier komt uw code voor de volgende stappen.
}
```
## Stap 3: Ontvang de eerste dia
```csharp
ISlide sld = pres.Slides[0];
```
## Stap 4: Rechthoek AutoVorm toevoegen
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Deze code voegt een rechthoekige vorm toe op de coördinaten (50, 150) met een breedte van 150 en een hoogte van 50.
## Stap 5: Sla de presentatie op
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Met deze stap wordt de presentatie met de toegevoegde rechthoekige vorm opgeslagen in de opgegeven map.
## Conclusie
Gefeliciteerd! Je hebt met succes een eenvoudige rechthoekige vorm in een presentatiedia gemaakt met Aspose.Slides voor .NET. Dit is nog maar het begin – Aspose.Slides biedt een breed scala aan functies om je presentaties verder te personaliseren en te verbeteren.
## Veelgestelde vragen
### Kan ik Aspose.Slides voor .NET in zowel Windows- als Linux-omgevingen gebruiken?
Ja, Aspose.Slides voor .NET is platformonafhankelijk en kan worden gebruikt in zowel Windows- als Linux-omgevingen.
### Is er een gratis proefversie beschikbaar voor Aspose.Slides voor .NET?
Ja, u kunt een gratis proefperiode krijgen [hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
Bezoek de [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) voor steun van de gemeenschap.
### Kan ik een tijdelijke licentie voor Aspose.Slides voor .NET kopen?
Ja, u kunt een tijdelijke licentie aanschaffen [hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik de documentatie voor Aspose.Slides voor .NET vinden?
Raadpleeg de documentatie [hier](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}