---
"description": "Tanuld meg, hogyan állíthatsz be feliratokat adatcímkékhez az Aspose.Slides Java-ban. Lépésről lépésre útmutató forráskóddal."
"linktitle": "Adatcímke kiemelésének beállítása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Adatcímke kiemelésének beállítása Java diákban"
"url": "/hu/java/data-manipulation/setting-callout-data-label-java-slides/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adatcímke kiemelésének beállítása Java diákban


## Bevezetés az adatcímke kiemelésének beállításába az Aspose.Slides for Java programban

Ebben az oktatóanyagban bemutatjuk, hogyan állíthatsz be kiemeléseket az adatcímkékhez egy diagramban az Aspose.Slides for Java használatával. A kiemelések hasznosak lehetnek a diagram adott adatpontjainak kiemelésére. Lépésről lépésre végigvezetjük a kódon, és megadjuk a szükséges forráskódot.

## Előfeltételek

- Telepítenie kell az Aspose.Slides for Java programot.
- Hozz létre egy Java projektet, és add hozzá az Aspose.Slides könyvtárat.

## 1. lépés: Bemutató létrehozása és diagram hozzáadása

Először is létre kell hoznunk egy prezentációt, és hozzá kell adnunk egy diagramot egy diához. Ügyeljünk arra, hogy kicseréljük `"Your Document Directory"` a dokumentumkönyvtár tényleges elérési útjával.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 2. lépés: A diagram konfigurálása

Ezután konfiguráljuk a diagramot olyan tulajdonságok beállításával, mint a jelmagyarázat, az adatsorok és a kategóriák.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Sorozatok és kategóriák konfigurálása (A sorozatok és kategóriák számát módosíthatja)
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
        // Adatpontok hozzáadása itt
        // ...
        i++;
    }
    categoryIndex++;
}
```

## 3. lépés: Adatcímkék testreszabása

Most testreszabjuk az adatfeliratokat, beleértve az utolsó sorozat feliratainak beállítását is.

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    // Adatpontok formázásának testreszabása (kitöltés, vonal stb.)

    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        // Címkeformázás testreszabása (betűtípus, kitöltés stb.)
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        // Felhívások engedélyezése
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(true);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
    }
    i++;
}
```

## 4. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a konfigurált diagrammal.

```java
pres.save("chart.pptx", SaveFormat.Pptx);
```

Most sikeresen beállítottad az adatcímkék feliratait egy diagramban az Aspose.Slides for Java használatával. Szabd testre a kódot az adott diagram és adatkövetelmények szerint.

## Teljes forráskód az adatcímke kiemelésének beállításához Java diákban

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

Ebben az oktatóanyagban azt vizsgáltuk meg, hogyan állíthatunk be kiemeléseket adatcímkékhez egy diagramban az Aspose.Slides for Java használatával. A kiemelések értékes eszközök a diagramok és prezentációk adott adatpontjainak kiemelésére. Lépésről lépésre útmutatót és forráskódot készítettünk, amely segít ebben a testreszabásban.

## GYIK

### Hogyan szabhatom testre az adatcímkék megjelenését?

Az adatfeliratok megjelenésének testreszabásához módosíthatja a tulajdonságokat, például a betűtípust, a kitöltést és a vonalstílusokat. Például:

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

### Hogyan engedélyezhetem vagy letilthatom az adatfeliratok feliratait?

Az adatfeliratok feliratainak engedélyezéséhez vagy letiltásához használja a `setShowLabelAsDataCallout` metódus. Állítsa be erre: `true` felhívások engedélyezéséhez és `false` hogy letiltsa őket.

```java
lbl.getDataLabelFormat().setShowLabelAsDataCallout(true); // Felhívások engedélyezése
lbl.getDataLabelFormat().setShowLabelAsDataCallout(false); // Felhívások letiltása
```

### Testreszabhatom az adatfeliratok vezető vonalait?

Igen, testreszabhatja az adatfeliratok vezető vonalait olyan tulajdonságok használatával, mint a vonalstílus, a szín és a szélesség. Például:

```java
lbl.getDataLabelFormat().setShowLeaderLines(true); // Vezető vonalak engedélyezése
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setStyle(LineStyle.Single);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().setWidth(1);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
lbl.getDataLabelFormat().getLeaderLinesFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```

Íme néhány gyakori testreszabási lehetőség az adatcímkékhez és a feliratokhoz az Aspose.Slides for Java programban. A megjelenést tovább szabhatja az igényeinek megfelelően.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}