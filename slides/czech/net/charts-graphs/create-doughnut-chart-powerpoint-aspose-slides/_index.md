---
"date": "2025-04-15"
"description": "Naučte se, jak vytvářet dynamické a vizuálně atraktivní prstencové grafy v prezentacích v PowerPointu pomocí výkonné knihovny Aspose.Slides pro .NET."
"title": "Jak vytvořit prstencový graf v PowerPointu pomocí Aspose.Slides pro .NET"
"url": "/cs/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit prstencový graf v PowerPointu pomocí Aspose.Slides pro .NET
Vytváření vizuálně poutavých grafů je nezbytné pro efektivní prezentaci dat. Prstencové grafy jsou ideální pro ilustraci částí celku, což je činí ideálními pro vizualizaci dat v procentech. Tento tutoriál vás provede vytvořením dynamického prstencového grafu v PowerPointu pomocí výkonné knihovny Aspose.Slides pro .NET.

## Zavedení
Prezentace často vyžadují vizuální reprezentace složitých datových sad, kde tradiční sloupcové nebo spojnicové grafy nemusí stačit. Prstencový graf se stává všestranným nástrojem pro efektivní a stylovou a srozumitelnou komunikaci procentuálních dat. V tomto tutoriálu se podíváme na to, jak Aspose.Slides pro .NET zjednodušuje proces vytváření těchto grafů přímo v PowerPointu.

**Co se naučíte:**
- Nastavení Aspose.Slides pro .NET
- Podrobné pokyny k vytvoření prstencového grafu
- Přidávání řad a kategorií do grafu
- Konfigurace popisků dat pro lepší přehlednost
- Uložení finální prezentace

Pojďme se ponořit do toho, jak můžete využít Aspose.Slides pro .NET k vylepšení vašich prezentací pomocí vlastních prstencových grafů.

## Předpoklady
Než začneme, ujistěte se, že máte připraveno následující:
- **Knihovna Aspose.Slides pro .NET**K dispozici přes NuGet nebo přímo ke stažení.
- **Vývojové prostředí**Pro projekty .NET se doporučuje Visual Studio.
- Základní znalost jazyka C# a znalost struktury PowerPointu.

## Nastavení Aspose.Slides pro .NET
Abyste mohli začít vytvářet grafy, musíte nejprve ve svém projektu nastavit knihovnu Aspose.Slides. Zde je několik způsobů, jak ji nainstalovat:

**Použití .NET CLI:**

```bash
dotnet add package Aspose.Slides
```

**Použití konzole Správce balíčků:**

```powershell
Install-Package Aspose.Slides
```

**Prostřednictvím uživatelského rozhraní Správce balíčků NuGet:**
Vyhledejte „Aspose.Slides“ a nainstalujte nejnovější verzi.

Po instalaci můžete začít s nastavením projektu. Pokud s Aspose.Slides teprve začínáte, zvažte pořízení dočasné licence nebo bezplatné zkušební verze, abyste si mohli vyzkoušet všechny jeho funkce bez omezení.

### Inicializujte svůj projekt
Zde je návod, jak inicializovat Aspose.Slides ve vaší aplikaci:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Vytvoření instance třídy Presentation
        Presentation presentation = new Presentation();
        
        // Váš kód pro manipulaci s prezentací patří sem
        
        // Uložit prezentaci
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Průvodce implementací
### Vytvoření prstencového grafu
#### Přehled
Nejprve si v PowerPointu vytvoříme prázdný prstencový graf. Ten poslouží jako základ pro přidávání dat a úpravu jeho vzhledu.

**Krok 1: Přidání prstencového grafu**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Přidat prstencový graf na první snímek na pozici (10, 10) o velikosti (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Vymazat existující série a kategorie
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Pro čistší vzhled vypněte legendu
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Vysvětlení:**
- **přidatGraf**Vloží na snímek nový prstencový graf.
- **getChartDataWorkbook**: Poskytuje přístup k datovým buňkám v grafu pro manipulaci.

### Přidávání sérií a kategorií
#### Přehled
Dále do grafu doplníme smysluplná data přidáním řad a kategorií.

**Krok 2: Přidání datových řad**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Přidat sérii
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Přizpůsobení otvoru pro prstenec a počátečního úhlu
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Přidat kategorie
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Formátování výplně a čáry datového bodu
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Vysvětlení:**
- **přidat**Vloží do grafu nové řady a kategorie.
- **setDoughnutHoleSize**Konfiguruje velikost otvoru v koblize a zvyšuje tak její vizuální atraktivitu.

### Konfigurace popisků dat
#### Přehled
Popisky dat poskytují kontext k datům v grafu. Zlepšeme čitelnost jejich přizpůsobením.

**Krok 3: Úprava popisků dat**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Přizpůsobení popisků dat
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Vysvětlení:**
- **IDataLabel**: Přizpůsobí popisky dat pro lepší přehlednost a prezentaci.
- **setCenterText**, **zobrazitProcento**Zlepšete čitelnost štítků vycentrováním textu a zobrazením procent.

## Závěr
Dodržováním tohoto návodu jste se naučili, jak vytvořit dynamický prstencový graf v PowerPointu pomocí knihovny Aspose.Slides pro .NET. Tato výkonná knihovna umožňuje rozsáhlé úpravy, které vám umožní přesně přizpůsobit grafy potřebám vaší prezentace.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}