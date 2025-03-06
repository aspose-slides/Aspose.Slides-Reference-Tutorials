---
title: Exportujte mediální soubory do HTML z prezentace
linktitle: Exportujte mediální soubory do HTML z prezentace
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Optimalizujte sdílení prezentací pomocí Aspose.Slides pro .NET! V tomto podrobném průvodci se dozvíte, jak exportovat mediální soubory do HTML z vaší prezentace.
weight: 15
url: /cs/net/presentation-manipulation/export-media-files-to-html-from-presentation/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


V tomto tutoriálu vás provedeme procesem exportu mediálních souborů do HTML z prezentace pomocí Aspose.Slides for .NET. Aspose.Slides je výkonné API, které umožňuje programově pracovat s prezentacemi PowerPoint. Na konci této příručky budete moci snadno převádět své prezentace do formátu HTML. Takže, pojďme začít!

## 1. Úvod

Prezentace PowerPoint často obsahují multimediální prvky, jako jsou videa, a možná budete muset tyto prezentace exportovat do formátu HTML, aby byly kompatibilní s webem. Aspose.Slides for .NET poskytuje pohodlný způsob, jak tento úkol provést programově.

## 2. Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Slides for .NET: Měli byste mít nainstalovanou knihovnu Aspose.Slides for .NET. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).

## 3. Načtení prezentace

Chcete-li začít, musíte načíst prezentaci PowerPoint, kterou chcete převést do HTML. Budete také muset zadat výstupní adresář, kam bude soubor HTML uložen. Zde je kód pro načtení prezentace:

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

Nyní nastavíme možnosti HTML pro převod. Nakonfigurujeme řadič HTML, formátovač HTML a formát obrázků snímků. Tento kód zajistí, že váš HTML soubor bude obsahovat potřebné komponenty pro zobrazení multimediálních prvků.

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

## 5. Uložení souboru HTML

 S nakonfigurovanými možnostmi HTML můžete nyní uložit soubor HTML. The`Save` metoda objektu prezentace vygeneruje soubor HTML s vloženými multimediálními prvky.

```csharp
// Ukládání souboru
pres.Save(outPath + fileName, SaveFormat.Html, htmlOptions);
```

## 6. Závěr

Gratulujeme! Úspěšně jste exportovali mediální soubory do HTML z prezentace PowerPoint pomocí Aspose.Slides for .NET. To vám umožní snadno sdílet vaše prezentace online a zajistit správné zobrazení multimediálních prvků.

## 7. Nejčastější dotazy

### Q1: Je Aspose.Slides for .NET bezplatná knihovna?
 A1: Aspose.Slides for .NET je komerční knihovna, ale můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/) vyzkoušet to.

### Q2: Mohu dále upravit výstup HTML?
A2: Ano, můžete upravit výstup HTML úpravou možností HTML v kódu.

### Q3: Podporuje Aspose.Slides pro .NET další exportní formáty?
Odpověď 3: Ano, Aspose.Slides for .NET podporuje různé exportní formáty, včetně PDF, obrázkových formátů a dalších.

### Q4: Kde mohu získat podporu pro Aspose.Slides pro .NET?
 Odpověď 4: Podporu a dotazy můžete najít na fórech Aspose[tady](https://forum.aspose.com/).

### Q5: Jak mohu zakoupit licenci pro Aspose.Slides pro .NET?
 A5: Můžete si zakoupit licenci od[tento odkaz](https://purchase.aspose.com/buy).

Nyní, když jste dokončili tento tutoriál, máte dovednosti exportovat mediální soubory do HTML z prezentací PowerPoint pomocí Aspose.Slides for .NET. Užijte si sdílení multimediálních prezentací online!
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
