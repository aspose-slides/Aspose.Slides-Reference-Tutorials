---
title: Ověřit rozvržení grafu Přidáno do Slides Java
linktitle: Ověřit rozvržení grafu Přidáno do Slides Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ověření rozložení hlavního grafu v PowerPointu pomocí Aspose.Slides pro Javu. Naučte se programově manipulovat s grafy pro úžasné prezentace.
type: docs
weight: 10
url: /cs/java/data-manipulation/validate-chart-layout-added-java-slides/
---

## Úvod do ověřování rozložení grafu v Aspose.Slides pro Javu

V tomto tutoriálu prozkoumáme, jak ověřit rozložení grafu v prezentaci PowerPoint pomocí Aspose.Slides for Java. Tato knihovna umožňuje programově pracovat s prezentacemi PowerPoint, což usnadňuje manipulaci a ověřování různých prvků, včetně grafů.

## Krok 1: Inicializace prezentace

Nejprve musíme inicializovat objekt prezentace a načíst existující prezentaci v PowerPointu. Nahradit`"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace (`test.pptx` v tomto příkladu).

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## Krok 2: Přidání grafu

 Dále do prezentace přidáme graf. V tomto příkladu přidáváme seskupený sloupcový graf, ale můžete změnit`ChartType` podle potřeby.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## Krok 3: Ověření rozložení grafu

 Nyní ověříme rozložení grafu pomocí`validateChartLayout()` metoda. Tím je zajištěno, že je graf na snímku správně rozložen.

```java
chart.validateChartLayout();
```

## Krok 4: Načtení pozice a velikosti grafu

Po ověření rozložení grafu možná budete chtít získat informace o jeho poloze a velikosti. Můžeme získat skutečné souřadnice X a Y, stejně jako šířku a výšku oblasti grafu.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## Krok 5: Uložení prezentace

 Nakonec si upravenou prezentaci nezapomeňte uložit. V tomto příkladu jej ukládáme jako`Result.pptx`, ale v případě potřeby můžete zadat jiný název souboru.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro ověření rozvržení grafu přidán do Java Slides

```java
// Cesta k adresáři dokumentů.
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

V tomto tutoriálu jsme se ponořili do světa práce s grafy v prezentacích PowerPoint pomocí Aspose.Slides for Java. Probrali jsme základní kroky k ověření rozložení grafu, načtení jeho pozice a velikosti a uložení upravené prezentace. Zde je rychlá rekapitulace:

## FAQ

### Jak změním typ grafu?

 Chcete-li změnit typ grafu, jednoduše jej nahraďte`ChartType.ClusteredColumn` s požadovaným typem grafu v`addChart()` metoda.

### Mohu přizpůsobit data grafu?

Ano, data grafu můžete přizpůsobit přidáním a úpravou datových řad, kategorií a hodnot. Další podrobnosti naleznete v dokumentaci Aspose.Slides.

### Co když chci upravit další vlastnosti grafu?

Můžete přistupovat k různým vlastnostem grafu a upravovat je podle svých požadavků. Prozkoumejte dokumentaci Aspose.Slides, kde najdete komplexní informace o manipulaci s grafy.
