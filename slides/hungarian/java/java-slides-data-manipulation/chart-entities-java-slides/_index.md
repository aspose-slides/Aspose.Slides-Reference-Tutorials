---
title: Diagram entitások a Java Slides-ben
linktitle: Diagram entitások a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg a Java Slides diagramok létrehozását és testreszabását az Aspose.Slides segítségével. Javítsa prezentációit hatékony diagram entitásokkal.
weight: 13
url: /hu/java/data-manipulation/chart-entities-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Bevezetés a Java Slides diagram entitásaiba

diagramok hatékony eszközök az adatok megjelenítéséhez a prezentációkban. Akár üzleti jelentéseket, tudományos prezentációkat vagy bármilyen más tartalomformát készít, a diagramok segítenek az információk hatékony közvetítésében. Az Aspose.Slides for Java robusztus szolgáltatásokat nyújt a diagramokkal való munkavégzéshez, így a Java fejlesztők számára ideális választás.

## Előfeltételek

Mielőtt belemerülnénk a diagram entitások világába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Java Development Kit (JDK) telepítve
- Aspose.Slides for Java könyvtár letöltve és hozzáadva a projekthez
- Java programozási alapismeretek

Most kezdjük el a diagramok létrehozását és testreszabását az Aspose.Slides for Java használatával.

## 1. lépés: Prezentáció létrehozása

Az első lépés egy új prezentáció létrehozása, amelyhez hozzá kell adni a diagramot. Íme egy kódrészlet a prezentáció létrehozásához:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Diagram hozzáadása

Ha elkészült a prezentációval, ideje hozzáadni egy diagramot. Ebben a példában egy egyszerű vonaldiagramot adunk hozzá jelölőkkel. A következőképpen teheti meg:

```java
// Az első dia elérése
ISlide slide = pres.getSlides().get_Item(0);

// A minta diagram hozzáadása
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## 3. lépés: A diagram címének testreszabása

Egy jól definiált diagramnak legyen címe. Adjunk címet a diagramunknak:

```java
// A diagram címének beállítása
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## 4. lépés: Rácsvonalak formázása

Formázhatja a diagram fő- és mellékrácsvonalait. Állítsunk be néhány formázást a függőleges tengelyű rácsvonalakhoz:

```java
// A főbb rácsvonalak formátumának beállítása az értéktengelyhez
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Kisebb rácsvonalak formátumának beállítása az értéktengelyhez
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 5. lépés: Az értéktengely testreszabása

Ön szabályozhatja az értéktengely számformátumát, maximális és minimális értékeit. A következőképpen szabhatja testre:

```java
// Beállítási érték tengelyszám formátum
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Beállítási diagram maximum, minimum értékek
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
// Beállítási érték tengely címe
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## 7. lépés: A kategóriatengely formázása

A jellemzően adatkategóriákat képviselő kategóriatengely is testreszabható:

```java
// A főbb rácsvonalak formátumának beállítása a kategória tengelyhez
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Kisebb rácsvonalak formátumának beállítása a kategória tengelyhez
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## 8. lépés: Legendák hozzáadása

legendák segítenek elmagyarázni a diagram adatsorait. Tegyük testre a legendákat:

```java
// Jelmagyarázatok szövegtulajdonságainak beállítása
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Állítsa be a diagram jelmagyarázatait átfedő diagram nélkül
chart.getLegend().setOverlay(true);
```

## 9. lépés: A prezentáció mentése

Végül mentse el a prezentációt a diagrammal:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## A Java Slides diagram entitásainak teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre könyvtárat, ha még nincs jelen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Példányos prezentáció// Példányos prezentáció
Presentation pres = new Presentation();
try
{
	// Az első dia elérése
	ISlide slide = pres.getSlides().get_Item(0);
	// A minta diagram hozzáadása
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// A diagram címének beállítása
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// A főbb rácsvonalak formátumának beállítása az értéktengelyhez
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Kisebb rácsvonalak formátumának beállítása az értéktengelyhez
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Beállítási érték tengelyszám formátum
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Beállítási diagram maximum, minimum értékek
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
	// Beállítási érték tengely címe
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Beállítási érték tengely formátuma : Most Obselete
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// A főbb rácsvonalak formátumának beállítása a kategória tengelyhez
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Kisebb rácsvonalak formátumának beállítása a kategória tengelyhez
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Kategória tengely szövegtulajdonságainak beállítása
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Kategória címének beállítása
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Kategória tengelyének címkepozíciójának beállítása
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Kategória tengely címkével ellátott elforgatási szög beállítása
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Jelmagyarázatok szövegtulajdonságainak beállítása
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Állítsa be a diagram jelmagyarázatait átfedő diagram nélkül
	chart.getLegend().setOverlay(true);
	// Az első sorozat ábrázolása a másodlagos értéktengelyen
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = igaz;
	// Beállítási táblázat hátsó fal színe
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// telekterület színének beállítása
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

Ebben a cikkben a Java Slides diagram entitásainak világát fedeztük fel az Aspose.Slides for Java segítségével. Megtanulta, hogyan hozhat létre, testreszabhat és kezelhet diagramokat prezentációinak javítása érdekében. A diagramok nemcsak vizuálisan teszik vonzóvá adatait, hanem segítik a közönséget az összetett információk könnyebb megértésében.

## GYIK

### Hogyan változtathatom meg a diagram típusát?

 A diagram típusának módosításához használja a`chart.setType()` módszert, és adja meg a kívánt diagramtípust.

### Hozzáadhatok több adatsort egy diagramhoz?

 Igen, a diagram használatával több adatsort is hozzáadhat`chart.getChartData().getSeries().addSeries()` módszer.

### Hogyan szabhatom testre a diagram színeit?

A diagram színeit testreszabhatja a különböző diagramelemek, például rácsvonalak, cím és jelmagyarázatok kitöltési formátumának beállításával.

### Készíthetek 3D diagramokat?

 Igen, az Aspose.Slides for Java támogatja a 3D diagramok létrehozását. Beállíthatja a`ChartType` 3D diagramtípusra, hogy létrehozzon egyet.

### Az Aspose.Slides for Java kompatibilis a legújabb Java-verziókkal?

Igen, az Aspose.Slides for Java rendszeresen frissül, hogy támogassa a legújabb Java-verziókat, és kompatibilitást biztosít a Java-környezetek széles körében.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
