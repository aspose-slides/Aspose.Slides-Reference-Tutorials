---
"description": "Normál diagramok létrehozása Java diákban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató és forráskód diagramok létrehozásához, testreszabásához és mentéséhez PowerPoint prezentációkban."
"linktitle": "Normál diagramok Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Normál diagramok Java diákban"
"url": "/hu/java/chart-data-manipulation/normal-charts-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Normál diagramok Java diákban


## Bevezetés a Java normál diagramjaiba - Diák

Ebben az oktatóanyagban végigvezetjük a normál diagramok létrehozásának folyamatán Java Slides-ban az Aspose.Slides for Java API használatával. Lépésről lépésre bemutatjuk, hogyan hozhat létre fürtözött oszlopdiagramot egy PowerPoint-bemutatóban.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. Aspose.Slides Java API-hoz telepítve.
2. Java fejlesztői környezet beállítása.
3. Java programozási alapismeretek.

## 1. lépés: A projekt beállítása

Győződj meg róla, hogy van egy könyvtárad a projektedhez. Nevezzük ezt "A dokumentumkönyvtáradnak", ahogy a kódban is szerepel. Ezt lecserélheted a projektkönyvtár tényleges elérési útjára.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy könyvtárat, ha az még nem létezik.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```

## 2. lépés: Prezentáció létrehozása

Most hozzunk létre egy PowerPoint bemutatót, és lépjünk be az első diájába.

```java
// PPTX fájlt reprezentáló megjelenítési osztály példányosítása
Presentation pres = new Presentation();
// Első dia elérése
ISlide sld = pres.getSlides().get_Item(0);
```

## 3. lépés: Diagram hozzáadása

Hozzáadunk egy csoportos oszlopdiagramot a diához, és beállítjuk a címét.

```java
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Beállítási táblázat címe
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

## 4. lépés: Diagramadatok beállítása

Ezután beállítjuk a diagram adatait sorozatok és kategóriák definiálásával.

```java
// Az első sorozat beállítása az Értékek megjelenítése lehetőségre
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);

// Diagram adatlap indexének beállítása
int defaultWorksheetIndex = 0;

// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

// Alapértelmezetten generált sorozatok és kategóriák törlése
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();

// Új sorozatok hozzáadása
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
// Vegye az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Sorozat kitöltési színének beállítása
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);

// Sorozatadatok feltöltése
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));

// Sorozat kitöltési színének beállítása
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
```

## 6. lépés: Címkék testreszabása

Testreszabhatjuk a diagramsorozat adatcímkéit.

```java
// Az első címke a kategória nevét fogja mutatni.
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

Végül mentsd el a diagramot tartalmazó prezentációt a projektkönyvtáradba.

```java
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```

Ennyi! Sikeresen létrehoztál egy csoportos oszlopdiagramot egy PowerPoint bemutatóban az Aspose.Slides for Java használatával. A diagramot a saját igényeid szerint tovább testreszabhatod.

## Teljes forráskód normál diagramokhoz Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy könyvtárat, ha az még nem létezik.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// PPTX fájlt reprezentáló megjelenítési osztály példányosítása
Presentation pres = new Presentation();
// Első dia elérése
ISlide sld = pres.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = sld.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Beállítási táblázat címe
// Chart.getChartTitle().getTextFrameForOverriding().setText("Minta cím");
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
int s = chart.getChartData().getSeries().size();
s = chart.getChartData().getCategories().size();
// Új sorozatok hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());
// Új kategóriák hozzáadása
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Caetegoty 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Caetegoty 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Caetegoty 3"));
// Vegye az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Most feltöltjük a sorozat adatait
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
// Sorozat kitöltési színének beállítása
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.RED);
// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);
// Most feltöltjük a sorozat adatait
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
// Sorozat kitöltési színének beállítása
series.getFormat().getFill().setFillType(FillType.Solid);
series.getFormat().getFill().getSolidFillColor().setColor(Color.GREEN);
// Az első címke a kategória nevét fogja mutatni.
IDataLabel lbl = series.getDataPoints().get_Item(0).getLabel();
lbl.getDataLabelFormat().setShowCategoryName(true);
lbl = series.getDataPoints().get_Item(1).getLabel();
lbl.getDataLabelFormat().setShowSeriesName(true);
// Harmadik címke értékének megjelenítése
lbl = series.getDataPoints().get_Item(2).getLabel();
lbl.getDataLabelFormat().setShowValue(true);
lbl.getDataLabelFormat().setShowSeriesName(true);
lbl.getDataLabelFormat().setSeparator("/");
// Prezentáció mentése diagrammal
pres.save(dataDir + "AsposeChart_out.pptx", SaveFormat.Pptx);
```
# Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan hozhatunk létre normál diagramokat Java Slides-ban az Aspose.Slides for Java API használatával. Lépésről lépésre bemutattuk, hogyan hozhatunk létre fürtözött oszlopdiagramot egy PowerPoint-bemutatóban forráskóddal.

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

A diagram típusának módosításához módosítsa a `ChartType` paraméter a diagram hozzáadásakor a következő használatával: `sld.getShapes().addChart()`Az Aspose.Slides-ban elérhető különféle diagramtípusok közül választhat.

### Meg tudom változtatni a diagramsorozat színeit?

Igen, a diagramsorozatok színeit módosíthatja az egyes sorozatok kitöltési színének beállításával a következő segítségével: `series.getFormat().getFill().getSolidFillColor().setColor(Color.YOUR_COLOR)`.

### Hogyan adhatok hozzá további kategóriákat vagy sorozatokat a diagramhoz?

További kategóriákat vagy sorozatokat adhatsz a diagramhoz új adatpontok és címkék hozzáadásával a `chart.getChartData().getCategories().add()` és `chart.getChartData().getSeries().add()` mód.

### Hogyan tudom tovább testreszabni a diagram címét?

A diagram címét tovább testreszabhatja a tulajdonságok módosításával. `chart.getChartTitle()` például a szöveg igazítása, betűméret és szín.

### Hogyan menthetem el a diagramot egy másik fájlformátumban?

A diagram más fájlformátumba mentéséhez módosítsa a `SaveFormat` paraméter a `pres.save()` módszert a kívánt formátumra (pl. PDF, PNG, JPEG).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}