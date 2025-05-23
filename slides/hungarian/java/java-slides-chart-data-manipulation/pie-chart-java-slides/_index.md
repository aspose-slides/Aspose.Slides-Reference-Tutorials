---
"description": "Tanuld meg, hogyan készíthetsz lenyűgöző kördiagramokat PowerPoint prezentációkban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal Java fejlesztők számára."
"linktitle": "Kördiagram Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Kördiagram Java diákban"
"url": "/hu/java/chart-data-manipulation/pie-chart-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Kördiagram Java diákban


## Bevezetés a Java-beli kördiagramok készítéséhez az Aspose.Slides használatával

Ebben az oktatóanyagban bemutatjuk, hogyan hozhatsz létre kördiagramot egy PowerPoint bemutatóban az Aspose.Slides for Java használatával. Lépésről lépésre bemutatjuk a folyamatot, és bemutatjuk a Java forráskódot is, hogy segítsünk az indulásban. Ez az útmutató feltételezi, hogy már beállítottad a fejlesztői környezetedet az Aspose.Slides for Java segítségével.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és konfigurálva van a projektedben. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Szükséges könyvtárak importálása

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Ügyelj arra, hogy importáld a szükséges osztályokat az Aspose.Slides könyvtárból.

## 2. lépés: A prezentáció inicializálása

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// PPTX fájlt reprezentáló megjelenítési osztály példányosítása
Presentation presentation = new Presentation();
```

Hozz létre egy új Presentation objektumot a PowerPoint fájlod ábrázolására. `"Your Document Directory"` a prezentáció mentésének tényleges elérési útjával.

## 3. lépés: Dia hozzáadása

```java
// Az első dia elérése
ISlide slide = presentation.getSlides().get_Item(0);
```

Keresse meg a bemutató első diáját, ahová a kördiagramot hozzá szeretné adni.

## 4. lépés: Kördiagram hozzáadása

```java
// Alapértelmezett adatokat tartalmazó kördiagram hozzáadása
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Kördiagram hozzáadása a diához a megadott helyen és méretben.

## 5. lépés: Diagram címének beállítása

```java
// Diagram címének beállítása
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Adjon meg egy címet a kördiagramnak. A címet szükség szerint testreszabhatja.

## 6. lépés: Diagramadatok testreszabása

```java
// Az első sorozat beállítása értékek megjelenítésére
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// A diagram adatlapjának indexének beállítása
int defaultWorksheetIndex = 0;

// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Alapértelmezetten generált sorozatok és kategóriák törlése
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Új kategóriák hozzáadása
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Új sorozatok hozzáadása
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Testreszabhatja a diagram adatait kategóriák és sorozatok hozzáadásával, valamint értékük beállításával. Ebben a példában három kategóriánk és egy sorozatunk van a megfelelő adatpontokkal.

## 7. lépés: A kördiagram szektorainak testreszabása

```java
// Szektorszínek beállítása
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Testreszabhatja az egyes szektorok megjelenését
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Szektorszegély testreszabása
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Más szektorok testreszabása hasonló módon
```

Testreszabhatja a kördiagram egyes szektorainak megjelenését. Módosíthatja a színeket, a szegélystílusokat és egyéb vizuális tulajdonságokat.

## 8. lépés: Adatcímkék testreszabása

```java
// Adatcímkék testreszabása
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Más adatpontok adatcímkéinek testreszabása hasonló módon
```

Testreszabhatja az adatcímkéket a kördiagram minden egyes adatpontjához. Beállíthatja, hogy mely értékek jelenjenek meg a diagramon.

## 9. lépés: Vezetővonalak megjelenítése

```java
// Diagram vezető vonalainak megjelenítése
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Engedélyezze a vezetővonalakat az adatcímkék megfelelő szektorokhoz való csatlakoztatásához.

## 10. lépés: Kördiagram elforgatási szögének beállítása

```java
// A kördiagram szektorainak elforgatási szögének beállítása
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Állítsd be a kördiagram szektorainak elforgatási szögét. Ebben a példában 180 fokra állítottuk be.

## 11. lépés: Mentse el a prezentációt

