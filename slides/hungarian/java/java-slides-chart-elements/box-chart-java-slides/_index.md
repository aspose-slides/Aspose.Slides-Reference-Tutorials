---
title: Dobozdiagram a Java Slides-ben
linktitle: Dobozdiagram a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre dobozdiagramokat Java prezentációkban az Aspose.Slides segítségével. Lépésről lépésre útmutató és forráskód a hatékony adatok megjelenítéséhez.
weight: 10
url: /hu/java/chart-elements/box-chart-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Az Aspose.Slides for Java Box Chart bemutatása

Ebben az oktatóanyagban végigvezetjük a dobozdiagram létrehozásának folyamatán az Aspose.Slides for Java használatával. A dobozdiagramok hasznosak statisztikai adatok megjelenítéséhez különféle kvartilisekkel és kiugró értékekkel. A kezdéshez lépésről lépésre útmutatást adunk a forráskóddal együtt.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Az Aspose.Slides for Java könyvtár telepítve és konfigurálva.
- Java fejlesztői környezet beállítva.

## 1. lépés: Inicializálja a prezentációt

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Ebben a lépésben inicializálunk egy prezentációs objektumot egy meglévő PowerPoint-fájl elérési útjával (a példában "test.pptx").

## 2. lépés: Hozd létre a dobozdiagramot

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Ebben a lépésben létrehozunk egy dobozdiagram alakzatot a bemutató első diáján. Töröljük a meglévő kategóriákat és sorozatokat is a diagramról.

## 3. lépés: Kategóriák meghatározása

```java
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    wb.clear(0);
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
```

 Ebben a lépésben meghatározzuk a dobozdiagram kategóriáit. Használjuk a`IChartDataWorkbook` kategóriák hozzáadásához és megfelelő címkézéséhez.

## 4. lépés: Hozd létre a sorozatot

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Itt létrehozunk egy BoxAndWhisker sorozatot a diagramhoz, és különféle beállításokat konfigurálunk, mint például a kvartilis módszer, az átlagvonal, az átlagjelzők, a belső pontok és a kiugró pontok.

## 5. lépés: Adatpontok hozzáadása

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Ebben a lépésben adatpontokat adunk a BoxAndWhisker sorozathoz. Ezek az adatpontok a diagram statisztikai adatait képviselik.

## 6. lépés: Mentse el a bemutatót

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Végül elmentjük a bemutatót a dobozdiagrammal egy új PowerPoint fájlba, melynek neve "BoxAndWhisker.pptx".

Gratulálunk! Sikeresen létrehozott egy dobozdiagramot az Aspose.Slides for Java segítségével. A diagramot tovább testreszabhatja különféle tulajdonságok módosításával, és szükség szerint további adatpontok hozzáadásával.

## A Java Slides dobozdiagramjának teljes forráskódja

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
	chart.getChartData().getCategories().clear();
	chart.getChartData().getSeries().clear();
	IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
	wb.clear(0);
	chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A4", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A5", "Category 1"));
	chart.getChartData().getCategories().add(wb.getCell(0, "A6", "Category 1"));
	IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
	series.setQuartileMethod(QuartileMethodType.Exclusive);
	series.setShowMeanLine(true);
	series.setShowMeanMarkers(true);
	series.setShowInnerPoints(true);
	series.setShowOutlierPoints(true);
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
	series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
	pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet dobozdiagramot létrehozni az Aspose.Slides for Java használatával. A dobozdiagramok értékes eszközök a statisztikai adatok megjelenítéséhez, beleértve a kvartiliseket és a kiugró értékeket. Lépésről lépésre útmutatót adtunk a forráskóddal együtt, hogy segítsen elkezdeni a dobozdiagramok létrehozását Java-alkalmazásaiban.

## GYIK

### Hogyan változtathatom meg a dobozdiagram megjelenését?

Testreszabhatja a dobozdiagram megjelenését a tulajdonságok, például a vonalstílusok, színek és betűtípusok módosításával. A diagram testreszabásával kapcsolatos részletekért tekintse meg az Aspose.Slides for Java dokumentációt.

### Hozzáadhatok további adatsorokat a dobozdiagramhoz?

 Igen, több adatsort is hozzáadhat a dobozdiagramhoz további létrehozásával`IChartSeries` objektumok és adatpontok hozzáadása hozzájuk.

### Mit jelent a QuartileMethodType.Exclusive?

 A`QuartileMethodType.Exclusive` A beállítás azt határozza meg, hogy a kvartilis számításokat kizárólagos módszerrel kell elvégezni. Adataitól és követelményeitől függően különböző kvartilis számítási módszereket választhat.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
