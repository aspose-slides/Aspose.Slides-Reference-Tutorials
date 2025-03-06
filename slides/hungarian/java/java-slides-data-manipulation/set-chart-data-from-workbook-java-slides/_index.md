---
title: Állítsa be a diagramadatokat a munkafüzetből a Java Slides alkalmazásban
linktitle: Állítsa be a diagramadatokat a munkafüzetből a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be diagramadatokat egy Excel-munkafüzetből a Java Slides alkalmazásban az Aspose.Slides segítségével. Lépésről lépésre útmutató kódpéldákkal dinamikus prezentációkhoz.
type: docs
weight: 15
url: /hu/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Bevezetés a diagramadatok munkafüzetből történő beállításához a Java Slides programban

Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak PowerPoint prezentációkkal. Széleskörű szolgáltatásokat kínál a PowerPoint diák létrehozásához, kezeléséhez és kezeléséhez. A prezentációkkal végzett munka során az egyik általános követelmény a diagramadatok dinamikus beállítása külső adatforrásból, például Excel-munkafüzetből. Ebben az oktatóanyagban bemutatjuk, hogyan érhető el ez a Java használatával.

## Előfeltételek

Mielőtt belevágnánk a megvalósításba, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:

- Java Development Kit (JDK) telepítve a rendszerére.
- Aspose.Slides for Java könyvtár hozzáadva a projekthez.
- Egy Excel-munkafüzet a diagramhoz használni kívánt adatokkal.

## 1. lépés: Hozzon létre egy prezentációt

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Kezdjük egy új PowerPoint prezentáció létrehozásával az Aspose.Slides for Java segítségével.

## 2. lépés: Adjon hozzá egy diagramot

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Ezután hozzáadunk egy diagramot a prezentáció egyik diájához. Ebben a példában kördiagramot adunk hozzá, de kiválaszthatja az igényeinek megfelelő diagramtípust.

## 3. lépés: A diagramadatok törlése

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Minden meglévő adatot törölünk a diagramból, hogy felkészítsük az Excel-munkafüzet új adataira.

## 4. lépés: Töltse be az Excel-munkafüzetet

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 Betöltjük azt az Excel munkafüzetet, amely a diagramhoz használni kívánt adatokat tartalmazza. Cserélje ki`"book1.xlsx"` az Excel-fájl elérési útjával.

## 5. lépés: Írja be a munkafüzet adatfolyamot a diagramadatok közé

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Az Excel munkafüzet adatait folyammá alakítjuk és a diagramadatokba írjuk.

## 6. lépés: Állítsa be a diagram adattartományát

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Megadjuk az Excel-munkafüzet azon celláinak tartományát, amelyeket adatként kell használni a diagramhoz. Állítsa be a tartományt az adatoknak megfelelően.

## 7. lépés: A diagramsorozat testreszabása

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Testreszabhatja a diagramsorozat különféle tulajdonságait az igényeinek megfelelően. Ebben a példában változatos színeket engedélyezünk a diagramsorozatokhoz.

## 8. lépés: Mentse el a prezentációt

```java
pres.save(outPath, SaveFormat.Pptx);
```

Végül elmentjük a prezentációt a frissített diagramadatokkal a megadott kimeneti útvonalra.

## A Java Slides munkafüzetből származó diagramadatok teljes forráskódja

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan állíthat be diagramadatokat egy Excel-munkafüzetből a Java Slides programban az Aspose.Slides for Java könyvtár használatával. A lépésenkénti útmutató követésével és a mellékelt forráskód-példák használatával könnyedén integrálhatja a dinamikus diagramadatokat PowerPoint-prezentációiba.

## GYIK

### Hogyan szabhatom testre a diagram megjelenését a prezentációmban?

Testreszabhatja a diagram megjelenését a tulajdonságok, például színek, betűtípusok, címkék és egyebek módosításával. A diagram testreszabási lehetőségeiről az Aspose.Slides for Java dokumentációjában talál részletes információkat.

### Használhatok egy másik Excel-fájlból származó adatokat a diagramhoz?

Igen, bármilyen Excel-fájlból felhasználhatja az adatokat, ha megadja a helyes fájl elérési utat a munkafüzet kódban való betöltésekor.

### Milyen más típusú diagramokat hozhatok létre az Aspose.Slides for Java programmal?

Az Aspose.Slides for Java különféle diagramtípusokat támogat, beleértve az oszlopdiagramokat, vonaldiagramokat, szóródiagramokat és még sok mást. Kiválaszthatja az adatábrázolási igényeinek leginkább megfelelő diagramtípust.

### Lehetséges a diagramadatok dinamikus frissítése futó prezentációban?

Igen, dinamikusan frissítheti a diagramadatokat egy prezentációban az alapul szolgáló munkafüzet módosításával, majd a diagramadatok frissítésével.

### Hol találhatok további példákat és forrásokat az Aspose.Slides for Java használatához?

 További példákat és forrásokat fedezhet fel a[Aspose honlapja](https://www.aspose.com/). Ezenkívül az Aspose.Slides for Java dokumentáció átfogó útmutatást ad a könyvtár használatához.