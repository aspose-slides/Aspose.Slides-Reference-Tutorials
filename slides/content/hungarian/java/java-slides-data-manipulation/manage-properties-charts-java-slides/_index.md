---
title: Tulajdonságdiagramok kezelése a Java Slides alkalmazásban
linktitle: Tulajdonságdiagramok kezelése a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Tanuljon meg lenyűgöző diagramokat készíteni és tulajdonságait kezelni a Java diákon az Aspose.Slides segítségével. Lépésről lépésre útmutató forráskóddal a hatékony prezentációkhoz.
type: docs
weight: 13
url: /hu/java/data-manipulation/manage-properties-charts-java-slides/
---

## Bevezetés a Java Slides tulajdonságainak és diagramjainak kezelésébe az Aspose.Slides segítségével

Ebben az oktatóanyagban megvizsgáljuk, hogyan kezelhetünk tulajdonságokat és hozhatunk létre diagramokat Java diákon az Aspose.Slides segítségével. Az Aspose.Slides egy hatékony Java API a PowerPoint prezentációkkal való munkavégzéshez. Lépésről lépésre végigjárjuk a folyamatot, beleértve a forráskód példákat is.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a Java Aspose.Slides könyvtára telepítve van és be van állítva a projektben. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## Diagram hozzáadása a diához

Ha diagramot szeretne hozzáadni egy diához, kövesse az alábbi lépéseket:

1. Importálja a szükséges osztályokat, és hozzon létre egy példányt a Presentation osztályból.

```java
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
```

2. Nyissa meg azt a diát, amelyhez hozzá szeretné adni a diagramot. Ebben a példában elérjük az első diát.

```java
// Hozzáférés az első diához
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Adjon hozzá egy diagramot alapértelmezett adatokkal. Ebben az esetben egy StackedColumn3D diagramot adunk hozzá.

```java
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Diagramadatok beállítása

A diagramadatok beállításához létre kell hoznunk egy diagramadat-munkafüzetet, és hozzá kell adni sorozatokat és kategóriákat. Kovesd ezeket a lepeseket:

4. Állítsa be a diagram adatlap indexét.

```java
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
```

5. Szerezze be a diagramadatok munkafüzetét.

```java
// A diagram adatlapjának lekérése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Sorozat hozzáadása a diagramhoz. Ebben a példában két sorozatot adunk hozzá: „1. sorozat” és „2. sorozat”.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Adjon hozzá kategóriákat a diagramhoz. Itt három kategóriát adunk hozzá.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## A 3D elforgatás tulajdonságainak beállítása

Most állítsuk be a diagram 3D elforgatási tulajdonságait:

8. Állítsa be a derékszögű tengelyeket.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Állítsa be az X és Y tengely elforgatási szögeit. Ebben a példában X-et 40 fokkal, Y-t 270 fokkal elforgatjuk.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Állítsa a mélység százalékát 150-re.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Sorozatadatok feltöltése

11. Vegyük a második diagramsorozatot, és töltsük fel adatpontokkal.

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## Átfedés beállítása

12. Állítsa be a sorozatok átfedési értékét. Például beállíthatja 100-ra, hogy ne legyen átfedés.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## A prezentáció mentése

Végül mentse a prezentációt lemezre.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen létrehozott egy 3D halmozott oszlopdiagramot egyéni tulajdonságokkal a Java Aspose.Slides segítségével.

## A Java Slides tulajdonságai diagramjainak teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
// Hozzáférés az első diához
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// A diagram adatlapjának lekérése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Catgories hozzáadása
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Állítsa be a Rotation3D tulajdonságait
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Vegyük a második diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Most a sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Állítsa be az OverLap értékét
series.getParentSeriesGroup().setOverlap((byte) 100);
// Prezentáció írása lemezre
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebben az oktatóanyagban az Aspose.Slides segítségével elmélyültünk a tulajdonságok kezelésének és a Java diákon lévő diagramok létrehozásának világában. Az Aspose.Slides egy robusztus Java API, amely képessé teszi a fejlesztőket arra, hogy hatékonyan dolgozzanak PowerPoint prezentációkkal. Leírtuk az alapvető lépéseket, és forráskód-példákat mutattunk be, amelyek végigvezetik Önt a folyamaton.

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

 A diagram típusát módosíthatja a`ChartType` paramétert a diagram hozzáadásakor. Az elérhető diagramtípusokat az Aspose.Slides dokumentációjában találja.

### Testreszabhatom a diagram színeit?

Igen, testreszabhatja a diagram színeit a sorozat adatpontjainak vagy kategóriáinak kitöltési tulajdonságainak beállításával.

### Hogyan adhatok több adatpontot egy sorozathoz?

 A sorozathoz további adatpontokat adhat hozzá a`series.getDataPoints().addDataPointForBarSeries()` metódussal és az adatértéket tartalmazó cella megadásával.

### Hogyan állíthatok be más elforgatási szöget?

 Az X és Y tengely eltérő elforgatási szögének beállításához használja a`chart.getRotation3D().setRotationX()` és`chart.getRotation3D().setRotationY()` a kívánt szögértékekkel.

### Milyen további 3D tulajdonságokat szabhatok testre?

Az Aspose.Slides dokumentációjában megtekintheti a diagram egyéb 3D tulajdonságait, például a mélységet, a perspektívát és a megvilágítást.