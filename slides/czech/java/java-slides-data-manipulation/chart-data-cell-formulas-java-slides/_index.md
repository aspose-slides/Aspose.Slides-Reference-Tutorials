---
title: Graf vzorců datových buněk v Java Slides
linktitle: Graf vzorců datových buněk v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit vzorce datových buněk grafu v prezentacích Java PowerPoint pomocí Aspose.Slides pro Java. Vytvářejte dynamické grafy se vzorci.
weight: 11
url: /cs/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod do vzorců datových buněk grafu v Aspose.Slides pro Java

V tomto tutoriálu prozkoumáme, jak pracovat se vzorci datových buněk grafu pomocí Aspose.Slides pro Java. Pomocí Aspose.Slides můžete vytvářet a manipulovat s grafy v prezentacích PowerPoint, včetně nastavení vzorců pro datové buňky.

## Předpoklady

 Než začnete, ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvořte prezentaci v PowerPointu

Nejprve vytvoříme novou PowerPoint prezentaci a přidáme do ní graf.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Přidejte graf na první snímek
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Získejte sešit pro data grafu
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Pokračujte v operacích s datovými buňkami
    // ...
    
    // Uložte prezentaci
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Krok 2: Nastavte vzorce pro datové buňky

Nyní nastavíme vzorce pro konkrétní datové buňky v grafu. V tomto příkladu nastavíme vzorce pro dvě různé buňky.

### Buňka 1: Použití notace A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Ve výše uvedeném kódu jsme nastavili vzorec pro buňku B2 pomocí notace A1. Vzorec vypočítá součet buněk F2 až H5 a k výsledku přidá 1.

### Buňka 2: Použití zápisu R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Zde nastavíme vzorec pro buňku C2 pomocí zápisu R1C1. Vzorec vypočítá maximální hodnotu v rozsahu R2C6 až R5C8 a poté ji vydělí 3.

## Krok 3: Vypočítejte vzorce

Po nastavení vzorců je nezbytné je vypočítat pomocí následujícího kódu:

```java
workbook.calculateFormulas();
```

Tento krok zajistí, že graf bude odrážet aktualizované hodnoty založené na vzorcích.

## Krok 4: Uložte prezentaci

Nakonec upravenou prezentaci uložte do souboru.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro vzorce datových buněk grafu v Java Slides

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak pracovat se vzorci datových buněk grafu v Aspose.Slides pro Java. Probrali jsme vytvoření prezentace v PowerPointu, přidání grafu, nastavení vzorců pro datové buňky, výpočet vzorců a uložení prezentace. Nyní můžete tyto funkce využít k vytváření dynamických a datově řízených grafů ve vašich prezentacích.

## Nejčastější dotazy

### Jak přidám graf na konkrétní snímek?

 Chcete-li přidat graf na konkrétní snímek, můžete použít`getSlides().get_Item(slideIndex)` pro přístup k požadovanému snímku a poté použijte`addChart` způsob přidání grafu.

### Mohu v datových buňkách používat různé typy vzorců?

Ano, ve vzorcích datových buněk můžete používat různé typy vzorců, včetně matematických operací, funkcí a odkazů na jiné buňky.

### Jak změním typ grafu?

 Typ grafu můžete změnit pomocí`setChartType` metoda na`IChart` objekt a specifikování požadovaného`ChartType`.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
