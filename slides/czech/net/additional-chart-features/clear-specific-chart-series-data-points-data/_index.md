---
"description": "Naučte se, jak vymazat konkrétní datové body řady grafů v prezentacích PowerPointu pomocí Aspose.Slides pro .NET. Podrobný návod."
"linktitle": "Vymazat specifické datové body řady grafů"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Vymazání specifických datových bodů řady grafů pomocí Aspose.Slides .NET"
"url": "/cs/net/additional-chart-features/clear-specific-chart-series-data-points-data/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vymazání specifických datových bodů řady grafů pomocí Aspose.Slides .NET


Aspose.Slides pro .NET je výkonná knihovna, která vám umožňuje programově pracovat s prezentacemi v PowerPointu. V tomto tutoriálu vás provedeme procesem mazání konkrétních datových bodů řady grafů v prezentaci v PowerPointu pomocí knihovny Aspose.Slides pro .NET. Po skončení tohoto tutoriálu budete schopni snadno manipulovat s datovými body grafů.

## Předpoklady

Než začneme, musíte se ujistit, že máte splněny následující předpoklady:

1. Knihovna Aspose.Slides pro .NET: Měli byste mít nainstalovanou knihovnu Aspose.Slides pro .NET. Můžete si ji stáhnout [zde](https://releases.aspose.com/slides/net/).

2. Vývojové prostředí: Měli byste mít nastavené vývojové prostředí s Visual Studiem nebo jiným vývojovým nástrojem pro .NET.

Nyní, když máte připravené předpoklady, pojďme se ponořit do podrobného návodu, jak vymazat konkrétní datové body řady grafů pomocí Aspose.Slides pro .NET.

## Importovat jmenné prostory

Ve vašem kódu C# nezapomeňte importovat potřebné jmenné prostory:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Krok 1: Načtení prezentace

Nejprve je třeba načíst prezentaci PowerPointu, která obsahuje graf, se kterým chcete pracovat. Nahraďte `"Your Document Directory"` se skutečnou cestou k souboru prezentace.

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "TestChart.pptx"))
{
    // Váš kód patří sem
}
```

## Krok 2: Přístup ke snímku a grafu

Jakmile načtete prezentaci, budete potřebovat přístup ke snímku a grafu na tomto snímku. V tomto příkladu předpokládáme, že graf se nachází na prvním snímku (index 0).

```csharp
ISlide slide = pres.Slides[0];
IChart chart = (IChart)slide.Shapes[0];
```

## Krok 3: Vymazání datových bodů

Nyní projděme datové body v sérii grafu a vymažeme jejich hodnoty. Tím efektivně odstraníme datové body z řady.

```csharp
foreach (IChartDataPoint dataPoint in chart.ChartData.Series[0].DataPoints)
{
    dataPoint.XValue.AsCell.Value = null;
    dataPoint.YValue.AsCell.Value = null;
}

chart.ChartData.Series[0].DataPoints.Clear();
```

## Krok 4: Uložte prezentaci

Po vymazání konkrétních datových bodů řady grafů byste měli upravenou prezentaci uložit do nového souboru nebo přepsat původní, v závislosti na vašich požadavcích.

```csharp
pres.Save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## Závěr

Úspěšně jste se naučili, jak pomocí Aspose.Slides pro .NET vymazat konkrétní datové body řady grafů. Tato funkce může být užitečná, když potřebujete programově manipulovat s daty grafů ve vašich prezentacích v PowerPointu.

Pokud máte jakékoli dotazy nebo narazíte na nějaké problémy, neváhejte navštívit [Dokumentace k Aspose.Slides pro .NET](https://reference.aspose.com/slides/net/) nebo vyhledejte pomoc v [Fórum Aspose.Slides](https://forum.aspose.com/).

## Často kladené otázky

### Mohu používat Aspose.Slides pro .NET s jinými programovacími jazyky?
Aspose.Slides je primárně navržen pro programovací jazyky .NET. Existují však verze i pro Javu a další platformy.

### Je Aspose.Slides pro .NET placená knihovna?
Ano, Aspose.Slides je komerční knihovna, ale můžete si prohlédnout [bezplatná zkušební verze](https://releases.aspose.com/) před nákupem.

### Jak mohu přidat nové datové body do grafu pomocí Aspose.Slides pro .NET?
Nové datové body můžete přidat vytvořením instancí `IChartDataPoint` a jejich naplnění požadovanými hodnotami.

### Mohu si přizpůsobit vzhled grafu v Aspose.Slides?
Ano, vzhled grafů si můžete přizpůsobit úpravou jejich vlastností, jako jsou barvy, písma a styly.

### Existuje nějaká komunita nebo komunita vývojářů pro Aspose.Slides pro .NET?
Ano, můžete se připojit ke komunitě Aspose na jejich fóru, kde můžete diskutovat, klást otázky a sdílet své zkušenosti.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}