---
"description": "Tanuld meg, hogyan szabhatsz testre diagramokat Java Slides-ben az Aspose.Slides for Java használatával. Fedezd fel a második diagram lehetőségeit és javítsd a prezentációidat."
"linktitle": "Második diagrambeállítások Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Második diagrambeállítások Java diákban"
"url": "/hu/java/chart-creation/second-plot-options-charts-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Második diagrambeállítások Java diákban


## Bevezetés a Java-diagramok második diagrambeállításaiba

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan adhatunk hozzá második ábrázolási opciókat diagramokhoz az Aspose.Slides for Java használatával. A második ábrázolási opciók lehetővé teszik a diagramok megjelenésének és viselkedésének testreszabását, különösen olyan esetekben, mint a kördiagramok. Lépésről lépésre bemutatjuk a megvalósítás módját, valamint forráskódpéldákat is adunk. 

## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg róla, hogy az Aspose.Slides for Java telepítve és beállítva van a Java projektedben.

## 1. lépés: Prezentáció létrehozása
Kezdjük egy új prezentáció létrehozásával:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
```

## 2. lépés: Diagram hozzáadása egy diához
Következőként egy diagramot fogunk hozzáadni egy diához. Ebben a példában egy kördiagramot fogunk létrehozni:

```java
// Diagram hozzáadása a diához
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## 3. lépés: Diagram tulajdonságainak testreszabása
Most állítsuk be a diagram különböző tulajdonságait, beleértve a második diagram beállításait is:

```java
// Az első sorozat adatcímkéinek megjelenítése
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// A második kördiagram méretének beállítása (százalékban)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Ossza fel a tortát százalékosan
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// A felosztás pozíciójának beállítása
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## 4. lépés: Mentse el a prezentációt
Végül mentse el a prezentációt a diagram és a második ábrázolási beállításokkal:

```java
// Prezentáció írása lemezre
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a második diagram opcióihoz

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
// Diagram hozzáadása a diához
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Különböző tulajdonságok beállítása
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Prezentáció írása lemezre
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan adhatunk hozzá második diagrambeállításokat a Java diákban található diagramokhoz az Aspose.Slides for Java használatával. Testreszabhatja a különböző tulajdonságokat a diagramok megjelenésének és funkcionalitásának javítása érdekében, így a prezentációk informatívabbak és vizuálisan vonzóbbak lesznek.

## GYIK

### Hogyan tudom megváltoztatni a második kördiagram méretét egy kördiagramban?

A kördiagram második körének méretének módosításához használja a `setSecondPieSize` metódust, ahogy a fenti kódpéldában látható. Módosítsa az értéket a méret százalékos megadásához.

### Mit jelent `PieSplitBy` kontroll egy kördiagramon?

A `PieSplitBy` tulajdonság szabályozza, hogy a kördiagram hogyan legyen felosztva. Beállíthatja a kettő közül: `PieSplitType.ByPercentage` vagy `PieSplitType.ByValue` a diagram százalékos vagy egy adott érték szerinti felosztásához.

### Hogyan tudom beállítani a felosztás pozícióját egy kördiagramban?

A kördiagram felosztásának pozícióját a következővel állíthatja be: `setPieSplitPosition` módszer. Módosítsa az értéket a kívánt pozíció megadásához.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}