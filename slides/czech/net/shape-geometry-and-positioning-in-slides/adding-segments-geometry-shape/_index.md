---
title: Mastering Visuals – Přidání segmentů pomocí Aspose.Slides v .NET
linktitle: Přidání segmentů do geometrického tvaru v prezentaci pomocí Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak vylepšit své aplikace .NET pomocí Aspose.Slides. Tento výukový program vás provede přidáváním segmentů do geometrických tvarů pro poutavé prezentace.
weight: 13
url: /cs/net/shape-geometry-and-positioning-in-slides/adding-segments-geometry-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
Ve světě vývoje .NET je vytváření vizuálně přitažlivých prezentací běžným požadavkem. Aspose.Slides for .NET je výkonná knihovna, která usnadňuje bezproblémovou integraci robustních možností tvorby prezentací do vašich aplikací .NET. Tento tutoriál se zaměřuje na specifický aspekt návrhu prezentace – přidávání segmentů do geometrických tvarů.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Základní znalost programovacího jazyka C#.
- Visual Studio nainstalované na vašem počítači.
- Knihovna Aspose.Slides for .NET stažená a odkazovaná ve vašem projektu.
## Importovat jmenné prostory
Ujistěte se, že ve svém kódu C# importujete potřebné jmenné prostory pro přístup k funkcím Aspose.Slides. Přidejte do kódu následující řádky:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Nyní si příklad rozdělíme do několika kroků.
## Krok 1: Nastavte svůj projekt
Začněte vytvořením nového projektu C# v sadě Visual Studio. Ujistěte se, že máte ve svém projektu odkaz na knihovnu Aspose.Slides.
## Krok 2: Vytvořte prezentaci
Inicializujte nový objekt prezentace pomocí knihovny Aspose.Slides. To bude sloužit jako plátno pro váš geometrický tvar.
```csharp
using (Presentation pres = new Presentation())
{
    // Zde je váš kód pro vytvoření prezentace
}
```
## Krok 3: Přidejte geometrický tvar
Vytvořte geometrický tvar v rámci prezentace. Přidejme například na první snímek obdélník.
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
```
## Krok 4: Získejte geometrickou cestu
Načtěte geometrickou cestu vytvořeného tvaru, abyste mohli manipulovat s jeho segmenty.
```csharp
IGeometryPath geometryPath = shape.GetGeometryPaths()[0];
```
## Krok 5: Přidejte segmenty
Přidejte segmenty (čáry) do geometrické cesty. V tomto příkladu jsou k cestě přidány dvě čáry.
```csharp
geometryPath.LineTo(100, 50, 1);
geometryPath.LineTo(100, 50, 4);
```
## Krok 6: Přiřaďte upravenou geometrickou cestu
Přiřaďte upravenou geometrickou cestu zpět k tvaru, abyste použili změny.
```csharp
shape.SetGeometryPath(geometryPath);
```
## Krok 7: Uložte prezentaci
Uložte upravenou prezentaci na požadované místo.
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Pomocí těchto kroků jste úspěšně přidali segmenty do geometrického tvaru v prezentaci pomocí Aspose.Slides for .NET.
## Závěr
Aspose.Slides for .NET umožňuje vývojářům vylepšit jejich aplikace o pokročilé možnosti tvorby prezentací. Přidání segmentů do geometrických tvarů poskytuje prostředky k přizpůsobení vizuálních prvků vašich prezentací.
### Často kladené otázky
### Mohu pomocí Aspose.Slides přidávat různé typy tvarů?
Ano, Aspose.Slides podporuje různé typy tvarů, včetně obdélníků, kruhů a tvarů vlastní geometrie.
### Je pro použití Aspose.Slides v mém projektu vyžadována licence?
Ano, je potřeba platná licence. Můžete získat dočasnou licenci pro testovací účely nebo zakoupit plnou licenci pro produkci.
### Jak mohu získat podporu pro dotazy související s Aspose.Slides?
 Navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) za podporu komunity a diskuze.
### Jsou k dispozici další výukové programy pro Aspose.Slides?
 Prozkoumat[dokumentace](https://reference.aspose.com/slides/net/) pro komplexní návody a příklady.
### Mohu si Aspose.Slides před nákupem zdarma vyzkoušet?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
