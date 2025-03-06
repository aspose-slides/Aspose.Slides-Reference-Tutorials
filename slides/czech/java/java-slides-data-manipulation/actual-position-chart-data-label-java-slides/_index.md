---
title: Získejte skutečnou polohu štítku dat grafu v Java Slides
linktitle: Získejte skutečnou polohu štítku dat grafu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak získat skutečnou polohu štítků dat grafu v Java Slides pomocí Aspose.Slides for Java. Průvodce krok za krokem se zdrojovým kódem.
type: docs
weight: 18
url: /cs/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

## Úvod k získání skutečné polohy štítku dat grafu v Java Slides

V tomto tutoriálu se naučíte, jak získat skutečnou polohu štítků dat grafu pomocí Aspose.Slides pro Java. Vytvoříme Java program, který vygeneruje powerpointovou prezentaci s grafem, přizpůsobí popisky dat a poté přidá tvary představující pozice těchto datových popisků.

## Předpoklady

Než začnete, ujistěte se, že máte v projektu Java nastavenou knihovnu Aspose.Slides for Java.

## Krok 1: Vytvořte prezentaci v PowerPointu

Nejprve vytvoříme novou PowerPoint prezentaci a přidáme do ní graf. Popisky dat grafu přizpůsobíme později v tutoriálu.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Krok 2: Přizpůsobte štítky dat
Nyní přizpůsobíme štítky dat pro řadu grafů. Nastavíme jejich polohu a ukážeme hodnoty.

```java
try {
    // ... (předchozí kód)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (zbývající kód)
} finally {
    if (pres != null) pres.dispose();
}
```

## Krok 3: Získejte skutečnou polohu datových štítků
tomto kroku budeme iterovat datové body řady grafů a získáme skutečnou polohu datových štítků, které mají hodnotu větší než 4. Poté přidáme elipsy, které budou reprezentovat tyto pozice.

```java
try {
    // ... (předchozí kód)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (zbývající kód)
} finally {
    if (pres != null) pres.dispose();
}
```

## Krok 4: Uložte prezentaci
Nakonec vygenerovanou prezentaci uložte do souboru.

```java
try {
    // ... (předchozí kód)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Kompletní zdrojový kód pro získání skutečné polohy štítku dat grafu v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//DĚLAT
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak získat skutečnou polohu štítků dat grafu v Java Slides pomocí Aspose.Slides for Java. Tyto znalosti nyní můžete využít k vylepšení svých prezentací PowerPoint pomocí přizpůsobených štítků dat a vizuálních reprezentací jejich pozic.

## FAQ

### Jak mohu přizpůsobit štítky dat v grafu?

 Chcete-li upravit štítky dat v grafu, můžete použít`setDefaultDataLabelFormat` metodu na sérii grafů a nastavte vlastnosti, jako je poloha a viditelnost. Například:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Jak mohu přidat tvary, které reprezentují pozice štítků dat?

 Můžete iterovat datové body řady grafů a použít`getActualX`, `getActualY`, `getActualWidth` , a`getActualHeight`metody datového štítku k získání jeho pozice. Poté můžete přidávat tvary pomocí`addAutoShape` metoda. Zde je příklad:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Jak mohu uložit vygenerovanou prezentaci?

 Vygenerovanou prezentaci můžete uložit pomocí`save` metoda. Zadejte požadovanou cestu k souboru a`SaveFormat` jako parametry. Například:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```