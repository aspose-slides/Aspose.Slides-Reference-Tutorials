---
"description": "Vylepšete vlastnosti písma grafů v Javě pomocí Aspose.Slides pro Javu. Přizpůsobte si velikost, styl a barvu písma pro působivé prezentace."
"linktitle": "Vlastnosti písma pro graf v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vlastnosti písma pro graf v Javě Slides"
"url": "/cs/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vlastnosti písma pro graf v Javě Slides


## Úvod do vlastností písma pro grafy v Javě Slides

Tato příručka vás provede nastavením vlastností písma pro graf v Java Slides pomocí Aspose.Slides. Velikost písma a vzhled textu grafu si můžete přizpůsobit a vylepšit tak vizuální atraktivitu vašich prezentací.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu integrované rozhraní Aspose.Slides pro Java API. Pokud tak ještě neučiníte, můžete si jej stáhnout z [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/).

## Krok 1: Vytvořte prezentaci

Nejprve vytvořte novou prezentaci pomocí následujícího kódu:

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání grafu

Nyní si do prezentace přidejme seskupený sloupcový graf:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Zde přidáváme na první snímek na souřadnicích (100, 100) klastrovaný sloupcový graf o šířce 500 jednotek a výšce 400 jednotek.

## Krok 3: Úprava vlastností písma

Dále upravíme vlastnosti písma grafu. V tomto příkladu nastavujeme velikost písma na 20 pro veškerý text grafu:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Tento kód nastaví velikost písma na 20 bodů pro veškerý text v grafu.

## Krok 4: Zobrazení popisků dat

Popisky dat v grafu můžete také zobrazit pomocí následujícího kódu:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Tento řádek kódu povoluje popisky dat pro první sérii v grafu a zobrazuje hodnoty ve sloupcích grafu.

## Krok 5: Uložte prezentaci

Nakonec uložte prezentaci s upravenými vlastnostmi písma grafu:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Tento kód uloží prezentaci do zadaného adresáře s názvem souboru „FontPropertiesForChart.pptx“.

## Kompletní zdrojový kód pro vlastnosti písma pro graf v Javě Slides

```java
// Cesta k adresáři s dokumenty.
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

tomto tutoriálu jste se naučili, jak přizpůsobit vlastnosti písma pro graf v Java Slides pomocí Aspose.Slides pro Javu. Tyto techniky můžete použít k vylepšení vzhledu vašich grafů a prezentací. Prozkoumejte další možnosti v [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/).

## Často kladené otázky

### Jak mohu změnit barvu písma?

Chcete-li změnit barvu písma textu grafu, použijte `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, nahrazující `Color.RED` s požadovanou barvou.

### Mohu změnit styl písma (tučné, kurzíva atd.)?

Ano, můžete změnit styl písma. Použijte `chart.getTextFormat().getPortionFormat().setFontBold(true);` pro tučné písmo. Podobně můžete použít `setFontItalic(true)` aby to bylo kurzíva.

### Jak mohu přizpůsobit vlastnosti písma pro konkrétní prvky grafu?

Chcete-li přizpůsobit vlastnosti písma pro konkrétní prvky grafu, jako jsou popisky os nebo text legendy, můžete k těmto prvkům přistupovat a nastavit jejich vlastnosti písma pomocí podobných metod, jak je uvedeno výše.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}