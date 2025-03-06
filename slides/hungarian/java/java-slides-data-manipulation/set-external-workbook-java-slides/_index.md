---
title: Állítsa be a külső munkafüzetet a Java Slides alkalmazásban
linktitle: Állítsa be a külső munkafüzetet a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be külső munkafüzeteket a Java Slides programban az Aspose.Slides for Java segítségével. Hozzon létre dinamikus prezentációkat az Excel adatintegrációjával.
weight: 19
url: /hu/java/data-manipulation/set-external-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Bevezetés a külső munkafüzet beállításához Java Slides-ben

Ebben az oktatóanyagban megvizsgáljuk, hogyan állíthat be külső munkafüzetet a Java Slides alkalmazásban az Aspose.Slides segítségével. Megtanulja, hogyan hozhat létre PowerPoint-prezentációt egy külső Excel-munkafüzet adataira hivatkozó diagrammal. Az útmutató végére világosan megérti, hogyan integrálhat külső adatokat a Java Slides prezentációiba.

## Előfeltételek

Mielőtt belevágnánk a megvalósításba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- Java Development Kit (JDK) telepítve a rendszerére.
- Aspose.Slides for Java könyvtár hozzáadva a projekthez.
- Excel-munkafüzet a prezentációban hivatkozni kívánt adatokkal.

## 1. lépés: Hozzon létre egy új prezentációt

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Kezdjük egy új PowerPoint prezentáció létrehozásával az Aspose.Slides segítségével.

## 2. lépés: Adjon hozzá egy diagramot

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Ezután egy kördiagramot illesztünk be a prezentációba. Igény szerint testreszabhatja a diagram típusát és pozícióját.

## 3. lépés: Nyissa meg a külső munkafüzetet

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 A külső munkafüzet eléréséhez a`setExternalWorkbook` módszert, és adja meg az adatokat tartalmazó Excel-munkafüzet elérési útját.

## 4. lépés: A diagramadatok összerendelése

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

Végül elmentjük a bemutatót a külső munkafüzet hivatkozásával PowerPoint fájlként.

## A Java Slides külső munkafüzetének teljes forráskódja

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

Ebben az oktatóanyagban megtanultuk, hogyan állíthat be külső munkafüzetet a Java Slides programban az Aspose.Slides segítségével. Mostantól prezentációkat hozhat létre, amelyek dinamikusan hivatkoznak az Excel-munkafüzetekből származó adatokra, növelve a diák rugalmasságát és interaktivitását.

## GYIK

### Hogyan telepíthetem az Aspose.Slides for Java programot?

Az Aspose.Slides for Java úgy telepíthető, hogy hozzáadja a könyvtárat a Java projekthez. A könyvtár letölthető az Aspose webhelyéről, és kövesse a dokumentációban található telepítési utasításokat.

### Használhatok különböző diagramtípusokat külső munkafüzetekkel?

Igen, az Aspose.Slides által támogatott különféle diagramtípusokat használhatja, és külső munkafüzetekből származó adatokhoz kötheti őket. A folyamat a választott diagramtípustól függően kissé eltérhet.

### Mi a teendő, ha a külső munkafüzetem adatszerkezete megváltozik?

Ha a külső munkafüzet adatszerkezete megváltozik, előfordulhat, hogy frissítenie kell a Java-kód cellahivatkozásait, hogy a diagramadatok pontosak maradjanak.

### Az Aspose.Slides kompatibilis a legújabb Java-verziókkal?

Az Aspose.Slides for Java programot rendszeresen frissítik, hogy biztosítsák a kompatibilitást a legújabb Java-verziókkal. Ügyeljen arra, hogy ellenőrizze a frissítéseket, és használja a könyvtár legújabb verzióját az optimális teljesítmény és kompatibilitás érdekében.

### Hozzáadhatok több diagramot, amelyek ugyanarra a külső munkafüzetre hivatkoznak?

Igen, több diagramot is hozzáadhat a prezentációhoz, amelyek mindegyike ugyanarra a külső munkafüzetre hivatkozik. Egyszerűen ismételje meg az ebben az oktatóanyagban vázolt lépéseket minden létrehozni kívánt diagramnál.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
