---
title: Mapový graf v Java Slides
linktitle: Mapový graf v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vytvářejte úžasné mapové grafy v prezentacích PowerPoint pomocí Aspose.Slides pro Java. Podrobný průvodce a zdrojový kód pro vývojáře v jazyce Java.
weight: 15
url: /cs/java/chart-elements/map-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod do Map Chart v Java Slides pomocí Aspose.Slides pro Java

V tomto tutoriálu vás provedeme procesem vytváření mapového grafu v powerpointové prezentaci pomocí Aspose.Slides for Java. Mapové grafy jsou skvělým způsobem, jak vizualizovat geografická data ve vašich prezentacích.

## Předpoklady

 Než začnete, ujistěte se, že máte knihovnu Aspose.Slides for Java integrovanou do svého projektu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Nastavte svůj projekt

Ujistěte se, že jste nastavili svůj projekt Java a přidali knihovnu Aspose.Slides for Java do cesty třídy vašeho projektu.

## Krok 2: Vytvořte prezentaci v PowerPointu

Nejprve vytvoříme novou PowerPoint prezentaci.

```java
String resultPath = "MapChart_out.pptx";
Presentation presentation = new Presentation();
```

## Krok 3: Přidejte mapový diagram

Nyní do prezentace přidáme mapový graf.

```java
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
```

## Krok 4: Přidejte data do mapy

Přidejme do mapového grafu nějaké údaje. Vytvoříme řadu a přidáme k ní datové body.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
```

## Krok 5: Přidejte kategorie

Do mapového grafu musíme přidat kategorie, které představují různé geografické oblasti.

```java
chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
```

## Krok 6: Přizpůsobte datové body

Jednotlivé datové body si můžete přizpůsobit. V tomto příkladu změníme barvu a hodnotu konkrétního datového bodu.

```java
IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
dataPoint.getColorValue().getAsCell().setValue("15");
dataPoint.getFormat().getFill().setFillType(FillType.Solid);
dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## Krok 7: Uložte prezentaci

Nakonec uložte prezentaci s mapovým grafem.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

A je to! Vytvořili jste mapový graf v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Graf si můžete dále přizpůsobit a prozkoumat další funkce nabízené Aspose.Slides pro vylepšení vašich prezentací.

## Kompletní zdrojový kód pro mapový graf v Java Slides

```java
String resultPath = "Your Output Directory" +  "MapChart_out.pptx";
Presentation presentation = new Presentation();
try {
	//vytvořit prázdný graf
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Map, 50, 50, 500, 400, false);
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	//Přidejte řadu a několik datových bodů
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Map);
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B2", 5));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B3", 1));
	series.getDataPoints().addDataPointForMapSeries(wb.getCell(0, "B4", 10));
	//přidat kategorie
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "United States"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Mexico"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Brazil"));
	//změnit hodnotu datového bodu
	IChartDataPoint dataPoint = series.getDataPoints().get_Item(1);
	dataPoint.getColorValue().getAsCell().setValue("15");
	//nastavit vzhled datového bodu
	dataPoint.getFormat().getFill().setFillType(FillType.Solid);
	dataPoint.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Závěr

tomto tutoriálu jsme prošli procesem vytváření mapového grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Java. Mapové grafy jsou efektivním způsobem vizualizace geografických dat, díky čemuž jsou vaše prezentace poutavější a informativnější. Pojďme si shrnout hlavní kroky:

## FAQ

### Jak mohu změnit typ mapového grafu?

 Typ grafu můžete změnit nahrazením`ChartType.Map` s požadovaným typem grafu při vytváření grafu v kroku 3.

### Jak mohu přizpůsobit vzhled mapového grafu?

 Vzhled grafu můžete upravit úpravou vlastností grafu`dataPoint` objekt v kroku 6. Můžete změnit barvy, hodnoty a další.

### Mohu přidat další datové body a kategorie?

 Ano, můžete přidat tolik datových bodů a kategorií, kolik potřebujete. Jednoduše použijte`series.getDataPoints().addDataPointForMapSeries()` a`chart.getChartData().getCategories().add()` způsoby, jak je přidat.

### Jak integruji Aspose.Slides for Java do svého projektu?

 Stáhněte si knihovnu z[tady](https://releases.aspose.com/slides/java/) a přidejte jej do třídy třídy svého projektu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
