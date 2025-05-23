---
"date": "2025-04-15"
"description": "Naučte se, jak vytvářet a upravovat grafy pomocí Aspose.Slides pro .NET, včetně zobrazení procent jako popisků dat. Postupujte podle tohoto podrobného návodu."
"title": "Jak vytvářet a upravovat grafy pomocí Aspose.Slides .NET a zobrazovat procenta jako popisky"
"url": "/cs/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvářet a upravovat grafy pomocí Aspose.Slides .NET: Zobrazení procent jako popisků

## Zavedení

Efektivní prezentace dat je v mnoha oblastech klíčová a grafy hrají zásadní roli tím, že převádějí složité informace do jasných vizuální podob. Vytvoření dokonalého grafu zahrnuje úkoly přizpůsobení, jako je zobrazení procent na popiscích – úkol, který je snazší díky knihovně Aspose.Slides pro .NET. Tato knihovna zjednodušuje proces vytváření a úpravy grafů v prezentacích PowerPointu.

tomto tutoriálu se naučíte, jak pomocí Aspose.Slides pro .NET vytvořit skládaný sloupcový graf od nuly a přizpůsobit ho zobrazením procentuálních hodnot jako popisků dat. Dodržením těchto kroků vylepšíte své snímky přesnými a vizuálně atraktivními reprezentacemi dat.

**Co se naučíte:**
- Inicializace Aspose.Slides pro .NET
- Vytvoření skládaného sloupcového grafu
- Výpočet a zobrazení procent na popiscích dat
- Optimalizace osvědčených postupů pro výkon grafů

Než se pustíme do implementace, ujistěte se, že máte vše připravené k zahájení.

## Předpoklady

Abyste mohli tento tutoriál efektivně sledovat, ujistěte se, že máte:
- **Sada SDK pro .NET Core** nainstalovaný na vašem počítači.
- Základní znalost vývoje aplikací v C# a .NET.
- Visual Studio nebo podobné IDE pro psaní a spouštění kódu C#.

K vytváření grafů budete potřebovat Aspose.Slides pro .NET, proto se ujistěte, že je nastavený dle níže uvedeného popisu.

## Nastavení Aspose.Slides pro .NET

Aspose.Slides pro .NET je výkonná knihovna, která umožňuje programově pracovat s prezentacemi v PowerPointu. Zde je návod, jak ji přidat do projektu:

### Instalace

**Rozhraní příkazového řádku .NET:**
```bash
dotnet add package Aspose.Slides
```

**Konzola Správce balíčků:**
```powershell
Install-Package Aspose.Slides
```

**Uživatelské rozhraní Správce balíčků NuGet:** 
- Otevřete Správce balíčků NuGet a vyhledejte „Aspose.Slides“. Nainstalujte nejnovější verzi.

### Získání licence

