---
"date": "2025-04-16"
"description": "Leer hoe u op efficiënte wijze inhoud, verticale tekst, grafieken en tabelaanduidingen toevoegt aan uw PowerPoint-dia's met Aspose.Slides voor .NET."
"title": "Tijdelijke aanduidingen toevoegen in .NET-dia's met Aspose.Slides"
"url": "/nl/net/shapes-text-frames/add-placeholders-in-dotnet-slides-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tijdelijke aanduidingen toevoegen in .NET-dia's met Aspose.Slides

## Invoering

Bent u op zoek naar een efficiënte manier om automatisch tijdelijke aanduidingen zoals inhoud, verticale tekst, grafieken en tabellen aan uw presentaties toe te voegen? Met Aspose.Slides voor .NET verloopt dit proces naadloos. Deze tutorial begeleidt u bij het gebruik van Aspose.Slides om het toevoegen van tijdelijke aanduidingen in PowerPoint-dia's in een .NET-omgeving te stroomlijnen.

In deze uitgebreide gids bespreken we:
- Aspose.Slides instellen voor .NET
- Stapsgewijze instructies voor het toevoegen van verschillende tijdelijke aanduidingen
- Toepassingen van deze functies in de echte wereld
- Prestatieoverwegingen voor optimaal gebruik

## Vereisten

### Vereiste bibliotheken en versies
Om deze tutorial te kunnen volgen, moet u het volgende doen:
- Aspose.Slides voor .NET-bibliotheekversie 22.x of hoger.
- Een compatibele .NET-omgeving (bijvoorbeeld .NET Core 3.1 of hoger).

### Vereisten voor omgevingsinstellingen
Zorg ervoor dat uw ontwikkelomgeving is ingesteld met Visual Studio of een andere IDE die .NET-projecten ondersteunt.

### Kennisvereisten
Basiskennis van C# en vertrouwdheid met .NET-programmeerconcepten zijn nuttig, maar niet noodzakelijk. We behandelen alle basisbeginselen tijdens de cursus.

## Aspose.Slides instellen voor .NET
Om Aspose.Slides in uw project te kunnen gebruiken, moet u het installeren. Zo werkt het:

**Met behulp van .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Pakketbeheerconsole gebruiken:**
```powershell
Install-Package Aspose.Slides
```

**Gebruikersinterface van NuGet Package Manager:**
Zoek naar "Aspose.Slides" en installeer de nieuwste versie.

