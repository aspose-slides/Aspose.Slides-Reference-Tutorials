---
"description": "Naučte se, jak nastavit vzorce pro buňky grafů v prezentacích v PowerPointu v Javě pomocí Aspose.Slides pro Javu. Vytvářejte dynamické grafy se vzorci."
"linktitle": "Vzorce pro buňky s daty v grafu v Javě - Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vzorce pro buňky s daty v grafu v Javě - Slides"
"url": "/cs/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vzorce pro buňky s daty v grafu v Javě - Slides


## Úvod do vzorců pro datové buňky grafů v Aspose.Slides pro Javu

V tomto tutoriálu se podíváme na to, jak pracovat se vzorci pro datové buňky grafů pomocí Aspose.Slides pro Javu. S Aspose.Slides můžete vytvářet a manipulovat s grafy v prezentacích v PowerPointu, včetně nastavení vzorců pro datové buňky.

## Předpoklady

Než začnete, ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvořte prezentaci v PowerPointu

Nejprve si vytvořme novou prezentaci v PowerPointu a přidáme do ní graf.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Přidání grafu na první snímek
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Získejte sešit pro data grafu
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Pokračovat v operacích s datovými buňkami
    // ...
    
    // Uložit prezentaci
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Krok 2: Nastavení vzorců pro datové buňky

Nyní nastavme vzorce pro konkrétní datové buňky v grafu. V tomto příkladu nastavíme vzorce pro dvě různé buňky.

### Buňka 1: Použití notace A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

Ve výše uvedeném kódu jsme nastavili vzorec pro buňku B2 s použitím notace A1. Vzorec vypočítá součet buněk F2 až H5 a k výsledku přičte 1.

### Buňka 2: Použití notace R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Zde nastavíme vzorec pro buňku C2 s použitím notace R1C1. Vzorec vypočítá maximální hodnotu v rozsahu R2C6 až R5C8 a poté ji vydělí číslem 3.

## Krok 3: Výpočet vzorců

Po nastavení vzorců je nezbytné je vypočítat pomocí následujícího kódu:

```java
workbook.calculateFormulas();
```

Tento krok zajistí, že graf odráží aktualizované hodnoty na základě vzorců.

## Krok 4: Uložte prezentaci

Nakonec upravenou prezentaci uložte do souboru.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro vzorce buněk s daty grafu v Javě - Slides

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

V tomto tutoriálu jsme se seznámili s prací se vzorci pro datové buňky grafů v Aspose.Slides pro Javu. Probrali jsme vytvoření prezentace v PowerPointu, přidání grafu, nastavení vzorců pro datové buňky, výpočet vzorců a uložení prezentace. Nyní můžete tyto funkce využít k vytváření dynamických a datově řízených grafů ve vašich prezentacích.

## Často kladené otázky

### Jak přidám graf na konkrétní snímek?

Chcete-li přidat graf na konkrétní snímek, můžete použít `getSlides().get_Item(slideIndex)` metodu pro přístup k požadovanému snímku a poté použijte `addChart` metoda pro přidání grafu.

### Mohu v datových buňkách používat různé typy vzorců?

Ano, ve vzorcích datových buněk můžete použít různé typy vzorců, včetně matematických operací, funkcí a odkazů na jiné buňky.

### Jak změním typ grafu?

Typ grafu můžete změnit pomocí `setChartType` metoda na `IChart` objektu a specifikací požadovaného `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}