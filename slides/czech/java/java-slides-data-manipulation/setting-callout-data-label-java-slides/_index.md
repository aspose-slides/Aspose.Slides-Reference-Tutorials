---
title: Nastavení popisku pro štítek dat v Java Slides
linktitle: Nastavení popisku pro štítek dat v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Přečtěte si, jak nastavit popisky pro datové štítky v Aspose.Slides pro Java. Průvodce krok za krokem se zdrojovým kódem.
weight: 25
url: /cs/java/data-manipulation/setting-callout-data-label-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod do nastavení popisku pro štítek dat v Aspose.Slides pro Javu

tomto tutoriálu si ukážeme, jak nastavit popisky pro popisky dat v grafu pomocí Aspose.Slides for Java. Popisky mohou být užitečné ke zvýraznění konkrétních datových bodů v grafu. Projdeme si kód krok za krokem a poskytneme potřebný zdrojový kód.

## Předpoklady

- Měli byste mít nainstalovaný Aspose.Slides for Java.
- Vytvořte projekt Java a přidejte do svého projektu knihovnu Aspose.Slides.

## Krok 1: Vytvořte prezentaci a přidejte graf

 Nejprve musíme vytvořit prezentaci a přidat graf na snímek. Nezapomeňte vyměnit`"Your Document Directory"` se skutečnou cestou k vašemu adresáři dokumentů.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Krok 2: Nakonfigurujte graf

Dále nakonfigurujeme graf nastavením vlastností, jako je legenda, série a kategorie.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Konfigurace sérií a kategorií (Můžete upravit počet sérií a kategorií)
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        // Zde přidejte datové body
        // ...
        i++;
    }
    categoryIndex++;
}
```

## Krok 3: Přizpůsobte štítky dat

Nyní přizpůsobíme štítky dat, včetně nastavení popisků pro poslední sérii.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Přizpůsobte formátování datových bodů (výplň, čára atd.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Přizpůsobte formátování štítků (Písmo, Výplň atd.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Povolit popisky
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## Krok 4: Uložte prezentaci

Nakonec uložte prezentaci s nakonfigurovaným grafem.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Nyní jste úspěšně nastavili popisky pro popisky dat v grafu pomocí Aspose.Slides for Java. Přizpůsobte kód podle vašich specifických požadavků na graf a data.

## Kompletní zdrojový kód pro nastavení popisku pro datový štítek v Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15)
{
	IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
	series.setExplosion(0);
	series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
	series.getParentSeriesGroup().setFirstSliceAngle(351);
	seriesIndex++;
}
int categoryIndex = 0;
while (categoryIndex < 15)
{
	chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
	int i = 0;
	while (i < chart.getChartData().getSeries().size())
	{
		IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
		IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
		dataPoint.getFormat().getFill().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
		dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
		dataPoint.getFormat().getLine().setWidth(1);
		dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
		dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
		if (i == chart.getChartData().getSeries().size() - 1)
		{
			IDataLabel lbl = dataPoint.getLabel();
			lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
			lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
			lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
			lbl.getDataLabelFormat().setShowValue(false);
			lbl.getDataLabelFormat().setShowCategoryName(true);
			lbl.getDataLabelFormat().setShowSeriesName(false);
			//lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
			lbl.getDataLabelFormat().setShowLeaderLines(true);
			lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);
			chart.validateChartLayout();
			lbl.setX(lbl.getX() + (float) 0.5);
			lbl.setY(lbl.getY() + (float) 0.5);
		}
		i++;
	}
	categoryIndex++;
}
pres.save("chart.pptx", SaveFormat.Pptx);
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak nastavit popisky pro štítky dat v grafu pomocí Aspose.Slides pro Java. Popisky jsou cennými nástroji pro zdůraznění konkrétních datových bodů ve vašich grafech a prezentacích. Poskytli jsme podrobného průvodce spolu se zdrojovým kódem, který vám pomůže dosáhnout tohoto přizpůsobení.

## FAQ

### Jak přizpůsobím vzhled datových štítků?

Chcete-li upravit vzhled štítků dat, můžete upravit vlastnosti, jako je písmo, výplň a styly čar. Například:

```java
IDataLabel lbl = dataPoint.getLabel();
lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

### Jak mohu povolit nebo zakázat popisky pro datové štítky?

 Chcete-li povolit nebo zakázat popisky pro datové štítky, použijte`setShowLabelAsDataCallout` metoda. Nastavte na`true` pro povolení popisků a`false`zakázat je.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Povolit popisky
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Zakázat popisky
```

### Mohu přizpůsobit vodicí čáry pro datové štítky?

Ano, vodicí čáry pro popisky dat můžete přizpůsobit pomocí vlastností, jako je styl čáry, barva a šířka. Například:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Povolit odkazové čáry
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Toto jsou některé běžné možnosti přizpůsobení štítků dat a popisků v Aspose.Slides pro Java. Vzhled můžete dále přizpůsobit svým konkrétním potřebám.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
