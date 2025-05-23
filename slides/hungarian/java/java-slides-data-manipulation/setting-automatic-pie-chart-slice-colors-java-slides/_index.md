---
"description": "Tanuld meg, hogyan hozhatsz létre dinamikus kördiagramokat automatikus szeletszínekkel Java PowerPoint prezentációkban az Aspose.Slides for Java használatával. Lépésről lépésre útmutató forráskóddal."
"linktitle": "Automatikus kördiagram szeletek színeinek beállítása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Automatikus kördiagram szeletek színeinek beállítása Java diákban"
"url": "/hu/java/data-manipulation/setting-automatic-pie-chart-slice-colors-java-slides/"
"weight": 24
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatikus kördiagram szeletek színeinek beállítása Java diákban


## Bevezetés a kördiagram szeletek színeinek automatikus beállításába Java diákban

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan hozhatsz létre kördiagramot egy PowerPoint bemutatóban az Aspose.Slides for Java segítségével, és hogyan állíthatsz be automatikus szeletszíneket a diagramhoz. Lépésről lépésre útmutatást és forráskódot is biztosítunk.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java projektedben. A könyvtárat letöltheted az Aspose weboldaláról: [Aspose.Slides letöltése Java-hoz](https://releases.aspose.com/slides/java/).

## 1. lépés: Szükséges csomagok importálása

Először importálnod kell a szükséges csomagokat az Aspose.Slides for Java-ból:

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

## 2. lépés: PowerPoint-bemutató létrehozása

Példányosítsa a `Presentation` osztály új PowerPoint prezentáció létrehozásához:

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 3. lépés: Dia hozzáadása

Nyissa meg a prezentáció első diáját, és adjon hozzá egy diagramot az alapértelmezett adatokkal:

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

## 4. lépés: Diagram címének beállítása

Adjon meg egy címet a diagramnak:

```java
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 5. lépés: Diagramadatok konfigurálása

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

## 7. lépés: Sorozatadatok feltöltése

Töltse ki a kördiagram sorozatadatait:

```java
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

## 8. lépés: Változatos szeletszínek engedélyezése

Különböző szeletszínek engedélyezése a kördiagramhoz:

```java
series.getParentSeriesGroup().setColorVaried(true);
```

## 9. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt egy PowerPoint fájlba:

```java
presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a kördiagram szeletek színeinek automatikus beállításához Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// PPTX fájlt reprezentáló megjelenítési osztály példányosítása
Presentation presentation = new Presentation();
try
{
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
	series.getParentSeriesGroup().setColorVaried(true);
	presentation.save(dataDir + "Pie.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Sikeresen létrehoztál egy kördiagramot egy PowerPoint bemutatóban az Aspose.Slides for Java segítségével, és beállítottad, hogy automatikus szeletszínek legyenek rajta. Ez a lépésenkénti útmutató biztosítja a szükséges forráskódot ehhez. Szükség szerint tovább testreszabhatod a diagramot és a bemutatót.

## GYIK

### Hogyan tudom testreszabni az egyes szeletek színét a kördiagramban?

A kördiagram egyes szeleteinek színeinek testreszabásához használhatja a `getAutomaticSeriesColors` metódus az alapértelmezett színséma lekéréséhez, majd a színek szükség szerinti módosításához. Íme egy példa:

```java
// Az alapértelmezett színséma beszerzése
IColorFormatCollection colors = chart.getChartData().getSeries().get_Item(0).getAutomaticSeriesColors();

// Módosítsa a színeket szükség szerint
colors.get_Item(0).setColor(Color.RED); // Az első szelet színét állítsd pirosra
colors.get_Item(1).setColor(Color.BLUE); // A második szelet színét állítsd kékre
// Szükség szerint további színmódosításokat végezhet
```

### Hogyan adhatok hozzá jelmagyarázatot a kördiagramhoz?

A kördiagramhoz jelmagyarázat hozzáadásához használhatja a `getLegend` metódust, és konfigurálja a következőképpen:

```java
ILegend legend = chart.getLegend();
legend.setPosition(LegendPositionType.Right); // Jelmagyarázat pozíciójának beállítása
legend.setOverlay(true); // Jelmagyarázat megjelenítése a diagram felett
```

### Meg lehet változtatni a cím betűtípusát és stílusát?

Igen, megváltoztathatod a cím betűtípusát és stílusát. Használd a következő kódot a cím betűtípusának és stílusának beállításához:

```java
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(20); // Betűméret beállítása
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontBold(NullableBool.True); // Tedd a címet félkövérré
chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontItalic(NullableBool.True); // A cím legyen dőlt betűs
```

Szükség szerint módosíthatja a betűméretet, a félkövérséget és a dőlt stílust.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}