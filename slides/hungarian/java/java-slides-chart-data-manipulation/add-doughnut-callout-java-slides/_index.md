---
title: Donut Callout hozzáadása a Java Slides-hez
linktitle: Donut Callout hozzáadása a Java Slides-hez
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá fánkfeliratokat a Java Slides-hez az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal a továbbfejlesztett prezentációkhoz.
weight: 12
url: /hu/java/chart-data-manipulation/add-doughnut-callout-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Fánk kiemelés hozzáadása Java Slides programhoz az Aspose.Slides for Java segítségével

Ebben az oktatóanyagban végigvezetjük Önt azon a folyamaton, hogyan adjon hozzá Donut Callout diát Java nyelven az Aspose.Slides for Java segítségével. A Donut Callout egy diagramelem, amellyel a fánkdiagram adott adatpontjait lehet kiemelni. Lépésről lépésre útmutatást és teljes forráskódot biztosítunk az Ön kényelme érdekében.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. Java fejlesztői környezet
2. Aspose.Slides for Java könyvtár
3. Integrált fejlesztői környezet (IDE), mint az Eclipse vagy az IntelliJ IDEA
4. Egy PowerPoint-prezentáció, amelyhez hozzá szeretné adni a fánk kiemelést

## 1. lépés: Állítsa be a Java projektet

1. Hozzon létre egy új Java-projektet a kiválasztott IDE-ben.
2. Adja hozzá az Aspose.Slides for Java könyvtárat a projekthez függőségként.

## 2. lépés: Inicializálja a prezentációt

A kezdéshez inicializálnia kell egy PowerPoint-prezentációt, és létre kell hoznia egy diát, amelyhez hozzá szeretné adni a Donut Callout-ot. Íme a kód ennek eléréséhez:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

 Mindenképpen cserélje ki`"Your Document Directory"` a PowerPoint bemutatófájl tényleges elérési útjával.

## 3. lépés: Hozzon létre egy fánkdiagramot

Ezután létrehoz egy Fánk diagramot a dián. Testreszabhatja a diagram helyzetét és méretét igényei szerint. Íme a kód a Donut diagram hozzáadásához:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 4. lépés: A Donut Chart testreszabása

Most itt az ideje, hogy személyre szabja a Donut diagramot. Különféle tulajdonságokat állítunk be, mint például a jelmagyarázat eltávolítása, a furat méretének beállítása és az első szelet szögének beállítása. Íme a kód:

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

Ez a kódrészlet beállítja a Donut diagram tulajdonságait. Az értékeket saját igényei szerint állíthatja be.

## 5. lépés: Adjon hozzá adatokat a fánkdiagramhoz

Most adjunk hozzá adatokat a Donut diagramhoz. Az adatpontok megjelenését is testre szabjuk. Íme a kód ennek végrehajtásához:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Itt testreszabhatja az adatpontok megjelenését
        i++;
    }
    categoryIndex++;
}
```

Ebben a kódban kategóriákat és adatpontokat adunk a Donut diagramhoz. Szükség szerint tovább testreszabhatja az adatpontok megjelenését.

## 6. lépés: Mentse el a bemutatót

Végül ne felejtse el menteni a prezentációt a Donut Callout hozzáadása után. Íme a kód a prezentáció mentéséhez:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

 Mindenképpen cserélje ki`"chart.pptx"` a kívánt fájlnévvel.

Gratulálunk! Sikeresen hozzáadott egy Donut Calloutot egy Java diához az Aspose.Slides for Java segítségével. Most már futtathatja a Java-alkalmazást a PowerPoint prezentáció létrehozásához a Donut diagrammal és a kiemeléssel.

## Teljes forráskód az Add Donut Callout Java Slides-hez

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

## Következtetés

Ebben az oktatóanyagban bemutattuk a Donut Callout Java diához való hozzáadásának folyamatát az Aspose.Slides for Java segítségével. Megtanulta, hogyan hozhat létre Donut diagramot, hogyan szabhatja testre a megjelenését, és hogyan adhat hozzá adatpontokat. Nyugodtan bővítheti tovább prezentációit ezzel a hatékony könyvtárral, és fedezzen fel további diagramkészítési lehetőségeket.

## GYIK

### Hogyan változtathatom meg a fánk kiemelés megjelenését?

Testreszabhatja a Donut Callout megjelenését a diagram adatpontjainak tulajdonságainak módosításával. A megadott kódban láthatja, hogyan állíthatja be az adatpontok kitöltési színét, vonalszínét, betűstílusát és egyéb attribútumait.

### Hozzáadhatok további adatpontokat a Donut diagramhoz?

Igen, annyi adatpontot adhat hozzá a Donut diagramhoz, amennyi szükséges. Egyszerűen bővítse ki a kód ciklusait, ahol kategóriákat és adatpontokat ad hozzá, és adja meg a megfelelő adatokat és formázást.

### Hogyan állíthatom be a fánk diagram helyzetét és méretét a dián?

 Módosíthatja a Donut diagram helyzetét és méretét a paraméterek módosításával a`addChart` módszer. Ebben a módszerben a négy szám megfelel a diagram bal felső sarkának X és Y koordinátáinak, illetve annak szélességének és magasságának.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
