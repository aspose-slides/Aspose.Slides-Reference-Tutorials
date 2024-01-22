---
title: Állítsa be a hézag szélességét a Java Slides-ben
linktitle: Állítsa be a hézag szélességét a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthatja be a hézagszélességet a Java Slides programban az Aspose.Slides for Java segítségével. Növelje PowerPoint-prezentációi diagramképét.
type: docs
weight: 21
url: /hu/java/data-manipulation/set-gap-width-java-slides/
---

## Bevezetés a hézagszélesség beállításába az Aspose.Slides for Java programban

Ebben az oktatóanyagban végigvezetjük az Aspose.Slides for Java segítségével a PowerPoint-prezentáció diagramjának hézagszélességének beállításán. A résszélesség meghatározza a diagram oszlopai vagy sávjai közötti távolságot, lehetővé téve a diagram vizuális megjelenésének szabályozását.

## Előfeltételek

 Mielőtt elkezdené, ellenőrizze, hogy telepítve van-e az Aspose.Slides for Java könyvtár. Letöltheti az Aspose webhelyéről[itt](https://releases.aspose.com/slides/java/).

## Útmutató lépésről lépésre

Kövesse az alábbi lépéseket a résszélesség beállításához egy diagramon az Aspose.Slides for Java segítségével:

### 1. Hozzon létre egy üres prezentációt

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
```

### 2. Nyissa meg az első diát

```java
// Nyissa meg az első diát
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Adjon hozzá egy diagramot az alapértelmezett adatokkal

```java
// Adjon hozzá egy diagramot alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Állítsa be a diagram adatlap indexét

```java
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
```

### 5. Szerezze be a diagramadatok munkafüzetet

```java
// diagram adatlap beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Sorozat hozzáadása a diagramhoz

```java
// Sorozat hozzáadása a diagramhoz
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Adjon hozzá kategóriákat a diagramhoz

```java
// Adjon hozzá kategóriákat a diagramhoz
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Sorozatadatok feltöltése

```java
// Sorozatadatok feltöltése
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Sorozat adatpontok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Állítsa be a hézag szélességét

```java
// Állítsa be a Gap Width értéket
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Mentse el a bemutatót

```java
// Mentse el a bemutatót a diagrammal
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a Java Slides résszélesség beállításához

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
// Hozzáférés az első diához
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// diagram adatlap beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Catgories hozzáadása
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Vegyük a második diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Most a sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Állítsa be a GapWidth értéket
series.getParentSeriesGroup().setGapWidth(50);
// Prezentáció mentése diagrammal
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebből az oktatóanyagból megtanulta, hogyan állíthatja be a hézagszélességet egy PowerPoint-prezentációban lévő diagramhoz az Aspose.Slides for Java használatával. A résszélesség beállításával szabályozhatja a diagram oszlopai vagy sávjai közötti távolságot, javítva az adatok vizuális megjelenítését.

## GYIK

### Hogyan változtathatom meg a Gap Width értéket?

 A résszélesség módosításához használja a`setGapWidth` módszer a`ParentSeriesGroup` diagramsorozatból. A megadott példában a Gap Width értéket 50-re állítottuk, de ezt az értéket a kívánt távolságra állíthatja.

### Testreszabhatok más diagramtulajdonságokat?

Igen, az Aspose.Slides for Java kiterjedt lehetőségeket kínál a diagramok testreszabásához. Módosíthatja a diagram különféle tulajdonságait, például színeket, címkéket, címeket és egyebeket. A diagram testreszabási lehetőségeivel kapcsolatos részletes információkért tekintse meg az API-referenciát.

### Hol találok további forrásokat és dokumentációt?

 Az Aspose.Slides for Java webhelyen átfogó dokumentációt és további forrásokat találhat[Aspose honlapja](https://reference.aspose.com/slides/java/).