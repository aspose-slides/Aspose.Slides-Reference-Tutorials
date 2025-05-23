---
"description": "Tanuld meg, hogyan hozhatsz létre radardiagramokat Java PowerPoint prezentációkban az Aspose.Slides for Java API használatával."
"linktitle": "Radardiagram létrehozása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Radardiagram létrehozása Java diákban"
"url": "/hu/java/chart-creation/radar-chart-creating-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Radardiagram létrehozása Java diákban


## Bevezetés a Java Slides radardiagram létrehozásába

Ebben az oktatóanyagban végigvezetünk egy radardiagram létrehozásának folyamatán az Aspose.Slides for Java API használatával. A radardiagramok hasznosak az adatok körkörös mintázatban történő vizualizálására, megkönnyítve több adatsor összehasonlítását. Lépésről lépésre bemutatjuk a folyamatot, valamint a Java forráskódot is.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg róla, hogy az Aspose.Slides for Java könyvtár integrálva van a projektedbe. A könyvtárat innen töltheted le: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: A prezentáció beállítása

Kezdjük egy új PowerPoint-bemutató létrehozásával és egy diának hozzáadásával.

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
```

## 2. lépés: Radardiagram hozzáadása

Ezután hozzáadunk egy radardiagramot a diához. Megadjuk a diagram pozícióját és méreteit.

```java
ISlide sld = pres.getSlides().get_Item(0);
IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
```

## 3. lépés: Diagramadatok beállítása

Most beállítjuk a diagram adatait. Ez magában foglalja egy adatmunkafüzet létrehozását, kategóriák hozzáadását és sorozatok hozzáadását.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();

// Diagram címének beállítása
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");

// Alapértelmezetten generált sorozatok és kategóriák törlése
ichart.getChartData().getCategories().clear();
ichart.getChartData().getSeries().clear();

// Új kategóriák hozzáadása
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 3"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 5"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Category 7"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Category 9"));
ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Category 11"));

// Új sorozatok hozzáadása
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
```

## 4. lépés: Sorozatadatok feltöltése

Most feltöltjük a radardiagramunk sorozatadatait.

```java
// Sorozatadatok feltöltése az 1. sorozathoz
IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));

// Sorozat színének beállítása
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);

// 2. sorozat adatsorainak feltöltése
series = ichart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));

// Sorozat színének beállítása
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
```

## 5. lépés: Tengelyek és jelmagyarázatok testreszabása

Testreszabhatjuk a radardiagram tengelyeit és jelmagyarázatait.

```java
// Jelmagyarázat pozíciójának beállítása
ichart.getLegend().setPosition(LegendPositionType.Bottom);

// Kategóriatengely szövegtulajdonságainak beállítása
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

// Értéktengely számformátumának beállítása
ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");

// Beállítási táblázat fő egységértéke
ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
```

## 6. lépés: A prezentáció mentése

Végül mentse el a létrehozott bemutatót a radardiagrammal

.

```java
pres.save(outPath, SaveFormat.Pptx);
```

Ennyi! Sikeresen létrehoztál egy sugárdiagramot egy PowerPoint bemutatóban az Aspose.Slides for Java használatával. Mostantól testreszabhatod ezt a példát a saját igényeidnek megfelelően.

## Teljes forráskód a Java diákban létrehozott radardiagram létrehozásához

```java
String outPath = "Your Output Directory" + File.separator + "RadarChart_Out.pptx";
Presentation pres = new Presentation();
try
{
	// Első dia elérése
	ISlide sld = pres.getSlides().get_Item(0);
	// Radardiagram hozzáadása
	IChart ichart = sld.getShapes().addChart(ChartType.Radar, 0, 0, 400, 400);
	// Diagram adatlap indexének beállítása
	int defaultWorksheetIndex = 0;
	// A diagram adatainak lekérése Munkalap
	IChartDataWorkbook fact = ichart.getChartData().getChartDataWorkbook();
	// Diagram címének beállítása
	ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
	// Alapértelmezetten generált sorozatok és kategóriák törlése
	ichart.getChartData().getCategories().clear();
	ichart.getChartData().getSeries().clear();
	// Új kategóriák hozzáadása
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 3"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 5"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 4, 0, "Caetegoty 7"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 5, 0, "Caetegoty 9"));
	ichart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 6, 0, "Caetegoty 11"));
	// Új sorozatok hozzáadása
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), ichart.getType());
	ichart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), ichart.getType());
	// Most feltöltjük a sorozat adatait
	IChartSeries series = ichart.getChartData().getSeries().get_Item(0);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 2.7));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 1.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 1, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 1, 5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 1, 3.5));
	// Sorozat színének beállítása
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Most egy másik sorozat adatait töltjük fel
	series = ichart.getChartData().getSeries().get_Item(1);
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 2.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 2.4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 1.6));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 4, 2, 3.5));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 5, 2, 4));
	series.getDataPoints().addDataPointForRadarSeries(fact.getCell(defaultWorksheetIndex, 6, 2, 3.6));
	// Sorozat színének beállítása
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.ORANGE);
	// Jelmagyarázat pozíciójának beállítása
	ichart.getLegend().setPosition(LegendPositionType.Bottom);
	// Kategóriatengely szövegtulajdonságainak beállítása
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
	// Értéktengely számformátumának beállítása
	ichart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	ichart.getAxes().getVerticalAxis().setNumberFormat("\"$\"#,##0.00");
	// Beállítási táblázat fő egységértéke
	ichart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	ichart.getAxes().getVerticalAxis().setMajorUnit(1.25f);
	// Mentse el a létrehozott prezentációt
	pres.save(outPath, SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultad, hogyan hozhatsz létre radardiagramot egy PowerPoint-bemutatóban az Aspose.Slides for Java segítségével. Ezeket a koncepciókat alkalmazhatod az adataid hatékony megjelenítésére és bemutatására Java-alkalmazásaidban.

## GYIK

### Hogyan tudom megváltoztatni a diagram címét?

A diagram címének módosításához módosítsa a következő sort:
```java
ichart.getChartTitle().addTextFrameForOverriding("Radar Chart");
```

### Hozzáadhatok további adatsorokat a radardiagramhoz?

Igen, további adatsorokat is hozzáadhat a „3. lépés” és a „4. lépés” lépéseinek követésével minden egyes további adatsorhoz, amelyet hozzá szeretne adni.

### Hogyan szabhatom testre a diagram színeit?

A sorozat színeit testreszabhatja a sorok színeit meghatározó vonalak módosításával. `SolidFillColor` tulajdonság minden sorozathoz. Például:
```java
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

### Hogyan tudom megváltoztatni a tengelyek feliratait és formázását?

A tengelyfeliratok és formázás, beleértve a betűméretet és -színt, testreszabásához lásd az „5. lépést”.

### Hogyan menthetem el a diagramot egy másik fájlformátumban?

A kimeneti formátumot a fájlkiterjesztés módosításával módosíthatja a `outPath` változó és a megfelelő használatával `SaveFormat`Például PDF formátumban történő mentéshez használja a következőt: `SaveFormat.Pdf`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}