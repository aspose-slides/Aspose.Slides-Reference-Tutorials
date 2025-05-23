---
"description": "Tanuld meg, hogyan állíthatod be a rés szélességét Java diákban az Aspose.Slides for Java segítségével. Javítsd a PowerPoint-bemutatóid diagramvizualizációit."
"linktitle": "A rés szélességének beállítása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "A rés szélességének beállítása Java diákban"
"url": "/hu/java/data-manipulation/set-gap-width-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# A rés szélességének beállítása Java diákban


## Bevezetés a rés szélességének beállításába az Aspose.Slides Java-ban

Ebben az oktatóanyagban végigvezetünk egy PowerPoint-bemutató diagramjainak résszélességének beállításán az Aspose.Slides for Java használatával. A résszélesség határozza meg az oszlopok vagy sávok közötti távolságot a diagramban, lehetővé téve a diagram vizuális megjelenésének szabályozását.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy telepítve van az Aspose.Slides for Java könyvtár. Letöltheted az Aspose weboldaláról. [itt](https://releases.aspose.com/slides/java/).

## Lépésről lépésre útmutató

Kövesse az alábbi lépéseket a diagramok résszélességének beállításához az Aspose.Slides for Java használatával:

### 1. Hozz létre egy üres prezentációt

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Üres prezentáció létrehozása 
Presentation presentation = new Presentation();
```

### 2. Az első diához való hozzáférés

```java
// Az első dia elérése
ISlide slide = presentation.getSlides().get_Item(0);
```

### 3. Alapértelmezett adatokat tartalmazó diagram hozzáadása

```java
// Alapértelmezett adatokat tartalmazó diagram hozzáadása
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
```

### 4. Állítsa be a diagram adatlapjának indexét

```java
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
```

### 5. Szerezd meg a Diagramadatok munkafüzetet

```java
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### 6. Sorozatok hozzáadása a diagramhoz

```java
// Sorozat hozzáadása a diagramhoz
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

### 7. Kategóriák hozzáadása a diagramhoz

```java
// Kategóriák hozzáadása a diagramhoz
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

### 8. Sorozatadatok feltöltése

```java
// Sorozatadatok feltöltése
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Sorozat adatpontjainak feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

### 9. Állítsa be a rés szélességét

```java
// Állítsa be a rés szélességét
series.getParentSeriesGroup().setGapWidth(50);
```

### 10. Mentse el a prezentációt

```java
// Mentse el a prezentációt a diagrammal együtt
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a Java diákban található rés szélességének beállításához

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása 
Presentation presentation = new Presentation();
// Első dia elérése
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategóriák hozzáadása
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Vegyük a második diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Most feltöltjük a sorozat adatait
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// GapWidth értékének beállítása
series.getParentSeriesGroup().setGapWidth(50);
// Prezentáció mentése diagrammal
presentation.save(dataDir + "GapWidth_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebben az oktatóanyagban megtanultad, hogyan állíthatod be a rés szélességét egy PowerPoint-bemutatóban lévő diagramhoz az Aspose.Slides for Java segítségével. A rés szélességének módosításával szabályozhatod az oszlopok vagy sávok közötti távolságot a diagramban, javítva az adatok vizuális ábrázolását.

## GYIK

### Hogyan módosíthatom a rés szélességének értékét?

A rés szélességének módosításához használja a `setGapWidth` módszer a `ParentSeriesGroup` a diagramsorozatból. A bemutatott példában a rés szélességét 50-re állítottuk be, de ezt az értéket a kívánt térközre állíthatja.

### Testreszabhatom a diagram más tulajdonságait?

Igen, az Aspose.Slides Java-ban elérhető, széleskörű diagram-testreszabási lehetőségeket kínál. Módosíthatja a diagram különböző tulajdonságait, például a színeket, címkéket, címeket és egyebeket. A diagram testreszabási lehetőségeiről részletes információkat az API-referenciában talál.

### Hol találok további forrásokat és dokumentációt?

Átfogó dokumentációt és további forrásokat talál az Aspose.Slides for Java oldalon a következő címen: [Aspose weboldal](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}