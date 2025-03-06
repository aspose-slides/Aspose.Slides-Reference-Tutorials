---
title: Szórt diagram a Java diákban
linktitle: Szórt diagram a Java diákban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre szóródiagramokat Java nyelven az Aspose.Slides segítségével. Lépésről lépésre útmutató Java forráskóddal az adatok megjelenítéséhez prezentációkban.
type: docs
weight: 11
url: /hu/java/chart-creation/scattered-chart-java-slides/
---

## Bevezetés az Aspose.Slides for Java szórt diagramjába

Ebben az oktatóanyagban végigvezetjük a szóródási diagram létrehozásának folyamatán az Aspose.Slides for Java használatával. A szóródiagramok hasznosak az adatpontok kétdimenziós síkon való megjelenítéséhez. Lépésről lépésre útmutatást adunk, és Java forráskódot is mellékelünk az Ön kényelme érdekében.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. [Aspose.Slides a Java számára](https://products.aspose.com/slides/java) telepítve.
2. Java fejlesztői környezet beállítva.

## 1. lépés: Inicializálja a prezentációt

Először importálja a szükséges könyvtárakat, és hozzon létre egy új bemutatót.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Hozzon létre könyvtárat, ha még nincs jelen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Hozzon létre egy új prezentációt
Presentation pres = new Presentation();
```

## 2. lépés: Adjon hozzá egy diát, és hozza létre a szóródiagramot

 Ezután adjunk hozzá egy diát, és hozzuk létre rajta a szóródiagramot. Használjuk a`ScatterWithSmoothLines`diagramtípus ebben a példában.

```java
// Szerezd meg az első diát
ISlide slide = pres.getSlides().get_Item(0);

// Szórványdiagram készítése
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## 3. lépés: Készítse elő a diagramadatokat

Most készítsük elő az adatokat a szóródiagramunkhoz. Két sorozatot adunk hozzá, mindegyik több adatponttal.

```java
// Az alapértelmezett diagramadat-munkalapindex lekérése
int defaultWorksheetIndex = 0;

// A diagram adatlapjának lekérése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Demósorozat törlése
chart.getChartData().getSeries().clear();

// Adja hozzá az első sorozatot
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Vegyük az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Adjon hozzá adatpontokat az első sorozathoz
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Szerkessze a sorozat típusát
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // A jelölő méretének módosítása
series.getMarker().setSymbol(MarkerStyleType.Star); // Marker szimbólum módosítása

// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);

// Adjon hozzá adatpontokat a második sorozathoz
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// Módosítsa a marker stílusát a második sorozathoz
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 4. lépés: Mentse el a bemutatót

Végül mentse a prezentációt a pontdiagrammal egy PPTX fájlba.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen létrehozott egy szóródiagramot az Aspose.Slides for Java használatával. Most tovább szabhatja ezt a példát, hogy megfeleljen az Ön konkrét adat- és tervezési követelményeinek.

## A Java Slides szórt diagramjának teljes forráskódja
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre könyvtárat, ha még nincs jelen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
//Az alapértelmezett diagram létrehozása
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Az alapértelmezett diagramadat-munkalapindex lekérése
int defaultWorksheetIndex = 0;
// A diagram adatlapjának lekérése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Demósorozat törlése
chart.getChartData().getSeries().clear();
// Új sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Vegyük az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Adjon hozzá új pontot (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Új pont hozzáadása (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Szerkessze a sorozat típusát
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// A diagramsorozat-jelölő módosítása
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);
// Adjon hozzá új pontot (5:2).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
// Új pont hozzáadása (3:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
// Új pont hozzáadása (2:2)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
// Új pont hozzáadása (5:1)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));
// A diagramsorozat-jelölő módosítása
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebben az oktatóanyagban végigvezettük a szóródási diagram létrehozásának folyamatán az Aspose.Slides for Java használatával. A szóródiagramok hatékony eszközök az adatpontok kétdimenziós térben történő megjelenítéséhez, megkönnyítve az összetett adatkapcsolatok elemzését és megértését.

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

 A diagram típusának módosításához használja a`setType` módszert a diagramsorozaton, és adja meg a kívánt diagramtípust. Például,`series.setType(ChartType.Line)` vonaldiagrammá változtatná a sorozatot.

### Hogyan szabhatom testre a marker méretét és stílusát?

 A jelölő méretét és stílusát a gombbal módosíthatja`getMarker` módszert a sorozaton, majd állítsa be a méretet és a szimbólum tulajdonságait. Például:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

Nyugodtan fedezze fel a további testreszabási lehetőségeket az Aspose.Slides for Java dokumentációjában.

 Ne felejtse el cserélni`"Your Document Directory"` azzal a tényleges elérési úttal, ahová a prezentációt menteni szeretné.