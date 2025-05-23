---
"description": "Tanuld meg, hogyan hozhatsz létre Java diákat alapértelmezett jelölőkkel a diagramokban az Aspose.Slides for Java használatával. Lépésről lépésre útmutató forráskóddal."
"linktitle": "Alapértelmezett jelölők a Java diák diagramjában"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Alapértelmezett jelölők a Java diák diagramjában"
"url": "/hu/java/chart-data-manipulation/default-markers-in-chart-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Alapértelmezett jelölők a Java diák diagramjában


## Bevezetés az alapértelmezett jelölőkbe a Java diák diagramjaiban

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan hozhatunk létre alapértelmezett jelölőkkel rendelkező diagramot az Aspose.Slides for Java használatával. Az alapértelmezett jelölők olyan szimbólumok vagy alakzatok, amelyeket a diagram adatpontjaihoz adunk, hogy kiemeljék azokat. Létrehozunk egy vonaldiagramot jelölőkkel az adatok vizualizálásához.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java projektedben.

## 1. lépés: Prezentáció létrehozása

Először is hozzunk létre egy prezentációt, és adjunk hozzá egy diát. Ezután adjunk hozzá egy diagramot a diához.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

## 2. lépés: Vonaldiagram hozzáadása jelölőkkel

Most adjunk hozzá egy jelölőkkel ellátott vonaldiagramot a diához. Emellett töröljük az alapértelmezett adatokat a diagramból.

```java
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 3. lépés: Diagramadatok feltöltése

A diagramot mintaadatokkal fogjuk feltölteni. Ebben a példában két sorozatot fogunk létrehozni adatpontokkal és kategóriákkal.

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

A diagramot tovább testreszabhatja, például jelmagyarázatot adhat hozzá és módosíthatja a megjelenését.

```java
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

## 5. lépés: Mentse el a prezentációt

Végül mentse el a diagramot tartalmazó bemutatót a kívánt helyre.

```java
pres.save(dataDir + "DefaultMarkersInChart.pptx", SaveFormat.Pptx);
```

Ez minden! Létrehoztál egy vonaldiagramot alapértelmezett jelölőkkel az Aspose.Slides for Java használatával.

## Teljes forráskód az alapértelmezett jelölőkhöz a Java diák diagramjában

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
            //Most feltöltjük a sorozat adatait
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

Ebben az átfogó oktatóanyagban megtanultad, hogyan hozhatsz létre Java diákat alapértelmezett jelölőkkel a diagramokban az Aspose.Slides for Java segítségével. Áttekintettük a teljes folyamatot, a prezentáció beállításától a diagram megjelenésének testreszabásán át az eredmény mentéséig.

## GYIK

### Hogyan tudom megváltoztatni a jelölő szimbólumokat?

A jelölő szimbólumokat testreszabhatja az egyes adatpontok jelölőstílusának beállításával. `IDataPoint.setMarkerStyle()` a jelölő szimbólumának módosításához.

### Hogyan tudom beállítani a diagram színeit?

A diagram színeinek módosításához használhatja a `IChartSeriesFormat` és `IShapeFillFormat` felületek a kitöltési és vonaltulajdonságok beállításához.

### Hozzáadhatok címkéket az adatpontokhoz?

Igen, címkéket adhatsz hozzá az adatpontokhoz a használatával. `IDataPoint.getLabel()` módszert, és szükség szerint testreszabhatja azokat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}