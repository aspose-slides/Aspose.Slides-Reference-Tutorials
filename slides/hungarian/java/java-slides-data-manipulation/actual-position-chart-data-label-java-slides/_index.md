---
"description": "Tanuld meg, hogyan szerezheted meg a diagram adatcímkéinek tényleges pozícióját Java diákban az Aspose.Slides for Java használatával. Lépésről lépésre útmutató forráskóddal."
"linktitle": "A diagram adatcímkéjének tényleges pozíciójának lekérése Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "A diagram adatcímkéjének tényleges pozíciójának lekérése Java diákban"
"url": "/hu/java/data-manipulation/actual-position-chart-data-label-java-slides/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# A diagram adatcímkéjének tényleges pozíciójának lekérése Java diákban


## Bevezetés a diagram adatcímkéjének tényleges pozíciójának lekéréséhez Java diákban

Ebben az oktatóanyagban megtanulod, hogyan kérheted le a diagram adatcímkéinek tényleges pozícióját az Aspose.Slides for Java segítségével. Létrehozunk egy Java programot, amely létrehoz egy PowerPoint bemutatót egy diagrammal, testreszabja az adatcímkéket, majd hozzáadja az adatcímkék pozícióját ábrázoló alakzatokat.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár be van állítva a Java projektedben.

## 1. lépés: PowerPoint-bemutató létrehozása

Először is hozzunk létre egy új PowerPoint-bemutatót, és adjunk hozzá egy diagramot. A diagram adatcímkéit a bemutató későbbi részében fogjuk testreszabni.

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

## 2. lépés: Adatcímkék testreszabása
Most szabjuk testre a diagramsorozat adatcímkéit. Beállítjuk a pozíciójukat és megjelenítjük az értékeket.

```java
try {
    // ... (előző kód)
    for (IChartSeries series : chart.getChartData().getSeries()) {
        series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    // ... (a fennmaradó kód)
} finally {
    if (pres != null) pres.dispose();
}
```

## 3. lépés: Az adatcímkék tényleges pozíciójának lekérése
Ebben a lépésben végigmegyünk a diagramsorozat adatpontjain, és lekérjük a 4-nél nagyobb értékű adatcímkék tényleges pozícióját. Ezután kihagyásokat adunk hozzá ezen pozíciók ábrázolásához.

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
    // ... (a fennmaradó kód)
} finally {
    if (pres != null) pres.dispose();
}
```

## 4. lépés: Mentse el a prezentációt
Végül mentse el a létrehozott prezentációt egy fájlba.

```java
try {
    // ... (előző kód)
    pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Teljes forráskód a diagram adatcímkéjének tényleges pozíciójának lekéréséhez Java diákban

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
				shape.getFillFormat().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(100, 0, 255, 0).d());//TENNIVALÓ
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

Ebben az oktatóanyagban megtanultad, hogyan kérheted le a diagram adatcímkéinek tényleges pozícióját Java diákban az Aspose.Slides for Java segítségével. Ezt a tudást most felhasználhatod PowerPoint-bemutatóid fejlesztésére testreszabott adatcímkékkel és azok pozíciójának vizuális ábrázolásával.

## GYIK

### Hogyan szabhatom testre az adatfeliratokat egy diagramban?

A diagram adatcímkéinek testreszabásához használhatja a `setDefaultDataLabelFormat` metódust a diagramsorozaton, és olyan tulajdonságokat állíthat be, mint a pozíció és a láthatóság. Például:
```java
for (IChartSeries series : chart.getChartData().getSeries()) {
    series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.OutsideEnd);
    series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
}
```

### Hogyan adhatok hozzá alakzatokat az adatfeliratok pozícióinak ábrázolásához?

Egy diagramsorozat adatpontjain végighaladva használhatod a `getActualX`, `getActualY`, `getActualWidth`, és `getActualHeight` az adatcímke metódusait a pozíciójának lekéréséhez. Ezután alakzatokat adhat hozzá a `addAutoShape` módszer. Íme egy példa:
```java
float x = point.getLabel().getActualX();
float y = point.getLabel().getActualY();
float w = point.getLabel().getActualWidth();
float h = point.getLabel().getActualHeight();
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Ellipse, x, y, w, h);
```

### Hogyan tudom elmenteni a létrehozott prezentációt?

A létrehozott prezentációt a következővel mentheti el: `save` metódus. Adja meg a kívánt fájl elérési útját és a `SaveFormat` paraméterként. Például:
```java
pres.save(dataDir + "GetActualPositionOFChartDatalabel.pptx", SaveFormat.Pptx);
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}