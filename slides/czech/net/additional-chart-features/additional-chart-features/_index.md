---
title: Zkoumání pokročilých funkcí grafu s Aspose.Slides pro .NET
linktitle: Další funkce grafu v Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se pokročilé funkce grafů v Aspose.Slides pro .NET, abyste vylepšili své prezentace v PowerPointu. Vymažte datové body, obnovte sešity a další!
weight: 10
url: /cs/net/additional-chart-features/additional-chart-features/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Ve světě vizualizace dat a designu prezentací vyniká Aspose.Slides for .NET jako výkonný nástroj pro vytváření úžasných grafů a vylepšení vašich prezentací v PowerPointu. Tento podrobný průvodce vás provede různými pokročilými funkcemi grafů, které Aspose.Slides for .NET nabízí. Ať už jste vývojář nebo nadšenec do prezentací, tento tutoriál vám pomůže využít plný potenciál této knihovny.

## Předpoklady

Než se pustíme do podrobných příkladů, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Slides for .NET: Musíte mít nainstalovaný Aspose.Slides for .NET. Pokud jste to ještě neudělali, můžete si ji stáhnout[tady](https://releases.aspose.com/slides/net/).

2. Visual Studio: Měli byste mít nainstalované Visual Studio nebo jakékoli vhodné vývojové prostředí C#, abyste mohli postupovat podle příkladů kódu.

3. Základní znalost C#: Znalost programování v C# je nezbytná pro pochopení a úpravu kódu podle potřeby.

Nyní, když máte pokryty předpoklady, pojďme prozkoumat některé pokročilé funkce grafu v Aspose.Slides pro .NET.

## Import nezbytných jmenných prostorů

Pro začátek importujme požadované jmenné prostory pro přístup k funkcím Aspose.Slides ve vašem projektu C#.

### Příklad 1: Import jmenných prostorů

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using System;
```

## Příklad 1: Získat rozsah dat grafu

V tomto příkladu si ukážeme, jak načíst rozsah dat z grafu v prezentaci PowerPoint pomocí Aspose.Slides for .NET.

### Krok 1: Inicializujte prezentaci

Nejprve vytvořte novou PowerPointovou prezentaci pomocí Aspose.Slides.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation())
{
    // Přidejte seskupený sloupcový graf na první snímek.
    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 10, 10, 400, 300);
    string result = chart.ChartData.GetRange();
    Console.WriteLine("GetRange result: {0}", result);
}
```

 tomto fragmentu kódu vytvoříme novou prezentaci a na první snímek přidáme seskupený sloupcový graf. Poté načteme rozsah dat grafu pomocí`chart.ChartData.GetRange()` a zobrazit jej.

## Příklad 2: Obnovení sešitu z grafu

Nyní se podívejme, jak obnovit sešit z grafu v prezentaci PowerPoint.

### Krok 1: Načtěte prezentaci pomocí grafu

Začněte načtením prezentace PowerPoint, která obsahuje graf.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

string pptxFile = Path.Combine(dataDir, "ExternalWB.pptx");
string outPptxFile = Path.Combine(RunExamples.OutPath, "ExternalWB_out.pptx");

LoadOptions lo = new LoadOptions();
lo.SpreadsheetOptions.RecoverWorkbookFromChartCache = true;

using (Presentation pres = new Presentation(pptxFile, lo))
{
    IChart chart = pres.Slides[0].Shapes[0] as IChart;
    IChartDataWorkbook wb = chart.ChartData.ChartDataWorkbook;

    // Uložte upravenou prezentaci s obnoveným sešitem.
    pres.Save(outPptxFile, SaveFormat.Pptx);
}
```

V tomto příkladu načteme prezentaci PowerPoint (`ExternalWB.pptx` ) a zadejte možnosti obnovení sešitu z grafu. Po obnovení sešitu uložíme upravenou prezentaci jako`ExternalWB_out.pptx`.

## Příklad 3: Vymazání konkrétních datových bodů řady grafů

Nyní se podívejme, jak vymazat konkrétní datové body z řady grafů v prezentaci PowerPoint.

### Krok 1: Načtěte prezentaci pomocí grafu

Nejprve načtěte prezentaci PowerPoint, která obsahuje graf s datovými body.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "TestChart.pptx"))
{
    ISlide sl = pres.Slides[0];
    IChart chart = (IChart)sl.Shapes[0];

    //Iterujte každý datový bod v první řadě a vymažte hodnoty X a Y.
    foreach (IChartDataPoint dataPoint in chart.ChartData.Series[0].DataPoints)
    {
        dataPoint.XValue.AsCell.Value = null;
        dataPoint.YValue.AsCell.Value = null;
    }

    // Vymažte všechny datové body z první série.
    chart.ChartData.Series[0].DataPoints.Clear();

    // Uložte upravenou prezentaci.
    pres.Save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
}
```

V tomto příkladu načteme prezentaci PowerPoint (`TestChart.pptx` ) a vymažte konkrétní datové body z první řady grafu. Iterujeme každý datový bod, vymažeme hodnoty X a Y a nakonec vymažeme všechny datové body ze série. Upravená prezentace se uloží jako`ClearSpecificChartSeriesDataPointsData.pptx`.

# Závěr

Aspose.Slides for .NET poskytuje robustní platformu pro práci s grafy v prezentacích PowerPoint. S pokročilými funkcemi předvedenými v tomto kurzu můžete posunout vizualizaci dat a návrh prezentace na další úroveň. Ať už potřebujete extrahovat data, obnovit sešity nebo manipulovat s datovými body grafu, Aspose.Slides pro .NET vás pokryje.

Podle poskytnutých příkladů kódu a kroků můžete využít sílu Aspose.Slides pro .NET k vylepšení vašich prezentací v PowerPointu a vytvořit působivé vizuály založené na datech.

## Často kladené otázky (FAQ)

### Je Aspose.Slides for .NET vhodný pro začátečníky i zkušené vývojáře?
   
Ano, Aspose.Slides for .NET vychází vstříc vývojářům všech úrovní, od začátečníků po experty. Knihovna poskytuje uživatelsky přívětivé rozhraní a zároveň nabízí pokročilé funkce pro zkušené vývojáře.

### Mohu použít Aspose.Slides pro .NET k vytváření grafů v jiných formátech dokumentů, jako je PDF nebo obrázky?

Ano, Aspose.Slides for .NET můžete použít k vytváření grafů v různých formátech, včetně PDF, obrázků a dalších. Knihovna nabízí všestranné možnosti exportu.

### Kde najdu komplexní dokumentaci k Aspose.Slides pro .NET?

 Podrobnou dokumentaci a zdroje pro Aspose.Slides pro .NET naleznete na adrese[dokumentace](https://reference.aspose.com/slides/net/).

### Je k dispozici zkušební verze pro Aspose.Slides pro .NET?

 Ano, knihovnu můžete prozkoumat pomocí bezplatné zkušební verze dostupné na adrese[tady](https://releases.aspose.com/). To vám umožní vyhodnotit jeho vlastnosti před nákupem.

### Jak mohu získat podporu nebo pomoc s Aspose.Slides pro .NET?

 případě jakýchkoli technických dotazů nebo podpory můžete navštívit stránku[Fórum Aspose.Slides](https://forum.aspose.com/), kde můžete najít odpovědi na běžné otázky a získat pomoc od komunity.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
