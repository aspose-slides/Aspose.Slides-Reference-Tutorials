---
title: Szerezzen szélességet és magasságot a Java Slides diagrammezőterületéből
linktitle: Szerezzen szélességet és magasságot a Java Slides diagrammezőterületéből
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan kérheti le a diagrammezőterület méreteit a Java Slides programban az Aspose.Slides for Java segítségével. Fejlessze PowerPoint automatizálási készségeit.
type: docs
weight: 21
url: /hu/java/data-manipulation/get-width-height-chart-plot-area-java-slides/
---

## Bevezetés

diagramok hatékony módja az adatok megjelenítésének a PowerPoint-prezentációkban. Előfordulhat, hogy különböző okok miatt, például a diagramon belüli elemek átméretezése vagy áthelyezése miatt, ismernie kell a diagram ábrázolási területének méreteit. Ez az útmutató bemutatja, hogyan lehet meghatározni a nyomtatási terület szélességét és magasságát a Java és az Aspose.Slides for Java használatával.

## Előfeltételek

 Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van, és be van állítva a Java projektben. A könyvtár letölthető az Aspose webhelyéről[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: A környezet beállítása

Győződjön meg arról, hogy az Aspose.Slides for Java könyvtár hozzáadva van a Java projekthez. Ezt úgy teheti meg, hogy felveszi a könyvtárat a projekt függőségei közé, vagy manuálisan adja hozzá a JAR-fájlt.

## 2. lépés: PowerPoint-bemutató létrehozása

Kezdjük egy PowerPoint prezentáció létrehozásával, és adjunk hozzá egy diát. Ez szolgál majd a diagramunk tárolójaként.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

 Cserélje ki`"Your Document Directory"` a dokumentumkönyvtár elérési útjával.

## 3. lépés: Diagram hozzáadása

Most adjunk hozzá egy fürtözött oszlopdiagramot a diához. A diagram elrendezését is érvényesíteni fogjuk.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Ez a kód fürtözött oszlopdiagramot hoz létre a (100, 100) pozícióban (500, 350) méretekkel.

## 4. lépés: A telekterület méreteinek lekérése

A diagram ábrázolási területének szélességének és magasságának lekéréséhez a következő kódot használhatjuk:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

 Most a változók`x`, `y`, `w` , és`h` tartalmazza a telekterület X-koordinátájának, Y-koordinátájának, szélességének és magasságának megfelelő értékeit.

## 5. lépés: A prezentáció mentése

Végül mentse el a prezentációt a diagrammal együtt.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

 Ügyeljen arra, hogy cserélje ki`"Chart_out.pptx"` a kívánt kimeneti fájlnévvel.

## Teljes forráskód a Java Slides diagrammezőterületének szélességéhez és magasságához

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Prezentáció mentése diagrammal
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben a cikkben megtudtuk, hogyan szerezheti meg a diagram diagramterületének szélességét és magasságát a Java Slides alkalmazásban az Aspose.Slides for Java API használatával. Ezek az információk értékesek lehetnek, ha dinamikusan módosítani kell a diagramok elrendezését a PowerPoint-prezentációkban.

## GYIK

### Hogyan módosíthatom a diagram típusát a fürtözött oszlopoktól eltérőre?

 A diagram típusát cserével módosíthatja`ChartType.ClusteredColumn` a kívánt diagram típusú felsorolással, mint pl`ChartType.Line` vagy`ChartType.Pie`.

### Módosíthatom a diagram egyéb tulajdonságait?

Igen, az Aspose.Slides for Java API használatával módosíthatja a diagram különféle tulajdonságait, például az adatokat, a címkéket és a formázást. További részletekért tekintse meg a dokumentációt.

### Az Aspose.Slides for Java alkalmas a professzionális PowerPoint automatizálásra?

Igen, az Aspose.Slides for Java egy hatékony könyvtár a PowerPoint feladatok automatizálására Java alkalmazásokban. Átfogó funkciókat biztosít a prezentációk, diák, alakzatok, diagramok és egyebek kezeléséhez.

### Hogyan tudhatok meg többet az Aspose.Slides for Java programról?

 Részletes dokumentációt és példákat találhat az Aspose.Slides for Java dokumentációs oldalán[itt](https://reference.aspose.com/slides/java/).
