---
title: Kiemelés beállítása adatcímkéhez a Java Slides-ben
linktitle: Kiemelés beállítása adatcímkéhez a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be kiemeléseket adatcímkékhez az Aspose.Slides for Java programban. Lépésről lépésre útmutató forráskóddal.
weight: 25
url: /hu/java/data-manipulation/setting-callout-data-label-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Kiemelés beállítása adatcímkéhez a Java Slides-ben


## Bevezetés az adatcímkék kiemelésének beállításába az Aspose.Slides for Java programban

Ebben az oktatóanyagban bemutatjuk, hogyan állíthat be kiemeléseket az adatcímkékhez egy diagramon az Aspose.Slides for Java segítségével. A kiemelések hasznosak lehetnek bizonyos adatpontok kiemelésére a diagramon. Lépésről lépésre végigjárjuk a kódot, és megadjuk a szükséges forráskódot.

## Előfeltételek

- Az Aspose.Slides for Java-nak telepítve kell lennie.
- Hozzon létre egy Java-projektet, és adja hozzá az Aspose.Slides könyvtárat a projekthez.

## 1. lépés: Hozzon létre egy prezentációt és adjon hozzá egy diagramot

 Először is létre kell hoznunk egy prezentációt, és diagramot kell hozzáadnunk egy diához. Mindenképpen cserélje ki`"Your Document Directory"` a dokumentumkönyvtár tényleges elérési útjával.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 2. lépés: A diagram konfigurálása

Ezután konfiguráljuk a diagramot olyan tulajdonságok beállításával, mint a jelmagyarázat, sorozatok és kategóriák.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Sorozatok és kategóriák konfigurálása (beállíthatja a sorozatok és kategóriák számát)
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
        // Adjon hozzá adatpontokat ide
        // ...
        i++;
    }
    categoryIndex++;
}
```

## 3. lépés: Az adatcímkék testreszabása

Most személyre szabjuk az adatcímkéket, beleértve a kiemelések beállítását az utolsó sorozathoz.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Az adatpont formázásának testreszabása (kitöltés, vonal stb.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        //Címkeformázás testreszabása (betűtípus, kitöltés stb.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Feliratok engedélyezése
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## 4. lépés: Mentse el a bemutatót

Végül mentse el a prezentációt a konfigurált diagrammal.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Az Aspose.Slides for Java segítségével sikeresen beállította az adatcímkék feliratait egy diagramon. Szabja testre a kódot saját diagram- és adatkövetelményei szerint.

## Teljes forráskód a Java Slides adatcímkéjének kiemelésének beállításához

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

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan állíthat be kiemeléseket az adatcímkékhez egy diagramon az Aspose.Slides for Java segítségével. A kiemelések értékes eszközök a diagramok és prezentációk bizonyos adatpontjainak kiemeléséhez. Lépésről lépésre útmutatót adtunk a forráskóddal együtt, hogy segítsünk elérni ezt a testreszabást.

## GYIK

### Hogyan szabhatom testre az adatcímkék megjelenését?

Az adatcímkék megjelenésének testreszabásához módosíthatja a tulajdonságokat, például a betűtípust, a kitöltést és a vonalstílust. Például:

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

### Hogyan engedélyezhetem vagy tilthatom le az adatcímkék kiemelését?

 Az adatcímkék kiemelésének engedélyezéséhez vagy letiltásához használja a`setShowLabelAsDataCallout` módszer. Állítsa be`true` feliratok engedélyezéséhez és`false`letiltani őket.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Feliratok engedélyezése
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // A kiemelések letiltása
```

### Testreszabhatom az adatcímkék vezető sorait?

Igen, testreszabhatja az adatcímkék vezetővonalait olyan tulajdonságok használatával, mint a vonalstílus, szín és szélesség. Például:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Vezérvonalak engedélyezése
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Íme néhány gyakori testreszabási lehetőség az Aspose.Slides for Java adatcímkéihez és felirataihoz. Tovább szabhatja a megjelenést az Ön egyedi igényeihez.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
