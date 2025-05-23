---
"date": "2025-04-15"
"description": "Leer hoe je fotolijsten met relatieve schaal toevoegt met Aspose.Slides voor .NET. Deze handleiding behandelt de installatie, het verwerken van afbeeldingen en de schaaltechnieken."
"title": "Hoe u fotolijsten met relatieve schaal toevoegt in Aspose.Slides .NET&#58; een stapsgewijze handleiding"
"url": "/nl/net/images-multimedia/aspose-slides-net-picture-frame-relative-scaling/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe u fotolijsten met relatieve schaal toevoegt in Aspose.Slides .NET: een stapsgewijze handleiding

## Invoering

Het maken van visueel aantrekkelijke PowerPoint-presentaties is cruciaal voor effectieve communicatie, of u nu een zakelijke presentatie geeft of een educatieve lezing geeft. Het aanpassen van afbeeldingen aan het ontwerp van uw dia's kan vervelend en tijdrovend zijn. Met Aspose.Slides voor .NET kunt u eenvoudig afbeeldingskaders met relatieve schaal toevoegen, zodat uw afbeeldingen hun beeldverhouding behouden en perfect op uw dia's passen.

In deze tutorial laten we zien hoe je Aspose.Slides voor .NET kunt gebruiken om een afbeelding als kader toe te voegen en de afmetingen proportioneel aan te passen. Je leert de basisprincipes van het instellen van Aspose.Slides in je ontwikkelomgeving en het implementeren van relatieve schaalfuncties in je presentaties. Uiteindelijk heb je een presentatie die er niet alleen professioneel uitziet, maar zich ook dynamisch aanpast aan verschillende weergave-instellingen.

**Wat je leert:**
- Aspose.Slides instellen voor .NET
- Een afbeelding als fotolijst toevoegen aan een PowerPoint-dia
- Relatieve schaalbaarheid implementeren voor fotolijsten
- Aanbevolen werkwijzen en tips voor probleemoplossing

Laten we eens kijken naar de vereisten voordat we aan de slag gaan met Aspose.Slides.

## Vereisten

Zorg ervoor dat u het volgende geregeld hebt voordat u begint:

### Vereiste bibliotheken en afhankelijkheden

Om deze functie te implementeren, moet u Aspose.Slides voor .NET geïnstalleerd hebben. Deze bibliotheek maakt uitgebreide bewerking van PowerPoint-presentaties met C# mogelijk.

### Vereisten voor omgevingsinstellingen

Zorg ervoor dat uw ontwikkelomgeving is ingesteld met:
- Een compatibele versie van .NET (bij voorkeur .NET Core of .NET Framework 4.5 en hoger)
- Een code-editor zoals Visual Studio, Visual Studio Code of een andere IDE die .NET-ontwikkeling ondersteunt
- Toegang tot een bestandsmap waar u uw PowerPoint-bestanden kunt opslaan

### Kennisvereisten

Kennis van C#-programmering is een pré, maar niet verplicht. Basiskennis van het werken met afbeeldingen en begrip van de principes van objectgeoriënteerd programmeren zijn ook nuttig.

## Aspose.Slides instellen voor .NET

Om Aspose.Slides voor .NET te gaan gebruiken, volgt u de onderstaande installatiestappen:

**.NET CLI**
```bash
dotnet add package Aspose.Slides
```

**Pakketbeheerder**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager-gebruikersinterface**
Open uw project in Visual Studio, ga naar NuGet Package Manager en zoek naar 'Aspose.Slides' om de nieuwste versie te installeren.

### Stappen voor het verkrijgen van een licentie

- **Gratis proefperiode**: U kunt beginnen met een gratis proefperiode waarmee u de functies van Aspose.Slides kunt uitproberen.
- **Tijdelijke licentie**:Verkrijg een tijdelijke licentie voor uitgebreide evaluatie zonder beperkingen.
- **Aankoop**: Voor volledige toegang en ondersteuning kunt u overwegen een licentie aan te schaffen bij Aspose.

#### Basisinitialisatie en -installatie

Nadat u Aspose.Slides hebt geïnstalleerd, initialiseert u het in uw project door de nodige using-richtlijnen toe te voegen:

```csharp
using Aspose.Slides;
```

## Implementatiegids

### Een fotolijst toevoegen met relatieve schaal

In dit gedeelte leggen we u uit hoe u een afbeelding als fotolijst toevoegt en de relatieve schaal ervan instelt.

#### Uw afbeelding laden

Begin met het laden van de gewenste afbeelding in de afbeeldingsverzameling van de presentatie:

```csharp
string dataDir = @"YOUR_DOCUMENT_DIRECTORY";
IImage img = Images.FromFile(dataDir + "aspose-logo.jpg");
IPPImage image = presentation.Images.AddImage(img);
```

Met dit codefragment wordt een afbeelding uit een opgegeven map geladen en aan de presentatie toegevoegd.

#### Het fotolijstje toevoegen

Voeg vervolgens een fotokader van het type rechthoek toe aan uw dia:

```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```

Hier, `ShapeType.Rectangle` specificeert de vorm en de parameters bepalen de positie en de oorspronkelijke grootte.

#### Relatieve schaal instellen

Pas de afmetingen proportioneel aan door de relatieve schaalhoogte en -breedte in te stellen:

```csharp
pf.RelativeScaleHeight = 0.8f; // Schaalbaar tot 80% van de oorspronkelijke hoogte
pf.RelativeScaleWidth = 1.35f; // Schaal naar 135% van de oorspronkelijke breedte
```

Zo weet u zeker dat uw afbeelding correct wordt geschaald en de beeldverhouding consistent blijft.

#### Uw presentatie opslaan

Sla ten slotte de presentatie op met het aangepaste afbeeldingskader:

```csharp\presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}