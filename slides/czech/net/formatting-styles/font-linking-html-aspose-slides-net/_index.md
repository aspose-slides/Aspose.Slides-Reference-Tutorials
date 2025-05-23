---
"date": "2025-04-15"
"description": "Naučte se, jak zajistit konzistentní vykreslování písem při převodu prezentací do HTML pomocí Aspose.Slides pro .NET přímým vložením písem."
"title": "Jak propojit fonty v HTML pomocí Aspose.Slides pro .NET – podrobný návod"
"url": "/cs/net/formatting-styles/font-linking-html-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak propojit fonty v HTML pomocí Aspose.Slides pro .NET

## Zavedení

Převod prezentací do HTML při zachování konzistentního vykreslování písem napříč platformami může být náročný. **Aspose.Slides pro .NET** nabízí bezproblémové řešení tím, že umožňuje propojit všechna písma použitá v prezentaci přímo v HTML výstupu prostřednictvím vložených souborů písem.

V tomto tutoriálu se podíváme na to, jak implementovat propojení písem pomocí Aspose.Slides pro .NET a jak zajistit konzistenci designu napříč různými platformami. 

**Co se naučíte:**
- Nastavení prostředí s Aspose.Slides pro .NET
- Propojení písem při konverzi HTML
- Psaní vlastních kontrolerů pro vkládání fontů
- Praktické aplikace a aspekty výkonu

Pojďme se ponořit do kroků potřebných k dosažení tohoto cíle.

## Předpoklady

Než začneme, ujistěte se, že máte následující:

### Požadované knihovny a závislosti
- **Aspose.Slides pro .NET** knihovna: Klíčová komponenta pro naši implementaci.

### Požadavky na nastavení prostředí
- Vývojové prostředí s nainstalovaným .NET Frameworkem nebo .NET Core.

### Předpoklady znalostí
- Základní znalost programování v C#.
- Znalost HTML a CSS, zejména `@font-face` pravidlo.

## Nastavení Aspose.Slides pro .NET

Chcete-li ve svém projektu .NET použít Aspose.Slides, musíte si nainstalovat knihovnu. Zde je několik způsobů:

### Používání rozhraní .NET CLI
```bash
dotnet add package Aspose.Slides
```

### Používání konzole Správce balíčků
```powershell
Install-Package Aspose.Slides
```

### Prostřednictvím uživatelského rozhraní Správce balíčků NuGet
- Otevřete svůj projekt ve Visual Studiu.
- Přejděte do sekce „Správce balíčků NuGet“.
- Vyhledejte „Aspose.Slides“ a nainstalujte nejnovější verzi.

### Kroky získání licence
Bezplatnou zkušební licenci pro vyzkoušení všech funkcí bez omezení můžete získat následujícím způsobem:
1. **Bezplatná zkušební verze**Stáhnout dočasnou licenci [zde](https://releases.aspose.com/slides/net/).
2. **Dočasná licence**Požádejte o prodloužený přístup [zde](https://purchase.aspose.com/temporary-license/).
3. **Nákup**Pro plnou funkčnost si zakupte licenci [zde](https://purchase.aspose.com/buy).

### Základní inicializace a nastavení
```csharp
// Vytvořte instanci třídy License
easpose.slides.License license = new aspose.slides.License();

// Použijte licenci z cesty k souboru
license.SetLicense("Aspose.Slides.lic");
```

## Průvodce implementací

Nyní implementujme propojení fontů v HTML konverzi pomocí **Aspose.Slides pro .NET**.

### Přehled funkcí: Propojení písem při konverzi HTML
Tato funkce zajišťuje, že všechna písma použitá v prezentaci jsou přímo propojena ve výsledném souboru HTML vložením souborů písem. Tato metoda poskytuje robustní řešení pro zachování konzistence designu napříč různými prohlížeči a platformami.

#### Krok 1: Vytvořte vlastní ovladač
Vytvořte vlastní třídu kontroleru `LinkAllFontsHtmlController` který dědí z `EmbedAllFontsHtmlController`:
```csharp
using Aspose.Slides.Export;
using System.IO;

public class LinkAllFontsHtmlController : EmbedAllFontsHtmlController
{
    private readonly string m_basePath;

    public LinkAllFontsHtmlController(string[] fontNameExcludeList, string basePath)
        : base(fontNameExcludeList)
    {
        m_basePath = basePath; // Nastavte adresář, kam budou uloženy soubory písem
    }
}
```
#### Krok 2: Implementace metody psaní fontů
Ten/Ta/To `WriteFont` Metoda zapíše data fontu do souboru a vygeneruje odpovídající HTML kód pro vložení:
```csharp
public override void WriteFont(
    IHtmlGenerator generator,
    IFontData originalFont,
    IFontData substitutedFont,
    string fontStyle,
    string fontWeight,
    byte[] fontData)
{
    // Určete název písma, které se má použít, a pokud jsou k dispozici, upřednostněte náhradní písma.
    string fontName = substitutedFont == null ? originalFont.FontName : substitutedFont.FontName;

    // Vytvořte cestu k souboru písma .woff.
    string path = Path.Combine(m_basePath, $"{fontName}.woff`);
    
    // Zapište data písma do zadané cesty k souboru.
    File.WriteAllBytes(path, fontData);

    // Vygenerujte blok HTML stylu s vloženým písmem pomocí pravidla @font-face.
    generator.AddHtml("<style>");
    generator.AddHtml("@font-face { ");
    generator.AddHtml($"font-family: '{fontName}'; ");
    generator.AddHtml($"src: url('{path}');");
    generator.AddHtml(\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}