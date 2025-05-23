---
"description": "Naučte se přidávat popisky koblih do slidů v Javě pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem pro vylepšené prezentace."
"linktitle": "Přidání popisku koblihy v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání popisku koblihy v Javě Slides"
"url": "/cs/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání popisku koblihy v Javě Slides


## Úvod do přidání popisku koblihy v Java Slides pomocí Aspose.Slides pro Javu

V tomto tutoriálu vás provedeme procesem přidání prstencového popisku na snímek v Javě pomocí Aspose.Slides for Java. Prstencový popisek je prvek grafu, který lze použít k zvýraznění konkrétních datových bodů v prstencovém grafu. Pro vaše pohodlí vám poskytneme podrobné pokyny a kompletní zdrojový kód.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

1. Vývojové prostředí v Javě
2. Aspose.Slides pro knihovnu Java
3. Integrované vývojové prostředí (IDE) jako Eclipse nebo IntelliJ IDEA
4. Prezentace v PowerPointu, kam chcete přidat popisek koblihy

## Krok 1: Nastavení projektu Java

1. Vytvořte nový projekt Java ve zvoleném IDE.
2. Přidejte do projektu knihovnu Aspose.Slides pro Javu jako závislost.

## Krok 2: Inicializace prezentace

Chcete-li začít, budete muset inicializovat prezentaci v PowerPointu a vytvořit snímek, kam chcete přidat popisek prstence. Zde je kód, který toho dosáhnete:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Nezapomeňte vyměnit `"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace v PowerPointu.

## Krok 3: Vytvořte prstencový graf

Dále na snímku vytvoříte prstencový graf. Umístění a velikost grafu si můžete přizpůsobit podle svých požadavků. Zde je kód pro přidání prstencového grafu:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## Krok 4: Přizpůsobení prstencového grafu

Nyní je čas přizpůsobit prstencový graf. Nastavíme různé vlastnosti, jako je odstranění legendy, konfigurace velikosti otvoru a úprava úhlu prvního řezu. Zde je kód:

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

Tento úryvek kódu nastavuje vlastnosti prstencového grafu. Hodnoty můžete upravit podle svých specifických potřeb.

## Krok 5: Přidání dat do prstencového grafu

Nyní přidáme data do prstencového grafu. Také upravíme vzhled datových bodů. Zde je kód, který toho dosáhne:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Zde si můžete upravit vzhled datových bodů
        i++;
    }
    categoryIndex++;
}
```

V tomto kódu přidáváme kategorie a datové body do prstencového grafu. Vzhled datových bodů si můžete dále přizpůsobit dle potřeby.

## Krok 6: Uložte prezentaci

Nakonec nezapomeňte po přidání popisku koblihy prezentaci uložit. Zde je kód pro uložení prezentace:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Nezapomeňte vyměnit `"chart.pptx"` s požadovaným názvem souboru.

Gratulujeme! Úspěšně jste přidali prstencový popisek do snímku v Javě pomocí Aspose.Slides pro Javu. Nyní můžete spustit aplikaci Java a vygenerovat prezentaci PowerPoint s prstencovým grafem a popiskem.

## Kompletní zdrojový kód pro přidání popisku koblihy v Javě Slides

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

V tomto tutoriálu jsme se zabývali procesem přidání prstencového popisku na snímek v Javě pomocí knihovny Aspose.Slides pro Javu. Naučili jste se, jak vytvořit prstencový graf, přizpůsobit jeho vzhled a přidat datové body. Neváhejte a vylepšete své prezentace pomocí této výkonné knihovny a prozkoumejte další možnosti vytváření grafů.

## Často kladené otázky

### Jak mohu změnit vzhled popisku koblihy?

Vzhled prstencového popisku si můžete přizpůsobit úpravou vlastností datových bodů v grafu. V poskytnutém kódu vidíte, jak nastavit barvu výplně, barvu čáry, styl písma a další atributy datových bodů.

### Mohu do prstencového grafu přidat další datové body?

Ano, do prstencového grafu můžete přidat libovolný počet datových bodů. Jednoduše rozšířte smyčky v kódu, kde se přidávají kategorie a datové body, a zadejte příslušná data a formátování.

### Jak mohu upravit polohu a velikost prstencového grafu na snímku?

Umístění a velikost prstencového grafu můžete změnit úpravou parametrů v `addChart` metoda. Čtyři čísla v této metodě odpovídají souřadnicím X a Y levého horního rohu grafu a jeho šířce a výšce.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}