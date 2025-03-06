---
title: Získejte šířku a výšku z oblasti grafu v aplikaci Java Slides
linktitle: Získejte šířku a výšku z oblasti grafu v aplikaci Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak načíst rozměry oblasti grafu v aplikaci Java Slides pomocí Aspose.Slides for Java. Vylepšete své dovednosti v automatizaci aplikace PowerPoint.
weight: 21
url: /cs/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod

Grafy představují účinný způsob vizualizace dat v prezentacích PowerPoint. Někdy můžete potřebovat znát rozměry vykreslované oblasti grafu z různých důvodů, jako je změna velikosti nebo přemístění prvků v grafu. Tato příručka ukáže, jak získat šířku a výšku plochy pozemku pomocí Java a Aspose.Slides for Java.

## Předpoklady

 Než se ponoříme do kódu, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z webu Aspose[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Nastavení prostředí

Ujistěte se, že máte knihovnu Aspose.Slides for Java přidanou do vašeho projektu Java. Můžete to udělat zahrnutím knihovny do závislostí vašeho projektu nebo ručním přidáním souboru JAR.

## Krok 2: Vytvoření prezentace v PowerPointu

Začněme vytvořením powerpointové prezentace a přidáním snímku do ní. To bude sloužit jako kontejner pro náš graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Nahradit`"Your Document Directory"` s cestou k adresáři s dokumenty.

## Krok 3: Přidání grafu

Nyní na snímek přidáme seskupený sloupcový graf. Ověříme také rozložení grafu.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Tento kód vytvoří seskupený sloupcový graf na pozici (100, 100) s rozměry (500, 350).

## Krok 4: Získání rozměrů plochy grafu

K načtení šířky a výšky oblasti grafu můžeme použít následující kód:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 A teď ty proměnné`x`, `y`, `w` , a`h` obsahovat příslušné hodnoty pro souřadnici X, souřadnici Y, šířku a výšku oblasti grafu.

## Krok 5: Uložení prezentace

Nakonec uložte prezentaci s grafem.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Nezapomeňte vyměnit`"Chart_out.pptx"` s požadovaným názvem výstupního souboru.

## Kompletní zdrojový kód pro získání šířky a výšky z oblasti grafu v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Uložit prezentaci s grafem
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

tomto článku jsme se zabývali tím, jak získat šířku a výšku oblasti grafu v aplikaci Java Slides pomocí Aspose.Slides for Java API. Tyto informace mohou být cenné, když potřebujete dynamicky upravit rozvržení grafů v prezentacích PowerPoint.

## FAQ

### Jak mohu změnit typ grafu na něco jiného než seskupené sloupce?

 Typ grafu můžete změnit nahrazením`ChartType.ClusteredColumn` s požadovaným výčtem typu grafu, jako je např`ChartType.Line` nebo`ChartType.Pie`.

### Mohu upravit další vlastnosti grafu?

Ano, pomocí rozhraní Aspose.Slides for Java API můžete upravit různé vlastnosti grafu, jako jsou data, štítky a formátování. Další podrobnosti naleznete v dokumentaci.

### Je Aspose.Slides for Java vhodný pro profesionální automatizaci PowerPointu?

Ano, Aspose.Slides for Java je výkonná knihovna pro automatizaci úloh aplikace PowerPoint v aplikacích Java. Poskytuje komplexní funkce pro práci s prezentacemi, snímky, tvary, grafy a dalšími.

### Jak se mohu dozvědět více o Aspose.Slides pro Java?

 Rozsáhlou dokumentaci a příklady můžete najít na stránce dokumentace Aspose.Slides for Java[tady](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
