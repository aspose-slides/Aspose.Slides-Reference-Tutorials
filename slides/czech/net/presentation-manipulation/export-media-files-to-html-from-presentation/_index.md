---
"description": "Optimalizujte sdílení svých prezentací s Aspose.Slides pro .NET! V tomto podrobném návodu se naučte, jak exportovat mediální soubory z vaší prezentace do HTML."
"linktitle": "Export mediálních souborů z prezentace do HTML"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Export mediálních souborů z prezentace do HTML"
"url": "/cs/net/presentation-manipulation/export-media-files-to-html-from-presentation/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Export mediálních souborů z prezentace do HTML


tomto tutoriálu vás provedeme procesem exportu mediálních souborů do HTML z prezentace pomocí Aspose.Slides pro .NET. Aspose.Slides je výkonné API, které vám umožňuje programově pracovat s prezentacemi v PowerPointu. Po přečtení tohoto návodu budete schopni snadno převést své prezentace do formátu HTML. Tak pojďme na to!

## 1. Úvod

Prezentace v PowerPointu často obsahují multimediální prvky, jako jsou videa, a pro webovou kompatibilitu je může být nutné exportovat do formátu HTML. Aspose.Slides pro .NET nabízí pohodlný způsob, jak tohoto úkolu dosáhnout programově.

## 2. Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- Aspose.Slides pro .NET: Měli byste mít nainstalovanou knihovnu Aspose.Slides pro .NET. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/net/).

## 3. Načítání prezentace

Nejprve je třeba načíst prezentaci v PowerPointu, kterou chcete převést do formátu HTML. Také je třeba zadat výstupní adresář, kam bude soubor HTML uložen. Zde je kód pro načtení prezentace:

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

// Načítání prezentace
using (Presentation pres = new Presentation(dataDir + "example.pptx"))
{
    // Váš kód zde
}
```

## 4. Nastavení možností HTML

Nyní nastavíme možnosti HTML pro převod. Nakonfigurujeme HTML kontroler, HTML formátovač a formát obrázku snímku. Tento kód zajistí, aby váš HTML soubor obsahoval potřebné komponenty pro zobrazení multimediálních prvků.

```csharp
const string fileName = "video.html";
const string baseUri = "http://www.example.com/";

VideoPlayerHtmlController controller = new VideoPlayerHtmlController(path: path, fileName: fileName, baseUri: baseUri);

// Nastavení možností HTML
HtmlOptions htmlOptions = new HtmlOptions(controller);
SVGOptions svgOptions = new SVGOptions(controller);

htmlOptions.HtmlFormatter = HtmlFormatter.CreateCustomFormatter(controller);
htmlOptions.SlideImageFormat = SlideImageFormat.Svg(svgOptions);
```

## 5. Uložení HTML souboru

Po nakonfigurování možností HTML můžete nyní uložit soubor HTML. `Save` Metoda objektu prezentace vygeneruje HTML soubor s vloženými multimediálními prvky.

```csharp
// Uložení souboru
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Závěr

Gratulujeme! Úspěšně jste exportovali mediální soubory z prezentace v PowerPointu do formátu HTML pomocí nástroje Aspose.Slides pro .NET. To vám umožní snadno sdílet vaše prezentace online a zajistit správné zobrazení multimediálních prvků.

## 7. Často kladené otázky

### Q1: Je Aspose.Slides pro .NET bezplatná knihovna?
A1: Aspose.Slides pro .NET je komerční knihovna, ale bezplatnou zkušební verzi si můžete stáhnout z [zde](https://releases.aspose.com/) vyzkoušet si to.

### Q2: Mohu si HTML výstup dále přizpůsobit?
A2: Ano, výstup HTML můžete přizpůsobit úpravou možností HTML v kódu.

### Q3: Podporuje Aspose.Slides pro .NET i jiné exportní formáty?
A3: Ano, Aspose.Slides pro .NET podporuje různé exportní formáty, včetně PDF, obrazových formátů a dalších.

### Q4: Kde mohu získat podporu pro Aspose.Slides pro .NET?
A4: Podporu a dotazy můžete najít na fórech Aspose. [zde](https://forum.aspose.com/).

### Q5: Jak si mohu zakoupit licenci pro Aspose.Slides pro .NET?
A5: Licenci si můžete zakoupit od [tento odkaz](https://purchase.aspose.com/buy).

Nyní, když jste dokončili tento tutoriál, máte dovednosti exportovat mediální soubory do HTML z prezentací v PowerPointu pomocí Aspose.Slides pro .NET. Užijte si sdílení svých multimediálních prezentací online!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}