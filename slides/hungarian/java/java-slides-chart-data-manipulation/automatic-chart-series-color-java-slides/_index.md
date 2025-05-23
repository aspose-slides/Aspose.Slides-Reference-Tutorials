---
"description": "Tanuld meg, hogyan hozhatsz létre dinamikus diagramokat automatikus sorozatszínekkel PowerPoint-bemutatókban az Aspose.Slides for Java segítségével. Fejleszd adatvizualizációidat könnyedén."
"linktitle": "Automatikus diagramsorozat színezése Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Automatikus diagramsorozat színezése Java diákban"
"url": "/hu/java/chart-data-manipulation/automatic-chart-series-color-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Automatikus diagramsorozat színezése Java diákban


## Bevezetés az automatikus diagramsorozat-színezésbe az Aspose.Slides Java-ban

Ebben az oktatóanyagban megvizsgáljuk, hogyan hozhat létre diagrammal ellátott PowerPoint-bemutatót az Aspose.Slides Java-verziójával, és hogyan állíthat be automatikus kitöltési színeket a diagramsorozatokhoz. Az automatikus kitöltési színek vizuálisan vonzóbbá tehetik a diagramokat, és időt takaríthatnak meg azáltal, hogy a könyvtárra bízzák a színek kiválasztását.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve van a projektedben. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Új prezentáció létrehozása

Először is létrehozunk egy új PowerPoint bemutatót, és hozzáadunk egy diát.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
```

## 2. lépés: Diagram hozzáadása a diához

Ezután egy csoportos oszlopdiagramot adunk hozzá a diához. Az első sorozatot úgy is beállítjuk, hogy értékeket jelenítsen meg.

```java
// Első dia elérése
ISlide slide = presentation.getSlides().get_Item(0);
// Diagram hozzáadása alapértelmezett adatokkal
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
// Az első sorozat beállítása az Értékek megjelenítése lehetőségre
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

## 3. lépés: Diagramadatok feltöltése

Most feltöltjük a diagramot adatokkal. Először töröljük az alapértelmezett generált sorozatokat és kategóriákat, majd új sorozatokat és kategóriákat adunk hozzá.

```java
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

## 4. lépés: Sorozatadatok feltöltése

Mind az 1., mind a 2. sorozat adatsorait feltöltjük.

```java
// Vegye az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
// Most feltöltjük a sorozat adatait
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Vegyük a második diagramsorozatot
series = chart.getChartData().getSeries().get_Item(1);
// Most feltöltjük a sorozat adatait
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
```

## 5. lépés: Automatikus kitöltési szín beállítása sorozatokhoz

Most állítsunk be automatikus kitöltési színeket a diagramsorozathoz. Ezáltal a könyvtár fogja kiválasztani helyettünk a színeket.

```java
// Automatikus kitöltési szín beállítása sorozatokhoz
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

## 6. lépés: Mentse el a prezentációt

Végül a diagramot tartalmazó bemutatót egy PowerPoint-fájlba mentjük.

```java
// Prezentáció mentése diagrammal
presentation.save(dataDir + "AutomaticColor_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód az automatikus diagramsorozat-színezéshez Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
try
{
	// Első dia elérése
	ISlide slide = presentation.getSlides().get_Item(0);
	// Diagram hozzáadása alapértelmezett adatokkal
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 0, 0, 500, 500);
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
	// Automatikus kitöltési szín beállítása sorozatokhoz
	series.getFormat().getFill().setFillType(FillType.NotDefined);
	// Vegyük a második diagramsorozatot
	series = chart.getChartData().getSeries().get_Item(1);
	// Most feltöltjük a sorozat adatait
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
	series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
	// Sorozat kitöltési színének beállítása
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

Ebben az oktatóanyagban megtanultuk, hogyan hozhatunk létre PowerPoint prezentációt diagramokkal az Aspose.Slides Java segítségével, és hogyan állíthatunk be automatikus kitöltési színeket a diagramsorozatokhoz. Az automatikus színek javíthatják a diagramok vizuális megjelenését, és lebilincselőbbé tehetik a prezentációkat. A diagramot szükség szerint testreszabhatja az Ön egyedi igényeinek megfelelően.

## GYIK

### Hogyan állíthatok be automatikus kitöltési színeket a diagramsorozatokhoz az Aspose.Slides for Java programban?

Az Aspose.Slides Java verziójában a diagramsorozatok automatikus kitöltési színeinek beállításához használja a következő kódot:

```java
// Automatikus kitöltési szín beállítása sorozatokhoz
series.getFormat().getFill().setFillType(FillType.NotDefined);
```

Ez a kód lehetővé teszi a könyvtár számára, hogy automatikusan válassza ki a színeket a diagramsorozathoz.

### Testreszabhatom a diagram színeit, ha szükséges?

Igen, a diagram színeit szükség szerint testreszabhatja. A bemutatott példában automatikus kitöltési színeket használtunk, de a színek módosításával beállíthat konkrét színeket. `FillType` és `SolidFillColor` A sorozat formátumának tulajdonságai.

### Hogyan adhatok hozzá további sorozatokat vagy kategóriákat a diagramhoz?

További sorozatok vagy kategóriák hozzáadásához a diagramhoz használja a `getSeries()` és `getCategories()` a diagram metódusai `ChartData` objektum. Új sorozatokat és kategóriákat adhat hozzá az adataik és címkéik megadásával.

### Lehetséges a diagram és a címkék további formázása?

Igen, a diagramot, sorozatokat és címkéket szükség szerint tovább formázhatja. Az Aspose.Slides for Java kiterjedt formázási lehetőségeket kínál a diagramokhoz, beleértve a betűtípusokat, színeket, stílusokat és egyebeket. A formázási lehetőségekkel kapcsolatos további részletekért tekintse meg a dokumentációt.

### Hol találok további információt az Aspose.Slides Java-ban való használatáról?

További információkért és részletes dokumentációért az Aspose.Slides for Java-ról, látogassa meg a referencia dokumentációt. [itt](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}