---
title: Sunburst diagram a Java Slides-ben
linktitle: Sunburst diagram a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Az Aspose.Slides segítségével lenyűgöző Sunburst diagramokat készíthet a Java Slides-ben. Ismerje meg a diagramok létrehozását és adatkezelését lépésről lépésre.
weight: 16
url: /hu/java/chart-elements/sunburst-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Bevezetés a Sunburst Chart-ba a Java Slides alkalmazásban az Aspose.Slides segítségével

Ebből az oktatóanyagból megtudhatja, hogyan hozhat létre Sunburst diagramot egy PowerPoint-prezentációban az Aspose.Slides for Java API használatával. A Sunburst diagram egy radiális diagram, amelyet hierarchikus adatok ábrázolására használnak. Lépésről lépésre útmutatást adunk a forráskóddal együtt.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Importálja a szükséges könyvtárakat

Először is importálja a szükséges könyvtárakat az Aspose.Slides használatához, és hozzon létre egy Sunburst diagramot a Java alkalmazásban.

```java
import com.aspose.slides.*;
```

## 2. lépés: Inicializálja a prezentációt

Inicializáljon egy PowerPoint-prezentációt, és adja meg azt a könyvtárat, ahová a bemutatófájl mentésre kerül.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 3. lépés: Készítse el a Sunburst diagramot

Hozzon létre egy Sunburst diagramot egy dián. Megadjuk a diagram helyzetét (X, Y) és méreteit (szélesség, magasság).

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 50, 50, 500, 400);
```

## 4. lépés: Készítse elő a diagramadatokat

Törölje a meglévő kategóriákat és sorozatadatokat a diagramból, és hozzon létre egy adatmunkafüzetet a diagramhoz.

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);
```

## 5. lépés: Határozza meg a diagram hierarchiáját

Határozza meg a Sunburst diagram hierarchikus szerkezetét. Kategóriaként hozzáadhat ágakat, szárakat és leveleket.

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

## 6. lépés: Adjon hozzá adatokat a diagramhoz

Adjon hozzá adatpontokat a Sunburst diagramsorozathoz.

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

## 7. lépés: Mentse el a bemutatót

Végül mentse el a prezentációt a Sunburst diagrammal.

```java
pres.save("Sunburst.pptx", SaveFormat.Pptx);
```

## A Java Slides Sunburst diagramjának teljes forráskódja

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
	//ág 1
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

Ebben az oktatóanyagban megtanulta, hogyan hozhat létre Sunburst diagramot egy PowerPoint-prezentációban az Aspose.Slides for Java API használatával. Látta, hogyan inicializálhatja a bemutatót, hogyan hozhat létre diagramot, definiálhatja a diagram hierarchiáját, hogyan adhat hozzá adatpontokat és mentheti a bemutatót. Ezt a tudást most felhasználhatja interaktív és informatív Sunburst diagramok létrehozására Java-alkalmazásaiban.

## GYIK

### Hogyan szabhatom testre a Sunburst diagram megjelenését?

Testreszabhatja a Sunburst diagram megjelenését a tulajdonságok, például a színek, címkék és stílusok módosításával. A részletes testreszabási lehetőségeket az Aspose.Slides dokumentációjában találja.

### Hozzáadhatok több adatpontot a diagramhoz?

 Igen, a diagram használatával további adatpontokat adhat hozzá`series.getDataPoints().addDataPointForSunburstSeries()` módszert minden egyes felvenni kívánt adatponthoz.

### Hogyan adhatok eszköztippeket a Sunburst diagramhoz?

Ha eszköztippeket szeretne hozzáadni a Sunburst diagramhoz, beállíthatja az adatcímke formátumát, hogy további információkat, például értékeket vagy leírásokat jelenítsen meg, amikor az egérmutatót diagramszegmensekre viszi.

### Lehetséges interaktív Sunburst diagramok létrehozása hiperhivatkozásokkal?

Igen, létrehozhat interaktív Sunburst diagramokat hiperhivatkozásokkal, ha hiperhivatkozásokat ad hozzá adott diagramelemekhez vagy szegmensekhez. A hiperhivatkozások hozzáadásával kapcsolatos részletekért tekintse meg az Aspose.Slides dokumentációját.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
