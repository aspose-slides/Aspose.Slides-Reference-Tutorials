---
"description": "Naučte se v tomto podrobném návodu, jak do grafů přidávat různé trendové linie pomocí Aspose.Slides pro .NET. Snadno si vylepšete své dovednosti vizualizace dat!"
"linktitle": "Trendové linie grafu"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Prozkoumání trendových linií grafu v Aspose.Slides pro .NET"
"url": "/cs/net/advanced-chart-customization/chart-trend-lines/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Prozkoumání trendových linií grafu v Aspose.Slides pro .NET


Ve světě vizualizace a prezentace dat může být začlenění grafů účinným způsobem, jak efektivně sdělovat informace. Aspose.Slides pro .NET poskytuje bohatou sadu nástrojů pro práci s grafy, včetně možnosti přidávat do grafů trendové čáry. V tomto tutoriálu se krok za krokem ponoříme do procesu přidávání trendových čar do grafu pomocí Aspose.Slides pro .NET. 

## Předpoklady

Než začneme pracovat s Aspose.Slides pro .NET, je třeba se ujistit, že máte splněny následující předpoklady:

1. Aspose.Slides pro .NET: Pro přístup ke knihovně a její používání musíte mít nainstalovanou Aspose.Slides pro .NET. Knihovnu můžete získat z [stránka ke stažení](https://releases.aspose.com/slides/net/).

2. Vývojové prostředí: Měli byste mít nastavené vývojové prostředí, nejlépe s využitím integrovaného vývojového prostředí .NET, jako je Visual Studio.

3. Základní znalost C#: Základní znalost programování v C# je výhodou, protože budeme C# používat pro práci s Aspose.Slides pro .NET.

Nyní, když jsme si probrali předpoklady, pojďme si krok za krokem rozebrat proces přidávání trendových čar do grafu.

## Import jmenných prostorů

Nejprve se ujistěte, že jste do svého projektu v C# importovali potřebné jmenné prostory. Tyto jmenné prostory jsou nezbytné pro práci s Aspose.Slides pro .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Krok 1: Vytvořte prezentaci

V tomto kroku vytvoříme prázdnou prezentaci pro práci.

```csharp
// Cesta k adresáři s dokumenty.
string dataDir = "Your Document Directory";

// Vytvořte adresář, pokud ještě neexistuje.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Vytvoření prázdné prezentace
Presentation pres = new Presentation();
```

## Krok 2: Přidání grafu do snímku

Dále přidáme na snímek klastrovaný sloupcový graf.

```csharp
// Vytvoření seskupeného sloupcového grafu
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Krok 3: Přidání trendových linií do grafu

Nyní do grafové série přidáme různé typy trendových čar.

### Přidání exponenciální trendové linie

```csharp
// Přidání exponenciální trendové linie pro sérii grafů 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Přidání lineární trendové linie

```csharp
// Přidání lineární trendové linie pro sérii grafů 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Přidání logaritmické trendové linie

```csharp
// Přidání logaritmické trendové linie pro sérii grafů 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Přidání trendové linie klouzavého průměru

```csharp
// Přidání trendové linie klouzavého průměru pro sérii grafů 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Přidání polynomiální trendové linie

```csharp
// Přidání polynomiální trendové linie pro sérii grafů 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Přidání výkonnostní trendové linie

```csharp
// Přidání trendové linie síly pro sérii grafů 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Krok 4: Uložte prezentaci

Po přidání trendových linií do grafu prezentaci uložte.

```csharp
// Ukládání prezentace
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

To je vše! Úspěšně jste do grafu přidali různé trendové linie pomocí Aspose.Slides pro .NET.

## Závěr

Aspose.Slides pro .NET je všestranná knihovna, která vám umožňuje snadno vytvářet a manipulovat s grafy. Pomocí tohoto podrobného návodu můžete do grafů přidávat různé typy trendových čar, čímž vylepšíte vizuální reprezentaci dat.

### Často kladené otázky

### Kde najdu dokumentaci k Aspose.Slides pro .NET?
Dokumentaci si můžete prohlédnout [zde](https://reference.aspose.com/slides/net/).

### Jak si mohu stáhnout Aspose.Slides pro .NET?
Aspose.Slides pro .NET si můžete stáhnout ze stránky pro stahování. [zde](https://releases.aspose.com/slides/net/).

### Je k dispozici bezplatná zkušební verze Aspose.Slides pro .NET?
Ano, Aspose.Slides pro .NET si můžete zdarma vyzkoušet na adrese [tento odkaz](https://releases.aspose.com/).

### Kde mohu zakoupit Aspose.Slides pro .NET?
Chcete-li zakoupit Aspose.Slides pro .NET, navštivte stránku nákupu [zde](https://purchase.aspose.com/buy).

### Potřebuji dočasnou licenci pro Aspose.Slides pro .NET?
Dočasnou licenci pro Aspose.Slides pro .NET můžete získat od [tento odkaz](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}