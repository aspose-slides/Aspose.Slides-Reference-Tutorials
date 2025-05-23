---
"date": "2025-04-15"
"description": "Naučte se, jak vytvářet dynamické prstencové grafy pomocí Aspose.Slides pro .NET. Postupujte podle této příručky, která obsahuje podrobné pokyny, včetně nastavení a pokročilých funkcí."
"title": "Podrobný návod&#58; Vytvořte prstencový graf pomocí Aspose.Slides .NET | Grafy a tabulky"
"url": "/cs/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Podrobný návod: Vytvořte prstencový graf pomocí Aspose.Slides .NET

## Zavedení

Představte si, že máte za úkol prezentovat výsledky analýzy dat svému týmu nebo klientům a potřebujete poutavý způsob, jak tyto informace vizualizovat. Zkuste prstencový graf – všestranný nástroj, který dokáže transformovat hrubá čísla do snadno stravitelných poznatků. S Aspose.Slides pro .NET je vytváření vlastního prstencového grafu ve slidech vaší prezentace jednoduché a efektivní. Tato příručka vás provede používáním Aspose.Slides k vytvoření vizuálně atraktivního prstencového grafu s možností přizpůsobení konfigurací sérií.

**Co se naučíte:**
- Nastavení vývojového prostředí s Aspose.Slides pro .NET
- Vytváření a úprava prstencových grafů v prezentacích
- Implementace pokročilých funkcí, jako jsou názvy kategorií a vodicí čáry
- Optimalizace výkonu pro velké datové sady

Pojďme se ponořit do předpokladů, které potřebujete k zahájení.

## Předpoklady

Před implementací této funkce se ujistěte, že je vaše vývojové prostředí správně nastaveno. Tento tutoriál předpokládá základní znalosti programování v .NET a znalost Visual Studia nebo podobného IDE.

### Požadované knihovny a verze
- **Aspose.Slides pro .NET**: Zajistěte kompatibilitu s nejnovější verzí kontrolou jejich [oficiální dokumentace](https://reference.aspose.com/slides/net/).

### Požadavky na nastavení prostředí
- Funkční prostředí .NET.
- Přístup k editoru kódu, jako je Visual Studio.

### Předpoklady znalostí
- Základní znalost C# a .NET frameworku.
- Znalost konceptů prezentačního softwaru (volitelné, ale užitečné).

## Nastavení Aspose.Slides pro .NET

Abyste mohli začít používat Aspose.Slides ve svém projektu, musíte si jej nainstalovat pomocí NuGetu. Zde jsou dostupné metody:

**Použití .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Používání Správce balíčků:**
```powershell
Install-Package Aspose.Slides
```

**Uživatelské rozhraní Správce balíčků NuGet:**
Vyhledejte „Aspose.Slides“ a nainstalujte nejnovější verzi.

### Kroky získání licence

1. **Bezplatná zkušební verze**Začněte s [bezplatná zkušební verze](https://releases.aspose.com/slides/net/) prozkoumat základní funkce.
2. **Dočasná licence**: Pokud potřebujete přístup k plným funkcím pro účely hodnocení, získejte dočasnou licenci na adrese [zde](https://purchase.aspose.com/temporary-license/).
3. **Nákup**Pro komerční použití si zakupte licenci od [Webové stránky Aspose](https://purchase.aspose.com/buy).

Po instalaci a licenci inicializujte Aspose.Slides ve vašem projektu:
```csharp
using Aspose.Slides;

// Inicializace Aspose.Slides pro .NET
var presentation = new Presentation();
```

## Průvodce implementací

### Vytvoření nové prezentace a přidání prstencového grafu

#### Přehled
Začneme vytvořením nové prezentace a přidáním prstencového grafu na první snímek. Tato část se zabývá načtením existující prezentace, přístupem ke snímkům a vkládáním grafů.

**Krok 1: Načtení nebo vytvoření prezentace**
Nejprve zadejte adresář dokumentů a načtěte existující prezentaci:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Pokud nemáte existující soubor, vytvořte nový pomocí `new Presentation()`.

**Krok 2: Otevření prvního snímku**
Získejte přístup k prvnímu snímku, kam přidáme náš graf:
```csharp
ISlide slide = pres.Slides[0];
```

**Krok 3: Přidání prstencového grafu**
Přidat prstencový graf v zadaných souřadnicích a rozměrech:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurace datového sešitu

#### Přehled
Tato část vysvětluje, jak nakonfigurovat datový sešit přidružený ke prstencovému grafu.

**Krok 4: Přístup k existujícím datům a jejich vymazání**
Otevřete datový sešit grafu. Poté vymažte všechny existující řady nebo kategorie:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Krok 5: Zakázat legendu a přidat sérii**
Vypněte legendu, aby graf zůstal čistý, a poté přidejte až 15 sérií s vlastními konfiguracemi:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Přidávání kategorií a datových bodů

#### Přehled
Nyní naplňme graf kategoriemi a datovými body pro každou sérii.

**Krok 6: Přidání kategorií**
Pro přidání 15 kategorií projděte následujícím postupem:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Krok 7: Naplnění datových bodů**
Přidejte datové body pro každou sérii v rámci aktuální kategorie:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Přizpůsobit vzhled
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Konfigurace formátu popisku pro poslední sérii
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Konfigurace zobrazení štítků
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Uložení prezentace

**Krok 8: Uložte soubor**
Nakonec uložte prezentaci do určeného adresáře:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}