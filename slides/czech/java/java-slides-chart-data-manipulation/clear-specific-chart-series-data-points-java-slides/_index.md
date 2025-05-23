---
"description": "Naučte se, jak v aplikaci Java Slides s Aspose.Slides pro Javu vymazat konkrétní datové body ze série grafů. Podrobný návod se zdrojovým kódem pro efektivní správu vizualizace dat."
"linktitle": "Vymazat specifická data datových bodů řady grafů v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vymazat specifická data datových bodů řady grafů v Javě Slides"
"url": "/cs/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vymazat specifická data datových bodů řady grafů v Javě Slides


## Úvod do mazání datových bodů specifických sérií grafů v Javě (prezentace)

V tomto tutoriálu vás provedeme procesem odstranění konkrétních datových bodů z grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. To může být užitečné, když chcete z grafu odstranit určité datové body za účelem aktualizace nebo úpravy vizualizace dat.

## Předpoklady

Než začneme, ujistěte se, že máte ve svém projektu integrovanou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Načtení prezentace

Nejprve musíme načíst prezentaci PowerPointu, která obsahuje graf, který chcete upravit. Nahraďte `"Your Document Directory"` se skutečnou cestou k souboru prezentace.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## Krok 2: Přístup k grafu

Dále se k grafu dostaneme ze snímku. V tomto příkladu předpokládáme, že graf je na prvním snímku (snímek s indexem 0). Index snímku můžete podle potřeby upravit.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## Krok 3: Vymazání konkrétních datových bodů

Nyní projdeme datovými body první série grafu a vymažeme jejich hodnoty X a Y.

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

Tento kód prochází každý datový bod v první sérii (index 0) a nastavuje hodnoty X i Y na `null`, čímž se efektivně vyčistí datové body.

## Krok 4: Odstranění vymazaných datových bodů

Abychom zajistili, že vymazané datové body budou z řady odstraněny, vymažeme celou řadu.

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

Tento kód vymaže všechny datové body z první série.

## Krok 5: Uložení upravené prezentace

Nakonec upravenou prezentaci uložíme do nového souboru.

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro vyčištění specifických datových bodů řady grafů v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
try
{
	ISlide sl = pres.getSlides().get_Item(0);
	IChart chart = (IChart) sl.getShapes().get_Item(0);
	for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints())
	{
		dataPoint.getXValue().getAsCell().setValue(null);
		dataPoint.getYValue().getAsCell().setValue(null);
	}
	chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
	pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V této příručce jste se naučili, jak vymazat konkrétní datové body z grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. To může být užitečné, když potřebujete dynamicky aktualizovat nebo upravovat data grafu ve vašich aplikacích Java. Máte-li další otázky nebo potřebujete-li další pomoc, podívejte se prosím na [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/).

## Často kladené otázky

### Jak mohu odstranit konkrétní datové body ze série grafů v Aspose.Slides pro Javu?

Chcete-li v Aspose.Slides pro Javu odstranit konkrétní datové body z grafické série, postupujte takto:

1. Načtěte prezentaci.
2. Přístup k grafu na snímku.
3. Projděte datovými body požadované řady a vymažte jejich hodnoty X a Y.
4. Vymazáním celé série odstraníte vymazané datové body.
5. Uložte upravenou prezentaci.

### Mohu vymazat datové body z více řad ve stejném grafu?

Ano, datové body z více řad ve stejném grafu můžete vymazat iterací datových bodů každé řady a jejich jednotlivým vymazáním.

### Existuje způsob, jak vymazat datové body na základě podmínky nebo kritérií?

Ano, datové body můžete vymazat na základě podmínky přidáním podmíněné logiky do smyčky, která iteruje datovými body. Můžete zkontrolovat hodnoty datových bodů a na základě vašich kritérií rozhodnout, zda je vymazat či nikoli.

### Jak mohu přidat nové datové body do série grafů pomocí Aspose.Slides pro Javu?

Chcete-li do grafové série přidat nové datové body, můžete použít `addDataPoint` metoda řady. Jednoduše vytvořte nové datové body a přidejte je do řady pomocí této metody.

### Kde najdu více informací o Aspose.Slides pro Javu?

Podrobnou dokumentaci a příklady naleznete v [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}