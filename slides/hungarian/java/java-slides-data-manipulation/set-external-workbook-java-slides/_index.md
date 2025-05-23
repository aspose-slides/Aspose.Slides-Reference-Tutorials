---
"description": "Ismerje meg, hogyan állíthat be külső munkafüzeteket Java Slides-ben az Aspose.Slides for Java használatával. Készítsen dinamikus prezentációkat Excel adatintegrációval."
"linktitle": "Külső munkafüzet beállítása Java Slides-ben"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Külső munkafüzet beállítása Java Slides-ben"
"url": "/hu/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Külső munkafüzet beállítása Java Slides-ben


## Bevezetés a külső munkafüzet beállításába Java Slides-ben

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan állíthatunk be külső munkafüzetet Java Slides-ben az Aspose.Slides használatával. Megtanulod, hogyan hozhatsz létre PowerPoint-bemutatót egy olyan diagrammal, amely egy külső Excel-munkafüzetből származó adatokra hivatkozik. Az útmutató végére világos képet kapsz arról, hogyan integrálhatsz külső adatokat a Java Slides-bemutatóidba.

## Előfeltételek

Mielőtt belevágnánk a megvalósításba, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

- Java fejlesztőkészlet (JDK) telepítve van a rendszerére.
- Az Aspose.Slides for Java könyvtár hozzáadva a projektedhez.
- Egy Excel-munkafüzet, amely tartalmazza a bemutatóban hivatkozni kívánt adatokat.

## 1. lépés: Új prezentáció létrehozása

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Először egy új PowerPoint prezentációt hozunk létre az Aspose.Slides segítségével.

## 2. lépés: Diagram hozzáadása

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Ezután beszúrunk egy kördiagramot a prezentációba. A diagram típusát és pozícióját szükség szerint testreszabhatjuk.

## 3. lépés: Külső munkafüzet elérése

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

A külső munkafüzet eléréséhez a következőt használjuk: `setExternalWorkbook` metódust, és adja meg az adatokat tartalmazó Excel-munkafüzet elérési útját.

## 4. lépés: Diagramadatok kötése

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

A diagramot a külső munkafüzet adataihoz kötjük a sorozatok és kategóriák cellahivatkozásainak megadásával.

## 5. lépés: Mentse el a prezentációt

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Végül a külső munkafüzet-hivatkozással ellátott bemutatót PowerPoint-fájlként mentjük.

## Teljes forráskód a külső munkafüzet beállításához Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan állíthatunk be külső munkafüzetet Java Slides-ban az Aspose.Slides használatával. Mostantól olyan prezentációkat hozhatunk létre, amelyek dinamikusan hivatkoznak az Excel-munkafüzetek adataira, növelve a diák rugalmasságát és interaktivitását.

## GYIK

### Hogyan telepíthetem az Aspose.Slides-t Java-hoz?

Az Aspose.Slides Java-hoz telepíthető a könyvtár Java-projekthez való hozzáadásával. A könyvtárat letöltheti az Aspose webhelyéről, és követheti a dokumentációban található telepítési utasításokat.

### Használhatok különböző diagramtípusokat külső munkafüzetekkel?

Igen, használhatsz különféle, az Aspose.Slides által támogatott diagramtípusokat, és külső munkafüzetekből származó adatokhoz kötheted őket. A folyamat kissé eltérhet a választott diagramtípustól függően.

### Mi van, ha megváltozik a külső munkafüzetem adatszerkezete?

Ha a külső munkafüzet adatainak szerkezete megváltozik, előfordulhat, hogy frissítenie kell a cellahivatkozásokat a Java-kódban, hogy a diagram adatai pontosak maradjanak.

### Kompatibilis az Aspose.Slides a legújabb Java verziókkal?

Az Aspose.Slides Java-hoz rendszeresen frissül, hogy biztosítsa a kompatibilitást a legújabb Java verziókkal. Az optimális teljesítmény és kompatibilitás érdekében ellenőrizze a frissítéseket, és használja a könyvtár legújabb verzióját.

### Hozzáadhatok több diagramot, amelyek ugyanarra a külső munkafüzetre hivatkoznak?

Igen, több diagramot is hozzáadhat a bemutatójához, amelyek mindegyike ugyanarra a külső munkafüzetre hivatkozik. Egyszerűen ismételje meg az ebben az oktatóanyagban ismertetett lépéseket minden létrehozni kívánt diagramhoz.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}