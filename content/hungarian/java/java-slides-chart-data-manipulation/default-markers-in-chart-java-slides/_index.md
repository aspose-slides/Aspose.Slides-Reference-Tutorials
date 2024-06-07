---
title: Alapértelmezett jelölők a diagramban a Java Slides-ben
linktitle: Alapértelmezett jelölők a diagramban a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre Java-diákat alapértelmezett jelölőkkel a diagramokon az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal.
type: docs
weight: 16
url: /hu/java/chart-data-manipulation/default-markers-in-chart-java-slides/
---

## Bevezetés az alapértelmezett jelölőkhöz a Java Slides diagramjában

Ebben az oktatóanyagban megvizsgáljuk, hogyan hozhat létre diagramot alapértelmezett jelölőkkel az Aspose.Slides for Java használatával. Az alapértelmezett jelölők a diagram adatpontjaihoz hozzáadott szimbólumok vagy alakzatok, amelyek kiemelik azokat. Létrehozunk egy vonaldiagramot markerekkel az adatok megjelenítéséhez.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben.

## 1. lépés: Hozzon létre egy prezentációt

Először hozzunk létre egy prezentációt, és adjunk hozzá egy diát. Ezután hozzáadunk egy diagramot a diához.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## 2. lépés: Adjon hozzá egy vonaldiagramot jelölőkkel

Most adjunk hozzá egy vonaldiagramot jelölőkkel a diához. Ezenkívül töröljük az alapértelmezett adatokat a diagramból.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 3. lépés: Töltse fel a diagramadatokat

A diagramot mintaadatokkal töltjük fel. Ebben a példában két sorozatot hozunk létre adatpontokkal és kategóriákkal.

```java
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// 1. sorozat
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"));
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));

// 2. sorozat
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"));
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Sorozatadatok feltöltése
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

## 4. lépés: A diagram testreszabása

A diagram testreszabható, például jelmagyarázat hozzáadásával és megjelenésének módosításával.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## 5. lépés: Mentse el a prezentációt

Végül mentse a prezentációt a diagrammal a kívánt helyre.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Ez az! Létrehozott egy vonaldiagramot alapértelmezett jelölőkkel az Aspose.Slides for Java használatával.

## Teljes forráskód az alapértelmezett jelölőkhöz a Java Slides diagramjában

```java
        // A dokumentumok könyvtárának elérési útja.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
            chart.getChartData().getSeries().clear();
            chart.getChartData().getCategories().clear();
            IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));
            chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));
            chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));
            chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
            series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
            chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());
            //Vegyük a második diagramsorozatot
            IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);
            //Most a sorozatadatok feltöltése
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
            series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
            chart.setLegend(true);
            chart.getLegend().setOverlay(false);
            pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Következtetés

Ebben az átfogó oktatóanyagban megtanulta, hogyan hozhat létre Java-diákat alapértelmezett jelölőkkel a diagramokon az Aspose.Slides for Java használatával. A teljes folyamatot lefedtük, a prezentáció felállításától a diagram megjelenésének testreszabásáig és az eredmény mentéséig.

## GYIK

### Hogyan változtathatom meg a jelölő szimbólumokat?

 A jelölőszimbólumokat testreszabhatja az egyes adatpontokhoz tartozó jelölőstílusok beállításával. Használat`IDataPoint.setMarkerStyle()` a jelölő szimbólum megváltoztatásához.

### Hogyan állíthatom be a diagram színeit?

 A diagram színeinek módosításához használhatja a`IChartSeriesFormat` és`IShapeFillFormat` interfészek a kitöltési és vonali tulajdonságok beállításához.

### Hozzáadhatok címkéket az adatpontokhoz?

 Igen, az adatpontokhoz címkéket adhat hozzá a`IDataPoint.getLabel()` módszert, és szükség szerint testreszabhatja azokat.