---
title: Prozkoumávání trendových linií grafu v Aspose.Slides pro .NET
linktitle: Graf trendových linií
second_title: Aspose.Slides .NET PowerPoint Processing API
description: V tomto podrobném průvodci se dozvíte, jak přidat různé čáry trendu do grafů pomocí Aspose.Slides for .NET. Vylepšete své dovednosti vizualizace dat snadno!
weight: 12
url: /cs/net/advanced-chart-customization/chart-trend-lines/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Ve světě vizualizace a prezentace dat může být začlenění grafů účinným způsobem, jak efektivně předávat informace. Aspose.Slides for .NET poskytuje funkčně bohatou sadu nástrojů pro práci s grafy, včetně možnosti přidávat do grafů trendové čáry. V tomto tutoriálu se ponoříme do procesu přidávání trendových čar do grafu krok za krokem pomocí Aspose.Slides for .NET. 

## Předpoklady

Než začneme pracovat s Aspose.Slides pro .NET, musíte se ujistit, že máte splněny následující předpoklady:

1. Aspose.Slides for .NET: Pro přístup ke knihovně a její používání musíte mít nainstalovanou aplikaci Aspose.Slides for .NET. Knihovnu můžete získat z[stránka ke stažení](https://releases.aspose.com/slides/net/).

2. Vývojové prostředí: Měli byste mít nastavené vývojové prostředí, nejlépe pomocí integrovaného vývojového prostředí .NET, jako je Visual Studio.

3. Základní znalost C#: Základní znalost programování v C# je prospěšná, protože C# budeme používat pro práci s Aspose.Slides pro .NET.

Nyní, když jsme pokryli předpoklady, pojďme si krok za krokem rozebrat proces přidávání trendových čar do grafu.

## Import jmenných prostorů

Nejprve se ujistěte, že jste do svého projektu C# importovali potřebné jmenné prostory. Tyto jmenné prostory jsou nezbytné pro práci s Aspose.Slides pro .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Krok 1: Vytvořte prezentaci

V tomto kroku vytvoříme prázdnou prezentaci, se kterou budeme pracovat.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

// Vytvořte adresář, pokud ještě není přítomen.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Vytváření prázdné prezentace
Presentation pres = new Presentation();
```

## Krok 2: Přidejte graf do snímku

Dále na snímek přidáme seskupený sloupcový graf.

```csharp
// Vytvoření seskupeného sloupcového grafu
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Krok 3: Přidejte čáry trendu do grafu

Nyní do řady grafů přidáváme různé typy trendových čar.

### Přidání exponenciální trendové linie

```csharp
// Přidání exponenciální trendové čáry pro grafovou řadu 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Přidání linie lineárního trendu

```csharp
// Přidání lineární trendové linie pro řadu grafů 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Přidání logaritmické trendové linie

```csharp
// Přidání logaritmické trendové linie pro grafovou řadu 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Přidání trendové linie klouzavého průměru

```csharp
// Přidání trendové linie klouzavého průměru pro řadu grafů 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Přidání polynomické trendové čáry

```csharp
// Přidání polynomické trendové čáry pro řadu grafů 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Přidání čáry trendu výkonu

```csharp
// Přidání čáry trendu výkonu pro řadu grafů 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Krok 4: Uložte prezentaci

Po přidání trendových čar do grafu uložte prezentaci.

```csharp
// Ukládání prezentace
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

A je to! Pomocí Aspose.Slides for .NET jste do grafu úspěšně přidali různé trendové čáry.

## Závěr

Aspose.Slides for .NET je všestranná knihovna, která vám umožní snadno vytvářet a manipulovat s grafy. Podle tohoto podrobného průvodce můžete do grafů přidat různé typy trendových čar a zlepšit tak vizuální reprezentaci vašich dat.

### Nejčastější dotazy

### Kde najdu dokumentaci k Aspose.Slides pro .NET?
 Máte přístup k dokumentaci[tady](https://reference.aspose.com/slides/net/).

### Jak si mohu stáhnout Aspose.Slides pro .NET?
 Aspose.Slides for .NET si můžete stáhnout ze stránky stahování[tady](https://releases.aspose.com/slides/net/).

### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro .NET?
 Ano, Aspose.Slides pro .NET můžete zdarma vyzkoušet na návštěvě[tento odkaz](https://releases.aspose.com/).

### Kde mohu zakoupit Aspose.Slides pro .NET?
 Chcete-li zakoupit Aspose.Slides pro .NET, navštivte stránku nákupu[tady](https://purchase.aspose.com/buy).

### Potřebuji dočasnou licenci pro Aspose.Slides pro .NET?
 Můžete získat dočasnou licenci pro Aspose.Slides pro .NET od[tento odkaz](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
