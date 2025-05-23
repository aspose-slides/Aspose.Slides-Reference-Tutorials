---
"date": "2025-04-15"
"description": "Leer hoe u een consistente lettertypeweergave kunt garanderen bij het converteren van presentaties naar HTML met Aspose.Slides voor .NET door lettertypen rechtstreeks in te sluiten."
"title": "Hoe u lettertypen in HTML koppelt met Aspose.Slides voor .NET&#58; een stapsgewijze handleiding"
"url": "/nl/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Lettertypen koppelen in HTML met Aspose.Slides voor .NET

## Invoering

Het kan een uitdaging zijn om presentaties naar HTML te converteren en tegelijkertijd een consistente lettertypeweergave op alle platforms te behouden. **Aspose.Slides voor .NET** biedt een naadloze oplossing doordat u alle in een presentatie gebruikte lettertypen direct in de HTML-uitvoer kunt koppelen via ingesloten lettertypebestanden.

In deze tutorial leggen we uit hoe u lettertypekoppeling kunt implementeren met Aspose.Slides voor .NET en hoe u een consistent ontwerp kunt garanderen op verschillende platforms. 

**Wat je leert:**
- Uw omgeving instellen met Aspose.Slides voor .NET
- Lettertypen koppelen in HTML-conversie
- Aangepaste controllers schrijven voor lettertype-insluiting
- Praktische toepassingen en prestatieoverwegingen

Laten we eens kijken welke stappen er nodig zijn om dit te bereiken.

## Vereisten

Voordat we beginnen, zorg ervoor dat u het volgende heeft:

### Vereiste bibliotheken en afhankelijkheden
- **Aspose.Slides voor .NET** bibliotheek: Het kernonderdeel van onze implementatie.

### Vereisten voor omgevingsinstellingen
- Een ontwikkelomgeving met .NET Framework of .NET Core geïnstalleerd.

### Kennisvereisten
- Basiskennis van C#-programmering.
- Kennis van HTML en CSS, met name de `@font-face` regel.

## Aspose.Slides instellen voor .NET

Om Aspose.Slides in uw .NET-project te gebruiken, moet u de bibliotheek installeren. Hier zijn verschillende methoden:

### .NET CLI gebruiken
```bash
dotnet add package Aspose.Slides
```

### De Package Manager Console gebruiken
```powershell
Install-Package Aspose.Slides
```

### Via NuGet Package Manager UI
- Open uw project in Visual Studio.
- Navigeer naar de "NuGet Package Manager".
- Zoek naar "Aspose.Slides" en installeer de nieuwste versie.

### Stappen voor het verkrijgen van een licentie
U kunt een gratis proeflicentie verkrijgen om alle functies zonder beperkingen te testen door de volgende stappen te volgen:
1. **Gratis proefperiode**: Download een tijdelijke licentie [hier](https://releases.aspose.com/slides/net/).
2. **Tijdelijke licentie**: Vraag een uitgebreide toegang aan [hier](https://purchase.aspose.com/temporary-license/).
3. **Aankoop**: Voor volledige functionaliteit, koop een licentie [hier](https://purchase.aspose.com/buy).

### Basisinitialisatie en -installatie
```csharp
// Een instantie van de klasse License maken
easpose.slides.License license = new aspose.slides.License();

// Pas de licentie toe vanuit het bestandspad
license.SetLicense("Aspose.Slides.lic");
```

## Implementatiegids

Laten we nu lettertypekoppeling implementeren in HTML-conversie met behulp van **Aspose.Slides voor .NET**.

### Functieoverzicht: lettertypen koppelen in HTML-conversie
Deze functie zorgt ervoor dat alle lettertypen die in een presentatie worden gebruikt, direct in het resulterende HTML-bestand worden gekoppeld door de lettertypebestanden in te sluiten. Deze methode biedt een robuuste oplossing voor het behouden van ontwerpconsistentie in verschillende browsers en platforms.

#### Stap 1: De aangepaste controller maken
Een aangepaste controllerklasse maken `LinkAllFontsHtmlController` die erft van `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Stel de map in waar lettertypebestanden worden opgeslagen
    }
}
```
#### Stap 2: Implementeer de lettertypeschrijfmethode
De `WriteFont` methode schrijft de lettertypegegevens naar een bestand en genereert bijbehorende HTML-code voor insluiting:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Bepaal welke lettertypenaam u wilt gebruiken, en geef de voorkeur aan vervangende lettertypen als deze beschikbaar zijn.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Maak een bestandspad voor het .woff-lettertypebestand.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Schrijf de lettertypegegevens naar het opgegeven bestandspad.
    File.WriteAllBytes(path, fontData);

    // Genereer een HTML-stijlblok waarin het lettertype wordt ingesloten met de regel @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}