---
"description": "Tanuld meg, hogyan hozhatsz létre hisztogramdiagramokat PowerPoint prezentációkban az Aspose.Slides for Java használatával. Lépésről lépésre útmutató forráskóddal az adatvizualizációhoz."
"linktitle": "Hisztogram diagram Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Hisztogram diagram Java diákban"
"url": "/hu/java/chart-data-manipulation/histogram-chart-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hisztogram diagram Java diákban


## Bevezetés a hisztogram diagramba Java diákban az Aspose.Slides használatával

Ebben az oktatóanyagban végigvezetünk egy hisztogram diagram létrehozásának folyamatán egy PowerPoint prezentációban az Aspose.Slides for Java API használatával. A hisztogram diagram az adatok eloszlásának ábrázolására szolgál egy folytonos intervallumon belül.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy telepítve van az Aspose.Slides for Java könyvtár. Letöltheted innen: [Aspose weboldal](https://releases.aspose.com/slides/java/).

## 1. lépés: A projekt inicializálása

Hozz létre egy Java projektet, és add hozzá az Aspose.Slides könyvtárat a projekted függőségeihez.

## 2. lépés: Szükséges könyvtárak importálása

```java
import com.aspose.slides.*;
```

## 3. lépés: Meglévő prezentáció betöltése

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Mindenképpen cserélje ki `"Your Document Directory"` a PowerPoint-dokumentum tényleges elérési útjával.

## 4. lépés: Hisztogramdiagram létrehozása

Most hozzunk létre egy hisztogramot a prezentáció egyik diáján.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Histogram, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Adatpontok hozzáadása a sorozathoz
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.Histogram);
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A1", 15));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A2", -41));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A3", 16));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A4", 10));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A5", -23));
    series.getDataPoints().addDataPointForHistogramSeries(wb.getCell(0, "A6", 16));
    
    // A vízszintes tengely összesítési típusának beállítása Automatikus értékre
    chart.getAxes().getHorizontalAxis().setAggregationType(AxisAggregationType.Automatic);
    
    // Mentse el a prezentációt
    pres.save(dataDir + "Histogram.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Ebben a kódban először töröljük a diagramról a meglévő kategóriákat és sorozatokat. Ezután adatpontokat adunk hozzá a sorozathoz a következő használatával: `getDataPoints().addDataPointForHistogramSeries` metódus. Végül a vízszintes tengely összesítési típusát Automatikusra állítjuk, és mentjük a prezentációt.

## Teljes forráskód hisztogram diagramhoz Java diákban

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

Ebben az oktatóanyagban azt vizsgáltuk meg, hogyan hozhatunk létre hisztogram diagramot egy PowerPoint prezentációban az Aspose.Slides for Java API használatával. A hisztogram diagramok értékes eszközök az adatok eloszlásának folyamatos intervallumon belüli vizualizálására, és hatékony kiegészítői lehetnek a prezentációinknak, különösen statisztikai vagy analitikai tartalmak esetén.

## GYIK

### Hogyan telepíthetem az Aspose.Slides-t Java-hoz?

Az Aspose.Slides for Java könyvtárat letöltheted innen: [itt](https://releases.aspose.com/slides/java/)Kövesse a weboldalukon található telepítési utasításokat.

### Mire használják a hisztogram diagramot?

A hisztogramdiagram az adatok eloszlásának folytonos intervallumon belüli megjelenítésére szolgál. Gyakran használják a statisztikában a gyakorisági eloszlások ábrázolására.

### Testreszabhatom a hisztogram diagram megjelenését?

Igen, testreszabhatod a diagram megjelenését, beleértve a színeket, címkéket és tengelyeket az Aspose.Slides API használatával.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}