```java
// A prezentáció mentése kördiagrammal
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Mentse el a kördiagramot tartalmazó bemutatót a megadott könyvtárba.

## Teljes forráskód a Java Slides kördiagramhoz

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// PPTX fájlt reprezentáló megjelenítési osztály példányosítása
Presentation presentation = new Presentation();
// Első dia elérése
ISlide slides = presentation.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Beállítási táblázat címe
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Az első sorozat beállítása az Értékek megjelenítése lehetőségre
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Alapértelmezetten generált sorozatok és kategóriák törlése
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Új kategóriák hozzáadása
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Új sorozatok hozzáadása
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Most feltöltjük a sorozat adatait
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Nem működik az új verzióban
// Új pontok hozzáadása és szektorszín beállítása
// series.IsColorVaried = true;
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);
IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Szektorhatár beállítása
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);
IChartDataPoint point1 = series.getDataPoints().get_Item(1);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Brown));
// Szektorhatár beállítása
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.Single);
point1.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDot);
IChartDataPoint point2 = series.getDataPoints().get_Item(2);
point2.getFormat().getFill().setFillType(FillType.Solid);
point2.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Coral));
// Szektorhatár beállítása
point2.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point2.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
point2.getFormat().getLine().setWidth(2.0);
point2.getFormat().getLine().setStyle(LineStyle.ThinThin);
point2.getFormat().getLine().setDashStyle(LineDashStyle.LargeDashDotDot);
// Hozzon létre egyéni címkéket az új sorozatok kategóriáihoz
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setMutasdKategóriaNeved(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Diagram vezető vonalainak megjelenítése
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// Kördiagram szektorok elforgatási szögének beállítása
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Prezentáció mentése diagrammal
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Sikeresen létrehoztál egy kördiagramot egy PowerPoint bemutatóban az Aspose.Slides for Java segítségével. A diagram megjelenését és adatfeliratait testreszabhatod az igényeid szerint. Ez az oktatóanyag egy alapvető példát mutat be, és a diagramokat szükség szerint tovább finomíthatod és testreszabhatod.

## GYIK

### Hogyan tudom megváltoztatni az egyes szektorok színét a kördiagramban?

kördiagram egyes szektorainak színének módosításához testreszabhatja az egyes adatpontok kitöltési színét. A megadott kódpéldában bemutattuk, hogyan állíthatja be az egyes szektorok kitöltési színét a `getSolidFillColor().setColor()` módszer. A kívánt megjelenés eléréséhez módosíthatja a színértékeket.

### Hozzáadhatok további kategóriákat és adatsorokat a kördiagramhoz?

Igen, további kategóriákat és adatsorokat adhatsz hozzá a kördiagramhoz. Ehhez használhatod a `getChartData().getCategories().add()` és `getChartData().getSeries().add()` metódusok, ahogy a példában is látható. Egyszerűen adja meg a megfelelő adatokat és címkéket az új kategóriákhoz és sorozatokhoz a diagram bővítéséhez.

### Hogyan szabhatom testre az adatcímkék megjelenését?

Az adatcímkék megjelenését testreszabhatja a `getDataLabelFormat()` metódust minden adatpont címkéjén. A példában bemutattuk, hogyan jeleníthető meg az érték az adatcímkéken a következő használatával: `getDataLabelFormat().setShowValue(true)`Az adatfeliratokat tovább testreszabhatja a megjelenítendő értékek szabályozásával, a jelmagyarázat-kulcsok megjelenítésével és egyéb formázási beállítások módosításával.

### Megváltoztathatom a kördiagram címét?

Igen, megváltoztathatod a kördiagram címét. A megadott kódban a diagram címét a következőképpen állítottuk be: `chart.getChartTitle().addTextFrameForOverriding("Sample Title")`. Lecserélheti `"Sample Title"` a kívánt címszöveggel.

### Hogyan menthetem el a kördiagrammal létrehozott bemutatót?

A kördiagrammal ellátott bemutató mentéséhez használja a `presentation.save()` metódus. Adja meg a kívánt fájl elérési útját és nevét, valamint a prezentáció mentésének kívánt formátumát. Például:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Győződjön meg róla, hogy a helyes fájlútvonalat és formátumot adta meg.

### Létrehozhatok más típusú diagramokat az Aspose.Slides for Java használatával?

Igen, az Aspose.Slides Java-ban különféle diagramtípusokat támogat, beleértve az oszlopdiagramokat, vonaldiagramokat és egyebeket. Különböző típusú diagramokat hozhat létre a `ChartType` diagram hozzáadásakor. A különböző típusú diagramok létrehozásával kapcsolatos további részletekért lásd az Aspose.Slides dokumentációját.

### Hogyan találok további információkat és példákat az Aspose.Slides Java-ban való használatához?

További információkért, részletes dokumentációért és további példákért látogasson el a következő oldalra: [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/)Átfogó forrásokat biztosít a könyvtár hatékony használatához.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}