---
"description": "Naučte se, jak skrýt tvary v PowerPointových slidech pomocí Aspose.Slides pro .NET. Upravte si prezentace programově pomocí tohoto podrobného návodu."
"linktitle": "Skrytí tvarů ve slidech prezentace pomocí Aspose.Slides"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Skrytí tvarů v PowerPointu pomocí Aspose.Slides .NET tutoriál"
"url": "/cs/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Skrytí tvarů v PowerPointu pomocí Aspose.Slides .NET tutoriál

## Zavedení
V dynamickém světě prezentací je přizpůsobení klíčové. Aspose.Slides pro .NET poskytuje výkonné řešení pro programovou manipulaci s prezentacemi v PowerPointu. Jedním z běžných požadavků je možnost skrýt určité tvary v rámci snímku. Tento tutoriál vás provede procesem skrytí tvarů v prezentačních snímcích pomocí Aspose.Slides pro .NET.
## Předpoklady
Než se pustíte do tutoriálu, ujistěte se, že máte splněny následující předpoklady:
- Aspose.Slides pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides. Můžete si ji stáhnout. [zde](https://releases.aspose.com/slides/net/).
- Vývojové prostředí: Nastavte si preferované vývojové prostředí pro .NET.
- Základní znalost jazyka C#: Seznamte se s jazykem C#, protože uvedené příklady kódu jsou v tomto jazyce.
## Importovat jmenné prostory
Chcete-li začít pracovat s Aspose.Slides, importujte potřebné jmenné prostory do svého projektu C#. Tím zajistíte přístup k požadovaným třídám a metodám.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Nyní si pro jasné a stručné pochopení rozdělme ukázkový kód do několika kroků.
## Krok 1: Nastavení projektu
Vytvořte nový projekt v C# a nezapomeňte do něj zahrnout knihovnu Aspose.Slides.
## Krok 2: Vytvořte prezentaci
Vytvořte instanci `Presentation` třída reprezentující soubor PowerPoint. Přidejte snímek a získejte na něj odkaz.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Krok 3: Přidání tvarů do snímku
Přidejte na snímek automatické tvary, například obdélníky a měsíce, s konkrétními rozměry.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Krok 4: Skrytí tvarů na základě alternativního textu
Zadejte alternativní text a skryjte tvary, které tomuto textu odpovídají.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Krok 5: Uložte prezentaci
Uložte upravenou prezentaci na disk ve formátu PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Závěr
Gratulujeme! Úspěšně jste skryli tvary ve vaší prezentaci pomocí Aspose.Slides pro .NET. To otevírá svět možností pro programovou tvorbu dynamických a přizpůsobených snímků.
---
## Často kladené otázky
### Je Aspose.Slides kompatibilní s .NET Core?
Ano, Aspose.Slides podporuje .NET Core, což poskytuje flexibilitu ve vašem vývojovém prostředí.
### Mohu skrýt tvary na základě jiných podmínek než alternativního textu?
Rozhodně! Logiku skrytí si můžete přizpůsobit na základě různých atributů, jako je typ tvaru, barva nebo pozice.
### Kde najdu další dokumentaci k Aspose.Slides?
Prozkoumejte dokumentaci [zde](https://reference.aspose.com/slides/net/) pro podrobné informace a příklady.
### Jsou pro Aspose.Slides k dispozici dočasné licence?
Ano, můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/) pro účely testování.
### Jak mohu získat podporu komunity pro Aspose.Slides?
Připojte se ke komunitě Aspose.Slides na [forum](https://forum.aspose.com/c/slides/11) pro diskuze a pomoc.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}