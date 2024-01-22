---
title: Automatikus diagramsorozat színe a Java diákban
linktitle: Automatikus diagramsorozat színe a Java diákban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre dinamikus diagramokat automatikus sorozatszínnel PowerPoint-prezentációkban az Aspose.Slides for Java segítségével. Fokozatmentesen javíthatja az adatok megjelenítését.
type: docs
weight: 14
url: /hu/java/chart-data-manipulation/automatic-chart-series-color-java-slides/
---

## Bevezetés az automatikus diagramsorozat színébe az Aspose.Slides for Java programban

Ebben az oktatóanyagban megvizsgáljuk, hogyan hozhat létre PowerPoint-prezentációt diagrammal az Aspose.Slides for Java használatával, és hogyan állíthat be automatikus kitöltési színeket a diagramsorozatokhoz. Az automatikus kitöltési színek látványosabbá tehetik diagramjait, és időt takaríthatnak meg azáltal, hogy a könyvtár kiválasztja a színeket.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van a projektben. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Hozzon létre egy új bemutatót

Először létrehozunk egy új PowerPoint-prezentációt, és hozzáadunk egy diát.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
```

## 2. lépés: Adjon hozzá egy diagramot a diához

Ezután hozzáadunk egy fürtözött oszlopdiagramot a diához. Az első sorozatot is beállítjuk az értékek megjelenítésére.

```java
// Hozzáférés az első diához
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Az első sorozat beállítása Értékek megjelenítése
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## 3. lépés: Töltse fel a diagramadatokat

Most feltöltjük adatokkal a diagramot. Kezdjük az alapértelmezett generált sorozatok és kategóriák törlésével, majd új sorozatok és kategóriák hozzáadásával.

```java
// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;
// diagram adatlap beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
// Törölje az alapértelmezett generált sorozatokat és kategóriákat
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Új sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Új kategóriák hozzáadása
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
```

## 4. lépés: Töltse fel a sorozatadatokat

sorozatadatokat mind az 1., mind a 2. sorozat esetében feltöltjük.

```java
// Vegyük az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Most a sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);
// Most a sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 5. lépés: Állítsa be a sorozat automatikus kitöltési színét

Most állítsuk be az automatikus kitöltési színeket a diagramsorozatokhoz. Ez arra készteti a könyvtárat, hogy színeket válasszon nekünk.

```java
// Automatikus kitöltési szín beállítása sorozatokhoz
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## 6. lépés: Mentse el a bemutatót

Végül elmentjük a prezentációt a diagrammal egy PowerPoint fájlba.

```java
// Prezentáció mentése diagrammal
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Az automatikus diagramsorozat színeinek teljes forráskódja a Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
try
{
	// Hozzáférés az első diához
	ISlide slide = presentation.getSlides().get_Item(0);
	// Diagram hozzáadása alapértelmezett adatokkal
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
	// Az első sorozat beállítása Értékek megjelenítése
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	// Diagram adatlap indexének beállítása
	int defaultWorksheetIndex = 0;
	// diagram adatlap beszerzése
	IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
	// Törölje az alapértelmezett generált sorozatokat és kategóriákat
	chart.getChartData().getSeries().clear();
	chart.getChartData().getCategories().clear();
	int s = chart.getChartData().getSeries().size();
	s = chart.getChartData().getCategories().size();
	// Új sorozat hozzáadása
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
	chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
	// Új kategóriák hozzáadása
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
	chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
	// Vegyük az első diagramsorozatot
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	// Most a sorozatadatok feltöltése
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	// Automatikus kitöltési szín beállítása sorozatokhoz
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Vegyük a második diagramsorozatot
	series = chart.getChartData().getSeries().get_Item(1);
	// Most a sorozatadatok feltöltése
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Kitöltési szín beállítása sorozatokhoz
	series.getFormat().getFill().setFillType(FillType.Solid);
	series.getFormat().getFill().getSolidFillColor().setColor(Color.GRAY);
	// Prezentáció mentése diagrammal
	presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan hozhat létre PowerPoint-prezentációt diagrammal az Aspose.Slides for Java használatával, és hogyan állíthat be automatikus kitöltési színeket a diagramsorozatokhoz. Az automatikus színek javíthatják a diagramok vizuális vonzerejét, és vonzóbbá tehetik prezentációit. A diagramot igény szerint tovább testreszabhatja az Ön egyedi igényei szerint.

## GYIK

### Hogyan állíthatom be az automatikus kitöltési színeket a diagramsorozatokhoz az Aspose.Slides for Java alkalmazásban?

Az Aspose.Slides for Java diagramsorozatok automatikus kitöltési színeinek beállításához használja a következő kódot:

```java
// Automatikus kitöltési szín beállítása sorozatokhoz
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Ez a kód lehetővé teszi a könyvtár számára, hogy automatikusan válassza ki a színeket a diagramsorozathoz.

### Testreszabhatom a diagram színeit, ha szükséges?

 Igen, szükség szerint testreszabhatja a diagram színeit. A megadott példában automatikus kitöltési színeket használtunk, de az adott színek módosításával beállíthat bizonyos színeket`FillType` és`SolidFillColor` a sorozat formátumának tulajdonságait.

### Hogyan adhatok hozzá további sorozatokat vagy kategóriákat a diagramhoz?

 Ha további sorozatokat vagy kategóriákat szeretne hozzáadni a diagramhoz, használja a`getSeries()` és`getCategories()` diagram módszerei`ChartData` tárgy. Új sorozatokat és kategóriákat adhat hozzá azok adatainak és címkéinek megadásával.

### Lehetséges a diagram és a címkék további formázása?

Igen, szükség szerint tovább formázhatja a diagramot, a sorozatokat és a címkéket. Az Aspose.Slides for Java kiterjedt formázási lehetőségeket kínál a diagramokhoz, beleértve a betűtípusokat, színeket, stílusokat és egyebeket. A formázási beállításokkal kapcsolatos további részletekért tekintse meg a dokumentációt.

### Hol találhatok további információt az Aspose.Slides for Java programmal való munkáról?

 Az Aspose.Slides for Java-ról további információkért és részletes dokumentációért tekintse meg a referenciadokumentációt[itt](https://reference.aspose.com/slides/java/).