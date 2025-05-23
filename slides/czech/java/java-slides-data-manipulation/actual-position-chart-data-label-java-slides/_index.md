---
"description": "Naučte se, jak získat skutečnou pozici popisků dat grafu v Java Slides pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem."
"linktitle": "Získejte skutečnou pozici popisku dat grafu v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Získejte skutečnou pozici popisku dat grafu v Java Slides"
"url": "/cs/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Získejte skutečnou pozici popisku dat grafu v Java Slides


## Úvod do získání skutečné pozice popisku dat grafu v Java Slides

tomto tutoriálu se naučíte, jak načíst skutečnou pozici popisků dat grafu pomocí Aspose.Slides pro Javu. Vytvoříme program v Javě, který vygeneruje prezentaci v PowerPointu s grafem, upraví popisky dat a poté přidá tvary představující pozice těchto popisků dat.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nastavenou knihovnu Aspose.Slides for Java.

## Krok 1: Vytvořte prezentaci v PowerPointu

Nejprve si vytvořme novou prezentaci v PowerPointu a přidejme do ní graf. Popisky dat grafu upravíme později v tutoriálu.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## Krok 2: Úprava popisků dat
Nyní si upravíme popisky dat pro sérii grafů. Nastavíme jejich pozici a zobrazíme hodnoty.

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

## Krok 3: Získejte skutečnou polohu datových popisků
tomto kroku budeme iterovat datovými body v sérii grafů a načíst skutečnou pozici datových popisků, které mají hodnotu větší než 4. Poté přidáme elipsy, které tyto pozice reprezentují.

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
Nakonec uložte vygenerovanou prezentaci do souboru.

```java
try {
    // ... (předchozí kód)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Kompletní zdrojový kód pro získání skutečné pozice popisku dat grafu v Java Slides

```java
// Cesta k adresáři s dokumenty.
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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//ÚKOL
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

V tomto tutoriálu jste se naučili, jak načíst skutečnou pozici popisků dat grafu v Java Slides pomocí Aspose.Slides pro Javu. Nyní můžete tyto znalosti využít k vylepšení svých prezentací v PowerPointu o přizpůsobené popisky dat a vizuální znázornění jejich pozic.

## Často kladené otázky

### Jak mohu přizpůsobit popisky dat v grafu?

Chcete-li přizpůsobit popisky dat v grafu, můžete použít `setDefaultDataLabelFormat` metodu na sérii grafů a nastavit vlastnosti, jako je pozice a viditelnost. Například:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Jak mohu přidat tvary, které budou reprezentovat pozice popisků dat?

Můžete iterovat datovými body série grafů a použít `getActualX`, `getActualY`, `getActualWidth`a `getActualHeight` metody popisku dat pro získání jeho pozice. Poté můžete přidat tvary pomocí `addAutoShape` metoda. Zde je příklad:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Jak mohu uložit vygenerovanou prezentaci?

Vygenerovanou prezentaci můžete uložit pomocí `save` metodu. Zadejte požadovanou cestu k souboru a `SaveFormat` jako parametry. Například:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}