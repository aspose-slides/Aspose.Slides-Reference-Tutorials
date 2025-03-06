---
title: Creëer eenvoudig een ellipsvorm met Aspose.Slides .NET
linktitle: Eenvoudige ellipsvorm creëren in presentatiedia's met Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint-verwerkings-API
description: Leer hoe u verbluffende ellipsvormen in presentatiedia's kunt maken met Aspose.Slides voor .NET. Eenvoudige stappen voor dynamisch ontwerp!
weight: 11
url: /nl/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Invoering
In de dynamische wereld van presentatieontwerp kan het integreren van vormen zoals ellipsen een vleugje creativiteit en professionaliteit toevoegen. Aspose.Slides voor .NET biedt een krachtige oplossing voor het programmatisch manipuleren van presentatiebestanden. Deze zelfstudie leidt u door het proces van het maken van een eenvoudige ellipsvorm in presentatiedia's met behulp van Aspose.Slides voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Aspose.Slides voor .NET: Zorg ervoor dat u de Aspose.Slides-bibliotheek voor .NET hebt geïnstalleerd. Je kunt het downloaden van de[releases pagina](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Zet een .NET-ontwikkelomgeving op uw computer op.
## Naamruimten importeren
Begin in uw .NET-project met het importeren van de benodigde naamruimten:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Deze naamruimten bieden de essentiële klassen en methoden die nodig zijn voor het werken met presentatiedia's en -vormen.
## Stap 1: Stel de presentatie in
Begin met het maken van een nieuwe presentatie en toegang tot de eerste dia. Voeg de volgende code toe om dit te bereiken:
```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Maak een directory aan als deze nog niet aanwezig is.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Presentatieklasse instantiëren
using (Presentation pres = new Presentation())
{
    // Haal de eerste dia
    ISlide sld = pres.Slides[0];
```
Deze code initialiseert een nieuwe presentatie en selecteert de eerste dia voor verdere manipulatie.
## Stap 2: Ellipsvorm toevoegen
 Laten we nu een ellipsvorm aan de dia toevoegen met behulp van de`AddAutoShape` methode:
```csharp
// Voeg een autovorm van het ellipstype toe
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Deze coderegel creëert een ellipsvorm op de coördinaten (50, 150) met een breedte van 150 eenheden en een hoogte van 50 eenheden.
## Stap 3: Sla de presentatie op
Sla ten slotte de gewijzigde presentatie op schijf op met een opgegeven bestandsnaam met behulp van de volgende code:
```csharp
// Schrijf het PPTX-bestand naar schijf
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Deze stap zorgt ervoor dat uw wijzigingen behouden blijven en dat u de resulterende presentatie kunt bekijken met de nieuw toegevoegde ellipsvorm.
## Conclusie
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## Veelgestelde vragen
### Kan ik de ellipsvorm verder aanpassen?
Ja, u kunt verschillende eigenschappen van de ellipsvorm wijzigen, zoals kleur, grootte en positie, om aan uw specifieke ontwerpvereisten te voldoen.
### Is Aspose.Slides compatibel met de nieuwste .NET-frameworks?
Ja, Aspose.Slides wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste .NET-frameworks te garanderen.
### Waar kan ik meer tutorials en voorbeelden vinden voor Aspose.Slides?
 Bezoek de[documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide handleidingen en voorbeelden.
### Hoe kan ik een tijdelijke licentie voor Aspose.Slides verkrijgen?
 Volg de[tijdelijke licentiekoppeling](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie aan te vragen voor testdoeleinden.
### Hulp nodig of specifieke vragen?
 Bezoek de[Ondersteuningsforum voor Aspose.Slides](https://forum.aspose.com/c/slides/11) om hulp te krijgen van de gemeenschap en experts.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
