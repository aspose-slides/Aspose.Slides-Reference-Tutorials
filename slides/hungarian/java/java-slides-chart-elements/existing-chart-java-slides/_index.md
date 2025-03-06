---
title: Meglévő diagram a Java Slides-ben
linktitle: Meglévő diagram a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Javítsa PowerPoint prezentációit az Aspose.Slides for Java segítségével. Ismerje meg a meglévő diagramok programozott módosítását. Lépésről lépésre útmutató forráskóddal a diagram testreszabásához.
weight: 12
url: /hu/java/chart-elements/existing-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Bevezetés a Java Slides meglévő diagramjába az Aspose.Slides for Java használatával

Ebben az oktatóanyagban bemutatjuk, hogyan lehet módosítani egy meglévő diagramot egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Végigvesszük a diagramadatok, kategórianevek és sorozatnevek módosításának lépéseit, valamint új sorozatok hozzáadását a diagramhoz. Győződjön meg arról, hogy az Aspose.Slides for Java be van állítva a projektben.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. Aspose.Slides for Java könyvtár szerepel a projektben.
2. Egy meglévő PowerPoint-prezentáció egy módosítani kívánt diagrammal.
3. Java fejlesztői környezet beállítása.

## 1. lépés: Töltse be a prezentációt

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Példányosítási osztály, amely a PPTX fájlt képviseli
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## 2. lépés: Nyissa meg a Dia és a diagramot

```java
// Nyissa meg az első diát
ISlide sld = pres.getSlides().get_Item(0);

// Nyissa meg a diagramot a dián
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## 3. lépés: A diagramadatok és a kategórianevek módosítása

```java
// A diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;

// A diagram adatlapjának lekérése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// A diagramkategória nevének módosítása
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## 4. lépés: Frissítse az első diagramsorozatot

```java
// Vegyük az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Frissítse a sorozat nevét
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Sorozatadatok frissítése
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## 5. lépés: Frissítse a második diagramsorozatot

```java
// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);

// Frissítse a sorozat nevét
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");

// Sorozatadatok frissítése
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
```

## 6. lépés: Új sorozat hozzáadása a diagramhoz

```java
// Új sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());

// Vegyük a harmadik diagramsorozatot
series = chart.getChartData().getSeries().get_Item(2);

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## 7. lépés: Változtassa meg a diagram típusát

```java
//Változtassa meg a diagram típusát Clustered Cylinder értékre
chart.setType(ChartType.ClusteredCylinder);
```

## 8. lépés: Mentse el a módosított prezentációt

```java
// Mentse el a bemutatót a módosított diagrammal
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Gratulálunk! Sikeresen módosított egy meglévő diagramot egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Ezzel a kóddal most már programozottan testreszabhatja a diagramokat PowerPoint-prezentációiban.

## A Java Slides meglévő diagramjának teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Példányosítási osztály, amely PPTX fájlt képvisel// Példányosítási bemutató osztály, amely PPTX fájlt képvisel
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Hozzáférés az első diajelölőhöz
ISlide sld = pres.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// A diagram adatlapjának lekérése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Diagram kategória nevének megváltoztatása
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Vegyük az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Most frissítjük a sorozat adatait
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// A sorozat nevének módosítása
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);
// Most frissítjük a sorozat adatait
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// A sorozat nevének módosítása
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Most egy új sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Vegyük a 3. diagramsorozatot
series = chart.getChartData().getSeries().get_Item(2);
// Most a sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Prezentáció mentése diagrammal
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Következtetés

Ebben az átfogó oktatóanyagban megtanultuk, hogyan lehet módosítani egy meglévő diagramot egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. A lépésenkénti útmutató követésével és a forráskód-példák felhasználásával könnyedén testreszabhatja és frissítheti a diagramokat, hogy megfeleljenek az Ön egyedi igényeinek. Íme egy összefoglaló, amivel foglalkoztunk:

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

 A diagram típusát a gombbal módosíthatja`chart.setType(ChartType.ChartTypeHere)` módszer. Cserélje ki`ChartTypeHere` a kívánt diagramtípussal, mint pl`ChartType.ClusteredCylinder` példánkban.

### Hozzáadhatok több adatpontot egy sorozathoz?

 Igen, további adatpontokat adhat hozzá egy sorozathoz a`series.getDataPoints().addDataPointForBarSeries(cell)` módszer. Ügyeljen arra, hogy megadja a megfelelő cellaadatokat.

### Hogyan frissíthetem a kategórianeveket?

 A kategórianeveket a használatával frissítheti`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` az új kategórianevek beállításához.

### Hogyan módosíthatom a sorozatok nevét?

 A sorozatnevek módosításához használja a`fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` az új sorozatnevek beállításához.

### Van mód egy sorozat eltávolítására a diagramról?

 Igen, eltávolíthat egy sorozatot a diagramból a`chart.getChartData().getSeries().removeAt(index)` módszer, hol`index`az eltávolítani kívánt sorozat indexe.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
