---
"description": "Tanuld meg, hogyan állíthatsz be dátumformátumot a kategóriatengelyhez egy PowerPoint-diagramban az Aspose.Slides for Java használatával. Lépésről lépésre útmutató forráskóddal."
"linktitle": "Dátumformátum beállítása a kategóriatengelyhez Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Dátumformátum beállítása a kategóriatengelyhez Java diákban"
"url": "/hu/java/data-manipulation/setting-date-format-category-axis-java-slides/"
"weight": 26
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dátumformátum beállítása a kategóriatengelyhez Java diákban


## Bevezetés a kategóriatengely dátumformátumának beállításába Java diákban

Ebben az oktatóanyagban megtanuljuk, hogyan állíthatunk be dátumformátumot a kategóriatengelyhez egy PowerPoint-diagramban az Aspose.Slides for Java használatával. Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi PowerPoint-bemutatók programozott létrehozását, kezelését és manipulálását.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:

1. Aspose.Slides Java könyvtárhoz (letöltheti innen: [itt](https://releases.aspose.com/slides/java/).
2. Java fejlesztői környezet beállítása.

## 1. lépés: PowerPoint-bemutató létrehozása

Először is létre kell hoznunk egy PowerPoint bemutatót, amelyhez diagramot fogunk hozzáadni. Győződj meg róla, hogy importáltad a szükséges Aspose.Slides osztályokat.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Diagram hozzáadása a diához

Most adjunk hozzá egy diagramot a PowerPoint diához. Ebben a példában egy területdiagramot fogunk használni.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);
```

## 3. lépés: Diagramadatok előkészítése

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
Most szabjuk testre a kategóriatengelyt, hogy a dátumokat egy adott formátumban jelenítse meg (pl. éééé).

```java
chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy");
```

## 5. lépés: Mentse el a prezentációt
Végül mentse el a PowerPoint bemutatót.

```java
pres.save(dataDir + "test.pptx", SaveFormat.Pptx);
```

Ennyi! Sikeresen beállítottál egy dátumformátumot a kategóriatengelyhez egy PowerPoint-diagramban az Aspose.Slides for Java használatával.

## Teljes forráskód a dátumformátum beállításához a kategóriatengelyhez Java diákban

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
		pres.save("Your Output Directory" + "test.pptx", SaveFormat.Pptx);
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

Sikeresen testre szabtad a kategóriatengely dátumformátumát egy Java Slides diagramban az Aspose.Slides for Java használatával. Ez lehetővé teszi, hogy a dátumértékeket a kívánt formátumban jelenítsd meg a diagramokon. Nyugodtan fedezd fel a további testreszabási lehetőségeket az igényeid alapján.

## GYIK

### Hogyan tudom megváltoztatni a kategóriatengely dátumformátumát?

A kategóriatengely dátumformátumának módosításához használja a `setNumberFormat` metódust a kategóriatengelyen, és adja meg a kívánt dátumformátum mintát, például „éééé-HH-nn” vagy „HH/éééé”. Győződjön meg róla, hogy beállította a `setNumberFormatLinkedToSource(false)` az alapértelmezett formátum felülbírálásához.

### Használhatok különböző dátumformátumokat ugyanazon prezentáció különböző diagramjaihoz?

Igen, ugyanazon prezentáción belül különböző diagramokban különböző dátumformátumokat állíthat be a kategóriatengelyekhez. Egyszerűen szabja testre a kategóriatengelyt az egyes diagramok igényei szerint.

### Hogyan adhatok hozzá több adatpontot a diagramhoz?

További adatpontok hozzáadásához a diagramhoz használja a `getDataPoints().addDataPointForLineSeries` metódust az adatsorokon, és adja meg az adatértékeket.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}