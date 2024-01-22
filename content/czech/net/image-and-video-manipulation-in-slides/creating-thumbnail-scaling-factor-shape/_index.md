---
title: Vytvoření miniatury s faktorem měřítka pro tvar v Aspose.Slides
linktitle: Vytvoření miniatury s faktorem měřítka pro tvar v Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se vytvářet PowerPointové miniatury se specifickými hranicemi pomocí Aspose.Slides for .NET. Postupujte podle našeho podrobného průvodce pro bezproblémovou integraci.
type: docs
weight: 12
url: /cs/net/image-and-video-manipulation-in-slides/creating-thumbnail-scaling-factor-shape/
---
## Úvod
Vítejte v našem komplexním průvodci vytvářením miniatur s hranicemi pro tvary v Aspose.Slides pro .NET. Aspose.Slides je výkonná knihovna, která umožňuje vývojářům bezproblémově pracovat s prezentacemi PowerPoint v jejich aplikacích .NET. V tomto tutoriálu se ponoříme do procesu generování miniatur se specifickými hranicemi pro tvary v prezentaci pomocí Aspose.Slides.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.Slides for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).
- Vývojové prostředí: Mějte na svém počítači nastavené vhodné vývojové prostředí pro .NET, jako je Visual Studio.
## Importovat jmenné prostory
Ve své aplikaci .NET začněte importováním potřebných jmenných prostorů pro přístup k funkcím Aspose.Slides:
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides;
```
## Krok 1: Nastavte prezentaci
Začněte vytvořením instance třídy Presentation, která představuje soubor prezentace PowerPoint, se kterým chcete pracovat:
```csharp
string dataDir = "Your Documents Directory";
using (Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx"))
{
    // Zde je váš kód pro generování miniatur
}
```
## Krok 2: Vytvořte obrázek v plném měřítku
V bloku Prezentace vytvořte v plném měřítku obraz tvaru, pro který chcete vygenerovat miniaturu:
```csharp
using (Bitmap bitmap = presentation.Slides[0].Shapes[0].GetThumbnail(ShapeThumbnailBounds.Shape, 1, 1))
{
    //Zde je váš kód pro uložení obrázku
}
```
## Krok 3: Uložte obrázek na disk
Uložte vygenerovaný obrázek na disk s určením formátu (v tomto případě PNG):
```csharp
bitmap.Save(dataDir + "Scaling Factor Thumbnail_out.png", ImageFormat.Png);
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak vytvářet miniatury s hranicemi pro tvary pomocí Aspose.Slides pro .NET. Tato funkce může být neuvěřitelně užitečná, když potřebujete programově generovat obrázky tvarů konkrétní velikosti v prezentacích PowerPoint.
## Často kladené otázky
### Q1: Mohu používat Aspose.Slides s jinými frameworky .NET?
Ano, Aspose.Slides je kompatibilní s různými .NET frameworky a poskytuje flexibilitu pro integraci do různých typů aplikací.
### Q2: Je k dispozici zkušební verze pro Aspose.Slides?
 Ano, funkčnost Aspose.Slides můžete prozkoumat stažením zkušební verze[tady](https://releases.aspose.com/).
### Q3: Jak mohu získat dočasnou licenci pro Aspose.Slides?
 Dočasnou licenci pro Aspose.Slides můžete získat návštěvou[tento odkaz](https://purchase.aspose.com/temporary-license/).
### Q4: Kde najdu další podporu pro Aspose.Slides?
Máte-li jakékoli dotazy nebo pomoc, neváhejte navštívit fórum podpory Aspose.Slides[tady](https://forum.aspose.com/c/slides/11).
### Q5: Mohu zakoupit Aspose.Slides pro .NET?
 Rozhodně! Chcete-li zakoupit Aspose.Slides pro .NET, navštivte stránku nákupu[tady](https://purchase.aspose.com/buy).