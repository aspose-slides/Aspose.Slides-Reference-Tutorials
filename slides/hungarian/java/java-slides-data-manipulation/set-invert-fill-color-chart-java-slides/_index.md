---
title: Invert Fill Color Chart beállítása a Java Slides alkalmazásban
linktitle: Invert Fill Color Chart beállítása a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be invertált kitöltési színeket a Java Slides diagramokhoz az Aspose.Slides segítségével. Fejlessze diagramja vizualizációját ezzel a lépésenkénti útmutatóval és forráskóddal.
weight: 22
url: /hu/java/data-manipulation/set-invert-fill-color-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Bevezetés az invertált kitöltési színdiagram beállításába a Java diákban

Ebben az oktatóanyagban bemutatjuk, hogyan lehet beállítani egy diagram kitöltési színét a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. A kitöltési szín megfordítása hasznos funkció, ha egy diagram negatív értékeit egy adott színnel szeretné kiemelni. Ennek eléréséhez lépésről lépésre nyújtunk útmutatást és forráskódot.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. Aspose.Slides for Java könyvtár telepítve.
2. Java fejlesztői környezet beállítása.

## 1. lépés: Hozzon létre egy prezentációt

Először is létre kell hoznunk egy prezentációt, amelyhez hozzáadjuk a diagramunkat. A következő kóddal prezentációt hozhat létre:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Adjon hozzá egy diagramot

Ezután egy fürtözött oszlopdiagramot adunk a bemutatóhoz. A következőképpen teheti meg:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);
```

## 3. lépés: A diagramadatok beállítása

Most állítsuk be a diagramadatokat, beleértve a sorozatokat és kategóriákat:

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

## 4. lépés: Töltse fel a sorozatadatokat

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

A fenti kódban a sorozatot úgy állítjuk be, hogy a negatív értékek invertálja a kitöltési színt, és adjuk meg az invertált kitöltés színét.

## 6. lépés: Mentse el a bemutatót

Végül mentse el a prezentációt a diagrammal:

```java
pres.save(dataDir + "SetInvertFillColorChart_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód az Invert Fill Color Chart beállításához a Java diákban

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
// Vegyük az első diagramsorozatot és töltsük fel a sorozatadatokat.
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

Ebben az oktatóanyagban megmutattuk, hogyan állíthatja be a diagram kitöltési színét a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Ez a funkció lehetővé teszi, hogy egy adott színnel kiemelje a negatív értékeket a diagramokon, így az adatok vizuálisan informatívabbak.

## GYIK

Ebben a részben néhány gyakori kérdéssel foglalkozunk, amelyek a Java Slides programban az Aspose.Slides for Java segítségével történő diagramok kitöltési színének megfordításával kapcsolatosak.

### Hogyan telepíthetem az Aspose.Slides for Java programot?

 Az Aspose.Slides for Java telepítéséhez vegye fel az Aspose.Slides JAR fájlokat a Java-projektbe. A könyvtár letölthető a[Aspose.Slides for Java letöltési oldal](https://releases.aspose.com/slides/java/). Kövesse az adott fejlesztői környezet dokumentációjában található telepítési utasításokat.

### Testreszabhatom a diagramsorozat fordított kitöltésének színét?

Igen, testreszabhatja a diagramsorozat fordított kitöltésének színét. A megadott kódpéldában a`series.getInvertedSolidFillColor().setColor(Color.RED)` line pirosra állítja a fordított kitöltés színét. Cserélheted`Color.RED` tetszőleges más színnel.

### Hogyan módosíthatom a diagram típusát az Aspose.Slides for Java alkalmazásban?

 A diagram típusát módosíthatja a`ChartType` paramétert, amikor diagramot ad hozzá a prezentációhoz. A kódpéldában használtuk`ChartType.ClusteredColumn` . Más diagramtípusokat is felfedezhet, például vonaldiagramokat, oszlopdiagramokat, kördiagramokat stb., ha megadja a megfelelő`ChartType` enum érték.

### Hogyan adhatok hozzá több adatsort egy diagramhoz?

 Ha több adatsort szeretne hozzáadni egy diagramhoz, használhatja a`chart.getChartData().getSeries().add(...)` módszert minden egyes hozzáadni kívánt sorozathoz. Ügyeljen arra, hogy minden sorozathoz megadja a megfelelő adatpontokat és címkéket, hogy a diagramot több sorozattal töltse fel.

### Van mód a diagram megjelenésének egyéb szempontjainak testreszabására?

Igen, az Aspose.Slides for Java segítségével testreszabhatja a diagram megjelenésének különböző aspektusait, beleértve a tengelycímkéket, címeket, jelmagyarázatokat és egyebeket. A diagram elemeinek és megjelenésének testreszabásával kapcsolatos részletes útmutatásért tekintse meg a dokumentációt.

### Elmenthetem a diagramot különböző formátumokban?

 Igen, a diagramot különböző formátumokban mentheti az Aspose.Slides for Java segítségével. A megadott kódpéldában a prezentációt PPTX fájlként mentettük el. Használhat különböző`SaveFormat` lehetőségekkel mentheti el más formátumban, például PDF, PNG vagy SVG, az Ön igényeitől függően.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
