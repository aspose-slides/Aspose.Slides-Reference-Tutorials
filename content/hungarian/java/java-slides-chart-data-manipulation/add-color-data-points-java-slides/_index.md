---
title: Adjon színt a Java Slides adatpontjaihoz
linktitle: Adjon színt a Java Slides adatpontjaihoz
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat színt a Java diák adatpontjaihoz az Aspose.Slides for Java segítségével.
type: docs
weight: 10
url: /hu/java/chart-data-manipulation/add-color-data-points-java-slides/
---

## Bevezetés a Java Slides adatpontjainak színezésébe

Ebben az oktatóanyagban bemutatjuk, hogyan adhatunk színt a Java diák adatpontjaihoz az Aspose.Slides for Java segítségével. Ez a lépésenkénti útmutató forráskód-példákat tartalmaz, amelyek segítenek a feladat megvalósításában.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

- Java fejlesztői környezet
- Aspose.Slides for Java könyvtár

## 1. lépés: Hozzon létre egy új prezentációt

Először is létrehozunk egy új prezentációt az Aspose.Slides for Java használatával. Ez a prezentáció a diagramunk tárolójaként szolgál majd.

```java
Presentation pres = new Presentation();
```

## 2. lépés: Adjon hozzá egy Sunburst diagramot

Most adjunk hozzá egy Sunburst diagramot a bemutatóhoz. Megadjuk a diagram típusát, pozícióját és méretét.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## 3. lépés: Adatpontok elérése

 A diagram adatpontjainak módosításához el kell érnünk a`IChartDataPointCollection` tárgy.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## 4. lépés: Az adatpontok testreszabása

Ebben a lépésben egyedi adatpontokat fogunk személyre szabni. Itt megváltoztatjuk az adatpontok színét és konfiguráljuk a címkebeállításokat.

```java
// 0. adatpont testreszabása
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// A 9. adatpont testreszabása
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## 5. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a testreszabott diagrammal.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Ez az! Az Aspose.Slides for Java segítségével sikeresen színt adott a Java-diák adott adatpontjaihoz.

## Teljes forráskód a Java Slides adatpontjainak színének hozzáadásához

```java
Presentation pres = new Presentation();
try
{
	// A dokumentumok könyvtárának elérési útja.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//CSINÁLNI
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan adhat színt a Java diák adatpontjaihoz az Aspose.Slides for Java segítségével. Tovább szabhatja diagramjait és prezentációit egyedi igényei szerint.

## GYIK

### Hogyan változtathatom meg más adatpontok színét?

Más adatpontok színének megváltoztatásához a 4. lépésben bemutatotthoz hasonló megközelítést követhet. Nyissa meg a testreszabni kívánt adatpontot, és módosítsa annak szín- és címkebeállításait.

### Testreszabhatom a diagram egyéb aspektusait?

 Igen, testreszabhatja a diagram különböző aspektusait, beleértve a betűtípusokat, címkéket, címeket és egyebeket. Utal[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/) a részletes testreszabási lehetőségekért.

### Hol találok további példákat és dokumentációt?

További példákat és részletes dokumentációt találhat az Aspose.Slides for Java használatáról a webhelyen[Aspose.Slides dokumentáció](https://reference.aspose.com/slides/java/) weboldal.