---
"description": "Tanuld meg, hogyan állíthatsz be diagramadatokat egy Excel-munkafüzetből Java Slides-ben az Aspose.Slides használatával. Lépésről lépésre útmutató kódpéldákkal dinamikus prezentációkhoz."
"linktitle": "Diagramadatok beállítása munkafüzetből Java Slides-ben"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Diagramadatok beállítása munkafüzetből Java Slides-ben"
"url": "/hu/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramadatok beállítása munkafüzetből Java Slides-ben


## Bevezetés a Java Slides munkafüzetből származó diagramadatok beállításába

Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak PowerPoint-bemutatókkal. Kiterjedt funkciókat biztosít a PowerPoint-diák létrehozásához, kezeléséhez és kezeléséhez. A prezentációkkal való munka egyik gyakori követelménye a diagramadatok dinamikus beállítása egy külső adatforrásból, például egy Excel-munkafüzetből. Ebben az oktatóanyagban bemutatjuk, hogyan érhető el ez Java használatával.

## Előfeltételek

Mielőtt belevágnánk a megvalósításba, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

- Java fejlesztőkészlet (JDK) telepítve van a rendszerére.
- Az Aspose.Slides for Java könyvtár hozzáadva a projektedhez.
- Egy Excel-munkafüzet, amely tartalmazza a diagramhoz használni kívánt adatokat.

## 1. lépés: Prezentáció létrehozása

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Először egy új PowerPoint prezentációt hozunk létre az Aspose.Slides for Java használatával.

## 2. lépés: Diagram hozzáadása

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Ezután hozzáadunk egy diagramot a prezentáció egyik diájához. Ebben a példában egy kördiagramot adunk hozzá, de kiválaszthatja az igényeinek megfelelő diagramtípust.

## 3. lépés: Diagramadatok törlése

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Töröljük a diagramból a meglévő adatokat, hogy felkészítsük az Excel-munkafüzetből származó új adatok fogadására.

## 4. lépés: Excel-munkafüzet betöltése

```java
Workbook workbook = new Workbook("Your Document Directory";
```

Betöltjük azt az Excel munkafüzetet, amely a diagramhoz használni kívánt adatokat tartalmazza. Csere `"book1.xlsx"` az Excel-fájl elérési útjával.

## 5. lépés: Munkafüzet-adatfolyam írása diagramadatokká

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Az Excel munkafüzet adatait egy adatfolyammá alakítjuk, és a diagram adataiba írjuk.

## 6. lépés: Diagram adattartományának beállítása

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Megadjuk az Excel munkafüzetből azokat a cellatartományokat, amelyeket a diagram adataként kell használni. Szükség szerint módosítsa a tartományt az adataihoz.

## 7. lépés: Diagramsorozat testreszabása

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

diagramsorozat különböző tulajdonságait testreszabhatja az igényeinek megfelelően. Ebben a példában különböző színeket engedélyezünk a diagramsorozathoz.

## 8. lépés: Mentse el a prezentációt

```java
pres.save(outPath, SaveFormat.Pptx);
```

Végül a frissített diagramadatokkal ellátott prezentációt a megadott kimeneti útvonalra mentjük.

## Teljes forráskód a Java Slides munkafüzetből származó diagramadatokhoz

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

Ebben az oktatóanyagban megtanultuk, hogyan állíthatunk be diagramadatokat egy Excel-munkafüzetből Java Slides-ben az Aspose.Slides for Java könyvtár használatával. A lépésről lépésre bemutatott útmutató követésével és a megadott forráskódpéldák használatával könnyedén integrálhatunk dinamikus diagramadatokat PowerPoint-bemutatóinkba.

## GYIK

### Hogyan tudom testreszabni a diagram megjelenését a prezentációmban?

A diagram megjelenését testreszabhatja olyan tulajdonságok módosításával, mint a színek, betűtípusok, címkék és egyebek. A diagram testreszabási lehetőségeiről részletes információkat az Aspose.Slides for Java dokumentációjában talál.

### Használhatok adatokat egy másik Excel-fájlból a diagramhoz?

Igen, bármelyik Excel-fájlból használhat adatokat, ha a munkafüzet kódba betöltésekor megadja a helyes fájlelérési utat.

### Milyen más típusú diagramokat hozhatok létre az Aspose.Slides for Java segítségével?

Az Aspose.Slides Java-ban különféle diagramtípusokat támogat, beleértve az oszlopdiagramokat, vonaldiagramokat, szóródási diagramokat és egyebeket. Kiválaszthatja az adatábrázolási igényeinek leginkább megfelelő diagramtípust.

### Lehetséges a diagram adatainak dinamikus frissítése egy futó prezentációban?

Igen, a diagramadatokat dinamikusan frissítheti egy bemutatóban az alapul szolgáló munkafüzet módosításával, majd a diagramadatok frissítésével.

### Hol találok további példákat és forrásokat az Aspose.Slides Java-ban való használathoz?

További példákat és forrásokat találhat a következő címen: [Aspose weboldal](https://www.aspose.com/)Ezenkívül az Aspose.Slides for Java dokumentációja átfogó útmutatást nyújt a könyvtárral való munkához.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}