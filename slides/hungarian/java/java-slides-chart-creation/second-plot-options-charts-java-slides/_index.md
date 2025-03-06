---
title: Második nyomtatási opciók a diagramokhoz a Java Slides-ben
linktitle: Második nyomtatási opciók a diagramokhoz a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan testreszabhatja a diagramokat a Java Slides programban az Aspose.Slides for Java segítségével. Fedezze fel a második cselekmény lehetőségeit, és javítsa prezentációit.
type: docs
weight: 12
url: /hu/java/chart-creation/second-plot-options-charts-java-slides/
---

## Bevezetés a Java Slides diagramjainak második ábrázolási opcióiba

Ebben az oktatóanyagban megvizsgáljuk, hogyan adhatunk hozzá második nyomtatási opciókat a diagramokhoz az Aspose.Slides for Java segítségével. A második diagram opciók lehetővé teszik a diagramok megjelenésének és viselkedésének testreszabását, különösen az olyan forgatókönyvekben, mint a kördiagramok. Ennek eléréséhez lépésenkénti utasításokat és forráskód-példákat fogunk nyújtani. 

## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java telepítve van, és be van állítva a Java projektben.

## 1. lépés: Hozzon létre egy prezentációt
Kezdjük egy új prezentáció létrehozásával:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
```

## 2. lépés: Diagram hozzáadása a diához
Ezután hozzáadunk egy diagramot egy diához. Ebben a példában egy kördiagramot hozunk létre:

```java
// Diagram hozzáadása a dián
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
```

## 3. lépés: A diagram tulajdonságainak testreszabása
Most állítsunk be különböző tulajdonságokat a diagramhoz, beleértve a második diagram opciókat is:

```java
// Az első sorozat adatcímkéinek megjelenítése
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Állítsa be a második pite méretét (százalékban)
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);

// Osszuk el a tortát százalékosan
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);

// Állítsa be a felosztás helyzetét
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
```

## 4. lépés: Mentse el a bemutatót
Végül mentse el a prezentációt a diagrammal és a második diagram opciókkal:

```java
// Prezentáció írása lemezre
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a második telek opciókhoz

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
// Diagram hozzáadása a dián
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.PieOfPie, 50, 50, 500, 400);
// Állítson be különböző tulajdonságokat
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setSecondPieSize(149);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitBy(PieSplitType.ByPercentage);
chart.getChartData().getSeries().get_Item(0).getParentSeriesGroup().setPieSplitPosition(53);
// Prezentáció írása lemezre
presentation.save(dataDir + "SecondPlotOptionsforCharts_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan adhatunk hozzá második nyomtatási beállításokat a Java Slides diagramjaihoz az Aspose.Slides for Java segítségével. Testreszabhatja a különböző tulajdonságokat a diagramok megjelenésének és funkcionalitásának javítása érdekében, így prezentációi informatívabbak és látványosabbak.

## GYIK

### Hogyan módosíthatom a második kör méretét egy kördiagramon?

 kördiagram második körének méretének módosításához használja a`setSecondPieSize` módszert a fenti kódpéldában látható módon. Módosítsa az értéket a méret százalékos megadásához.

###  Mit csinál`PieSplitBy` control in a Pie of Pie chart?

 A`PieSplitBy` tulajdonság szabályozza a kördiagram felosztását. Bármelyikre beállíthatja`PieSplitType.ByPercentage` vagy`PieSplitType.ByValue` a diagram százalékos vagy meghatározott érték szerinti felosztásához.

### Hogyan állíthatom be a felosztás pozícióját egy kördiagramon?

 Beállíthatja a felosztás pozícióját egy kördiagramon a`setPieSplitPosition` módszer. Állítsa be az értéket a kívánt pozíció megadásához.