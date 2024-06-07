---
title: Vytvářejte úžasné načrtnuté tvary pomocí Aspose.Slides
linktitle: Vytváření načrtnutých tvarů v prezentačních snímcích pomocí Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se přidávat kreativní načrtnuté tvary do snímků prezentace pomocí Aspose.Slides for .NET. Vylepšete vizuální přitažlivost bez námahy!
type: docs
weight: 13
url: /cs/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---
## Úvod
Vítejte v našem podrobném průvodci vytvářením načrtnutých tvarů na snímcích prezentace pomocí Aspose.Slides for .NET. Pokud chcete svým prezentacím dodat nádech kreativity, načrtnuté tvary poskytují jedinečnou a ručně kreslenou estetiku. V tomto tutoriálu vás provedeme celým procesem a rozdělíme ho do jednoduchých kroků, abyste zajistili hladký průběh.
## Předpoklady
Než se pustíme do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.Slides for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides pro .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/slides/net/).
- Vývojové prostředí: Nastavte vývojové prostředí .NET s preferovaným IDE.
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu .NET. Tento krok zajistí, že budete mít přístup ke třídám a funkcím potřebným pro práci s Aspose.Slides.
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
## Krok 1: Nastavte projekt
Začněte vytvořením nového projektu .NET nebo otevřením stávajícího. Nezapomeňte do referencí projektu zahrnout Aspose.Slides.
## Krok 2: Inicializujte Aspose.Slides
Inicializujte Aspose.Slides přidáním následujícího fragmentu kódu. Tím nastavíte prezentaci a určíte výstupní cesty pro soubor prezentace a obrázek miniatury.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Pokračujte dalšími kroky...
}
```
## Krok 3: Přidejte načrtnutý tvar
Nyní přidáme na snímek načrtnutý tvar. V tomto příkladu přidáme obdélník s efektem skici od ruky.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Transformujte tvar na skicu stylu od ruky
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Krok 4: Vygenerujte miniaturu
Vygenerujte miniaturu snímku pro vizualizaci načrtnutého tvaru. Uložte miniaturu jako soubor PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Krok 5: Uložte prezentaci
Uložte soubor prezentace s načrtnutým tvarem.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
A je to! Úspěšně jste vytvořili prezentaci s načrtnutými tvary pomocí Aspose.Slides for .NET.
## Závěr
Přidáním načrtnutých tvarů do snímků prezentace můžete zvýšit vizuální přitažlivost a zaujmout publikum. S Aspose.Slides pro .NET se proces stává přímočarým a umožňuje vám bez námahy popustit uzdu vaší kreativitě.
## Nejčastější dotazy
### 1. Mohu přizpůsobit načrtnutý efekt?
Ano, Aspose.Slides for .NET poskytuje různé možnosti přizpůsobení pro načrtnuté efekty. Odkazovat na[dokumentace](https://reference.aspose.com/slides/net/) pro podrobné informace.
### 2. Je k dispozici bezplatná zkušební verze?
 Rozhodně! Můžete prozkoumat bezplatnou zkušební verzi Aspose.Slides pro .NET[tady](https://releases.aspose.com/).
### 3. Kde mohu získat podporu?
 V případě jakékoli pomoci nebo dotazů navštivte stránku[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Jak si mohu zakoupit Aspose.Slides pro .NET?
 Chcete-li zakoupit Aspose.Slides pro .NET, navštivte stránku[nákupní stránku](https://purchase.aspose.com/buy).
### 5. Nabízíte dočasné licence?
 Ano, dočasné licence jsou k dispozici[tady](https://purchase.aspose.com/temporary-license/).