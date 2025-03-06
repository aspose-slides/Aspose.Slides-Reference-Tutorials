---
title: Adatcímkék százalékos bejelentkezés beállítása a Java Slides szolgáltatásban
linktitle: Adatcímkék százalékos bejelentkezés beállítása a Java Slides szolgáltatásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be adatcímkéket százalékjelekkel a PowerPoint-prezentációkban az Aspose.Slides for Java segítségével. Hozzon létre lenyűgöző diagramokat lépésről lépésre útmutatóval és forráskóddal.
type: docs
weight: 17
url: /hu/java/data-manipulation/set-data-labels-percentage-sign-java-slides/
---

## Bevezetés az adatcímkék százalékos bejelentkezésébe az Aspose.Slides for Java-ban

Ebben az útmutatóban végigvezetjük a százalékjellel ellátott adatcímkék beállításának folyamatán az Aspose.Slides for Java segítségével. Létrehozunk egy PowerPoint prezentációt halmozott oszlopdiagrammal, és beállítjuk az adatcímkéket a százalékok megjelenítéséhez.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár hozzáadva van a projekthez. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Hozzon létre egy új prezentációt

Először is létrehozunk egy új PowerPoint-prezentációt az Aspose.Slides segítségével.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
```

## 2. lépés: Adjon hozzá egy dia és egy diagramot

Ezután hozzáadunk egy diát és egy halmozott oszlopdiagramot a bemutatóhoz.

```java
// Szerezzen hivatkozást a diára
ISlide slide = presentation.getSlides().get_Item(0);

// Adja hozzá a PercentsStackedColumn diagramot egy diához
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## 3. lépés: A tengelyszám formátum konfigurálása

A százalékok megjelenítéséhez konfigurálnunk kell a diagram függőleges tengelyének számformátumát.

```java
// Állítsa be a NumberFormatLinkedToSource értéket false értékre
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## 4. lépés: Diagramadatok hozzáadása

Adatokat adunk a diagramhoz sorozatok és adatpontok létrehozásával. Ebben a példában két sorozatot adunk hozzá a megfelelő adatpontokkal.

```java
// A diagram adatlapjának lekérése
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();

// Új sorozat hozzáadása
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));

// Új sorozat hozzáadása
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
```

## 5. lépés: Az adatcímkék testreszabása

Most pedig szabjuk testre az adatcímkék megjelenését.

```java
// A LabelFormat tulajdonságainak beállítása
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);

series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
```

## 6. lépés: Mentse el a bemutatót

Végül elmentjük a prezentációt egy PowerPoint fájlba.

```java
// Prezentáció írása lemezre
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen létrehozott egy PowerPoint-prezentációt halmozott oszlopdiagrammal és konfigurálta az adatcímkéket a százalékok megjelenítéséhez az Aspose.Slides for Java használatával.

## Teljes forráskód az adatcímkék beállításához, százalékos bejelentkezés a Java Slides-be

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
// Szerezzen hivatkozást a diára
ISlide slide = presentation.getSlides().get_Item(0);
// Adja hozzá a PercentsStackedColumn diagramot egy diához
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Állítsa be a NumberFormatLinkedToSource értéket false értékre
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// A diagram adatlapjának lekérése
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Új sorozat hozzáadása
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// A sorozat kitöltési színének beállítása
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// A LabelFormat tulajdonságainak beállítása
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
// Új sorozat hozzáadása
IChartSeries series2 = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.getType());
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 2, 0.35));
// Beállítás Kitöltés típusa és színe
series2.getFormat().getFill().setFillType(FillType.Solid);
series2.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE);
series2.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormatLinkedToSource(false);
series2.getLabels().getDefaultDataLabelFormat().setNumberFormat("0.0%");
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(10);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
series2.getLabels().getDefaultDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
// Prezentáció írása lemezre
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Az útmutató követésével megtanulta, hogyan hozhat létre lenyűgöző prezentációkat százalékos adatcímkékkel, amelyek különösen hasznosak lehetnek az információk hatékony közvetítéséhez üzleti jelentésekben, oktatási anyagokban és egyebekben.

## GYIK

### Hogyan változtathatom meg a diagramsorozat színeit?

 A diagramsorozatok kitöltési színét a gombbal módosíthatja`setFill` példában látható módszer.

### Testreszabhatom az adatcímkék betűméretét?

Igen, testreszabhatja az adatcímkék betűméretét a`setFontHeight` kódban bemutatott tulajdonság.

### Hogyan tudok több sorozatot hozzáadni a diagramhoz?

 A diagram segítségével további sorozatokat adhat hozzá`add` módszer a`IChartSeriesCollection` tárgy.
