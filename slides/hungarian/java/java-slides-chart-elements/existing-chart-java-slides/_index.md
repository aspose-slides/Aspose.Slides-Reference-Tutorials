---
"description": "Dobd fel PowerPoint prezentációidat az Aspose.Slides Java verziójával. Tanuld meg, hogyan módosíthatod a meglévő diagramokat programozottan. Lépésről lépésre útmutató forráskóddal a diagramok testreszabásához."
"linktitle": "Meglévő diagram Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Meglévő diagram Java diákban"
"url": "/hu/java/chart-elements/existing-chart-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Meglévő diagram Java diákban


## Bevezetés a meglévő diagramok használatába Java diákban az Aspose.Slides for Java használatával

Ebben az oktatóanyagban bemutatjuk, hogyan módosíthatsz egy meglévő diagramot egy PowerPoint-bemutatóban az Aspose.Slides for Java használatával. Végigmegyünk a diagramadatok, a kategórianevek, a sorozatnevek módosításának lépésein, és új sorozatok diagramhoz való hozzáadásának lépésein. Győződj meg róla, hogy az Aspose.Slides for Java telepítve van a projektedben.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

1. Az Aspose.Slides Java könyvtárhoz a projekted része.
2. Egy meglévő PowerPoint-bemutató egy módosítani kívánt diagrammal.
3. Java fejlesztői környezet beállítása.

## 1. lépés: Töltse be a prezentációt

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// PPTX fájlt reprezentáló megjelenítési osztály példányosítása
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
```

## 2. lépés: A dia és a diagram elérése

```java
// Az első dia elérése
ISlide sld = pres.getSlides().get_Item(0);

// A dián lévő diagram elérése
IChart chart = (IChart) sld.getShapes().get_Item(0);
```

## 3. lépés: Diagramadatok és kategóriák nevének módosítása

```java
// A diagram adatlapjának indexének beállítása
int defaultWorksheetIndex = 0;

// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Diagramkategóriák nevének módosítása
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
```

## 4. lépés: Az első diagramsorozat frissítése

```java
// Vegyük az első slágerlista-sorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Sorozat nevének frissítése
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");

// Sorozatadatok frissítése
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
```

## 5. lépés: A második diagramsorozat frissítése

```java
// Vegyük a második slágerlista-sorozatot
series = chart.getChartData().getSeries().get_Item(1);

// Sorozat nevének frissítése
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

// Vegyük a harmadik slágerlistás sorozatot
series = chart.getChartData().getSeries().get_Item(2);

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
```

## 7. lépés: Diagramtípus módosítása

```java
// Változtasd meg a diagram típusát Fürtözött hengerre
chart.setType(ChartType.ClusteredCylinder);
```

## 8. lépés: Mentse el a módosított prezentációt

```java
// Mentse el a prezentációt a módosított diagrammal
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```

Gratulálunk! Sikeresen módosított egy meglévő diagramot egy PowerPoint-bemutatóban az Aspose.Slides for Java használatával. Mostantól ezt a kódot használhatja a PowerPoint-bemutatókban található diagramok programozott testreszabásához.

## Teljes forráskód a meglévő diagramhoz Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Példányosítsa a PPTX fájlt reprezentáló megjelenítési osztályt // Példányosítsa a PPTX fájlt reprezentáló megjelenítési osztályt
Presentation pres = new Presentation(dataDir + "ExistingChart.pptx");
// Első diajelölő elérése
ISlide sld = pres.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = (IChart) sld.getShapes().get_Item(0);
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Diagram kategória nevének módosítása
fact.getCell(defaultWorksheetIndex, 1, 0, "Modified Category 1");
fact.getCell(defaultWorksheetIndex, 2, 0, "Modified Category 2");
// Vegye az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Sorozatadatok frissítése folyamatban
fact.getCell(defaultWorksheetIndex, 0, 1, "New_Series1");// Sorozat nevének módosítása
series.getDataPoints().get_Item(0).getValue().setData(90);
series.getDataPoints().get_Item(1).getValue().setData(123);
series.getDataPoints().get_Item(2).getValue().setData(44);
// Vegyen második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);
// Sorozatadatok frissítése folyamatban
fact.getCell(defaultWorksheetIndex, 0, 2, "New_Series2");// Sorozat nevének módosítása
series.getDataPoints().get_Item(0).getValue().setData(23);
series.getDataPoints().get_Item(1).getValue().setData(67);
series.getDataPoints().get_Item(2).getValue().setData(99);
// Most, új sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 3, "Series 3"), chart.getType());
// Vegyük a 3. slágerlistás sorozatot
series = chart.getChartData().getSeries().get_Item(2);
// Most feltöltjük a sorozat adatait
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 3, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 30));
chart.setType(ChartType.ClusteredCylinder);
// Prezentáció mentése diagrammal
pres.save(dataDir + "AsposeChartModified_out.pptx", SaveFormat.Pptx);
```
## Következtetés

Ebben az átfogó oktatóanyagban megtanultuk, hogyan módosíthatunk egy meglévő diagramot egy PowerPoint-bemutatóban az Aspose.Slides for Java használatával. A lépésről lépésre haladó útmutató követésével és forráskódpéldák felhasználásával könnyedén testreszabhatja és frissítheti a diagramokat az Ön igényeinek megfelelően. Íme egy összefoglaló arról, amit áttekintettünk:

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

A diagram típusát a következővel módosíthatja: `chart.setType(ChartType.ChartTypeHere)` metódus. Csere `ChartTypeHere` a kívánt diagramtípussal, például `ChartType.ClusteredCylinder` példánkban.

### Hozzáadhatok több adatpontot egy sorozathoz?

Igen, további adatpontokat adhatsz hozzá egy sorozathoz a `series.getDataPoints().addDataPointForBarSeries(cell)` metódus. Győződjön meg róla, hogy a megfelelő cellaadatokat adta meg.

### Hogyan frissíthetem a kategórianeveket?

A kategórianeveket a következővel frissítheti: `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` az új kategórianevek beállításához.

### Hogyan módosíthatom a sorozatok nevét?

A sorozatnevek módosításához használja a `fact.getCell(worksheetIndex, columnIndex, rowIndex, newValue)` az új sorozatnevek beállításához.

### Van mód arra, hogy egy sorozatot eltávolítsak a diagramról?

Igen, eltávolíthat egy sorozatot a diagramról a használatával. `chart.getChartData().getSeries().removeAt(index)` módszer, ahol `index` az eltávolítani kívánt sorozat indexe.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}