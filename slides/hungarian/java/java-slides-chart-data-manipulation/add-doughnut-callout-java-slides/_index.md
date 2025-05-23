---
"description": "Tanuld meg, hogyan adhatsz hozzá fánk alakú feliratokat Java diákhoz az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal a továbbfejlesztett prezentációkhoz."
"linktitle": "Fánk kiemelés hozzáadása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Fánk kiemelés hozzáadása Java diákban"
"url": "/hu/java/chart-data-manipulation/add-doughnut-callout-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Fánk kiemelés hozzáadása Java diákban


## Bevezetés a fánkfelirat hozzáadásához Java diákban az Aspose.Slides for Java használatával

Ebben az oktatóanyagban végigvezetünk azon, hogyan adhatsz hozzá fánkdiagramot egy diához Java nyelven az Aspose.Slides for Java segítségével. A fánkdiagram egy diagramelem, amely felhasználható adott adatpontok kiemelésére egy fánkdiagramban. Lépésről lépésre útmutatást és teljes forráskódot biztosítunk a kényelmed érdekében.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. Java fejlesztői környezet
2. Aspose.Slides Java könyvtárhoz
3. Integrált fejlesztői környezet (IDE), mint például az Eclipse vagy az IntelliJ IDEA
4. Egy PowerPoint-bemutató, amelyhez hozzá szeretné adni a fánkfeliratot

## 1. lépés: Java-projekt beállítása

1. Hozz létre egy új Java projektet a kiválasztott IDE-ben.
2. Add hozzá az Aspose.Slides for Java könyvtárat a projektedhez függőségként.

## 2. lépés: A prezentáció inicializálása

A kezdéshez inicializálnia kell egy PowerPoint bemutatót, és létre kell hoznia egy diát, ahová a fánkdiagramot hozzá szeretné adni. Íme a kód ehhez:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);
```

Mindenképpen cserélje ki `"Your Document Directory"` a PowerPoint-bemutatófájl tényleges elérési útjával.

## 3. lépés: Fánkdiagram létrehozása

Ezután létrehoz egy fánkdiagramot a dián. A diagram pozícióját és méretét az igényeidnek megfelelően testreszabhatod. Íme a kód a fánkdiagram hozzáadásához:

```java
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

## 4. lépés: A fánkdiagram testreszabása

Most itt az ideje a fánkdiagram testreszabásának. Különböző tulajdonságokat fogunk beállítani, például a jelmagyarázat eltávolítását, a lyuk méretének konfigurálását és az első szelet szögének módosítását. Íme a kód:

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

Ez a kódrészlet a fánkdiagram tulajdonságait állítja be. Az értékeket az igényeidnek megfelelően módosíthatod.

## 5. lépés: Adatok hozzáadása a fánkdiagramhoz

Most adjunk hozzá adatokat a fánkdiagramhoz. Az adatpontok megjelenését is testreszabjuk. Íme a kód ehhez:

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        // Adatpontok megjelenésének testreszabása itt
        i++;
    }
    categoryIndex++;
}
```

Ebben a kódban kategóriákat és adatpontokat adunk a fánkdiagramhoz. Az adatpontok megjelenését szükség szerint tovább testreszabhatja.

## 6. lépés: Mentse el a prezentációt

Végül ne felejtsd el menteni a prezentációdat a fánkdiagram hozzáadása után. Íme a kód a prezentáció mentéséhez:

```java
pres.save(dataDir + "chart.pptx", SaveFormat.Pptx);
```

Mindenképpen cserélje ki `"chart.pptx"` a kívánt fájlnévvel.

Gratulálunk! Sikeresen hozzáadott egy fánkdiagramot egy Java diához az Aspose.Slides for Java segítségével. Most már futtathatja a Java alkalmazást a fánkdiagrammal és a diagrammal rendelkező PowerPoint bemutató létrehozásához.

## Teljes forráskód a fánkfelirat hozzáadásához Java diákban

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

Ebben az oktatóanyagban áttekintettük a fánkdiagram Java diákhoz való hozzáadásának folyamatát az Aspose.Slides for Java segítségével. Megtanultad, hogyan hozhatsz létre fánkdiagramot, hogyan szabhatod testre a megjelenését és hogyan adhatsz hozzá adatpontokat. Nyugodtan gazdagíthatod prezentációidat ezzel a hatékony könyvtárral, és felfedezhetsz további diagramkészítési lehetőségeket.

## GYIK

### Hogyan tudom megváltoztatni a fánkdiagram megjelenését?

fánkdiagram megjelenését testreszabhatja a diagram adatpontjainak tulajdonságainak módosításával. A megadott kódban láthatja, hogyan állíthatja be az adatpontok kitöltési színét, vonalszínét, betűstílusát és egyéb attribútumait.

### Hozzáadhatok további adatpontokat a fánkdiagramhoz?

Igen, annyi adatpontot adhatsz hozzá a fánkdiagramhoz, amennyire szükséged van. Egyszerűen bővítsd ki a kódban a kategóriák és adatpontok hozzáadásához szükséges ciklusokat, és add meg a megfelelő adatokat és formázást.

### Hogyan tudom beállítani a fánkdiagram pozícióját és méretét a dián?

A fánkdiagram pozícióját és méretét a paraméterek módosításával módosíthatja a `addChart` metódus. A metódusban szereplő négy szám a diagram bal felső sarkának X és Y koordinátáinak, illetve a szélességének és magasságának felel meg.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}