---
"description": "Tanuld meg, hogyan készíthetsz dobozdiagramokat Java prezentációkban az Aspose.Slides segítségével. Lépésről lépésre útmutató és forráskód is mellékelve a hatékony adatvizualizációhoz."
"linktitle": "Dobozdiagram Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Dobozdiagram Java diákban"
"url": "/hu/java/chart-elements/box-chart-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dobozdiagram Java diákban


## Bevezetés a dobozdiagramba az Aspose.Slides Java-ban

Ebben az oktatóanyagban végigvezetünk egy dobozdiagram létrehozásának folyamatán az Aspose.Slides for Java segítségével. A dobozdiagramok hasznosak különböző kvartiliseket és kiugró értékeket tartalmazó statisztikai adatok vizualizálására. Lépésről lépésre bemutatjuk a folyamatot, valamint forráskódot is biztosítunk, hogy segítsünk az indulásban.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:

- Az Aspose.Slides Java könyvtárhoz telepítve és konfigurálva.
- Java fejlesztői környezet beállítása.

## 1. lépés: A prezentáció inicializálása

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Ebben a lépésben egy prezentációs objektumot inicializálunk egy meglévő PowerPoint fájl elérési útjával (ebben a példában "test.pptx").

## 2. lépés: A dobozdiagram létrehozása

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.BoxAndWhisker, 50, 50, 500, 400);
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
```

Ebben a lépésben egy Dobozdiagram alakzatot hozunk létre a prezentáció első diáján. Emellett töröljük a diagramból a meglévő kategóriákat és sorozatokat is.

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

Ebben a lépésben definiáljuk a Dobozdiagram kategóriáit. A következőt használjuk: `IChartDataWorkbook` kategóriák hozzáadásához és ennek megfelelő címkézéséhez.

## 4. lépés: A sorozat létrehozása

```java
    IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
    series.setQuartileMethod(QuartileMethodType.Exclusive);
    series.setShowMeanLine(true);
    series.setShowMeanMarkers(true);
    series.setShowInnerPoints(true);
    series.setShowOutlierPoints(true);
```

Itt létrehozunk egy BoxAndWhisker sorozatot a diagramhoz, és konfigurálunk különféle opciókat, például a kvartilis módszert, az átlagvonalat, az átlagjelzőket, a belső pontokat és a kiugró pontokat.

## 5. lépés: Adatpontok hozzáadása

```java
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B1", 15));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B2", 41));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B3", 16));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B4", 10));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B5", 23));
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(wb.getCell(0, "B6", 16));
```

Ebben a lépésben adatpontokat adunk a BoxAndWhisker sorozathoz. Ezek az adatpontok a diagram statisztikai adatait jelölik.

## 6. lépés: Mentse el a prezentációt

```java
    pres.save("BoxAndWhisker.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

Végül a Dobozdiagrammal ellátott bemutatót egy új PowerPoint-fájlba mentjük, melynek neve „BoxAndWhisker.pptx”.

Gratulálunk! Sikeresen létrehoztál egy dobozdiagramot az Aspose.Slides for Java segítségével. A diagramot tovább testreszabhatod a különböző tulajdonságok módosításával és további adatpontok hozzáadásával, szükség szerint.

## Teljes forráskód a Java diák dobozdiagramjához

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

Ebben az oktatóanyagban megtanultuk, hogyan hozhatunk létre dobozdiagramot az Aspose.Slides for Java segítségével. A dobozdiagramok értékes eszközök statisztikai adatok, például kvartilisek és kiugró értékek vizualizálására. Lépésről lépésre útmutatót és forráskódot biztosítottunk, hogy segítsünk elkezdeni a dobozdiagramok létrehozását Java alkalmazásaidban.

## GYIK

### Hogyan tudom megváltoztatni a Dobozdiagram megjelenését?

A Dobozdiagram megjelenését testreszabhatja olyan tulajdonságok módosításával, mint a vonalstílusok, színek és betűtípusok. A diagram testreszabásával kapcsolatos részletekért lásd az Aspose.Slides for Java dokumentációját.

### Hozzáadhatok további adatsorokat a dobozdiagramhoz?

Igen, több adatsort is hozzáadhat a Dobozdiagramhoz továbbiak létrehozásával `IChartSeries` objektumok és adatpontok hozzáadása hozzájuk.

### Mit jelent a QuartileMethodType.Exclusive?

A `QuartileMethodType.Exclusive` beállítás azt határozza meg, hogy a kvartilis számításokat kizárólagos módszerrel kell elvégezni. Az adataitól és a követelményektől függően különböző kvartilis számítási módszereket választhat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}