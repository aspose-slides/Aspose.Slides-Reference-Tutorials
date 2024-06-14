---
title: Szerezze meg a diagram adatcímkéjének tényleges pozícióját a Java Slides-ben
linktitle: Szerezze meg a diagram adatcímkéjének tényleges pozícióját a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan kaphatja meg a diagram adatcímkéinek tényleges pozícióját a Java Slides programban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal.
type: docs
weight: 18
url: /hu/java/data-manipulation/actual-position-chart-data-label-java-slides/
---

## Bevezetés a diagram adatcímke tényleges pozíciójának lekéréséhez Java Slides-ben

Ebből az oktatóanyagból megtudhatja, hogyan kérheti le a diagram adatcímkéinek tényleges pozícióját az Aspose.Slides for Java használatával. Létrehozunk egy Java programot, amely PowerPoint prezentációt generál diagrammal, testreszabja az adatcímkéket, majd hozzáadja az adatcímkék pozícióit reprezentáló alakzatokat.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár be van állítva a Java projektben.

## 1. lépés: Hozzon létre egy PowerPoint-bemutatót

Először hozzunk létre egy új PowerPoint-prezentációt, és adjunk hozzá egy diagramot. Az oktatóanyag későbbi részében személyre szabjuk a diagram adatcímkéit.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
    chart.validateChartLayout();
} finally {
    if (pres != null) pres.dispose();
}
```

## 2. lépés: Az adatcímkék testreszabása
Most pedig szabjuk testre a diagramsorozat adatcímkéit. Beállítjuk a helyzetüket és megmutatjuk az értékeket.

```java
try {
    // ... (előző kód)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (fennmaradó kód)
} finally {
    if (pres != null) pres.dispose();
}
```

## 3. lépés: Az adatcímkék tényleges pozíciójának lekérése
Ebben a lépésben végigfutjuk a diagramsorozat adatpontjait, és lekérjük a 4-nél nagyobb értékű adatcímkék tényleges pozícióját. Ezután ellipsziseket adunk hozzá a pozíciók ábrázolásához.

```java
try {
    // ... (előző kód)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        for (IChartDataPoint point : series.getDataPoints()) {
            if (point.getValue().toDouble() > 4) {
                float x = point.getLabel().getActualX();
                float y = point.getLabel().getActualY();
                float w = point.getLabel().getActualWidth();
                float h = point.getLabel().getActualHeight();
                IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
                shape.getFillFormat().setFillType(FillType.Solid);
                shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());
            }
        }
    }
    // ... (fennmaradó kód)
} finally {
    if (pres != null) pres.dispose();
}
```

## 4. lépés: Mentse el a bemutatót
Végül mentse a létrehozott prezentációt fájlba.

```java
try {
    // ... (előző kód)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Teljes forráskód a diagram adatcímke tényleges pozíciójának lekéréséhez a Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400);
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
		series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	}
	chart.validateChartLayout();
	for (IChartSeries series : chart.getChartData().getSeries())
	{
		for (IChartDataPoint point : series.getDataPoints())
		{
			if (point.getValue().toDouble() > 4)
			{
				float x = point.getLabel().getActualX();
				float y = point.getLabel().getActualY();
				float w = point.getLabel().getActualWidth();
				float h = point.getLabel().getActualHeight();
				IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
				shape.getFillFormat().setFillType(FillType.Solid);
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//CSINÁLNI
			}
		}
	}
	pres.save(dataDir + "GetActualPositionOFChartDatalabel", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan kérheti le a diagram adatcímkéinek tényleges helyzetét a Java Slides programban az Aspose.Slides for Java segítségével. Ezt a tudást most felhasználhatja PowerPoint-prezentációinak testreszabott adatcímkéivel és pozícióik vizuális megjelenítésével.

## GYIK

### Hogyan szabhatom testre az adatcímkéket egy diagramon?

 A diagram adatcímkéinek testreszabásához használhatja a`setDefaultDataLabelFormat` módszert a diagramsorozaton, és állítsa be a tulajdonságokat, például a pozíciót és a láthatóságot. Például:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Hogyan adhatok hozzá alakzatokat az adatcímke pozícióinak megjelenítéséhez?

 Iterálhat egy diagramsorozat adatpontjain, és használhatja a`getActualX`, `getActualY`, `getActualWidth` , és`getActualHeight`az adatcímke pozíciójának megállapításához szükséges módszereket. Ezután alakzatokat adhat hozzá a`addAutoShape` módszer. Íme egy példa:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Hogyan tudom elmenteni a generált prezentációt?

 A létrehozott prezentációt a`save` módszer. Adja meg a kívánt fájl elérési utat és a`SaveFormat` mint paraméterek. Például:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```