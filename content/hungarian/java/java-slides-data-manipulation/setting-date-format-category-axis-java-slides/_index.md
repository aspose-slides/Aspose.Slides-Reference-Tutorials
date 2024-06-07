---
title: Dátumformátum beállítása a Java Slides kategóriatengelyéhez
linktitle: Dátumformátum beállítása a Java Slides kategóriatengelyéhez
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be dátumformátumot a kategóriatengelyhez egy PowerPoint diagramon az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal.
type: docs
weight: 26
url: /hu/java/data-manipulation/setting-date-format-category-axis-java-slides/
---

## Bevezetés a Java Slides kategóriatengely dátumformátumának beállításába

Ebben az oktatóanyagban megtanuljuk, hogyan állíthat be dátumformátumot a kategóriatengelyhez egy PowerPoint diagramban az Aspose.Slides for Java segítségével. Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi PowerPoint prezentációk programozott létrehozását, kezelését és kezelését.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

1. Aspose.Slides for Java könyvtár (letöltheti a[itt](https://releases.aspose.com/slides/java/).
2. Java fejlesztői környezet beállítása.

## 1. lépés: Hozzon létre egy PowerPoint-bemutatót

Először is létre kell hoznunk egy PowerPoint prezentációt, amelyhez hozzáadunk egy diagramot. Győződjön meg arról, hogy importálta a szükséges Aspose.Slides osztályokat.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Adjon hozzá egy diagramot a diához

Most adjunk hozzá egy diagramot a PowerPoint diához. Ebben a példában egy területdiagramot fogunk használni.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## 3. lépés: Készítse elő a diagramadatokat

Beállítjuk a diagram adatait és kategóriáit. Ebben a példában dátumkategóriákat fogunk használni.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0);

chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

// Dátumkategóriák hozzáadása
chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

// Adatsorok hozzáadása
IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
```

## 4. lépés: A kategóriatengely testreszabása
Most pedig szabjuk testre a kategóriatengelyt úgy, hogy a dátumokat meghatározott formátumban jelenítse meg (pl. éééé).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## 5. lépés: Mentse el a prezentációt
Végül mentse a PowerPoint bemutatót.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen beállította a dátumformátumot a kategóriatengelyhez egy PowerPoint diagramban az Aspose.Slides for Java segítségével.

## Teljes forráskód a Java Slides kategóriatengelyének dátumformátumának beállításához

```java
	// A dokumentumok könyvtárának elérési útja.
	String dataDir = "Your Document Directory";
	Presentation pres = new Presentation();
	try
	{
		IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
		IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
		wb.clear(0);
		chart.getChartData().getCategories().clear();
		chart.getChartData().getSeries().clear();
		chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
		chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));
		IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
		series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));
		chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
		chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
		chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
		pres.save(RunExamples.getOutPath() + "test.pptx", SaveFormat.Pptx);
	}
	finally
	{
		if (pres != null) pres.dispose();
	}
}
public static String convertToOADate(GregorianCalendar date) throws ParseException
{
	double oaDate;
	SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
	java.util.Date baseDate = myFormat.parse("30 12 1899");
	Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);
	oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24) + ((double) date.get(Calendar.MINUTE) / (60 * 24)) + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
	return String.valueOf(oaDate);
```

##Következtetés

Sikeresen testreszabta a dátumformátumot a kategóriatengelyhez a Java Slides diagramban az Aspose.Slides for Java segítségével. Ez lehetővé teszi, hogy a dátumértékeket a kívánt formátumban jelenítse meg a diagramokon. Nyugodtan fedezze fel a további testreszabási lehetőségeket sajátos igényei alapján.

## GYIK

### Hogyan változtathatom meg a kategóriatengely dátumformátumát?

 A kategóriatengely dátumformátumának módosításához használja a`setNumberFormat` módszert a kategóriatengelyen, és adja meg a kívánt dátumformátum-mintát, például „éééé-hh-nn” vagy “hh/éééé”. Ügyeljen a beállításra`setNumberFormatLinkedToSource(false)` az alapértelmezett formátum felülbírálásához.

### Használhatok különböző dátumformátumokat a különböző diagramokhoz ugyanabban a prezentációban?

Igen, beállíthat különböző dátumformátumokat a kategóriatengelyekhez ugyanazon a bemutatón belül a különböző diagramokon. Egyszerűen szabja testre a kategóriatengelyt az egyes diagramokhoz, ha szükséges.

### Hogyan adhatok hozzá további adatpontokat a diagramhoz?

 Ha további adatpontokat szeretne hozzáadni a diagramhoz, használja a`getDataPoints().addDataPointForLineSeries`módszert az adatsoron, és adja meg az adatértékeket.