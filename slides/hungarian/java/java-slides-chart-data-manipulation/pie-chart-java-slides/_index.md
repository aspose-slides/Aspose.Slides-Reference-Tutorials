---
title: Kördiagram a Java Slides-ben
linktitle: Kördiagram a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre lenyűgöző kördiagramokat PowerPoint-prezentációkban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal Java fejlesztők számára.
type: docs
weight: 23
url: /hu/java/chart-data-manipulation/pie-chart-java-slides/
---

## Bevezetés a kördiagram létrehozásába Java Slides programban az Aspose.Slides használatával

Ebben az oktatóanyagban bemutatjuk, hogyan lehet kördiagramot létrehozni egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutatást és Java forráskódot adunk az induláshoz. Ez az útmutató feltételezi, hogy már beállította fejlesztői környezetét az Aspose.Slides for Java segítségével.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a projektben. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Importálja a szükséges könyvtárakat

```java
import com.aspose.slides.*;
import com.aspose.slides.charts.*;
```

Ügyeljen arra, hogy importálja a szükséges osztályokat az Aspose.Slides könyvtárból.

## 2. lépés: Inicializálja a prezentációt

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Példányosítási osztály, amely a PPTX fájlt képviseli
Presentation presentation = new Presentation();
```

 Hozzon létre egy új bemutató objektumot a PowerPoint-fájl megjelenítéséhez. Cserélje ki`"Your Document Directory"` azzal a tényleges elérési úttal, ahová a prezentációt menteni szeretné.

## 3. lépés: Adjon hozzá egy diát

```java
// Nyissa meg az első diát
ISlide slide = presentation.getSlides().get_Item(0);
```

Szerezze meg a prezentáció első diáját, amelyhez hozzá szeretné adni a kördiagramot.

## 4. lépés: Kördiagram hozzáadása

```java
// Kördiagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

Adjon hozzá kördiagramot a diához a megadott helyen és méretben.

## 5. lépés: Állítsa be a diagram címét

```java
// Állítsa be a diagram címét
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

Adja meg a kördiagram címét. A címet igény szerint személyre szabhatja.

## 6. lépés: A diagramadatok testreszabása

```java
//Állítsa be az első sorozatot az értékek megjelenítésére
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// A diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;

// A diagram adatlapjának lekérése
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Törölje az alapértelmezett generált sorozatokat és kategóriákat
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Új kategóriák hozzáadása
chart.getChartData().getCategories().add(workbook.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(workbook.getCell(0, 3, 0, "3rd Qtr"));

// Új sorozat hozzáadása
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(0, 0, 1, "Series 1"), chart.getType());

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 30));
```

Testreszabhatja a diagram adatait kategóriák és sorozatok hozzáadásával, valamint értékük beállításával. Ebben a példában három kategóriánk és egy sorozatunk van a megfelelő adatpontokkal.

## 7. lépés: A kördiagram szektorok testreszabása

```java
// Állítsa be a szektor színeit
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

// Testreszabhatja az egyes szektorok megjelenését
IChartDataPoint point1 = series.getDataPoints().get_Item(0);
point1.getFormat().getFill().setFillType(FillType.Solid);
point1.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
// Szektorhatár testreszabása
point1.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point1.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point1.getFormat().getLine().setWidth(3.0);
point1.getFormat().getLine().setStyle(LineStyle.ThinThick);
point1.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Hasonló módon testreszabhatja a többi szektort is
```

Testreszabhatja az egyes szektorok megjelenését a kördiagramon. Módosíthatja a színeket, szegélystílusokat és egyéb vizuális tulajdonságokat.

## 8. lépés: Az adatcímkék testreszabása

```java
// Az adatcímkék testreszabása
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

// Hasonló módon testreszabhatja más adatpontok adatcímkéit
```

Testreszabhatja az adatcímkéket a kördiagram minden adatpontjához. Szabályozhatja, hogy mely értékek jelenjenek meg a diagramon.

## 9. lépés: Vezetővonalak megjelenítése

```java
// A diagram vezető vonalainak megjelenítése
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

Engedélyezze a vezetővonalakat, hogy az adatcímkéket a megfelelő szektorokhoz kapcsolják.

## 10. lépés: Állítsa be a kördiagram elforgatási szögét

```java
// Állítsa be a kördiagram szektorok elforgatási szögét
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
```

Állítsa be a kördiagram szektorok elforgatási szögét. Ebben a példában 180 fokra állítottuk.

## 11. lépés: Mentse el a prezentációt

