---
"date": "2025-04-15"
"description": "Lär dig hur du säkerställer konsekvent teckensnittsrendering när du konverterar presentationer till HTML med Aspose.Slides för .NET genom att bädda in teckensnitt direkt."
"title": "Hur man länkar teckensnitt i HTML med Aspose.Slides för .NET – en steg-för-steg-guide"
"url": "/sv/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man länkar teckensnitt i HTML med hjälp av Aspose.Slides för .NET

## Introduktion

Att konvertera presentationer till HTML samtidigt som man bibehåller en enhetlig teckensnittsrendering över olika plattformar kan vara utmanande. **Aspose.Slides för .NET** erbjuder en sömlös lösning genom att låta dig länka alla teckensnitt som används i en presentation direkt i HTML-utdata via inbäddade teckensnittsfiler.

I den här handledningen utforskar vi hur man implementerar teckensnittslänkning med Aspose.Slides för .NET och säkerställer designkonsekvens över olika plattformar. 

**Vad du kommer att lära dig:**
- Konfigurera din miljö med Aspose.Slides för .NET
- Länka teckensnitt i HTML-konvertering
- Skriva anpassade kontroller för inbäddning av teckensnitt
- Praktiska tillämpningar och prestandaöverväganden

Låt oss dyka in i de steg som krävs för att uppnå detta.

## Förkunskapskrav

Innan vi börjar, se till att du har följande:

### Obligatoriska bibliotek och beroenden
- **Aspose.Slides för .NET** bibliotek: Kärnkomponenten för vår implementering.

### Krav för miljöinstallation
- En utvecklingsmiljö med .NET Framework eller .NET Core installerat.

### Kunskapsförkunskaper
- Grundläggande förståelse för C#-programmering.
- Bekantskap med HTML och CSS, särskilt `@font-face` regel.

## Konfigurera Aspose.Slides för .NET

För att använda Aspose.Slides i ditt .NET-projekt måste du installera biblioteket. Här finns flera metoder:

### Använda .NET CLI
```bash
dotnet add package Aspose.Slides
```

### Använda pakethanterarkonsolen
```powershell
Install-Package Aspose.Slides
```

### Via NuGet Package Manager-gränssnittet
- Öppna ditt projekt i Visual Studio.
- Navigera till "NuGet-pakethanteraren".
- Sök efter "Aspose.Slides" och installera den senaste versionen.

### Steg för att förvärva licens
Du kan få en gratis provlicens för att testa alla funktioner utan begränsningar genom att följa dessa steg:
1. **Gratis provperiod**Ladda ner en tillfällig licens [här](https://releases.aspose.com/slides/net/).
2. **Tillfällig licens**Ansök om utökad åtkomst [här](https://purchase.aspose.com/temporary-license/).
3. **Köpa**För full funktionalitet, köp en licens [här](https://purchase.aspose.com/buy).

### Grundläggande initialisering och installation
```csharp
// Skapa en instans av License-klassen
easpose.slides.License license = new aspose.slides.License();

// Använd licensen från filsökvägen
license.SetLicense("Aspose.Slides.lic");
```

## Implementeringsguide

Nu ska vi implementera teckensnittslänkning i HTML-konvertering med hjälp av **Aspose.Slides för .NET**.

### Funktionsöversikt: Länka teckensnitt i HTML-konvertering
Den här funktionen säkerställer att alla teckensnitt som används i en presentation länkas direkt i den resulterande HTML-filen genom att teckensnittsfilerna bäddas in. Den här metoden ger en robust lösning för att upprätthålla designkonsekvens i olika webbläsare och plattformar.

#### Steg 1: Skapa den anpassade kontrollenheten
Skapa en anpassad kontrollklass `LinkAllFontsHtmlController` som ärver från `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Ange katalogen där teckensnittsfilerna ska lagras
    }
}
```
#### Steg 2: Implementera teckensnittsmetoden
De `WriteFont` Metoden skriver teckensnittsdata till en fil och genererar motsvarande HTML-kod för inbäddning:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Bestäm vilket teckensnitt som ska användas, och använd istället för teckensnitt om det finns tillgängliga.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Skapa en sökväg för .woff-teckensnittsfilen.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Skriv teckensnittsdata till den angivna filsökvägen.
    File.WriteAllBytes(path, fontData);

    // Generera HTML-stilblock som bäddar in teckensnittet med hjälp av @font-face-regeln.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}