---
title: Vlastnosti písma pro graf v Java Slides
linktitle: Vlastnosti písma pro graf v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vylepšete vlastnosti písma grafu v Java Slides pomocí Aspose.Slides pro Java. Přizpůsobte si velikost, styl a barvu písma pro působivé prezentace.
weight: 11
url: /cs/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod do vlastností písma pro graf v Java Slides

Tato příručka vás provede nastavením vlastností písma pro graf v aplikaci Java Slides pomocí Aspose.Slides. Můžete upravit velikost písma a vzhled textu grafu, abyste zvýšili vizuální přitažlivost svých prezentací.

## Předpoklady

 Než začnete, ujistěte se, že máte Aspose.Slides for Java API integrované do vašeho projektu. Pokud jste tak ještě neučinili, můžete si jej stáhnout z[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).

## Krok 1: Vytvořte prezentaci

Nejprve vytvořte novou prezentaci pomocí následujícího kódu:

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidejte graf

Nyní do prezentace přidáme seskupený sloupcový graf:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Zde přidáváme na první snímek seskupený sloupcový graf na souřadnicích (100, 100) o šířce 500 jednotek a výšce 400 jednotek.

## Krok 3: Přizpůsobte vlastnosti písma

Dále přizpůsobíme vlastnosti písma grafu. V tomto příkladu nastavujeme velikost písma na 20 pro veškerý text grafu:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Tento kód nastaví velikost písma na 20 bodů pro veškerý text v grafu.

## Krok 4: Zobrazit štítky dat

Na grafu můžete také zobrazit štítky dat pomocí následujícího kódu:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Tento řádek kódu umožňuje popisky dat pro první řadu v grafu, zobrazující hodnoty ve sloupcích grafu.

## Krok 5: Uložte prezentaci

Nakonec uložte prezentaci s vlastními vlastnostmi písma grafu:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Tento kód uloží prezentaci do zadaného adresáře s názvem "FontPropertiesForChart.pptx."

## Kompletní zdrojový kód pro vlastnosti písma pro graf v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

 tomto kurzu jste se naučili, jak upravit vlastnosti písma pro graf v aplikaci Java Slides pomocí Aspose.Slides for Java. Tyto techniky můžete použít k vylepšení vzhledu vašich grafů a prezentací. Prozkoumejte další možnosti v[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).

## FAQ

### Jak mohu změnit barvu písma?

 Chcete-li změnit barvu písma textu grafu, použijte`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , nahrazovat`Color.RED` s požadovanou barvou.

### Mohu změnit styl písma (tučné, kurzíva atd.)?

 Ano, můžete změnit styl písma. Použití`chart.getTextFormat().getPortionFormat().setFontBold(true);` aby bylo písmo tučné. Podobně můžete použít`setFontItalic(true)` aby to bylo kurzívou.

### Jak přizpůsobím vlastnosti písma pro konkrétní prvky grafu?

Chcete-li přizpůsobit vlastnosti písma pro konkrétní prvky grafu, jako jsou popisky os nebo text legendy, můžete k těmto prvkům přistupovat a nastavit jejich vlastnosti písma pomocí podobných metod, jak je uvedeno výše.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
