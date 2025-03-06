---
title: Vymažte konkrétní datové body řady grafů pomocí Aspose.Slides .NET
linktitle: Vymazat konkrétní datové body řady grafů
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak vymazat konkrétní datové body řady grafů v prezentacích PowerPoint pomocí Aspose.Slides pro .NET. Průvodce krok za krokem.
weight: 13
url: /cs/net/additional-chart-features/clear-specific-chart-series-data-points-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vymažte konkrétní datové body řady grafů pomocí Aspose.Slides .NET


Aspose.Slides for .NET je výkonná knihovna, která umožňuje programově pracovat s prezentacemi PowerPoint. V tomto tutoriálu vás provedeme procesem vymazání konkrétních datových bodů řad grafů v prezentaci PowerPoint pomocí Aspose.Slides pro .NET. Na konci tohoto tutoriálu budete schopni snadno manipulovat s datovými body grafu.

## Předpoklady

Než začneme, musíte se ujistit, že máte splněny následující předpoklady:

1.  Knihovna Aspose.Slides for .NET: Měli byste mít nainstalovanou knihovnu Aspose.Slides for .NET. Můžete si jej stáhnout[tady](https://releases.aspose.com/slides/net/).

2. Vývojové prostředí: Měli byste mít vývojové prostředí nastavené pomocí sady Visual Studio nebo jakéhokoli jiného vývojového nástroje .NET.

Nyní, když máte připravené předpoklady, pojďme se ponořit do podrobného průvodce, jak pomocí Aspose.Slides pro .NET vymazat konkrétní datové body řad grafů.

## Importovat jmenné prostory

V kódu C# nezapomeňte importovat potřebné jmenné prostory:

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
```

## Krok 1: Načtěte prezentaci

 Nejprve musíte načíst prezentaci PowerPoint obsahující graf, se kterým chcete pracovat. Nahradit`"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace.

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation(dataDir + "TestChart.pptx"))
{
    // Váš kód je zde
}
```

## Krok 2: Otevřete snímek a graf

Po načtení prezentace budete potřebovat přístup ke snímku a grafu na tomto snímku. V tomto příkladu předpokládáme, že graf je umístěn na prvním snímku (index 0).

```csharp
ISlide slide = pres.Slides[0];
IChart chart = (IChart)slide.Shapes[0];
```

## Krok 3: Vymažte datové body

Nyní projdeme datové body v řadě grafů a vymažeme jejich hodnoty. To účinně odstraní datové body ze série.

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

Úspěšně jste se naučili, jak vyčistit konkrétní datové body řad grafů pomocí Aspose.Slides pro .NET. To může být užitečná funkce, když potřebujete programově manipulovat s daty grafu v prezentacích PowerPoint.

 Pokud máte nějaké dotazy nebo narazíte na nějaké problémy, neváhejte navštívit[Aspose.Slides pro dokumentaci .NET](https://reference.aspose.com/slides/net/) nebo vyhledejte pomoc v[Fórum Aspose.Slides](https://forum.aspose.com/).

## Často kladené otázky

### Mohu používat Aspose.Slides pro .NET s jinými programovacími jazyky?
Aspose.Slides je primárně navržen pro jazyky .NET. Existují však verze dostupné i pro Javu a další platformy.

### Je Aspose.Slides for .NET placená knihovna?
 Ano, Aspose.Slides je komerční knihovna, ale můžete prozkoumat a[zkušební verze zdarma](https://releases.aspose.com/) před nákupem.

### Jak mohu přidat nové datové body do grafu pomocí Aspose.Slides pro .NET?
 Nové datové body můžete přidat vytvořením instancí`IChartDataPoint` a naplnit je požadovanými hodnotami.

### Mohu upravit vzhled grafu v Aspose.Slides?
Ano, vzhled grafů můžete upravit úpravou jejich vlastností, jako jsou barvy, písma a styly.

### Existuje komunita nebo komunita vývojářů pro Aspose.Slides pro .NET?
Ano, můžete se připojit ke komunitě Aspose na jejich fóru pro diskuse, dotazy a sdílení vašich zkušeností.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
