---
title: Trendvonalak diagramja a Java diákban
linktitle: Trendvonalak diagramja a Java diákban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá különböző trendvonalakat a Java Slides-hez az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató kódpéldákkal az adatok hatékony megjelenítéséhez.
type: docs
weight: 15
url: /hu/java/data-manipulation/chart-trend-lines-java-slides/
---

## Bevezetés a diagram trendvonalaiba a Java Slides-ben: Útmutató lépésről lépésre

Ebben az átfogó útmutatóban megvizsgáljuk, hogyan hozhat létre diagram trendvonalakat a Java Slides programban az Aspose.Slides for Java segítségével. A diagram trendvonalai értékes kiegészítői lehetnek prezentációinak, segítve az adattrendek hatékony megjelenítését és elemzését. Világos magyarázatokkal és kódpéldákkal végigvezetjük a folyamaton.

## Előfeltételek

Mielőtt belevágnánk a diagram trendvonalainak létrehozásába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Java fejlesztői környezet
- Aspose.Slides for Java Library
- Az Ön által választott kódszerkesztő

## 1. lépés: Kezdő lépések

Kezdjük a szükséges környezet beállításával és egy új prezentáció létrehozásával:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre könyvtárat, ha még nincs jelen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Üres prezentáció létrehozása
Presentation pres = new Presentation();
```

Inicializáltuk a bemutatónkat, és készen állunk egy fürtözött oszlopdiagram hozzáadására:

```java
// Csoportosított oszlopdiagram létrehozása
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## 2. lépés: Exponenciális trendvonal hozzáadása

Kezdjük azzal, hogy adjunk hozzá egy exponenciális trendvonalat diagramsorozatunkhoz:

```java
// Exponenciális trendvonal hozzáadása az 1. diagramsorozathoz
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## 3. lépés: Lineáris trendvonal hozzáadása

Ezután egy lineáris trendvonalat adunk a diagramsorozatunkhoz:

```java
// Lineáris trendvonal hozzáadása az 1. diagramsorozathoz
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## 4. lépés: Logaritmikus trendvonal hozzáadása

Most adjunk hozzá egy logaritmikus trendvonalat egy másik diagramsorozathoz:

```java
// Logaritmikus trendvonal hozzáadása a 2. diagramsorozathoz
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## 5. lépés: Mozgóátlag trendvonal hozzáadása

Hozzáadhatunk egy mozgóátlagos trendvonalat is:

```java
// Mozgóátlag trendvonal hozzáadása a 2. diagramsorozathoz
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## 6. lépés: Polinom trendvonal hozzáadása

Polinomiális trendvonal hozzáadása:

```java
// Polinomiális trendvonal hozzáadása a 3. diagramsorozathoz
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## 7. lépés: A Power Trend Line hozzáadása

Végül adjunk hozzá egy erőtrend-vonalat:

```java
// Hatékonysági trendvonal hozzáadása a 3. diagramsorozathoz
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## 8. lépés: A prezentáció mentése

Most, hogy különféle trendvonalakat adtunk hozzá diagramunkhoz, mentsük el a bemutatót:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Gratulálunk! Sikeresen létrehozott egy prezentációt különböző típusú trendvonalakkal a Java Slides programban az Aspose.Slides for Java segítségével.

## A Java Slides diagramok trendvonalainak teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre könyvtárat, ha még nincs jelen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Üres prezentáció létrehozása
Presentation pres = new Presentation();
// Csoportosított oszlopdiagram létrehozása
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Potencionális trendvonal hozzáadása az 1. diagramsorozathoz
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Lineáris trendvonal hozzáadása az 1. diagramsorozathoz
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Logaritmikus trendvonal hozzáadása a 2. diagramsorozathoz
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// MovingAverage trendvonal hozzáadása a 2. diagramsorozathoz
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Polinom trendvonal hozzáadása a 3. diagramsorozathoz
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Power trendvonal hozzáadása a 3. diagramsorozathoz
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Prezentáció mentése
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan adhatunk hozzá különböző típusú trendvonalakat a Java Slides diagramjaihoz az Aspose.Slides for Java könyvtár használatával. Akár adatelemzésen dolgozik, akár informatív prezentációkat készít, a trendek megjelenítésének képessége hatékony eszköz lehet.

## GYIK

### Hogyan változtathatom meg egy trendvonal színét az Aspose.Slides for Java programban?

 trendvonal színének megváltoztatásához használhatja a`getSolidFillColor().setColor(Color)` módszert, amint az a példában látható egy lineáris trendvonal hozzáadására.

### Hozzáadhatok több trendvonalat egyetlen diagramsorozathoz?

 Igen, több trendvonalat is hozzáadhat egyetlen diagramsorozathoz. Egyszerűen hívja a`getTrendLines().add()` módszert minden egyes hozzáadni kívánt trendvonalhoz.

### Hogyan távolíthatok el trendvonalat az Aspose.Slides for Java diagramjából?

 Ha el szeretne távolítani egy trendvonalat a diagramról, használhatja a`removeAt(int index)` módszerrel, megadva az eltávolítani kívánt trendvonal indexét.

### Testreszabható a trendvonal egyenlet megjelenítése?

 Igen, testreszabhatja a trendvonal-egyenlet megjelenítését a`setDisplayEquation(boolean)` módszerrel, ahogy a példában is látható.

### Hogyan férhetek hozzá további erőforrásokhoz és példákhoz az Aspose.Slides for Java számára?

 Az Aspose.Slides for Java további forrásaihoz, dokumentációihoz és példáihoz férhet hozzá a webhelyen[Aspose honlapja](https://reference.aspose.com/slides/java/).