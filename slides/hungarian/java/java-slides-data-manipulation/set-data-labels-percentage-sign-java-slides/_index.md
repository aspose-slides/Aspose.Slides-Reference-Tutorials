---
"description": "Tanuld meg, hogyan állíthatsz be százalékjelekkel ellátott adatcímkéket PowerPoint-bemutatókban az Aspose.Slides for Java segítségével. Készíts lebilincselő diagramokat lépésről lépésre útmutatóval és forráskóddal."
"linktitle": "Adatcímkék százalékos bejelentkezésének beállítása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Adatcímkék százalékos bejelentkezésének beállítása Java diákban"
"url": "/hu/java/data-manipulation/set-data-labels-percentage-sign-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Adatcímkék százalékos bejelentkezésének beállítása Java diákban


## Bevezetés az adatcímkék százalékos jelének beállításába az Aspose.Slides for Java programban

Ebben az útmutatóban végigvezetünk az adatcímkék százalékjellel történő beállításának folyamatán az Aspose.Slides for Java használatával. Létrehozunk egy PowerPoint bemutatót halmozott oszlopdiagrammal, és konfiguráljuk az adatcímkéket a százalékok megjelenítéséhez.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár hozzá van adva a projektedhez. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Új prezentáció létrehozása

Először is létrehozunk egy új PowerPoint prezentációt az Aspose.Slides segítségével.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
```

## 2. lépés: Dia és diagram hozzáadása

Ezután hozzáadunk egy diát és egy halmozott oszlopdiagramot a prezentációhoz.

```java
// Dia hivatkozásának lekérése
ISlide slide = presentation.getSlides().get_Item(0);

// PercentsStackedColumn diagram hozzáadása egy diához
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

## 3. lépés: Tengelyszám-formátum konfigurálása

A százalékos értékek megjelenítéséhez be kell állítanunk a diagram függőleges tengelyének számformátumát.

```java
// Állítsa a NumberFormatLinkedToSource értékét hamisra
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
```

## 4. lépés: Diagramadatok hozzáadása

Adatsorok és adatpontok létrehozásával adunk hozzá adatokat a diagramhoz. Ebben a példában két adatsort adunk hozzá a hozzájuk tartozó adatpontokkal.

```java
// A diagramadatok munkalapjának beszerzése
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

## 5. lépés: Adatcímkék testreszabása

Most pedig szabjuk testre az adatcímkék megjelenését.

```java
// LabelFormat tulajdonságok beállítása
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

## 6. lépés: Mentse el a prezentációt

Végül elmentjük a prezentációt egy PowerPoint fájlba.

```java
// Prezentáció írása lemezre
presentation.save(dataDir + "SetDataLabelsPercentageSign_out.pptx", SaveFormat.Pptx);
```

Ennyi! Sikeresen létrehoztál egy PowerPoint bemutatót halmozott oszlopdiagrammal, és az Aspose.Slides for Java segítségével beállítottad az adatfeliratokat százalékos értékek megjelenítésére.

## Teljes forráskód az adatcímkék százalékos bejelentkezéséhez Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
// Dia hivatkozásának lekérése
ISlide slide = presentation.getSlides().get_Item(0);
// PercentsStackedColumn diagram hozzáadása egy diához
IChart chart = slide.getShapes().addChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
// Állítsa a NumberFormatLinkedToSource értékét hamisra
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setNumberFormat("0.00%");
chart.getChartData().getSeries().clear();
int defaultWorksheetIndex = 0;
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
// Új sorozat hozzáadása
IChartSeries series = chart.getChartData().getSeries().add(workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 2, 1, 0.50));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 3, 1, 0.80));
series.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 4, 1, 0.65));
// Sorozat kitöltési színének beállítása
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// LabelFormat tulajdonságok beállítása
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
// Kitöltés típusának és színének beállítása
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

Az útmutató követésével megtanulta, hogyan hozhat létre lebilincselő prezentációkat százalékos alapú adatfeliratokkal, amelyek különösen hasznosak lehetnek az információk hatékony közvetítésében üzleti jelentésekben, oktatási anyagokban és egyebekben.

## GYIK

### Hogyan tudom megváltoztatni a diagramsorozat színeit?

A diagramsorozatok kitöltési színét a következővel módosíthatja: `setFill` a példában látható módszer.

### Testreszabhatom az adatfeliratok betűméretét?

Igen, testreszabhatja az adatcímkék betűméretét a következő beállítással: `setFontHeight` tulajdonság, ahogy a kódban is látható.

### Hogyan adhatok hozzá több sorozatot a diagramhoz?

További sorozatokat adhatsz a diagramhoz a segítségével. `add` módszer a `IChartSeriesCollection` objektum.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}