```java
// Mentse el a bemutatót a kördiagrammal
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Mentse a prezentációt a kördiagrammal a megadott könyvtárba.

## A Java Slides kördiagramjának teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Példányosítási osztály, amely a PPTX fájlt képviseli
Presentation presentation = new Presentation();
// Hozzáférés az első diához
ISlide slides = presentation.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
// Beállítási diagram Cím
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
// Az első sorozat beállítása Értékek megjelenítése
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// A diagram adatlapjának lekérése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Törölje az alapértelmezett generált sorozatokat és kategóriákat
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Új kategóriák hozzáadása
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
// Új sorozat hozzáadása
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Most a sorozatadatok feltöltése
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Az új verzióban nem működik
// Új pontok hozzáadása és szektorszín beállítása
// sorozat.IsColorVaried = igaz;
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
// Hozzon létre egyéni címkéket minden egyes kategóriához az új sorozatokhoz
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
// lbl.setShowCategoryName(true);
lbl1.getDataLabelFormat().setShowValue(true);
IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);
IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);
// Vezetővonalak megjelenítése a diagramhoz
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
// A kördiagram szektorok elforgatási szögének beállítása
chart.getChartData().getSeriesGroups().get_Item(0).setFirstSliceAngle(180);
// Prezentáció mentése diagrammal
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Sikeresen létrehozott kördiagramot egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Testreszabhatja a diagram megjelenését és az adatcímkéket saját igényei szerint. Ez az oktatóanyag egy alapvető példát mutat be, és szükség szerint továbbfejlesztheti és testreszabhatja diagramjait.

## GYIK

### Hogyan változtathatom meg az egyes szektorok színét a kördiagramon?

 A kördiagram egyes szektorai színének megváltoztatásához testreszabhatja az egyes adatpontok kitöltési színét. A megadott kódpéldában bemutattuk, hogyan állíthatjuk be az egyes szektorok kitöltési színét a`getSolidFillColor().setColor()` módszer. Módosíthatja a színértékeket a kívánt megjelenés elérése érdekében.

### Hozzáadhatok további kategóriákat és adatsorokat a kördiagramhoz?

 Igen, további kategóriákat és adatsorokat is hozzáadhat a kördiagramhoz. Ehhez használhatja a`getChartData().getCategories().add()` és`getChartData().getSeries().add()` módszereket, ahogy a példában is látható. Egyszerűen adja meg a megfelelő adatokat és címkéket az új kategóriákhoz és sorozatokhoz a diagram bővítéséhez.

### Hogyan szabhatom testre az adatcímkék megjelenését?

 Az adatcímkék megjelenését testreszabhatja a`getDataLabelFormat()` módszert minden adatpont címkéjén. A példában bemutattuk, hogyan jeleníthető meg az érték az adatcímkéken a segítségével`getDataLabelFormat().setShowValue(true)`. Tovább testreszabhatja az adatcímkéket a megjelenített értékek szabályozásával, a jelmagyarázat kulcsainak megjelenítésével és egyéb formázási beállítások módosításával.

### Módosíthatom a kördiagram címét?

 Igen, módosíthatja a kördiagram címét. A megadott kódban a diagram címét a segítségével állítjuk be`chart.getChartTitle().addTextFrameForOverriding("Sample Title")` . Cserélheted`"Sample Title"` a kívánt címszöveggel.

### Hogyan menthetem el a generált prezentációt a kördiagrammal?

 A prezentáció kördiagrammal történő mentéséhez használja a`presentation.save()` módszer. Adja meg a kívánt fájl elérési útját és nevét, valamint azt a formátumot, amelyben el szeretné menteni a bemutatót. Például:
```java
presentation.save(dataDir + "PieChart_out.pptx", SaveFormat.Pptx);
```

Ügyeljen arra, hogy a megfelelő fájl elérési utat és formátumot adja meg.

### Létrehozhatok más típusú diagramokat az Aspose.Slides for Java használatával?

Igen, az Aspose.Slides for Java különféle diagramtípusokat támogat, beleértve az oszlopdiagramokat, vonaldiagramokat és egyebeket. Különféle típusú diagramokat hozhat létre a`ChartType` diagram hozzáadásakor. A különböző típusú diagramok létrehozásáról az Aspose.Slides dokumentációjában talál további részleteket.

### Hogyan találhatok további információkat és példákat az Aspose.Slides for Java programhoz?

 További információkért, részletes dokumentációért és további példákért keresse fel a[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/). Átfogó forrásokat biztosít a könyvtár hatékony használatához.