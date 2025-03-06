---
title: Hisztogram diagram a Java diákban
linktitle: Hisztogram diagram a Java diákban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre hisztogram diagramokat PowerPoint prezentációkban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal az adatok megjelenítéséhez.
type: docs
weight: 19
url: /hu/java/chart-data-manipulation/histogram-chart-java-slides/
---

## A hisztogram diagram bemutatása Java Slides-ben az Aspose.Slides használatával

Ebben az oktatóanyagban végigvezetjük a hisztogram diagram létrehozásának folyamatán egy PowerPoint-prezentációban az Aspose.Slides for Java API használatával. A hisztogram diagram az adatok folyamatos intervallumon belüli eloszlását ábrázolja.

## Előfeltételek

 Mielőtt elkezdené, ellenőrizze, hogy telepítve van-e az Aspose.Slides for Java könyvtár. Letöltheti a[Aspose honlapja](https://releases.aspose.com/slides/java/).

## 1. lépés: Inicializálja a projektet

Hozzon létre egy Java-projektet, és foglalja bele az Aspose.Slides könyvtárat a projekt függőségeibe.

## 2. lépés: Importálja a szükséges könyvtárakat

```java
import com.aspose.slides.*;
```

## 3. lépés: Töltsön be egy meglévő prezentációt

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Mindenképpen cserélje ki`"Your Document Directory"` a PowerPoint-dokumentum tényleges elérési útjával.

## 4. lépés: Hozzon létre egy hisztogram diagramot

Most hozzunk létre egy hisztogram diagramot a bemutató dián.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Adjon hozzá adatpontokat a sorozathoz
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // Állítsa a vízszintes tengely összesítési típusát Automatikusra
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Mentse el a bemutatót
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

 Ebben a kódban először töröljük a diagramból a meglévő kategóriákat és sorozatokat. Ezután adatpontokat adunk a sorozathoz a`getDataPoints().addDataPointForHistogramSeries` módszer. Végül beállítjuk a vízszintes tengely összesítési típusát Automatikusra, és mentjük a prezentációt.

## A Java Slides hisztogram diagramjának teljes forráskódja

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
	series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
	chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
	pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan hozhat létre hisztogram diagramot egy PowerPoint-prezentációban az Aspose.Slides for Java API használatával. A hisztogram diagramok értékes eszközök az adatok folyamatos intervallumon belüli eloszlásának megjelenítéséhez, és hatékony kiegészítői lehetnek a prezentációknak, különösen statisztikai vagy elemzési tartalom esetén.

## GYIK

### Hogyan telepíthetem az Aspose.Slides for Java programot?

 Az Aspose.Slides for Java könyvtárat letöltheti innen[itt](https://releases.aspose.com/slides/java/). Kövesse a webhelyükön található telepítési utasításokat.

### Mire használható a hisztogram diagram?

A hisztogram diagram az adatok folyamatos intervallumon belüli eloszlásának megjelenítésére szolgál. A statisztikákban gyakran használják a gyakorisági eloszlások ábrázolására.

### Testreszabhatom a hisztogram diagram megjelenését?

Igen, az Aspose.Slides API segítségével testreszabhatja a diagram megjelenését, beleértve annak színeit, címkéit és tengelyeit.