---
"description": "Többkategóriás diagramok létrehozása Java diákban az Aspose.Slides for Java használatával. Lépésről lépésre útmutató forráskóddal a lenyűgöző adatvizualizációhoz prezentációkban."
"linktitle": "Többkategóriás diagram Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Többkategóriás diagram Java diákban"
"url": "/hu/java/chart-data-manipulation/multi-category-chart-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Többkategóriás diagram Java diákban


## Bevezetés a többkategóriás diagramokba Java diákban az Aspose.Slides segítségével

Ebben az oktatóanyagban megtanuljuk, hogyan hozhatunk létre többkategóriás diagramot Java diákon az Aspose.Slides for Java API használatával. Ez az útmutató lépésről lépésre bemutatja a forráskódot, és segít létrehozni egy több kategóriát és adatsort tartalmazó fürtözött oszlopdiagramot.

## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java fejlesztői környezetedben.

## 1. lépés: A környezet beállítása
Először importáld a szükséges osztályokat, és hozz létre egy új Presentation objektumot a diákkal való munkához.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Dia és diagram hozzáadása
Ezután hozzon létre egy diát, és adjon hozzá egy csoportos oszlopdiagramot.

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
Most állítsuk be a diagram adatkategóriáit. Létrehozunk több kategóriát, és csoportosítjuk őket.

```java
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);

int defaultWorksheetIndex = 0;

// Kategóriák hozzáadása és csoportosítása
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

## 5. lépés: Sorozatok hozzáadása
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

Ennyi! Sikeresen létrehoztál egy többkategóriás diagramot egy Java dián az Aspose.Slides használatával. Ezt a diagramot tovább testreszabhatod a saját igényeidnek megfelelően.

## Teljes forráskód többkategóriás diagramhoz Java diákban

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
//            Sorozatok hozzáadása
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

Ebben az oktatóanyagban megtanultuk, hogyan hozhatunk létre többkategóriás diagramot Java diákon az Aspose.Slides for Java API használatával. Lépésről lépésre bemutattuk, hogyan hozhatunk létre egy több kategóriát és adatsort tartalmazó fürtözött oszlopdiagramot forráskóddal.

## GYIK

### Hogyan tudom testreszabni a diagram megjelenését?

A diagram megjelenését testreszabhatja olyan tulajdonságok módosításával, mint a színek, betűtípusok és stílusok. A részletes testreszabási lehetőségekért lásd az Aspose.Slides dokumentációját.

### Hozzáadhatok több sorozatot a diagramhoz?

Igen, további sorozatokat adhat a diagramhoz az 5. lépésben bemutatotthoz hasonló folyamatot követve.

### Hogyan tudom megváltoztatni a diagram típusát?

A diagram típusának módosításához cserélje ki a `ChartType.ClusteredColumn` a kívánt diagramtípussal, amikor a 2. lépésben hozzáadta a diagramot.

### Hogyan adhatok címet a diagramhoz?

A diagramhoz a következővel adhatsz címet: `ch.getChartTitle().getTextFrame().setText("Chart Title");` módszer.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}