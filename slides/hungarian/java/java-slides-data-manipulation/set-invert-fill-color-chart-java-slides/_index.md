---
"description": "Tanuld meg, hogyan állíthatsz be invertált kitöltési színeket Java Slides diagramokhoz az Aspose.Slides segítségével. Javítsd diagramvizualizációidat ezzel a lépésről lépésre útmutatóval és forráskóddal."
"linktitle": "Invertált kitöltési színdiagram beállítása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Invertált kitöltési színdiagram beállítása Java diákban"
"url": "/hu/java/data-manipulation/set-invert-fill-color-chart-java-slides/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Invertált kitöltési színdiagram beállítása Java diákban


## Bevezetés a Java diákban található invertált kitöltési színdiagram beállításába

Ebben az oktatóanyagban bemutatjuk, hogyan állíthatod be az invertált kitöltési színt egy Java Slides diagramhoz az Aspose.Slides for Java segítségével. A kitöltési szín invertálása hasznos funkció, ha egy diagram negatív értékeit egy adott színnel szeretnéd kiemelni. Lépésről lépésre bemutatjuk a megvalósításhoz szükséges utasításokat és forráskódot.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. Aspose.Slides Java könyvtárhoz telepítve.
2. Java fejlesztői környezet beállítása.

## 1. lépés: Prezentáció létrehozása

Először is létre kell hoznunk egy prezentációt, amelyhez hozzáadhatjuk a diagramunkat. A következő kóddal hozhatunk létre egy prezentációt:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Diagram hozzáadása

Következő lépésként egy csoportos oszlopdiagramot fogunk hozzáadni a prezentációhoz. Így teheted meg:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## 3. lépés: Diagramadatok beállítása

Most állítsuk be a diagram adatait, beleértve a sorozatokat és a kategóriákat:

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Új sorozatok és kategóriák hozzáadása
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
```

## 4. lépés: Sorozatadatok feltöltése

Most töltsük fel a diagram sorozatadatait:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
```

## 5. lépés: Állítsa be a kitöltés színének megfordítását

A diagramsorozat invertált kitöltési színének beállításához a következő kódot használhatja:

```java
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
```

A fenti kódban úgy állítottuk be a sorozatot, hogy negatív értékek esetén invertálja a kitöltés színét, és megadtuk az invertált kitöltés színét.

## 6. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a diagrammal:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a Java diákban található invertált kitöltési színdiagramhoz

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Color inverColor = Color.RED;
Presentation pres = new Presentation();
try
{
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Új sorozatok és kategóriák hozzáadása
chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));
// Vegyük az első diagramsorozatot, és töltsük fel a sorozat adataival.
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, -30));
Color seriesColor = series.getAutomaticSeriesColor();
series.setInvertIfNegative(true);
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(seriesColor);
series.getInvertedSolidFillColor().setColor(Color.RED);
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
}
finally
{
if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan állíthatod be a diagramok invertált kitöltési színét Java Slides-ben az Aspose.Slides for Java használatával. Ez a funkció lehetővé teszi, hogy a diagramokban a negatív értékeket egy adott színnel emeld ki, így az adataid vizuálisan informatívabbak lesznek.

## GYIK

Ebben a részben néhány gyakori kérdést fogunk megvitatni a Java Slides diagramok invertált kitöltési színének beállításával kapcsolatban az Aspose.Slides for Java használatával.

### Hogyan telepíthetem az Aspose.Slides-t Java-hoz?

Az Aspose.Slides Java-hoz való telepítéséhez a Java projektbe beillesztheti az Aspose.Slides JAR fájlokat. A könyvtárat letöltheti innen: [Aspose.Slides Java letöltési oldalhoz](https://releases.aspose.com/slides/java/)Kövesse az adott fejlesztői környezet dokumentációjában található telepítési utasításokat.

### Testreszabhatom a diagramsorozat invertált kitöltéseinek színét?

Igen, testreszabhatja a diagramsorozat invertált kitöltésének színét. A megadott kódpéldában a `series.getInvertedSolidFillColor().setColor(Color.RED)` vonal pirosra állítja a fordított kitöltés színét. Lecserélheti `Color.RED` bármilyen más, általad választott színnel.

### Hogyan módosíthatom a diagram típusát az Aspose.Slides for Java programban?

A diagram típusát a következő módosításával módosíthatja: `ChartType` paramétert, amikor diagramot adunk a prezentációhoz. A kódpéldában ezt használtuk `ChartType.ClusteredColumn`Más diagramtípusokat is felfedezhet, például vonaldiagramokat, oszlopdiagramokat, kördiagramokat stb. a megfelelő adatok megadásával. `ChartType` felsorolási érték.

### Hogyan adhatok hozzá több adatsort egy diagramhoz?

Több adatsor diagramhoz való hozzáadásához használhatja a `chart.getChartData().getSeries().add(...)` metódust minden hozzáadni kívánt sorozathoz. Győződjön meg róla, hogy minden sorozathoz megadja a megfelelő adatpontokat és címkéket, hogy a diagram több sorozattal legyen feltöltve.

### Van mód a diagram megjelenésének más aspektusainak testreszabására?

Igen, az Aspose.Slides Java segítségével testreszabhatja a diagram megjelenésének különböző aspektusait, beleértve a tengelyfeliratokat, címeket, jelmagyarázatokat és egyebeket. A diagramelemek és a megjelenés testreszabásával kapcsolatos részletes útmutatásért lásd a dokumentációt.

### Elmenthetem a diagramot különböző formátumokban?

Igen, a diagramot különböző formátumokban mentheted az Aspose.Slides for Java segítségével. A megadott kódpéldában PPTX fájlként mentettük a prezentációt. Különböző formátumokat használhatsz `SaveFormat` lehetőségek más formátumokban, például PDF, PNG vagy SVG formátumban történő mentésre, az igényeidtől függően.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}