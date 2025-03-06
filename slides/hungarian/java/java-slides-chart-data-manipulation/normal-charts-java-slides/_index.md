---
title: Normál diagramok a Java Slides-ben
linktitle: Normál diagramok a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Hozzon létre normál diagramokat a Java Slides-ben az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató és forráskód diagramok létrehozásához, testreszabásához és mentéséhez PowerPoint prezentációkban.
weight: 21
url: /hu/java/chart-data-manipulation/normal-charts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Normál diagramok a Java Slides-ben


## Bevezetés a Java Slides normál diagramjaiba

Ebben az oktatóanyagban végigvezetjük a normál diagramok létrehozásának folyamatát a Java Slides alkalmazásban az Aspose.Slides for Java API használatával. A forráskóddal együtt lépésről lépésre bemutatjuk, hogyan lehet fürtözött oszlopdiagramot létrehozni egy PowerPoint-prezentációban.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

1. Aspose.Slides for Java API telepítve.
2. Java fejlesztői környezet beállítva.
3. Java programozási alapismeretek.

## 1. lépés: A projekt beállítása

Győződjön meg róla, hogy van könyvtára a projekthez. Nevezzük "Az Ön dokumentumkönyvtárának" a kódban említett módon. Ezt helyettesítheti a projektkönyvtár tényleges elérési útjával.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre könyvtárat, ha még nincs jelen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## 2. lépés: Prezentáció készítése

Most hozzunk létre egy PowerPoint-prezentációt, és nyissa meg az első diát.

```java
// Példányosítási osztály, amely a PPTX fájlt képviseli
Presentation pres = new Presentation();
// Hozzáférés az első diához
ISlide sld = pres.getSlides().get_Item(0);
```

## 3. lépés: Diagram hozzáadása

Hozzáadunk egy fürtözött oszlopdiagramot a diához, és beállítjuk a címét.

```java
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Beállítási diagram Cím
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 4. lépés: A diagramadatok beállítása

Ezután sorozatok és kategóriák meghatározásával állítjuk be a diagram adatait.

```java
// Az első sorozat beállítása Értékek megjelenítése
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;

// A diagram adatlapjának lekérése
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

## 5. lépés: Sorozatadatok feltöltése

Most töltsük fel a diagram sorozatadatpontjait.

```java
// Vegyük az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Kitöltési szín beállítása sorozatokhoz
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Kitöltési szín beállítása sorozatokhoz
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## 6. lépés: A címkék testreszabása

Testreszabjuk a diagramsorozat adatcímkéit.

```java
// Az első címke a kategória nevét fogja mutatni
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);

lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);

// A harmadik címke értékének megjelenítése sorozatnévvel és elválasztóval
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
```

## 7. lépés: A prezentáció mentése

Végül mentse a prezentációt a diagrammal a projektkönyvtárába.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen létrehozott egy fürtözött oszlopdiagramot egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Ezt a táblázatot igényei szerint tovább testreszabhatja.

## A Java Slides normál diagramjainak teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre könyvtárat, ha még nincs jelen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Példányosítási osztály, amely a PPTX fájlt képviseli
Presentation pres = new Presentation();
// Hozzáférés az első diához
ISlide sld = pres.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Beállítási diagram Cím
// Chart.getChartTitle().getTextFrameForOverriding().setText("Mintacím");
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
// Kitöltési szín beállítása sorozatokhoz
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);
// Most a sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Kitöltési szín beállítása sorozatokhoz
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Az első címke a kategórianév megjelenítése lesz
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// A harmadik címke értékének megjelenítése
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Prezentáció mentése diagrammal
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet normál diagramokat létrehozni a Java Slides programban az Aspose.Slides for Java API használatával. Végigmentünk egy lépésről lépésre, forráskóddal, hogy fürtözött oszlopdiagramot hozzunk létre egy PowerPoint-prezentációban.

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

 A diagram típusának módosításához módosítsa a`ChartType`paraméterrel a diagram hozzáadásakor`sld.getShapes().addChart()`. Az Aspose.Slides-ben elérhető különféle diagramtípusok közül választhat.

### Módosíthatom a diagramsorozat színeit?

 Igen, módosíthatja a diagramsorozat színeit az egyes sorozatok kitöltési színének beállításával`series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Hogyan adhatok hozzá további kategóriákat vagy sorozatokat a diagramhoz?

 További kategóriákat vagy sorozatokat adhat hozzá a diagramhoz új adatpontok és címkék hozzáadásával a`chart.getChartData().getCategories().add()` és`chart.getChartData().getSeries().add()` mód.

### Hogyan szabhatom tovább a diagram címét?

 A diagram címét tovább szabhatja a tulajdonságok módosításával`chart.getChartTitle()` például a szöveg igazítása, a betűméret és a szín.

### Hogyan menthetem el a diagramot másik fájlformátumba?

 A diagram másik fájlformátumba mentéséhez módosítsa a`SaveFormat` paraméter a`pres.save()` módszert a kívánt formátumra (pl. PDF, PNG, JPEG).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
