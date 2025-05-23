---
"date": "2025-04-15"
"description": "Naučte se, jak vytvářet vizuálně poutavé skládané sloupcové grafy založené na procentech pomocí Aspose.Slides pro .NET. Postupujte podle tohoto podrobného návodu pro přehlednou vizualizaci dat."
"title": "Jak vytvořit procentuálně založené skládané sloupcové grafy v .NET pomocí Aspose.Slides"
"url": "/cs/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit procentuálně založený skládaný sloupcový graf pomocí Aspose.Slides pro .NET

## Zavedení

oblasti vizualizace dat je jasné a efektivní prezentování informací klíčové pro efektivní rozhodování. Pro intuitivní zobrazení složitých datových sad jsou ideální skládané sloupcové grafy založené na procentech. Tato příručka vás provede vytvářením těchto grafů pomocí Aspose.Slides pro .NET, robustní knihovny určené pro manipulaci s prezentačními soubory.

Díky tomuto tutoriálu se naučíte:
- Nastavení dat grafu a konfigurace číselných formátů.
- Přidávání sérií a úprava jejich vzhledu.
- Formátování popisků pro zlepšení čitelnosti.

Jste připraveni se do toho pustit? Začněme s předpoklady, které potřebujete!

## Předpoklady

Před vytvořením procentuálně založené sloupcové grafy se ujistěte, že je vaše prostředí správně nastaveno. Budete potřebovat:

### Požadované knihovny, verze a závislosti
- **Aspose.Slides pro .NET**Ujistěte se, že je tato knihovna nainstalována.

### Požadavky na nastavení prostředí
- Vývojové prostředí s nainstalovanou .NET SDK.
- Visual Studio nebo jakékoli kompatibilní IDE pro spouštění kódu C#.

### Předpoklady znalostí
- Základní znalost programování v C#.
- Znalost nastavení .NET projektů a správy balíčků.

## Nastavení Aspose.Slides pro .NET

Chcete-li začít vytvářet grafy pomocí Aspose.Slides, nejprve nainstalujte knihovnu pomocí jedné z těchto metod:

**Rozhraní příkazového řádku .NET**
```bash
dotnet add package Aspose.Slides
```

**Správce balíčků**
```powershell
Install-Package Aspose.Slides
```

**Uživatelské rozhraní Správce balíčků NuGet**
- Vyhledejte „Aspose.Slides“ a nainstalujte nejnovější verzi.

### Kroky získání licence

Začněte s bezplatnou zkušební verzí stažením dočasné licence z [Webové stránky společnosti Aspose](https://purchase.aspose.com/temporary-license/)Pro další používání zvažte zakoupení plné licence. 

Po nastavení spusťte Aspose.Slides ve vašem projektu:
```csharp
using Aspose.Slides;
```

## Průvodce implementací

S připraveným prostředím si rozdělme vytvoření skládaného sloupcového grafu založeného na procentech do kroků.

### Vytvoření a konfigurace grafu

#### Přehled
Vytvořte instanci `Presentation` třída, která je nezbytná pro práci se snímky. Poté na snímek přidejte a nakonfigurujte skládaný sloupcový graf.

#### Přidání skládaného sloupcového grafu
```csharp
// Vytvoření instance třídy Presentation
document = new Presentation();

// Získání odkazu na první snímek
slide = document.Slides[0];

// Přidat graf PercentsStackedColumn na pozici (20, 20) o velikosti (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Konfigurace formátu čísel
Ujistěte se, že jsou vaše data zobrazena v procentech:
```csharp
// Konfigurace formátu čísel pro svislou osu
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Nastavit formát čísla na procenta
```

#### Přidávání datových řad a bodů
Vymazat existující data série a přidat nová:
```csharp
// Vymažte všechna existující data série
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Sešit s daty grafů v Accessu
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Přidat novou datovou řadu „Červené“
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Nastavit barvu výplně pro sérii na červenou
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Konfigurace vlastností formátu popisku pro řadu „Červené“
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Nastavení formátu procent
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Přidat další sérii „Blues“
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Nastavit barvu výplně pro sérii na modrou
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Nastavení formátu procent
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Uložení prezentace
Uložte prezentaci do souboru:
```csharp
// Uložte prezentaci ve formátu PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Tipy pro řešení problémů
- Ujistěte se, že všechny jmenné prostory jsou správně importovány.
- Zkontrolujte překlepy v názvech vlastností a voláních metod.
- Ověřte, zda cesty pro ukládání souborů existují a zda mají správná oprávnění.

## Praktické aplikace

Zde je několik scénářů, kde mohou být procentuálně založené skládané sloupcové grafy užitečné:
1. **Analýza prodeje**Vizualizace výkonnosti produktů v různých regionech jako podíl na celkových tržbách.
2. **Rozpočtové rozdělení**Ukažte, jak oddělení rozdělují svůj rozpočet ve vztahu k celkovým výdajům společnosti.
3. **Průzkum trhu**Porovnejte preference spotřebitelů u různých kategorií produktů v průběhu času.
4. **Vzdělávací data**Zobrazit rozložení známek studentů v různých předmětech.
5. **Statistiky zdravotnictví**Reprezentovat demografické údaje pacientů s různými zdravotními stavy.

## Úvahy o výkonu

Pro optimální výkon zvažte:
- Omezení počtu datových bodů na to, co je nezbytné.
- Předběžné načítání dat pro minimalizaci zpracování za běhu.
- Používání efektivních postupů správy paměti s Aspose.Slides pro .NET.

## Závěr

Gratulujeme! Úspěšně jste se naučili, jak vytvořit skládaný sloupcový graf založený na procentech pomocí nástroje Aspose.Slides pro .NET. Tento nástroj vylepšuje prezentace tím, že komplexní data činí srozumitelnějšími a vizuálně atraktivnějšími.

Další kroky? Prozkoumejte další typy grafů dostupné v Aspose.Slides nebo integrujte tuto funkci do větších aplikací. Přejeme vám příjemné programování!

## Sekce Často kladených otázek

**Q1: Mohu používat Aspose.Slides zdarma?**
A1: Ano, můžete začít s bezplatnou zkušební verzí a otestovat funkce Aspose.Slides.

**Q2: Jaké typy grafů podporuje Aspose.Slides pro .NET?**
A2: Podporuje různé grafy, jako jsou koláčové, sloupcové, sloupcové, čárové a další.

**Q3: Jak mohu začít s Aspose.Slides pro .NET?**
A3: Nainstalujte knihovnu pomocí NuGet nebo .NET CLI, jak je popsáno výše. Vytvořte si první graf podle naší dokumentace.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}