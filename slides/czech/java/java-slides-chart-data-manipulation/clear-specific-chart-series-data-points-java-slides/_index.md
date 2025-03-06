---
title: Vymazat data konkrétních datových bodů řady grafů v Java Slides
linktitle: Vymazat data konkrétních datových bodů řady grafů v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak vymazat konkrétní datové body ze série grafů v Java Slides pomocí Aspose.Slides for Java. Podrobný průvodce se zdrojovým kódem pro efektivní správu vizualizace dat.
weight: 15
url: /cs/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod k vymazání dat datových bodů konkrétní řady grafů v Java Slides

tomto tutoriálu vás provedeme procesem vymazání konkrétních datových bodů ze série grafů v prezentaci PowerPoint pomocí Aspose.Slides for Java. To může být užitečné, když chcete z grafu odstranit určité datové body a aktualizovat nebo upravit vizualizaci dat.

## Předpoklady

 Než začneme, ujistěte se, že máte do projektu integrovanou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Načtěte prezentaci

 Nejprve musíme načíst prezentaci PowerPoint obsahující graf, který chcete upravit. Nahradit`"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## Krok 2: Přístup k grafu

Dále přistoupíme k grafu ze snímku. V tomto příkladu předpokládáme, že graf je na prvním snímku (snímek na indexu 0). Index snímku můžete upravit podle potřeby.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## Krok 3: Vymažte specifické datové body

Nyní projdeme datové body první řady grafu a vymažeme jejich hodnoty X a Y.

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

 Tento kód prochází každý datový bod v první řadě (index 0) a nastavuje hodnoty X i Y na`null`efektivně vymaže datové body.

## Krok 4: Odstraňte vymazané datové body

Abychom zajistili, že vymazané datové body budou ze série odstraněny, vymažeme celou sérii.

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

Tento kód vymaže všechny datové body z první řady.

## Krok 5: Uložte upravenou prezentaci

Nakonec upravenou prezentaci uložíme do nového souboru.

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro vymazání dat datových bodů řady grafů v Java Slides

```java
// Cesta k adresáři dokumentů.
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

 V této příručce jste se naučili, jak vymazat konkrétní datové body z řady grafů v prezentaci PowerPoint pomocí Aspose.Slides for Java. To může být užitečné, když potřebujete dynamicky aktualizovat nebo upravit data grafu v aplikacích Java. Máte-li jakékoli další otázky nebo potřebujete další pomoc, přejděte na stránku[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).

## FAQ

### Jak mohu odstranit konkrétní datové body ze série grafů v Aspose.Slides pro Java?

Chcete-li odebrat konkrétní datové body z řady grafů v Aspose.Slides pro Java, postupujte takto:

1. Načtěte prezentaci.
2. Otevřete graf na snímku.
3. Iterujte datové body požadované řady a vymažte jejich hodnoty X a Y.
4. Chcete-li odstranit vymazané datové body, vymažte celou řadu.
5. Uložte upravenou prezentaci.

### Mohu vymazat datové body z více řad ve stejném grafu?

Ano, datové body z více řad ve stejném grafu můžete vymazat tak, že projdete datové body každé řady a vymažete je jednotlivě.

### Existuje způsob, jak vymazat datové body na základě podmínky nebo kritérií?

Ano, datové body můžete vymazat na základě podmínky přidáním podmíněné logiky do smyčky, která prochází datovými body. Můžete zkontrolovat hodnoty datových bodů a rozhodnout se, zda je vymažete nebo ne, na základě vašich kritérií.

### Jak mohu přidat nové datové body do řady grafů pomocí Aspose.Slides pro Java?

 Chcete-li přidat nové datové body do řady grafů, můžete použít`addDataPoint` metoda série. Jednoduše vytvořte nové datové body a přidejte je do série pomocí této metody.

### Kde najdu více informací o Aspose.Slides for Java?

 Komplexní dokumentaci a příklady naleznete v[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
