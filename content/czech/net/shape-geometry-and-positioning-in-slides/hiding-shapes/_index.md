---
title: Skrýt tvary v PowerPointu pomocí Aspose.Slides .NET Tutorial
linktitle: Skrytí obrazců v prezentačních snímcích s Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se skrýt tvary ve snímcích PowerPoint pomocí Aspose.Slides for .NET. Přizpůsobte si prezentace programově pomocí tohoto podrobného průvodce.
type: docs
weight: 21
url: /cs/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## Úvod
dynamickém světě prezentací je přizpůsobení klíčové. Aspose.Slides for .NET poskytuje výkonné řešení pro programovou manipulaci s prezentacemi PowerPoint. Jedním z běžných požadavků je schopnost skrýt určité tvary na snímku. Tento tutoriál vás provede procesem skrývání tvarů ve snímcích prezentace pomocí Aspose.Slides pro .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.Slides for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides. Můžete si jej stáhnout[tady](https://releases.aspose.com/slides/net/).
- Vývojové prostředí: Nastavte si preferované vývojové prostředí pro .NET.
- Základní znalost C#: Seznamte se s C#, protože uvedené příklady kódu jsou v tomto jazyce.
## Importovat jmenné prostory
Chcete-li začít pracovat s Aspose.Slides, importujte potřebné jmenné prostory do svého projektu C#. To zajišťuje, že máte přístup k požadovaným třídám a metodám.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Nyní si ukázkový kód rozdělíme do několika kroků pro jasné a stručné pochopení.
## Krok 1: Nastavte svůj projekt
Vytvořte nový projekt C# a nezapomeňte zahrnout knihovnu Aspose.Slides.
## Krok 2: Vytvořte prezentaci
 Vytvořte instanci`Presentation` třídy představující soubor PowerPoint. Přidejte snímek a získejte na něj odkaz.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Krok 3: Přidejte na snímek tvary
Přidejte na snímek automatické tvary, jako jsou obdélníky a měsíce, se specifickými rozměry.
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
Upravenou prezentaci uložte na disk ve formátu PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Závěr
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## Nejčastější dotazy
### Je Aspose.Slides kompatibilní s .NET Core?
Ano, Aspose.Slides podporuje .NET Core a poskytuje flexibilitu ve vašem vývojovém prostředí.
### Mohu skrýt tvary na základě jiných podmínek než alternativního textu?
Absolutně! Logiku skrytí můžete přizpůsobit na základě různých atributů, jako je typ tvaru, barva nebo poloha.
### Kde najdu další dokumentaci Aspose.Slides?
 Prozkoumejte dokumentaci[tady](https://reference.aspose.com/slides/net/) pro podrobné informace a příklady.
### Jsou pro Aspose.Slides dostupné dočasné licence?
 Ano, můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/) pro testovací účely.
### Jak mohu získat podporu komunity pro Aspose.Slides?
 Připojte se ke komunitě Aspose.Slides na[Fórum](https://forum.aspose.com/c/slides/11) za diskuze a pomoc.