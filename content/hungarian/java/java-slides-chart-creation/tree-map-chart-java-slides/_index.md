---
title: Fatérkép diagram a Java Slides-ben
linktitle: Fatérkép diagram a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Hozzon létre fatérkép-diagramokat a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal a hierarchikus adatok megjelenítéséhez.
type: docs
weight: 13
url: /hu/java/chart-creation/tree-map-chart-java-slides/
---

## A Java Slides fatérkép-diagramjának bemutatása

Ebben az oktatóanyagban bemutatjuk, hogyan hozhat létre fatérkép-diagramot egy PowerPoint-prezentációban az Aspose.Slides for Java könyvtár használatával. A fatérkép diagramok hatékony módja a hierarchikus adatok megjelenítésének.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár be van állítva a Java projektben.

## 1. lépés: Importálja a szükséges könyvtárakat

```java
import com.aspose.slides.*;
```

## 2. lépés: Töltse be a prezentációt

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 3. lépés: Hozzon létre egy fatérkép-diagramot

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);

    // 1. ág létrehozása
    IChartCategory leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C1", "Leaf1"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem1");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch1");

    chart.getChartData().getCategories().add(wb.getCell(0, "C2", "Leaf2"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C3", "Leaf3"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C4", "Leaf4"));

    // 2. ág létrehozása
    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C5", "Leaf5"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem3");
    leaf.getGroupingLevels().setGroupingItem(2, "Branch2");

    chart.getChartData().getCategories().add(wb.getCell(0, "C6", "Leaf6"));

    leaf = chart.getChartData().getCategories().add(wb.getCell(0, "C7", "Leaf7"));
    leaf.getGroupingLevels().setGroupingItem(1, "Stem4");

    chart.getChartData().getCategories().add(wb.getCell(0, "C8", "Leaf8"));

    // Adjon hozzá adatpontokat
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
    series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);

    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
    series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));

    series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);

    // Mentse el a bemutatót a Fatérkép diagrammal
    pres.save("Treemap.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## A Java Slides fatérkép-diagramjának teljes forráskódja
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Treemap, 50, 50, 500, 400);
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
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Treemap);
	series.getLabels().getDefaultDataLabelFormat().setShowCategoryName(true);
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D1", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D2", 5));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D3", 3));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D4", 6));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D5", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D6", 9));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D7", 4));
	series.getDataPoints().addDataPointForTreemapSeries(wb.getCell(0, "D8", 3));
	series.setParentLabelLayout(ParentLabelLayoutType.Overlapping);
	pres.save("Treemap.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan hozhat létre fatérkép-diagramot egy PowerPoint-prezentációban az Aspose.Slides for Java könyvtár használatával. A Tree Map diagramok értékes eszközt jelentenek a hierarchikus adatok megjelenítéséhez, így a prezentációk informatívabbak és vonzóbbak.

## GYIK

### Hogyan adhatok hozzá adatokat a fatérkép diagramhoz?

 Adatok hozzáadásához a fatérkép diagramhoz használja a`series.getDataPoints().addDataPointForTreemapSeries()` módszerrel, az adatértékeket paraméterként adja át.

### Hogyan szabhatom testre a fatérkép-diagram megjelenését?

 Testreszabhatja a fatérkép diagram megjelenését a különböző tulajdonságok módosításával`chart` és`series` objektumok, például színek, címkék és elrendezések.

### Létrehozhatok több fatérkép-diagramot egyetlen prezentációban?

Igen, több fatérkép-diagramot is létrehozhat egyetlen prezentációban, ha ugyanazokat a lépéseket követi, és különböző diapozíciókat ad meg.

### Hogyan menthetem el a prezentációt a fatérkép diagrammal?

 Használja a`pres.save()` módszerrel mentheti a prezentációt a fatérkép diagrammal a kívánt formátumban (pl. PPTX).