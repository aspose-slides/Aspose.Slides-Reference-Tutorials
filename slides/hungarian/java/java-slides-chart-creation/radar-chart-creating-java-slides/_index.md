---
title: Radar diagram létrehozása Java Slides-ben
linktitle: Radar diagram létrehozása Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre radardiagramokat Java PowerPoint prezentációkban az Aspose.Slides for Java API használatával.
weight: 10
url: /hu/java/chart-creation/radar-chart-creating-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Bevezetés a radardiagram létrehozásába Java Slides programban

Ebben az oktatóanyagban végigvezetjük a radardiagram létrehozásának folyamatán az Aspose.Slides for Java API használatával. A radardiagramok hasznosak az adatok körkörös mintázatban történő megjelenítéséhez, megkönnyítve több adatsor összehasonlítását. Lépésről lépésre útmutatást adunk a Java forráskóddal együtt.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár integrálva van a projektjébe. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: A prezentáció beállítása

Kezdjük egy új PowerPoint-prezentáció beállításával, és adjunk hozzá egy diát.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## 2. lépés: Radardiagram hozzáadása

Ezután egy radardiagramot adunk a diához. Meghatározzuk a diagram helyzetét és méreteit.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## 3. lépés: A diagramadatok beállítása

Most beállítjuk a diagram adatait. Ez magában foglalja egy adatmunkafüzet létrehozását, kategóriák és sorozatok hozzáadását.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Állítsa be a diagram címét
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Törölje az alapértelmezett generált sorozatokat és kategóriákat
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Új kategóriák hozzáadása
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Új sorozat hozzáadása
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## 4. lépés: Sorozatadatok feltöltése

Most feltöltjük a sorozatadatokat a radardiagramunkhoz.

```java
// Az 1. sorozathoz tartozó sorozatadatok feltöltése
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Állítsa be a sorozat színét
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// A 2. sorozathoz tartozó sorozatadatok feltöltése
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Állítsa be a sorozat színét
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## 5. lépés: A tengely és a legendák testreszabása

Szabjuk személyre a radardiagram tengelyét és jelmagyarázatát.

```java
// Állítsa be a jelmagyarázat pozícióját
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Kategória tengely szövegtulajdonságainak beállítása
IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
txtCat.setFontBold(NullableBool.True);
txtCat.setFontHeight(10);
txtCat.getFillFormat().setFillType(FillType.Solid);
txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtCat.setLatinFont(new FontData("Calibri"));

// Jelmagyarázatok szövegtulajdonságainak beállítása
IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(10);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtleg.setLatinFont(new FontData("Calibri"));

// Értéktengely szövegtulajdonságainak beállítása
IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
txtVal.setFontBold(NullableBool.True);
txtVal.setFontHeight(10);
txtVal.getFillFormat().setFillType(FillType.Solid);
txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
txtVal.setLatinFont(new FontData("Calibri"));

// Beállítási érték tengelyszám formátum
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// A diagram fő egységértékének beállítása
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## 6. lépés: A prezentáció mentése

Végül mentse el a generált prezentációt a radardiagrammal

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Ez az! Sikeresen létrehozott egy radardiagramot egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Most már tovább szabhatja ezt a példát saját igényeinek megfelelően.

## Teljes forráskód a radardiagram létrehozásához Java Slides-ben

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Hozzáférés az első diához
	ISlide sld = pres.getSlides().get_Item(0);
	// Adjon hozzá radardiagramot
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Diagram adatlap indexének beállítása
	int defaultWorksheetIndex = 0;
	// A diagramadatok munkalap lekérése
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Állítsa be a diagram címét
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Törölje az alapértelmezett generált sorozatokat és kategóriákat
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Új kategóriák hozzáadása
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Új sorozat hozzáadása
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Most a sorozatadatok feltöltése
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Állítsa be a sorozat színét
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	//Most újabb sorozatadatokat tölt fel
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Állítsa be a sorozat színét
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Állítsa be a jelmagyarázat pozícióját
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Kategória tengely szövegtulajdonságainak beállítása
	IChartPortionFormat txtCat = ichart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(10);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Jelmagyarázatok szövegtulajdonságainak beállítása
	IChartPortionFormat txtleg = ichart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(10);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtCat.setLatinFont(new FontData("Calibri"));
	// Értéktengely szövegtulajdonságainak beállítása
	IChartPortionFormat txtVal = ichart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(10);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.DimGray));
	txtVal.setLatinFont(new FontData("Calibri"));
	// Beállítási érték tengelyszám formátum
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// A diagram fő egységértékének beállítása
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// A létrehozott prezentáció mentése
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanulta, hogyan hozhat létre radardiagramot egy PowerPoint-prezentációban az Aspose.Slides for Java használatával. Ezeket a fogalmakat alkalmazhatja adatainak hatékony megjelenítéséhez és megjelenítéséhez Java-alkalmazásaiban.

## GYIK

### Hogyan tudom megváltoztatni a diagram címét?

A diagram címének módosításához módosítsa a következő sort:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Hozzáadhatok több adatsort a radardiagramhoz?

Igen, további adatsorokat is hozzáadhat a „3. lépés” és „4. lépés” lépéseinek követésével minden egyes további adatsorhoz.

### Hogyan szabhatom testre a diagram színeit?

 Testreszabhatja a sorozat színeit a beállító vonalak módosításával`SolidFillColor` tulajdonság minden sorozathoz. Például:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Hogyan módosíthatom a tengelycímkéket és a formázást?

Tekintse meg az "5. lépést" a tengelycímkék és a formázás testreszabásához, beleértve a betűméretet és a színt.

### Hogyan menthetem el a diagramot másik fájlformátumba?

Módosíthatja a kimeneti formátumot a fájl kiterjesztésének módosításával a`outPath` változó és a megfelelő használatával`SaveFormat` . Például PDF formátumban történő mentéshez használja a`SaveFormat.Pdf`.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
