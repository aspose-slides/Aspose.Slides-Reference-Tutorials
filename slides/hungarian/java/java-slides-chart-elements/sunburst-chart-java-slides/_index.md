---
"description": "Készítsen lenyűgöző Sunburst diagramokat Java diákban az Aspose.Slides segítségével. Tanulja meg a diagramkészítést és az adatkezelést lépésről lépésre."
"linktitle": "Sunburst diagram Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Sunburst diagram Java diákban"
"url": "/hu/java/chart-elements/sunburst-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Sunburst diagram Java diákban


## Bevezetés a Sunburst diagramba Java diákban az Aspose.Slides segítségével

Ebben az oktatóanyagban megtanulod, hogyan hozhatsz létre Sunburst diagramot egy PowerPoint bemutatóban az Aspose.Slides for Java API használatával. A Sunburst diagram egy kördiagram, amelyet hierarchikus adatok ábrázolására használnak. Lépésről lépésre bemutatjuk a folyamatot, valamint a forráskódot.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és konfigurálva van a Java projektedben. A könyvtárat innen töltheted le: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Szükséges könyvtárak importálása

Először importáld a szükséges könyvtárakat az Aspose.Slides használatához, és hozz létre egy Sunburst diagramot a Java alkalmazásodban.

```java
import com.aspose.slides.*;
```

## 2. lépés: A prezentáció inicializálása

Inicializáljon egy PowerPoint bemutatót, és adja meg azt a könyvtárat, ahová a bemutatófájl mentésre kerül.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 3. lépés: A Sunburst diagram létrehozása

Hozz létre egy napkitöréses diagramot egy dián. Megadjuk a diagram pozícióját (X, Y) és méreteit (szélesség, magasság).

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## 4. lépés: Diagramadatok előkészítése

Töröljön a diagramból minden meglévő kategóriát és adatsort, és hozzon létre egy adatmunkafüzetet a diagramhoz.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## 5. lépés: Diagramhierarchia meghatározása

Definiálja a Sunburst diagram hierarchikus szerkezetét. Hozzáadhat ágakat, szárakat és leveleket kategóriákként.

```java
// 1. ág
IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

// 2. ág
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
```

## 6. lépés: Adatok hozzáadása a diagramhoz

Adatpontok hozzáadása a Sunburst diagramsorozathoz.

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
```

## 7. lépés: Mentse el a prezentációt

Végül mentse el a Sunburst diagrammal ellátott bemutatót.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a Sunburst diagramhoz Java diákban

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	//1. ág
	IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch1");
	chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));
	//2. ág
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
	leaf.getGroupingLevels().setGroupingItem(2, "Branch2");
	chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));
	leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
	leaf.getGroupingLevels().setGroupingItem(1, "Stem4");
	chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Sunburst);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForSunburstSeries(wb.getCell(0, "D8", 3));
	pres.save("Sunburst.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultad, hogyan hozhatsz létre Sunburst diagramot egy PowerPoint bemutatóban az Aspose.Slides for Java API használatával. Láttad, hogyan inicializálhatod a bemutatót, hogyan hozhatod létre a diagramot, hogyan definiálhatod a diagram hierarchiáját, hogyan adhatsz hozzá adatpontokat, és hogyan mentheted a bemutatót. Ezt a tudást most felhasználhatod interaktív és informatív Sunburst diagramok létrehozására a Java alkalmazásaidban.

## GYIK

### Hogyan szabhatom testre a Sunburst diagram megjelenését?

A Sunburst diagram megjelenését testreszabhatja olyan tulajdonságok módosításával, mint a színek, címkék és stílusok. A részletes testreszabási lehetőségekért lásd az Aspose.Slides dokumentációját.

### Hozzáadhatok több adatpontot a diagramhoz?

Igen, további adatpontokat adhatsz hozzá a diagramhoz a használatával. `series.getDataPoints().addDataPointForSunburstSeries()` metódust minden egyes belefoglalni kívánt adatponthoz.

### Hogyan adhatok hozzá eszköztippeket a Sunburst diagramhoz?

Ha elemleírásokat szeretne hozzáadni a Napkitörés diagramhoz, beállíthatja az adatfelirat formátumát úgy, hogy további információkat, például értékeket vagy leírásokat jelenítsen meg, amikor az egérmutatót a diagram szegmensei fölé viszi.

### Lehetséges interaktív Sunburst diagramokat létrehozni hiperhivatkozásokkal?

Igen, létrehozhat interaktív Sunburst diagramokat hiperhivatkozásokkal, ha hiperhivatkozásokat ad hozzá bizonyos diagramelemekhez vagy szegmensekhez. A hiperhivatkozások hozzáadásáról az Aspose.Slides dokumentációjában talál részleteket.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}