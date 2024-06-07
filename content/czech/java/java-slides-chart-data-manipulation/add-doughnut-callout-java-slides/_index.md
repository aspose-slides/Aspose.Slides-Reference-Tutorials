---
title: Přidejte do Slides Java popisek donut
linktitle: Přidejte do Slides Java popisek donut
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přidávat donutové popisky do Java snímků pomocí Aspose.Slides pro Java. Podrobný průvodce se zdrojovým kódem pro vylepšené prezentace.
type: docs
weight: 12
url: /cs/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

## Úvod k přidání popisku donut do snímků Java pomocí Aspose.Slides pro Java

V tomto tutoriálu vás provedeme procesem přidání Donut Callout do snímku v Javě pomocí Aspose.Slides for Java. Popisek prstence je prvek grafu, který lze použít ke zvýraznění konkrétních datových bodů v prstencovém grafu. Pro vaše pohodlí vám poskytneme podrobné pokyny a kompletní zdrojový kód.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Vývojové prostředí Java
2. Aspose.Slides pro knihovnu Java
3. Integrované vývojové prostředí (IDE) jako Eclipse nebo IntelliJ IDEA
4. PowerPointová prezentace, do které chcete přidat popisek donut

## Krok 1: Nastavte svůj Java Project

1. Vytvořte nový Java projekt ve zvoleném IDE.
2. Přidejte knihovnu Aspose.Slides for Java do svého projektu jako závislost.

## Krok 2: Inicializujte prezentaci

Chcete-li začít, budete muset inicializovat prezentaci v PowerPointu a vytvořit snímek, kam chcete přidat popisek Donut. Zde je kód, jak toho dosáhnout:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Nezapomeňte vyměnit`"Your Document Directory"` se skutečnou cestou k souboru prezentace PowerPoint.

## Krok 3: Vytvořte prstencový graf

Dále na snímku vytvoříte prstencový graf. Umístění a velikost grafu můžete upravit podle svých požadavků. Zde je kód pro přidání prstencového grafu:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Krok 4: Přizpůsobte si prstencový graf

Nyní je čas upravit prstencový graf. Nastavíme různé vlastnosti, jako je odstranění legendy, konfigurace velikosti otvoru a úprava úhlu prvního řezu. Zde je kód:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

Tento fragment kódu nastavuje vlastnosti prstencového grafu. Hodnoty můžete upravit tak, aby vyhovovaly vašim konkrétním potřebám.

## Krok 5: Přidejte data do prstencového grafu

Nyní přidáme data do prstencového grafu. Přizpůsobíme také vzhled datových bodů. Zde je kód, jak toho dosáhnout:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Zde můžete přizpůsobit vzhled datových bodů
        i++;
    }
    categoryIndex++;
}
```

V tomto kódu přidáváme kategorie a datové body do prstencového grafu. Vzhled datových bodů můžete dále upravit podle potřeby.

## Krok 6: Uložte prezentaci

Nakonec nezapomeňte po přidání Donut Callout prezentaci uložit. Zde je kód pro uložení prezentace:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Nezapomeňte vyměnit`"chart.pptx"` s požadovaným názvem souboru.

Gratulujeme! Úspěšně jste přidali popisek donut na snímek Java pomocí Aspose.Slides for Java. Nyní můžete spustit aplikaci Java a vygenerovat PowerPointovou prezentaci s prstencovým grafem a popiskem.

## Kompletní zdrojový kód pro přidání Donut Callout v Java Slides

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
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

## Závěr

tomto tutoriálu jsme se zabývali procesem přidávání Donut Callout do snímku Java pomocí Aspose.Slides for Java. Naučili jste se, jak vytvořit prstencový graf, přizpůsobit jeho vzhled a přidat datové body. Neváhejte dále vylepšit své prezentace pomocí této výkonné knihovny a prozkoumejte další možnosti vytváření grafů.

## FAQ

### Jak mohu změnit vzhled Donut Callout?

Vzhled prstence můžete upravit úpravou vlastností datových bodů v grafu. V poskytnutém kódu můžete vidět, jak nastavit barvu výplně, barvu čáry, styl písma a další atributy datových bodů.

### Mohu do prstencového grafu přidat další datové body?

Ano, do prstencového grafu můžete přidat tolik datových bodů, kolik potřebujete. Jednoduše rozšiřte smyčky v kódu, kam se přidávají kategorie a datové body, a poskytněte příslušná data a formátování.

### Jak mohu upravit polohu a velikost prstencového grafu na snímku?

Pozici a velikost prstencového grafu můžete změnit úpravou parametrů v`addChart` metoda. Čtyři čísla v této metodě odpovídají souřadnicím X a Y levého horního rohu grafu a jeho šířce a výšce.