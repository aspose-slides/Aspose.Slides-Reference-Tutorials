---
"date": "2025-04-16"
"description": "Leer hoe u taalkenmerken instelt voor tekst in vormen met Aspose.Slides voor .NET. Deze handleiding behandelt het toevoegen van automatische vormen, het instellen van taal-ID's en het opslaan van presentaties."
"title": "Taal instellen in PowerPoint-vormen met Aspose.Slides voor .NET"
"url": "/nl/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Taal instellen in PowerPoint-vormen met Aspose.Slides voor .NET

In de wereld van digitale presentaties kan het een uitdaging zijn om ervoor te zorgen dat uw content toegankelijk en correct opgemaakt is in verschillende talen. Met Aspose.Slides voor .NET kunt u moeiteloos taalkenmerken instellen voor tekst in vormen in PowerPoint-dia's. Deze functie is vooral handig bij het voorbereiden van meertalige documenten of het waarborgen van consistentie in wereldwijde communicatie.

**Wat je leert:**
- Automatische vormen toevoegen en er tekst in invoegen.
- De taal-ID voor tekstgedeelten instellen met Aspose.Slides.
- Presentaties opslaan met aangepaste configuraties.

Laten we eens kijken hoe u deze functie naadloos kunt implementeren.

## Vereisten

Voordat we beginnen, zorg ervoor dat u het volgende heeft:

- **Bibliotheken en afhankelijkheden**: Je moet Aspose.Slides voor .NET geïnstalleerd hebben. Deze bibliotheek is essentieel voor het bewerken van PowerPoint-presentaties in C#.
  
- **Omgevingsinstelling**: Een ontwikkelomgeving met .NET Core of .NET Framework is vereist.

- **Kennisvereisten**: Kennis van de basisprincipes van C#-programmeren en inzicht in de principes van objectgeoriënteerd programmeren zijn nuttig.

## Aspose.Slides instellen voor .NET

Om te beginnen moet u de Aspose.Slides-bibliotheek installeren. U kunt dit op een van de volgende manieren doen:

**.NET CLI**
```shell
dotnet add package Aspose.Slides
```

**Pakketbeheerder**
```powershell
Install-Package Aspose.Slides
```

**NuGet Package Manager-gebruikersinterface**
Zoek naar "Aspose.Slides" en installeer de nieuwste versie.

### Licentieverwerving

U kunt beginnen met een gratis proefperiode door een tijdelijke licentie te downloaden van [hier](https://purchase.aspose.com/temporary-license/)Voor doorlopend gebruik kunt u overwegen een licentie aan te schaffen via [deze link](https://purchase.aspose.com/buy).

Zodra uw configuratie gereed is, initialiseert u Aspose.Slides in uw project:

```csharp
using Aspose.Slides;
```

## Implementatiegids

Nu we alles hebben ingesteld, kunnen we de functie implementeren om de taal voor vormtekst in te stellen.

### Functieoverzicht: de taal van vormtekst instellen

Met deze functie kunt u de taal van de tekst in een PowerPoint-vorm opgeven. Door de taal-ID in te stellen, zorgt u ervoor dat spellingcontrole en andere taalspecifieke functies correct worden toegepast.

#### Stap 1: Presentatie initialiseren

Begin met het maken van een exemplaar van de `Presentation` klas.

```csharp
using (Presentation pres = new Presentation())
{
    // Uw code hier
}
```

Hiermee initialiseert u een nieuw PowerPoint-presentatieobject dat u kunt bewerken.

#### Stap 2: Automatische vorm en tekstkader toevoegen

Voeg een rechthoekige vorm toe aan uw dia en voeg er tekst in in:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Hier, `AddAutoShape` Voegt een rechthoek toe aan de eerste dia. De parameters bepalen de positie en grootte ervan.

#### Stap 3: Taal-ID instellen

Stel de taal in voor het tekstgedeelte in de vorm:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Hiermee wordt Engels (VK) toegewezen als taal voor de spellingcontrole.

#### Stap 4: Sla de presentatie op

Sla ten slotte uw presentatie op in het opgegeven pad:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}