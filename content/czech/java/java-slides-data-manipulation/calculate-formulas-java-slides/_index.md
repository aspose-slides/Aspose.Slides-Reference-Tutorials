---
title: Vypočítat vzorce v Java Slides
linktitle: Vypočítat vzorce v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vypočítat vzorce v Java Slides pomocí Aspose.Slides pro Java. Podrobný průvodce se zdrojovým kódem pro dynamické prezentace v PowerPointu.
type: docs
weight: 10
url: /cs/java/data-manipulation/calculate-formulas-java-slides/
---

## Úvod do výpočtu vzorců v Java Slides pomocí Aspose.Slides

V této příručce si ukážeme, jak vypočítat vzorce v Java Slides pomocí Aspose.Slides for Java API. Aspose.Slides je výkonná knihovna pro práci s PowerPointovými prezentacemi a poskytuje funkce pro manipulaci s grafy a provádění výpočtů vzorců v rámci snímků.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Vývojové prostředí Java
-  Knihovna Aspose.Slides for Java (Můžete si ji stáhnout z[tady](https://releases.aspose.com/slides/java/)
- Základní znalost programování v Javě

## Krok 1: Vytvořte novou prezentaci

Nejprve vytvoříme novou PowerPoint prezentaci a přidáme do ní snímek. V tomto příkladu budeme pracovat s jedním snímkem.

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Krok 2: Přidejte graf do snímku

Nyní na snímek přidáme seskupený sloupcový graf. Tento graf použijeme k demonstraci výpočtů vzorce.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Krok 3: Nastavte vzorce a hodnoty

Dále nastavíme vzorce a hodnoty pro datové buňky grafu pomocí Aspose.Slides API. Vypočítáme vzorce pro tyto buňky.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Nastavte vzorec pro buňku A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Nastavte hodnotu pro buňku A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Nastavte vzorec pro buňku B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Nastavte vzorec pro buňku C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Znovu nastavte vzorec pro buňku A1
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Krok 4: Uložte prezentaci

Nakonec upravenou prezentaci s vypočtenými vzorci uložme.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro výpočet vzorců v Java Slides

```java
String resultPath = RunExamples.getOutPath() + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V této příručce jsme se naučili, jak vypočítat vzorce v Java Slides pomocí Aspose.Slides for Java. Vytvořili jsme novou prezentaci, přidali do ní graf, nastavili vzorce a hodnoty pro datové buňky grafu a uložili prezentaci s vypočítanými vzorci.

## FAQ

### Jak nastavím vzorce pro datové buňky grafu?

 Vzorce pro datové buňky grafu můžete nastavit pomocí`setFormula` metoda`IChartDataCell` v Aspose.Slides.

### Jak nastavím hodnoty pro datové buňky grafu?

 Hodnoty pro datové buňky grafu můžete nastavit pomocí`setValue` metoda`IChartDataCell` v Aspose.Slides.

### Jak vypočítám vzorce v sešitu?

 Vzorce v sešitu můžete vypočítat pomocí`calculateFormulas` metoda`IChartDataWorkbook` v Aspose.Slides.
