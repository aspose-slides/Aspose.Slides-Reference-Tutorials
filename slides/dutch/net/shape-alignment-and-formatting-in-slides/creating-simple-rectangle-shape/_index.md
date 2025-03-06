---
title: Rechthoekige vormen maken met Aspose.Slides voor .NET
linktitle: Eenvoudige rechthoekige vorm maken in presentatiedia's met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Ontdek de wereld van dynamische PowerPoint-presentaties met Aspose.Slides voor .NET. Leer hoe u aantrekkelijke rechthoekige vormen in dia's kunt maken met deze stapsgewijze handleiding.
weight: 12
url: /nl/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rechthoekige vormen maken met Aspose.Slides voor .NET

## Invoering
Als u uw .NET-toepassingen wilt verbeteren met dynamische en visueel aantrekkelijke PowerPoint-presentaties, is Aspose.Slides voor .NET uw beste oplossing. In deze zelfstudie begeleiden we u bij het maken van een eenvoudige rechthoekige vorm in presentatiedia's met behulp van Aspose.Slides voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Visual Studio: Zorg ervoor dat Visual Studio op uw ontwikkelmachine is geïnstalleerd.
-  Aspose.Slides voor .NET: Download en installeer de Aspose.Slides voor .NET-bibliotheek van[hier](https://releases.aspose.com/slides/net/).
- Basiskennis C#: Bekendheid met de programmeertaal C# is essentieel.
## Naamruimten importeren
Begin in uw C#-project met het importeren van de benodigde naamruimten om toegang te krijgen tot de Aspose.Slides-functionaliteiten:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Stap 1: Stel het project in
Begin met het maken van een nieuw C#-project in Visual Studio. Zorg ervoor dat Aspose.Slides voor .NET correct wordt verwezen in uw project.
## Stap 2: Initialiseer het presentatieobject
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Uw code voor de volgende stappen komt hier terecht.
}
```
## Stap 3: Verkrijg de eerste dia
```csharp
ISlide sld = pres.Slides[0];
```
## Stap 4: Voeg Rechthoek AutoShape toe
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
Gefeliciteerd! U hebt met succes een eenvoudige rechthoekige vorm in een presentatiedia gemaakt met Aspose.Slides voor .NET. Dit is nog maar het begin – Aspose.Slides biedt een breed scala aan functies om uw presentaties verder aan te passen en te verbeteren.
## Veel Gestelde Vragen
### Kan ik Aspose.Slides voor .NET gebruiken in zowel Windows- als Linux-omgevingen?
Ja, Aspose.Slides voor .NET is platformonafhankelijk en kan in zowel Windows- als Linux-omgevingen worden gebruikt.
### Is er een gratis proefversie beschikbaar voor Aspose.Slides voor .NET?
 Ja, u kunt een gratis proefperiode krijgen[hier](https://releases.aspose.com/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor .NET?
 Bezoek de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) voor gemeenschapssteun.
### Kan ik een tijdelijke licentie kopen voor Aspose.Slides voor .NET?
 Ja, u kunt een tijdelijke licentie aanschaffen[hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik de documentatie voor Aspose.Slides voor .NET vinden?
 Raadpleeg de documentatie[hier](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
