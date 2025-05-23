---
"description": "Naučte se, jak přidávat kreativní načrtnuté tvary do snímků prezentace pomocí Aspose.Slides pro .NET. Vylepšete vizuální atraktivitu bez námahy!"
"linktitle": "Vytváření načrtnutých tvarů v prezentačních snímcích pomocí Aspose.Slides"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Vytvářejte úžasné načrtnuté tvary s Aspose.Slides"
"url": "/cs/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vytvářejte úžasné načrtnuté tvary s Aspose.Slides

## Zavedení
Vítejte v našem podrobném návodu na vytváření načrtnutých tvarů v prezentačních snímcích pomocí Aspose.Slides pro .NET. Pokud chcete do svých prezentací vnést trochu kreativity, načrtnuté tvary poskytují jedinečný a ručně kreslený estetický vzhled. V tomto tutoriálu vás provedeme celým procesem a rozdělíme ho do jednoduchých kroků, abychom zajistili hladký průběh.
## Předpoklady
Než se pustíme do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Aspose.Slides pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/slides/net/).
- Vývojové prostředí: Nastavte si vývojové prostředí .NET s vámi preferovaným IDE.
## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů do vašeho projektu .NET. Tento krok vám zajistí přístup ke třídám a funkcím potřebným pro práci s Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Krok 1: Nastavení projektu
Začněte vytvořením nového projektu .NET nebo otevřením existujícího. Nezapomeňte do referencí projektu zahrnout Aspose.Slides.
## Krok 2: Inicializace Aspose.Slides
Inicializujte Aspose.Slides přidáním následujícího úryvku kódu. Tím se nastaví prezentace a určí se výstupní cesty pro soubor prezentace a miniaturní obrázek.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Pokračujte k dalším krokům...
}
```
## Krok 3: Přidání načrtnutého tvaru
Nyní přidáme na snímek načrtnutý tvar. V tomto příkladu přidáme obdélník s efektem kresby od ruky.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transformace tvaru do náčrtu od ruky
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Krok 4: Vytvoření miniatury
Vytvořte miniaturu snímku pro vizualizaci načrtnutého tvaru. Uložte miniaturu jako soubor PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Krok 5: Uložení prezentace
Uložte soubor prezentace s načrtnutým tvarem.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Hotovo! Úspěšně jste vytvořili prezentaci s načrtnutými tvary pomocí Aspose.Slides pro .NET.
## Závěr
Přidání načrtnutých tvarů do snímků vaší prezentace může zvýšit vizuální atraktivitu a zaujmout publikum. S Aspose.Slides pro .NET se proces stává přímočarým a umožňuje vám bez námahy popustit uzdu vaší kreativitě.
## Často kladené otázky
### 1. Mohu si přizpůsobit efekt náčrtu?
Ano, Aspose.Slides pro .NET nabízí různé možnosti přizpůsobení pro načrtnuté efekty. Viz [dokumentace](https://reference.aspose.com/slides/net/) pro podrobné informace.
### 2. Je k dispozici bezplatná zkušební verze?
Jistě! Můžete si vyzkoušet bezplatnou zkušební verzi Aspose.Slides pro .NET. [zde](https://releases.aspose.com/).
### 3. Kde mohu získat podporu?
V případě potřeby pomoci nebo dotazů navštivte [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Jak si mohu zakoupit Aspose.Slides pro .NET?
Chcete-li zakoupit Aspose.Slides pro .NET, navštivte [stránka nákupu](https://purchase.aspose.com/buy).
### 5. Nabízíte dočasné licence?
Ano, dočasné licence jsou k dispozici [zde](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}