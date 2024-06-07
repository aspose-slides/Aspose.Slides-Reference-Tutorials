---
title: Automatikus kördiagram szeletszínek beállítása a Java diákban
linktitle: Automatikus kördiagram szeletszínek beállítása a Java diákban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre dinamikus kördiagramokat automatikus szeletszínekkel Java PowerPoint prezentációkban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal.
type: docs
weight: 24
url: /hu/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/
---

## Bevezetés az automatikus kördiagram szeletszínek beállításába a Java diákban

Ebben az oktatóanyagban megvizsgáljuk, hogyan hozhatunk létre kördiagramot egy PowerPoint-prezentációban az Aspose.Slides for Java használatával, és hogyan állíthatunk be automatikus szeletszíneket a diagramhoz. Lépésről lépésre útmutatást adunk a forráskóddal együtt.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben. A könyvtár letölthető az Aspose weboldaláról:[Az Aspose.Slides letöltése Java-hoz](https://releases.aspose.com/slides/java/).

## 1. lépés: Importálja a szükséges csomagokat

Először is importálnia kell a szükséges csomagokat az Aspose.Slides for Java alkalmazásból:

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.NullableBool;
import com.aspose.slides.charts.IChartDataWorkbook;
```

## 2. lépés: Hozzon létre egy PowerPoint-bemutatót

 Példányosítsa a`Presentation` osztályban új PowerPoint prezentáció létrehozásához:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 3. lépés: Adjon hozzá egy diát

Nyissa meg a prezentáció első diáját, és adjon hozzá egy diagramot az alapértelmezett adatokkal:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## 4. lépés: Állítsa be a diagram címét

Adja meg a diagram címét:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 5. lépés: A diagramadatok konfigurálása

Állítsa be a diagramot az első sorozat értékeinek megjelenítésére, és konfigurálja a diagram adatait:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

## 6. lépés: Kategóriák és sorozatok hozzáadása

Új kategóriák és sorozatok hozzáadása a diagramhoz:

```java
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));

IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
```

## 7. lépés: Töltse fel a sorozatadatokat

Töltse fel a kördiagram sorozatadatait:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## 8. lépés: Engedélyezze a Változatos szeletszíneket

Változatos szeletszínek engedélyezése a kördiagramhoz:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## 9. lépés: Mentse el a bemutatót

Végül mentse a prezentációt egy PowerPoint fájlba:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Teljes forráskód az automatikus kördiagram szeletszínek beállításához a Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Példányosítási osztály, amely a PPTX fájlt képviseli
Presentation presentation = new Presentation();
try
{
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
	//Most a sorozatadatok feltöltése
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
	series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Sikeresen létrehozott egy kördiagramot egy PowerPoint-prezentációban az Aspose.Slides for Java használatával, és konfigurálta azt, hogy automatikus szeletszíneket használjon. Ez a lépésenkénti útmutató biztosítja az ehhez szükséges forráskódot. Szükség szerint tovább testreszabhatja a diagramot és a prezentációt.

## GYIK

### Hogyan szabhatom testre a kördiagram egyes szeleteinek színét?

 A kördiagram egyes szeleteinek színének testreszabásához használhatja a`getAutomaticSeriesColors` módszerrel lekérheti az alapértelmezett színsémát, majd szükség szerint módosíthatja a színeket. Íme egy példa:

```java
//Szerezze be az alapértelmezett színsémát
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Szükség szerint módosítsa a színeket
colors.get_Item(0).setColor(Color.RED); // Az első szelet színét állítsa pirosra
colors.get_Item(1).setColor(Color.BLUE); // A második szelet színét állítsa kékre
// Igény szerint adjon hozzá további színmódosításokat
```

### Hogyan adhatok hozzá jelmagyarázatot a kördiagramhoz?

 Jelmagyarázat hozzáadásához a kördiagramhoz használhatja a`getLegend` módszert, és állítsa be a következőképpen:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Állítsa be a jelmagyarázat pozícióját
legend.setOverlay(true); // Jelenítse meg a jelmagyarázatot a diagramon
```

### Módosíthatom a cím betűtípusát és stílusát?

Igen, módosíthatja a cím betűtípusát és stílusát. A cím betűtípusának és stílusának beállításához használja a következő kódot:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Betűméret beállítása
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Tegye félkövérre a címet
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // A címet dőlt betűvel szedjük
```

Szükség szerint módosíthatja a betűméretet, a vastagságot és a dőlt stílust.