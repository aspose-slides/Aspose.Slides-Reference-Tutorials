---
"date": "2025-04-15"
"description": "Naučte se, jak vytvářet spojnicové grafy se značkami pomocí Aspose.Slides pro .NET. Tato podrobná příručka zahrnuje nastavení, vytváření grafů a přizpůsobení."
"title": "Jak vytvořit spojnicový graf se značkami v C# pomocí Aspose.Slides pro .NET"
"url": "/cs/net/charts-graphs/create-line-chart-markers-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit spojnicový graf se značkami v C# pomocí Aspose.Slides pro .NET

## Zavedení
Vytváření vizuálně poutavých a informativních spojnicových grafů je nezbytné pro efektivní prezentaci dat v C#. **Aspose.Slides pro .NET** zjednodušuje proces přidávání profesionálně vypadajících grafů, včetně těch se značkami. Tento tutoriál vás provede vytvořením spojnicového grafu s výchozími značkami pomocí Aspose.Slides pro .NET.

V tomto tutoriálu se naučíte:
- Nastavení prostředí pro použití Aspose.Slides pro .NET.
- Vytvoření a přizpůsobení prezentace s čárovým grafem, který obsahuje značky.
- Konfigurace vlastností grafu, jako jsou kategorie, řady a datové body.
- Uložení finálního souboru prezentace.

Začněme tím, že si projdeme předpoklady, které jsou nutné před implementací našeho řešení.

## Předpoklady
Než začnete, ujistěte se, že máte následující:
- **Požadované knihovny:** Aspose.Slides pro .NET nainstalovaný ve vašem vývojovém prostředí přes NuGet.
- **Požadavky na nastavení prostředí:** Funkční vývojové prostředí C#, jako je Visual Studio a .NET framework nainstalované na vašem počítači.
- **Předpoklady znalostí:** Základní znalost programování v C# a znalost programově tvorby prezentací.

## Nastavení Aspose.Slides pro .NET
### Informace o instalaci
Chcete-li začít používat Aspose.Slides pro .NET, přidejte jej do svého projektu jednou z následujících metod:

**Použití .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Prostřednictvím konzole Správce balíčků ve Visual Studiu:**
```powershell
Install-Package Aspose.Slides
```

**Uživatelské rozhraní Správce balíčků NuGet:**
- Otevřete své řešení v aplikaci Visual Studio.
- Přejděte na „Spravovat balíčky NuGet pro řešení...“
- Vyhledejte „Aspose.Slides“ a nainstalujte nejnovější verzi.

### Získání licence
Před použitím Aspose.Slides si získejte zkušební verzi nebo si zakupte licenci:
1. **Bezplatná zkušební verze:** Návštěva [Stránka s bezplatnou zkušební verzí Aspose](https://releases.aspose.com/slides/net/) začít rychle.
2. **Dočasná licence:** Pro rozšířený přístup navštivte [Stránka s dočasnou licencí](https://purchase.aspose.com/temporary-license/).
3. **Nákup:** Chcete-li používat Aspose.Slides v produkčním prostředí, zakupte si licenci na adrese [Nákup Aspose](https://purchase.aspose.com/buy).

### Základní inicializace
Po nastavení projektu a získání potřebných licencí inicializujte Aspose.Slides takto:
```csharp
using Aspose.Slides;
// Vytvoření instance třídy Presentation
Presentation pres = new Presentation();
```
Nyní, když jsme si nastavili prostředí, pojďme vytvořit spojnicový graf se značkami.

## Průvodce implementací
### Vytvoření spojnicového grafu se značkami
V této části se dozvíte všechny kroky potřebné k vytvoření a konfiguraci spojnicového grafu s výchozími značkami ve vaší prezentaci pomocí Aspose.Slides pro .NET.

#### Krok 1: Vytvořte prezentační objekt
Začněte vytvořením instance `Presentation` třída:
```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
```
Zde máme přístup k prvnímu snímku v nově vytvořené prezentaci.

#### Krok 2: Přidání spojnicového grafu se značkami
Dále přidejte na snímek spojnicový graf se značkami:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
```
Tento kód přidává nový graf typu `LineWithMarkers` na souřadnicích `(10, 10)` s rozměry `400x400`.

#### Krok 3: Vymazání existujících sérií a kategorií
Před přidáním dat vymažte všechny existující řady nebo kategorie:
```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```
Díky tomu začíná náš graf s čistým štítem.

#### Krok 4: Konfigurace sešitu dat grafu
Přístup k `ChartDataWorkbook` pro správu dat v grafu:
```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```
Tento objekt je klíčový pro správu buněk obsahujících data řad a kategorií.

#### Krok 5: Přidání sérií a kategorií
Přidejte do grafu novou řadu a naplňte ji datovými body:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
IChartSeries series = chart.ChartData.Series[0];

// Definujte kategorie a odpovídající datové body
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "C1"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 1, 24));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "C2"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 1, 23));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "C3"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 1, -10));
chart.ChartData.Categories.Add(fact.GetCell(0, 4, 0, "C4"));

// Přidání nulového datového bodu pro demonstraci zpracování chybějících hodnot
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 1, (double?)null));
```
Zde naplníme graf kategoriemi a odpovídajícími daty řad. Všimněte si, jak `null` Hodnota je zpracována jako demonstrace.

#### Krok 6: Přidání další série
Pro přidání další série postup opakujte:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 2, "Series 2"), chart.Type);
IChartSeries series2 = chart.ChartData.Series[1];

series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 2, 30));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 2, 10));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 2, 60));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 2, 40));
```

#### Krok 7: Povolení a konfigurace legendy
Pro lepší čitelnost povolte legendu grafu:
```csharp
chart.HasLegend = true;
chart.Legend.Overlay = false;
```
Tím je zajištěno, že legenda bude viditelná a nebude překrývat graf.

#### Krok 8: Uložte prezentaci
Nakonec uložte prezentaci s nově přidaným grafem:
```csharp
pres.Save("DefaultMarkersInChart.pptx");
}
```
### Tipy pro řešení problémů
- **Chyby vázání dat:** Zajistěte, aby datové body správně odpovídaly kategoriím.
- **Graf se nezobrazuje:** Ověřte, že `chart.HasLegend` a další vlastnosti jsou nastaveny odpovídajícím způsobem.

## Praktické aplikace
1. **Obchodní zprávy:** Pro sledování prodejní výkonnosti v čase používejte spojnicové grafy se značkami, které zobrazují trendy v měsíčních tržbách.
2. **Finanční analýza:** Vizualizujte pohyby cen akcií pomocí výchozích značek pro zvýraznění vrcholů a minim.
3. **Vědecký výzkum:** Prezentujte experimentální výsledky, u kterých je pro analýzu nutné jasné vymezení datových bodů.

## Úvahy o výkonu
- Optimalizujte omezením počtu datových řad a kategorií při práci s velkými datovými sadami.
- Používejte techniky správy paměti, jako je například rychlé odstraňování objektů v .NET, abyste snížili využití zdrojů.

## Závěr
V tomto tutoriálu jste se naučili, jak vytvořit spojnicový graf se značkami pomocí Aspose.Slides pro .NET. Dodržením těchto kroků můžete vylepšit své prezentace detailními a profesionálně vypadajícími grafy. Zvažte prozkoumání dalších funkcí Aspose.Slides, které dále obohatí vaše prezentace.

### Další kroky
- Experimentujte s různými typy grafů dostupnými v Aspose.Slides.
- Přizpůsobte si vzhled grafů pro lepší vizuální efekt.
- Pro pokročilejší funkce si prohlédněte další dokumentaci k Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}