---
"description": "Tanuld meg, hogyan hozhatsz létre szóródási diagramokat Java nyelven az Aspose.Slides segítségével. Lépésről lépésre útmutató Java forráskóddal az adatvizualizációhoz prezentációkban."
"linktitle": "Szétszórt diagram Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Szétszórt diagram Java diákban"
"url": "/hu/java/chart-creation/scattered-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Szétszórt diagram Java diákban


## Bevezetés a szórt diagramba az Aspose.Slides Java-ban

Ebben az oktatóanyagban végigvezetünk egy szóródási diagram létrehozásának folyamatán az Aspose.Slides for Java segítségével. A szóródási diagramok hasznosak az adatpontok kétdimenziós síkon történő vizualizálására. Lépésről lépésre bemutatjuk a folyamatot, és a kényelmed érdekében Java forráskódot is mellékelünk.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. [Aspose.Slides Java-hoz](https://products.aspose.com/slides/java) telepítve.
2. Java fejlesztői környezet beállítása.

## 1. lépés: A prezentáció inicializálása

Először importálja a szükséges könyvtárakat, és hozzon létre egy új bemutatót.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Hozz létre egy könyvtárat, ha az még nem létezik.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();

// Új prezentáció létrehozása
Presentation pres = new Presentation();
```

## 2. lépés: Dia hozzáadása és a szóródási diagram létrehozása

Ezután adj hozzá egy diát, és hozd létre rajta a szóródási diagramot. A következőt fogjuk használni: `ScatterWithSmoothLines` diagramtípus ebben a példában.

```java
// Az első dia betöltése
ISlide slide = pres.getSlides().get_Item(0);

// A szóródási diagram létrehozása
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

## 3. lépés: Diagramadatok előkészítése

Most készítsük elő az adatokat a szóródási diagramhoz. Két sorozatot fogunk hozzáadni, mindegyiket több adatponttal.

```java
// Az alapértelmezett diagramadat-munkalap indexének lekérése
int defaultWorksheetIndex = 0;

// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Demósorozat törlése
chart.getChartData().getSeries().clear();

// Adja hozzá az első sorozatot
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());

// Vegyük az első slágerlista-sorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Adatpontok hozzáadása az első sorozathoz
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));

// Sorozat típusának szerkesztése
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10); // Jelölő méretének módosítása
series.getMarker().setSymbol(MarkerStyleType.Star); // Jelölő szimbólumának módosítása

// Vegyük a második slágerlista-sorozatot
series = chart.getChartData().getSeries().get_Item(1);

// Adatpontok hozzáadása a második sorozathoz
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

// A második sorozat jelölőstílusának módosítása
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

## 4. lépés: Mentse el a prezentációt

Végül mentse el a szóródási diagrammal ellátott bemutatót egy PPTX fájlba.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Ennyi! Sikeresen létrehoztál egy szóródási diagramot az Aspose.Slides for Java használatával. Mostantól testreszabhatod ezt a példát, hogy az megfeleljen az adott adatoknak és tervezési követelményeknek.

## Teljes forráskód a Java Slides szétszórt diagramhoz
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy könyvtárat, ha az még nem létezik.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
// Az alapértelmezett diagram létrehozása
IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
// Az alapértelmezett diagramadat-munkalap indexének lekérése
int defaultWorksheetIndex = 0;
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Demósorozat törlése
chart.getChartData().getSeries().clear();
// Új sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
// Vegye az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Adjon hozzá egy új pontot (1:3).
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
// Új pont hozzáadása (2:10)
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
// Sorozat típusának szerkesztése
series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
// A diagramsorozat-jelölő módosítása
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);
// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);
// Adjon hozzá egy új pontot (5:2).
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

Ebben az oktatóanyagban végigvezettünk a szóródási diagram létrehozásának folyamatán az Aspose.Slides for Java segítségével. A szóródási diagramok hatékony eszközök az adatpontok kétdimenziós térben történő vizualizálására, megkönnyítve az összetett adatkapcsolatok elemzését és megértését.

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

A diagram típusának módosításához használja a `setType` metódust a diagramsorozaton, és adja meg a kívánt diagramtípust. Például, `series.setType(ChartType.Line)` vonaldiagrammá változtatná a sorozatot.

### Hogyan szabhatom testre a jelölő méretét és stílusát?

A jelölő méretét és stílusát a következővel módosíthatja: `getMarker` metódust a sorozaton, majd állítsa be a méretet és a szimbólum tulajdonságait. Például:

```java
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

További testreszabási lehetőségeket az Aspose.Slides for Java dokumentációjában találsz.

Ne felejtsd el kicserélni `"Your Document Directory"` a prezentáció mentésének tényleges elérési útjával.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}