Chcete-li plně využít Aspose.Slides, začněte s bezplatnou zkušební verzí. Pro delší používání zvažte pořízení dočasné licence nebo zakoupení nové od [Aspose](https://purchase.aspose.com/buy)Řiďte se jejich pokyny k nastavení licence v prostředí vašeho projektu.

### Základní inicializace

Po instalaci inicializujte `Presentation` třída pro zahájení tvorby snímků:
```csharp
using Aspose.Slides;

// Inicializace instance třídy Presentation
tPresentation presentation = new Presentation();
```

Nyní se přesuňme k implementaci funkce pro vytváření a přizpůsobení grafů pomocí Aspose.Slides pro .NET.

## Průvodce implementací

### Vytvořte skládaný sloupcový graf

Naším cílem je vytvořit skládaný sloupcový graf a přizpůsobit ho zobrazením procent jako popisků dat. Postupujte takto:

#### Inicializace prezentace

Začněte vytvořením instance `Presentation`:
```csharp
using Aspose.Slides;

// Inicializace instance třídy Presentation
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Přidání grafu do snímku

Přidejte na první snímek skládaný sloupcový graf v zadaných souřadnicích a rozměrech:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Tato čára vytváří `StackedColumn` graf na pozici (20, 20) se šířkou a výškou 400.

#### Výpočet celkových hodnot pro procentuální výpočet

Pro zobrazení procent vypočítejte celkovou hodnotu pro každou kategorii napříč všemi sériemi:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Sečtěte hodnoty všech sérií pro každou kategorii
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Přizpůsobení popisků dat pro zobrazení procentuálních hodnot

Dále projděte každou sérii a upravte popisky dat:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Vypočítat procento
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Jasný text, aby se zabránilo překrývání
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Konfigurace formátu popisků pro skrytí výchozích popisků dat
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Tato část vypočítá procento pro každý datový bod a nastaví jej jako vlastní popisek, čímž zajistí, že se nepřekrývá s výchozími popisky.

#### Uložit prezentaci

Nakonec si prezentaci uložte, abyste si mohli prohlédnout výsledek:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Praktické aplikace

Zobrazování procent v grafech může být obzvláště užitečné v situacích, jako jsou:
1. **Finanční výkaznictví:** Zobrazte výnosy z portfolia nebo investiční výnosy v procentech.
2. **Analýza prodeje:** Zobrazte data o podílu na trhu v procentech pro zvýraznění výkonnosti v různých regionech.
3. **Výsledky průzkumu:** Pro lepší vizuální srovnání zobrazte odpovědi z průzkumu v procentech.
4. **Řízení projektu:** Pro ilustraci alokace zdrojů použijte koláčové grafy s procenty.
5. **Školství:** Vysvětlete statistické pojmy pomocí srozumitelných vizuálních pomůcek založených na procentech.

Integrace těchto přizpůsobených grafů do systémů, jako je CRM nebo ERP, může vylepšit dashboardy a reporty, což napomáhá rozhodovacím procesům.

## Úvahy o výkonu

Při práci s Aspose.Slides pro .NET, zejména s velkými datovými sadami:
- **Správa paměti:** Pro uvolnění paměti řádně zlikvidujte prezentační objekty. Použijte `using` prohlášení, kde je to relevantní.
- **Efektivní zpracování dat:** Provádějte výpočty mimo smyčky, pokud je to možné, abyste snížili výpočetní režii.
- **Vyvažování zátěže:** U webových aplikací zajistěte, aby byly serverové prostředky dostatečně zřízeny pro souběžné požadavky na generování grafů.

## Závěr

Tento tutoriál se zabýval vytvářením a úpravou grafů pomocí Aspose.Slides pro .NET zobrazováním procentuálních hodnot jako popisků. Zvládnutí těchto technik vám umožní vylepšit vaše prezentace detailními a vizuálně atraktivními reprezentacemi dat.

Jako další krok prozkoumejte další typy grafů a možnosti přizpůsobení dostupné v Aspose.Slides. Experimentujte s různými datovými sadami a proměňte je v působivé vizuály, které jasně sdělují poznatky.

## Sekce Často kladených otázek

**Q1: Jak mám zpracovat velké datové sady při vytváření grafů pomocí Aspose.Slides pro .NET?**
A1: Pro velké datové sady optimalizujte výpočty a používejte efektivní techniky správy paměti. Rozdělte úlohy zpracování, abyste předešli přetížení paměti.

**Q2: Mohu použít Aspose.Slides pro .NET ve webové aplikaci?**
A2: Ano, lze jej integrovat do aplikací ASP.NET. Pro optimální výkon zajistěte správnou alokaci serverových zdrojů.

**Q3: Je možné exportovat grafy vytvořené pomocí Aspose.Slides do jiných formátů?**
A3: Rozhodně! Prezentace obsahující vaše vlastní grafy můžete exportovat do různých formátů, jako je PDF a obrazové soubory, pomocí funkcí knihovny.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}