### Licentieverwerving
Om Aspose.Slides uit te proberen, kunt u kiezen voor een gratis proefperiode of een tijdelijke licentie aanschaffen. Voor productiegebruik kunt u overwegen een volledige licentie aan te schaffen. Bezoek [Aspose's aankooppagina](https://purchase.aspose.com/buy) voor meer informatie over licentieopties.

#### Basisinitialisatie
Initialiseer uw project door een exemplaar van de `Presentation` klas:
```csharp
using Aspose.Slides;
// ...
var presentation = new Presentation();
```

## Implementatiegids

### Inhoudsplaatsaanduiding toevoegen
Door een content placeholder toe te voegen, kun je tekst, afbeeldingen en andere media in dia's invoegen. Hier lees je hoe je dit doet met Aspose.Slides voor .NET.

#### Overzicht
In deze sectie wordt u door het proces geleid voor het toevoegen van een inhoudsplaceholder aan een lege dia-indeling met behulp van Aspose.Slides voor .NET.

#### Implementatiestappen
**1. Stel uw project in**
Begin met het maken van een nieuw C#-project en installeer de Aspose.Slides-bibliotheek zoals eerder vermeld.

**2. Initialiseer presentatie**
Maak een exemplaar van `Presentation` werken met dia's:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "content_placeholder.pptx");

using (var pres = new Presentation())
{
    // De code wordt hier toegevoegd.
}
```
**3. Toegang tot lay-outdia**
Haal de lege lay-outdia op waar u uw tijdelijke aanduiding gaat toevoegen:
```csharp
// De lege lay-outdia verkrijgen.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
Met deze stap krijgt u toegang tot een vooraf gedefinieerde, lege lay-out, die ideaal is voor aangepaste ontwerpen.

**4. Inhoudsplaatsaanduiding toevoegen**
Gebruik de `PlaceholderManager` om een inhoudsplaatsaanduiding op de opgegeven coördinaten en grootte in te voegen:
```csharp
// De tijdelijke aanduidingsbeheerder van de lay-outdia ophalen.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Een inhoudsplaatsaanduiding toevoegen op positie (10, 10) met een grootte van (300x200).
placeholderManager.AddContentPlaceholder(10, 10, 300, 200);
```
De parameters definiëren de positie `(x, y)` en afmetingen `(width x height)` van de tijdelijke aanduiding.

**5. Presentatie opslaan**
Sla ten slotte uw presentatiebestand op:
```csharp
// De presentatie opslaan met de toegevoegde inhoudsplaatsaanduiding.
pres.Save(outFilePath, SaveFormat.Pptx);
```
Hiermee wordt de gewijzigde lay-out opgeslagen in een opgegeven map.

### Verticale tekstplaatsaanduiding toevoegen
Verticale tekstplaatsaanduidingen zijn ideaal voor zijbalken of unieke ontwerpelementen waarbij de tekstrichting moet worden gewijzigd.

#### Overzicht
In dit gedeelte leert u hoe u een verticale tekstplaceholder toevoegt om de uitstraling van uw dia te verbeteren.

#### Implementatiestappen
**1. Initialiseer presentatie**
Maak een nieuw exemplaar van `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "vertical_text_placeholder.pptx");

using (var pres = new Presentation())
{
    // De code wordt hier toegevoegd.
}
```
**2. Toegang tot lay-outdia**
Haal de lege lay-outdia op:
```csharp
// De lege lay-outdia verkrijgen.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Verticale tekstplaatsaanduiding toevoegen**
Voeg een verticale tekstplaatsaanduiding toe met behulp van `PlaceholderManager`:
```csharp
// De tijdelijke aanduidingsbeheerder van de lay-outdia ophalen.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Een verticale tekstplaatsaanduiding toevoegen op positie (350, 10) met een grootte van (200x300).
placeholderManager.AddVerticalTextPlaceholder(350, 10, 200, 300);
```
**4. Presentatie opslaan**
Sla uw presentatie op:
```csharp
// De presentatie opslaan met toegevoegde verticale tekstplaceholder.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### Grafiek-placeholder toevoegen
Grafieken zijn cruciaal voor de weergave van gegevens in presentaties. Hier leest u hoe u een tijdelijke aanduiding voor een grafiek toevoegt met Aspose.Slides.

#### Overzicht
In deze sectie wordt uitgelegd hoe u een grafiektijdaanduiding in uw PowerPoint-dia's kunt integreren met behulp van Aspose.Slides.

#### Implementatiestappen
**1. Initialiseer presentatie**
Maak een exemplaar van `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "chart_placeholder.pptx");

using (var pres = new Presentation())
{
    // De code wordt hier toegevoegd.
}
```
**2. Toegang tot lay-outdia**
Haal de lege lay-outdia op:
```csharp
// De lege lay-outdia verkrijgen.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Grafiek-tijdaanduiding toevoegen**
Gebruik `PlaceholderManager` om een grafiek-placeholder toe te voegen:
```csharp
// De tijdelijke aanduidingsbeheerder van de lay-outdia ophalen.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Een grafiekplaatsaanduiding toevoegen op positie (10, 350) met een formaat van (300x300).
placeholderManager.AddChartPlaceholder(10, 350, 300, 300);
```
**4. Presentatie opslaan**
Sla uw presentatie op:
```csharp
// De presentatie opslaan met de toegevoegde grafiekplaceholder.
pres.Save(outFilePath, SaveFormat.Pptx);
```

### Tabelplaatsaanduiding toevoegen
Met tabellen kunt u gegevens op een effectieve manier ordenen. Ze worden in presentaties vaak gebruikt om de gegevens duidelijker te maken.

#### Overzicht
Leer hoe u een tabelplaatsaanduiding kunt toevoegen om informatie in uw dia's netjes te structureren met behulp van Aspose.Slides.

#### Implementatiestappen
**1. Initialiseer presentatie**
Maak een exemplaar van `Presentation`:
```csharp
using System.IO;
using Aspose.Slides;

string outFilePath = Path.Combine("YOUR_OUTPUT_DIRECTORY", "table_placeholder.pptx");

using (var pres = new Presentation())
{
    // De code wordt hier toegevoegd.
}
```
**2. Toegang tot lay-outdia**
Haal de lege lay-outdia op:
```csharp
// De lege lay-outdia verkrijgen.
ILayoutSlide layout = pres.LayoutSlides.GetByType(SlideLayoutType.Blank);
```
**3. Tabelplaatsaanduiding toevoegen**
Gebruik `PlaceholderManager` om een tabelplaatsaanduiding toe te voegen:
```csharp
// De tijdelijke aanduidingsbeheerder van de lay-outdia ophalen.
ILayoutPlaceholderManager placeholderManager = layout.PlaceholderManager;

// Een tabelplaatsaanduiding toevoegen op positie (350, 350) met een grootte van (300x200).
placeholderManager.AddTablePlaceholder(350, 350, 300, 200);
```
**4. Presentatie opslaan**
Sla uw presentatie op:
```csharp
// De presentatie opslaan met toegevoegde tabelplaceholder.
pres.Save(outFilePath, SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}