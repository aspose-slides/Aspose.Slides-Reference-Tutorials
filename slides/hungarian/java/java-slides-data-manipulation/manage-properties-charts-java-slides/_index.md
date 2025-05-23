---
"description": "Tanulj meg lenyűgöző diagramokat készíteni és tulajdonságokat kezelni Java diákon az Aspose.Slides segítségével. Lépésről lépésre útmutató forráskóddal a hatékony prezentációkhoz."
"linktitle": "Tulajdonságdiagramok kezelése Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Tulajdonságdiagramok kezelése Java diákban"
"url": "/hu/java/data-manipulation/manage-properties-charts-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tulajdonságdiagramok kezelése Java diákban


## Bevezetés a Java diák tulajdonságainak és diagramjainak kezelésébe az Aspose.Slides használatával

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan kezelhetjük a tulajdonságokat és hozhatunk létre diagramokat Java diákon az Aspose.Slides használatával. Az Aspose.Slides egy hatékony Java API PowerPoint-bemutatókkal való munkához. Lépésről lépésre végigvezetjük a folyamaton, beleértve a forráskód példákat is.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg róla, hogy telepítve és beállítva van a projektedben az Aspose.Slides Java könyvtár. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## Diagram hozzáadása diához

Diagram diához való hozzáadásához kövesse az alábbi lépéseket:

1. Importálja a szükséges osztályokat, és hozzon létre egy példányt a Presentation osztályból.

```java
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
```

2. Nyissa meg azt a diát, amelyhez a diagramot hozzá szeretné adni. Ebben a példában az első diát tesszük közzé.

```java
// Első dia elérése
ISlide slide = presentation.getSlides().get_Item(0);
```

3. Alapértelmezett adatokat tartalmazó diagram hozzáadása. Ebben az esetben egy StackedColumn3D diagramot adunk hozzá.

```java
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
```

## Táblázatadatok beállítása

A diagramadatok beállításához létre kell hoznunk egy diagramadatokkal foglalkozó munkafüzetet, és hozzá kell adnunk sorozatokat és kategóriákat. Kövesse az alábbi lépéseket:

4. Állítsa be a diagram adatlapjának indexét.

```java
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
```

5. Szerezd meg a diagramadatokkal foglalkozó munkafüzetet.

```java
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

6. Adatsorok hozzáadása a diagramhoz. Ebben a példában két adatsort adunk hozzá, „1. adatsor” és „2. adatsor” néven.

```java
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
```

7. Kategóriák hozzáadása a diagramhoz. Itt három kategóriát adunk hozzá.

```java
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 3D forgatási tulajdonságok beállítása

Most állítsuk be a diagram 3D forgatási tulajdonságait:

8. Állítsa be a derékszögű tengelyeket.

```java
chart.getRotation3D().setRightAngleAxes(true);
```

9. Állítsa be az X és Y tengelyek elforgatási szögeit. Ebben a példában az X tengelyt 40 fokkal, az Y tengelyt pedig 270 fokkal forgatjuk el.

```java
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
```

10. Állítsd a mélység százalékos értékét 150-re.

```java
chart.getRotation3D().setDepthPercents(150);
```

## Sorozatadatok feltöltése

11. Vegye a második diagramsorozatot, és töltse fel adatpontokkal.

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

12. Állítsa be az átfedés értékét a sorozatokhoz. Például 100-ra állíthatja, ha nincs átfedés.

```java
series.getParentSeriesGroup().setOverlap((byte) 100);
```

## A prezentáció mentése

Végül mentse el a prezentációt lemezre.

```java
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

Ez minden! Sikeresen létrehoztál egy 3D-s halmozott oszlopdiagramot egyéni tulajdonságokkal az Aspose.Slides használatával Java-ban.

## Teljes forráskód a Java diákban található tulajdonságdiagramok kezeléséhez

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
// Első dia elérése
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn3D, 0, 0, 500, 500);
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Kategóriák hozzáadása
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Rotation3D tulajdonságok beállítása
chart.getRotation3D().setRightAngleAxes(true);
chart.getRotation3D().setRotationX((byte) 40);
chart.getRotation3D().setRotationY(270);
chart.getRotation3D().setDepthPercents(150);
// Vegyük a második diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(1);
// Most feltöltjük a sorozat adatait
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Átfedés értékének beállítása
series.getParentSeriesGroup().setOverlap((byte) 100);
// Prezentáció írása lemezre
presentation.save(dataDir + "Rotation3D_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebben az oktatóanyagban elmélyedtünk a Java diák tulajdonságainak kezelésében és diagramok létrehozásában az Aspose.Slides használatával. Az Aspose.Slides egy robusztus Java API, amely lehetővé teszi a fejlesztők számára, hogy hatékonyan dolgozzanak PowerPoint prezentációkkal. Áttekintettük a lényeges lépéseket, és forráskódpéldákat is megadtunk, amelyek végigvezetnek a folyamaton.

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

A diagram típusát a következő módosításával módosíthatja: `ChartType` paramétert a diagram hozzáadásakor. Az elérhető diagramtípusokat lásd az Aspose.Slides dokumentációjában.

### Testreszabhatom a diagram színeit?

Igen, testreszabhatja a diagram színeit az adatsorok adatpontjainak vagy kategóriáinak kitöltési tulajdonságainak beállításával.

### Hogyan adhatok hozzá több adatpontot egy sorozathoz?

További adatpontokat adhatsz hozzá egy sorozathoz a használatával `series.getDataPoints().addDataPointForBarSeries()` metódust, és megadja az adatértéket tartalmazó cellát.

### Hogyan tudok más forgatási szöget beállítani?

Az X és Y tengelyek eltérő forgatási szögének beállításához használja a `chart.getRotation3D().setRotationX()` és `chart.getRotation3D().setRotationY()` kívánt szögértékekkel.

### Milyen egyéb 3D tulajdonságokat testreszabhatok?

A diagram egyéb 3D tulajdonságait, például a mélységet, a perspektívát és a megvilágítást az Aspose.Slides dokumentációjában tekintheti meg.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}