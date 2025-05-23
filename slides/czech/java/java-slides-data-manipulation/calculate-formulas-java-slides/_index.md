---
"description": "Naučte se, jak vypočítat vzorce v Java Slides pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem pro dynamické prezentace v PowerPointu."
"linktitle": "Výpočet vzorců v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Výpočet vzorců v Javě Slides"
"url": "/cs/java/data-manipulation/calculate-formulas-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Výpočet vzorců v Javě Slides


## Úvod do výpočtu vzorců v Javě Slides pomocí Aspose.Slides

této příručce si ukážeme, jak vypočítat vzorce v Java Slides pomocí rozhraní Aspose.Slides for Java API. Aspose.Slides je výkonná knihovna pro práci s prezentacemi v PowerPointu, která poskytuje funkce pro manipulaci s grafy a provádění výpočtů vzorců v rámci snímků.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Vývojové prostředí v Javě
- Knihovna Aspose.Slides pro Javu (můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/)
- Základní znalost programování v Javě

## Krok 1: Vytvořte novou prezentaci

Nejprve si vytvořme novou prezentaci v PowerPointu a přidejme do ní snímek. V tomto příkladu budeme pracovat s jedním snímkem.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Krok 2: Přidání grafu do snímku

Nyní si na snímek přidejme shlukový sloupcový graf. Tento graf použijeme k demonstraci výpočtů pomocí vzorců.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Krok 3: Nastavení vzorců a hodnot

Dále nastavíme vzorce a hodnoty pro datové buňky grafu pomocí API Aspose.Slides. Vypočítáme vzorce pro tyto buňky.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Nastavení vzorce pro buňku A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Nastavit hodnotu pro buňku A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Nastavení vzorce pro buňku B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Nastavení vzorce pro buňku C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Znovu nastavte vzorec pro buňku A1
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Krok 4: Uložte prezentaci

Nakonec uložme upravenou prezentaci s vypočítanými vzorci.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro výpočet vzorců v Javě (prezentace)

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
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

V této příručce jsme se naučili, jak vypočítat vzorce v Java Slides pomocí Aspose.Slides pro Javu. Vytvořili jsme novou prezentaci, přidali do ní graf, nastavili vzorce a hodnoty pro datové buňky grafu a prezentaci s vypočítanými vzorci uložili.

## Často kladené otázky

### Jak nastavím vzorce pro datové buňky grafu?

Vzorce pro datové buňky grafu můžete nastavit pomocí `setFormula` metoda `IChartDataCell` v Aspose.Slides.

### Jak nastavím hodnoty pro datové buňky grafu?

Hodnoty pro datové buňky grafu můžete nastavit pomocí `setValue` metoda `IChartDataCell` v Aspose.Slides.

### Jak vypočítám vzorce v sešitu?

Vzorce v sešitu můžete vypočítat pomocí `calculateFormulas` metoda `IChartDataWorkbook` v Aspose.Slides.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}