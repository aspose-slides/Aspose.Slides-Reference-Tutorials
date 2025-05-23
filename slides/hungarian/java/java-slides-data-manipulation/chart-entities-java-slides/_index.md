---
"description": "Tanuld meg, hogyan hozhatsz létre és szabhatsz testre Java Slides diagramokat az Aspose.Slides segítségével. Dobd fel prezentációidat hatékony diagram entitásokkal."
"linktitle": "Diagram entitások Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Diagram entitások Java diákban"
"url": "/hu/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagram entitások Java diákban


## Bevezetés a Java diák diagramentitásaiba

diagramok hatékony eszközök az adatok vizualizálására a prezentációkban. Akár üzleti jelentéseket, tudományos prezentációkat vagy bármilyen más tartalmat készít, a diagramok segítenek hatékonyan közvetíteni az információkat. Az Aspose.Slides for Java robusztus funkciókat kínál a diagramokkal való munkához, így a Java-fejlesztők számára ideális választás.

## Előfeltételek

Mielőtt belemerülnénk a diagram entitások világába, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

- Telepített Java fejlesztőkészlet (JDK)
- Az Aspose.Slides for Java könyvtár letöltődött és hozzáadódott a projektedhez.
- Alapvető Java programozási ismeretek

Most pedig kezdjük el a diagramok létrehozását és testreszabását az Aspose.Slides for Java használatával.

## 1. lépés: Prezentáció létrehozása

Az első lépés egy új prezentáció létrehozása, ahová felveszed a diagramodat. Íme egy kódrészlet a prezentáció létrehozásához:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Diagram hozzáadása

Miután elkészült a prezentációd, itt az ideje hozzáadni egy diagramot. Ebben a példában egy egyszerű vonaldiagramot fogunk hozzáadni jelölőkkel. Így teheted meg:

```java
// Az első dia elérése
ISlide slide = pres.getSlides().get_Item(0);

// Mintadiagram hozzáadása
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 3. lépés: Diagram címének testreszabása

Egy jól definiált diagramnak kell lennie címmel. Adjunk meg egy címet a diagramunknak:

```java
// Beállítási táblázat címe
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## 4. lépés: Rácsvonalak formázása

Formázhatod a diagramod fő és mellék rácsvonalait. Állítsunk be néhány formázást a függőleges tengely rácsvonalaihoz:

```java
// Értéktengely fő rácsvonalainak formátumának beállítása
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Értéktengely mellékrács-vonalainak formátumának beállítása
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 5. lépés: Az értéktengely testreszabása

Az értéktengely számformátumát, maximális és minimális értékeit Ön szabályozza. Így szabhatja testre:

```java
// Értéktengely számformátumának beállítása
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Beállítási táblázat maximum és minimum értékek
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## 6. lépés: Értéktengely címének hozzáadása

A diagram informatívabbá tételéhez címet adhat az értéktengelyhez:

```java
// Értéktengely címének beállítása
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## 7. lépés: Kategóriatengely formázása

A kategóriatengely, amely jellemzően az adatkategóriákat ábrázolja, testreszabható is:

```java
// Fő rácsvonalak formátumának beállítása a kategóriatengelyhez
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Kategóriatengely mellékrács-vonalainak formátumának beállítása
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 8. lépés: Jelmagyarázatok hozzáadása

A jelmagyarázatok segítenek elmagyarázni a diagram adatsorait. Testreszabhatjuk a jelmagyarázatokat:

```java
// Jelmagyarázatok szövegtulajdonságainak beállítása
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Diagramjelmagyarázatok megjelenítésének beállítása átfedés nélküli diagramok esetén
chart.getLegend().setOverlay(true);
```

## 9. lépés: A prezentáció mentése

Végül mentsd el a prezentációdat a diagrammal együtt:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Teljes forráskód diagram entitásokhoz Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy könyvtárat, ha az még nem létezik.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Prezentáció példányosítása// Prezentáció példányosítása
Presentation pres = new Presentation();
try
{
	// Az első dia elérése
	ISlide slide = pres.getSlides().get_Item(0);
	// Mintadiagram hozzáadása
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Beállítási táblázat címe
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Értéktengely fő rácsvonalainak formátumának beállítása
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Értéktengely mellékrács-vonalainak formátumának beállítása
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Értéktengely számformátumának beállítása
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Beállítási táblázat maximum és minimum értékek
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Értéktengely szövegtulajdonságainak beállítása
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Értéktengely címének beállítása
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Értéktengely vonalformátumának beállítása: Mostantól elavult
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Fő rácsvonalak formátumának beállítása a kategóriatengelyhez
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Kategóriatengely mellékrács-vonalainak formátumának beállítása
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Kategóriatengely szövegtulajdonságainak beállítása
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Beállítás kategória címe
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Kategóriatengely feliratának pozíciójának beállítása
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Kategóriatengely-címke elforgatási szögének beállítása
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Jelmagyarázatok szövegtulajdonságainak beállítása
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Diagramjelmagyarázatok megjelenítésének beállítása átfedés nélküli diagramok esetén
	chart.getLegend().setOverlay(true);
	// Első sorozat ábrázolása a másodlagos értéktengelyen
	// Chart.getChartData().getSeries().get_Item(0).PlotOnMásodikTengely = igaz;
	// Beállítási táblázat hátfal színe
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// nyomtatási terület színének beállítása
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Prezentáció mentése
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben a cikkben az Aspose.Slides for Java segítségével fedeztük fel a Java diákban használható diagram entitások világát. Megtanultad, hogyan hozhatsz létre, szabhatsz testre és manipulálhatsz diagramokat a prezentációid fejlesztése érdekében. A diagramok nemcsak vizuálisan vonzóbbá teszik az adataidat, hanem segítenek a közönségednek is könnyebben megérteni az összetett információkat.

## GYIK

### Hogyan tudom megváltoztatni a diagram típusát?

A diagram típusának módosításához használja a `chart.setType()` metódust, és adja meg a kívánt diagramtípust.

### Több adatsort is hozzáadhatok egy diagramhoz?

Igen, több adatsort is hozzáadhat egy diagramhoz a `chart.getChartData().getSeries().addSeries()` módszer.

### Hogyan szabhatom testre a diagram színeit?

A diagram színeit testreszabhatja a különböző diagramelemek, például a rácsvonalak, a cím és a jelmagyarázatok kitöltési formátumának beállításával.

### Létrehozhatok 3D-s diagramokat?

Igen, az Aspose.Slides Java-ban támogatja a 3D-s diagramok létrehozását. Beállíthatja a `ChartType` egy 3D-s diagramtípushoz egy létrehozásához.

### Kompatibilis az Aspose.Slides for Java a legújabb Java verziókkal?

Igen, az Aspose.Slides for Java rendszeresen frissül, hogy támogassa a legújabb Java verziókat, és kompatibilitást biztosít a Java környezetek széles skáláján.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}