---
title: Vytváření obdélníkových tvarů pomocí Aspose.Slides pro .NET
linktitle: Vytvoření jednoduchého obdélníkového tvaru v prezentačních snímcích pomocí Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Prozkoumejte svět dynamických prezentací PowerPoint s Aspose.Slides pro .NET. Naučte se vytvářet poutavé obdélníkové tvary na snímcích pomocí tohoto podrobného průvodce.
type: docs
weight: 12
url: /cs/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---
## Úvod
Pokud chcete vylepšit své aplikace .NET pomocí dynamických a vizuálně přitažlivých prezentací PowerPoint, Aspose.Slides for .NET je vaším řešením. V tomto tutoriálu vás provedeme procesem vytváření jednoduchého obdélníkového tvaru na snímcích prezentace pomocí Aspose.Slides pro .NET.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující předpoklady:
- Visual Studio: Ujistěte se, že máte na vývojovém počítači nainstalované Visual Studio.
-  Aspose.Slides for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Slides for .NET z[tady](https://releases.aspose.com/slides/net/).
- Základní znalost C#: Znalost programovacího jazyka C# je nezbytná.
## Importovat jmenné prostory
Ve svém projektu C# začněte importem potřebných jmenných prostorů pro přístup k funkcím Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Krok 1: Nastavte projekt
Začněte vytvořením nového projektu C# v sadě Visual Studio. Ujistěte se, že je ve vašem projektu správně odkazováno na Aspose.Slides for .NET.
## Krok 2: Inicializujte objekt prezentace
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Zde bude váš kód pro další kroky.
}
```
## Krok 3: Získejte první snímek
```csharp
ISlide sld = pres.Slides[0];
```
## Krok 4: Přidejte automatický tvar obdélníku
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Tento kód přidá tvar obdélníku na souřadnicích (50, 150) o šířce 150 a výšce 50.
## Krok 5: Uložte prezentaci
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Tento krok uloží prezentaci s přidaným tvarem obdélníku do zadaného adresáře.
## Závěr
Gratulujeme! Úspěšně jste vytvořili jednoduchý obdélníkový tvar na snímku prezentace pomocí Aspose.Slides for .NET. Toto je jen začátek – Aspose.Slides nabízí širokou škálu funkcí pro další přizpůsobení a vylepšení vašich prezentací.
## Často kladené otázky
### Mohu používat Aspose.Slides pro .NET v prostředí Windows i Linux?
Ano, Aspose.Slides for .NET je nezávislý na platformě a lze jej použít v prostředí Windows i Linux.
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro .NET?
 Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.Slides pro .NET?
 Navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) za podporu komunity.
### Mohu si zakoupit dočasnou licenci pro Aspose.Slides pro .NET?
 Ano, můžete si zakoupit dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu dokumentaci k Aspose.Slides pro .NET?
 Viz dokumentace[tady](https://reference.aspose.com/slides/net/).