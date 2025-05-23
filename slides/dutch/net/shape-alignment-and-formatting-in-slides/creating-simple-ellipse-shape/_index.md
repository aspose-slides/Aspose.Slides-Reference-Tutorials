---
"description": "Leer hoe je verbluffende ellipsvormen maakt in presentatieslides met Aspose.Slides voor .NET. Eenvoudige stappen voor dynamisch ontwerp!"
"linktitle": "Eenvoudige ellipsvormen maken in presentatieslides met Aspose.Slides"
"second_title": "Aspose.Slides .NET PowerPoint-verwerkings-API"
"title": "Creëer eenvoudig ellipsvormen met Aspose.Slides .NET"
"url": "/nl/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Creëer eenvoudig ellipsvormen met Aspose.Slides .NET

## Invoering
In de dynamische wereld van presentatieontwerp kan het toevoegen van vormen zoals ellipsen een vleugje creativiteit en professionaliteit toevoegen. Aspose.Slides voor .NET biedt een krachtige oplossing voor het programmatisch bewerken van presentatiebestanden. Deze tutorial begeleidt u door het proces van het maken van een eenvoudige ellipsvorm in presentatieslides met Aspose.Slides voor .NET.
## Vereisten
Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Aspose.Slides voor .NET: Zorg ervoor dat u de Aspose.Slides-bibliotheek voor .NET hebt geïnstalleerd. U kunt deze downloaden van de [releases pagina](https://releases.aspose.com/slides/net/).
- Ontwikkelomgeving: Stel een .NET-ontwikkelomgeving in op uw computer.
## Naamruimten importeren
Begin in uw .NET-project met het importeren van de benodigde naamruimten:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Deze naamruimten bieden de essentiële klassen en methoden die nodig zijn voor het werken met presentatieslides en vormen.
## Stap 1: De presentatie instellen
Begin met het maken van een nieuwe presentatie en open de eerste dia. Voeg hiervoor de volgende code toe:
```csharp
// Het pad naar de documentenmap.
string dataDir = "Your Document Directory";
// Maak een map aan als deze nog niet bestaat.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Instantieer presentatieklasse
using (Presentation pres = new Presentation())
{
    // Ontvang de eerste dia
    ISlide sld = pres.Slides[0];
```
Deze code initialiseert een nieuwe presentatie en selecteert de eerste dia voor verdere bewerking.
## Stap 2: Ellipsvorm toevoegen
Laten we nu een ellipsvorm aan de dia toevoegen met behulp van de `AddAutoShape` methode:
```csharp
// Autovorm van ellipstype toevoegen
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Deze regel code maakt een ellipsvorm op de coördinaten (50, 150) met een breedte van 150 eenheden en een hoogte van 50 eenheden.
## Stap 3: Sla de presentatie op
Sla ten slotte de gewijzigde presentatie op schijf op met een opgegeven bestandsnaam. Gebruik hiervoor de volgende code:
```csharp
// Schrijf het PPTX-bestand naar schijf
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Met deze stap zorgt u ervoor dat uw wijzigingen worden behouden en dat u de uiteindelijke presentatie kunt bekijken met de nieuw toegevoegde ellipsvorm.
## Conclusie
Gefeliciteerd! Je hebt met succes een eenvoudige ellipsvorm gemaakt in een presentatiedia met Aspose.Slides voor .NET. Deze tutorial biedt een basiskennis van het werken met vormen, het opzetten van presentaties en het opslaan van de gewijzigde bestanden.
---
## Veelgestelde vragen
### Kan ik de vorm van de ellips verder aanpassen?
Ja, u kunt verschillende eigenschappen van de ellipsvorm aanpassen, zoals kleur, grootte en positie, zodat deze voldoen aan uw specifieke ontwerpvereisten.
### Is Aspose.Slides compatibel met de nieuwste .NET-frameworks?
Ja, Aspose.Slides wordt regelmatig bijgewerkt om compatibiliteit met de nieuwste .NET Frameworks te garanderen.
### Waar kan ik meer tutorials en voorbeelden voor Aspose.Slides vinden?
Bezoek de [documentatie](https://reference.aspose.com/slides/net/) voor uitgebreide handleidingen en voorbeelden.
### Hoe kan ik een tijdelijke licentie voor Aspose.Slides verkrijgen?
Volg de [tijdelijke licentielink](https://purchase.aspose.com/temporary-license/) om een tijdelijke licentie voor testdoeleinden aan te vragen.
### Heeft u hulp nodig of specifieke vragen?
Bezoek de [Aspose.Slides ondersteuningsforum](https://forum.aspose.com/c/slides/11) om hulp te krijgen van de community en experts.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}