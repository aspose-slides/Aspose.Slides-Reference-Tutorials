---
title: Érvényesítse a Java diákhoz hozzáadott diagramelrendezést
linktitle: Érvényesítse a Java diákhoz hozzáadott diagramelrendezést
second_title: Aspose.Slides Java PowerPoint Processing API
description: Mesterdiagram elrendezésének ellenőrzése PowerPointban az Aspose.Slides for Java segítségével. Tanulja meg a diagramok programozott kezelését a lenyűgöző prezentációk érdekében.
weight: 10
url: /hu/java/data-manipulation/validate-chart-layout-added-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Bevezetés a diagramelrendezés érvényesítésébe az Aspose.Slides for Java programban

Ebben az oktatóanyagban megvizsgáljuk, hogyan érvényesíthető a diagram elrendezése egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Ez a könyvtár lehetővé teszi a PowerPoint prezentációk programozott kezelését, megkönnyítve ezzel a különféle elemek, köztük a diagramok kezelését és érvényesítését.

## 1. lépés: A prezentáció inicializálása

 Először inicializálnunk kell egy prezentációs objektumot, és betöltenünk egy meglévő PowerPoint-prezentációt. Cserélje ki`"Your Document Directory"` a prezentációs fájl tényleges elérési útjával (`test.pptx` ebben a példában).

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 2. lépés: Diagram hozzáadása

 Ezután egy diagramot adunk a bemutatóhoz. Ebben a példában fürtözött oszlopdiagramot adunk hozzá, de módosíthatja a`ChartType` szükség szerint.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
```

## 3. lépés: A diagram elrendezésének ellenőrzése

 Most ellenőrizzük a diagram elrendezését a`validateChartLayout()` módszer. Ez biztosítja, hogy a diagram megfelelően legyen elhelyezve a dián belül.

```java
chart.validateChartLayout();
```

## 4. lépés: A diagram pozíciójának és méretének lekérése

A diagram elrendezésének érvényesítése után érdemes információkat kérni a helyzetéről és méretéről. Meg tudjuk kapni a tényleges X és Y koordinátákat, valamint a diagramon látható terület szélességét és magasságát.

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

## 5. lépés: A prezentáció mentése

 Végül ne felejtse el menteni a módosított prezentációt. Ebben a példában a következő néven mentjük el`Result.pptx`, de szükség esetén más fájlnevet is megadhat.

```java
pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
```

## A Java Slides-hez hozzáadott diagramelrendezés érvényesítésének teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Prezentáció mentése
	pres.save(dataDir + "Result.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban elmélyültünk a PowerPoint-prezentációk diagramjaival való munka világában az Aspose.Slides for Java használatával. Áttekintettük a diagramelrendezés érvényesítésének, pozíciójának és méretének lekéréséhez, valamint a módosított prezentáció mentéséhez szükséges alapvető lépéseket. Íme egy gyors összefoglaló:

## GYIK

### Hogyan változtathatom meg a diagram típusát?

 A diagram típusának megváltoztatásához egyszerűen cserélje ki`ChartType.ClusteredColumn` kívánt diagramtípussal a`addChart()` módszer.

### Testreszabhatom a diagram adatait?

Igen, testreszabhatja a diagram adatait adatsorok, kategóriák és értékek hozzáadásával és módosításával. További részletekért tekintse meg az Aspose.Slides dokumentációját.

### Mi a teendő, ha más diagramtulajdonságokat szeretnék módosítani?

Különféle diagramtulajdonságokat érhet el, és igényei szerint testreszabhatja azokat. Fedezze fel az Aspose.Slides dokumentációját a diagramkezeléssel kapcsolatos átfogó információkért.

{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
