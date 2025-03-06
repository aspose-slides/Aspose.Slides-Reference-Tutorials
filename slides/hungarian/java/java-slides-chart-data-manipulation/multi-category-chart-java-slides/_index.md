---
title: Több kategóriás diagram a Java Slides-ben
linktitle: Több kategóriás diagram a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Hozzon létre többkategóriás diagramokat a Java Slides programban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal a lenyűgöző adatok megjelenítéséhez prezentációkban.
weight: 20
url: /hu/java/chart-data-manipulation/multi-category-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Több kategóriás diagram a Java Slides-ben


## Bevezetés a Java Slides többkategóriás diagramjába az Aspose.Slides segítségével

Ebben az oktatóanyagban megtanuljuk, hogyan lehet több kategóriás diagramot létrehozni Java diákban az Aspose.Slides for Java API használatával. Ez az útmutató lépésről lépésre tartalmaz utasításokat a forráskóddal együtt, hogy segítsen létrehozni több kategóriát és sorozatot tartalmazó fürtözött oszlopdiagramot.

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java fejlesztői környezetben.

## 1. lépés: A környezet beállítása
Először is importálja a szükséges osztályokat, és hozzon létre egy új bemutató objektumot a diákkal való munkavégzéshez.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Dia és diagram hozzáadása
Ezután hozzon létre egy diát, és adjon hozzá egy fürtözött oszlopdiagramot.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
```

## 3. lépés: Meglévő adatok törlése
Töröljön minden meglévő adatot a diagramból.

```java
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

## 4. lépés: Adatkategóriák beállítása
Most állítsunk be adatkategóriákat a diagramhoz. Több kategóriát hozunk létre és csoportosítunk.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Adjon hozzá kategóriákat és csoportosítsa őket
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));

category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
```

## 5. lépés: Sorozat hozzáadása
Most adjunk hozzá egy sorozatot a diagramhoz az adatpontokkal együtt.

```java
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);

series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
```

## 6. lépés: A prezentáció mentése
Végül mentse el a prezentációt a diagrammal együtt.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen létrehozott egy többkategóriás diagramot egy Java dián az Aspose.Slides segítségével. Ezt a diagramot tovább szabhatja saját igényeinek megfelelően.

## A Java Slides többkategóriás diagramjának teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
IChartCategory category = ch.getChartData().getCategories().add(fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c4", "C"));
category.getGroupingLevels().setGroupingItem(1, "Group2");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c5", "D"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c6", "E"));
category.getGroupingLevels().setGroupingItem(1, "Group3");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c7", "F"));
category = ch.getChartData().getCategories().add(fact.getCell(0, "c8", "G"));
category.getGroupingLevels().setGroupingItem(1, "Group4");
category = ch.getChartData().getCategories().add(fact.getCell(0, "c9", "H"));
// Sorozat hozzáadása
IChartSeries series = ch.getChartData().getSeries().add(fact.getCell(0, "D1", "Series 1"),
		ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D3", 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D4", 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D5", 40));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D6", 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D7", 60));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D8", 70));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D9", 80));
// Prezentáció mentése diagrammal
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet több kategóriás diagramot létrehozni Java diákban az Aspose.Slides for Java API használatával. A forráskódot tartalmazó, lépésről lépésre szóló útmutatón keresztül létrehoztunk egy több kategóriát és sorozatot tartalmazó fürtözött oszlopdiagramot.

## GYIK

### Hogyan szabhatom testre a diagram megjelenését?

Testreszabhatja a diagram megjelenését a tulajdonságok, például színek, betűtípusok és stílusok módosításával. A részletes testreszabási lehetőségeket az Aspose.Slides dokumentációjában találja.

### Hozzáadhatok több sorozatot a diagramhoz?

Igen, további sorozatokat is hozzáadhat a diagramhoz az 5. lépésben bemutatott hasonló folyamat követésével.

### Hogyan változtathatom meg a diagram típusát?

 A diagram típusának módosításához cserélje ki`ChartType.ClusteredColumn` a kívánt diagramtípussal, amikor hozzáadja a diagramot a 2. lépésben.

### Hogyan adhatok címet a diagramhoz?

 Címet adhat a diagramhoz a gombbal`ch.getChartTitle().getTextFrame().setText("Chart Title");` módszer.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
