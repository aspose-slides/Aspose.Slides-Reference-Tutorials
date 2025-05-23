---
"description": "Zvládněte validaci rozvržení grafů v PowerPointu s Aspose.Slides pro Javu. Naučte se programově manipulovat s grafy pro úžasné prezentace."
"linktitle": "Ověření rozvržení grafu přidaného do Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Ověření rozvržení grafu přidaného do Java Slides"
"url": "/cs/java/data-manipulation/validate-chart-layout-added-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ověření rozvržení grafu přidaného do Java Slides


## Úvod do ověřování rozvržení grafu v Aspose.Slides pro Javu

V tomto tutoriálu se podíváme na to, jak ověřit rozvržení grafu v prezentaci PowerPoint pomocí knihovny Aspose.Slides pro Javu. Tato knihovna umožňuje programově pracovat s prezentacemi PowerPoint, což usnadňuje manipulaci a ověřování různých prvků, včetně grafů.

## Krok 1: Inicializace prezentace

Nejprve musíme inicializovat objekt prezentace a načíst existující prezentaci v PowerPointu. Nahraďte `"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace (`test.pptx` v tomto příkladu).

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 2: Přidání grafu

Dále do prezentace přidáme graf. V tomto příkladu přidáváme klastrovaný sloupcový graf, ale můžete změnit `ChartType` podle potřeby.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Krok 3: Ověření rozvržení grafu

Nyní ověříme rozvržení grafu pomocí `validateChartLayout()` metoda. Tím je zajištěno správné uspořádání grafu na snímku.

```java
chart.validateChartLayout();
```

## Krok 4: Načtení pozice a velikosti grafu

Po ověření rozvržení grafu můžete chtít získat informace o jeho poloze a velikosti. Můžeme získat skutečné souřadnice X a Y, stejně jako šířku a výšku vykreslované oblasti grafu.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Krok 5: Uložení prezentace

Nakonec nezapomeňte upravenou prezentaci uložit. V tomto příkladu ji ukládáme jako `Result.pptx`, ale v případě potřeby můžete zadat jiný název souboru.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro ověření rozvržení grafu přidán do Java Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Ukládání prezentace
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se ponořili do světa práce s grafy v prezentacích PowerPointu pomocí Aspose.Slides pro Javu. Probrali jsme základní kroky pro ověření rozvržení grafu, načtení jeho pozice a velikosti a uložení upravené prezentace. Zde je stručné shrnutí:

## Často kladené otázky

### Jak změním typ grafu?

Chcete-li změnit typ grafu, jednoduše nahraďte `ChartType.ClusteredColumn` požadovaným typem grafu v `addChart()` metoda.

### Mohu si přizpůsobit data grafu?

Ano, data grafu si můžete přizpůsobit přidáním a úpravou datových řad, kategorií a hodnot. Další podrobnosti naleznete v dokumentaci k Aspose.Slides.

### Co když chci upravit další vlastnosti grafu?

Můžete přistupovat k různým vlastnostem grafu a přizpůsobovat je podle svých požadavků. Prostudujte si dokumentaci k Aspose.Slides, kde najdete komplexní informace o manipulaci s grafy.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}