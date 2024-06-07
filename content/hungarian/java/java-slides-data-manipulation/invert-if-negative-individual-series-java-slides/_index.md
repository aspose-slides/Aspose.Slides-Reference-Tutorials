---
title: Invert, ha negatív a Java Slides egyes sorozatainál
linktitle: Invert, ha negatív a Java Slides egyes sorozatainál
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan használhatja az Aspose.Slides for Java programban az Invert If Negative funkciót a diagramok megjelenítésének javítására a PowerPoint-prezentációkban.
type: docs
weight: 11
url: /hu/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

## Bevezetés az Invert If Negative használatához a Java Slides egyes sorozataihoz

Az Aspose.Slides for Java hatékony eszközöket biztosít a prezentációkhoz, és az egyik érdekes funkció az adatsorok diagramokon való megjelenítésének szabályozása. Ebben a cikkben megvizsgáljuk, hogyan használhatjuk a „Negatív megfordítása, ha negatív” funkciót a Java Slides egyes sorozataihoz. Ez a funkció lehetővé teszi a negatív adatpontok vizuális megkülönböztetését a diagramon, így a prezentáció informatívabb és vonzóbb.

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Java Development Kit (JDK) telepítve a rendszerére.
-  Aspose.Slides for Java könyvtár. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## A projekt beállítása

A kezdéshez hozzon létre egy új Java-projektet a kívánt integrált fejlesztési környezetben (IDE). A projekt beállítása után kövesse az alábbi lépéseket az „Invert If Negative” funkció megvalósításához a Java Slides egyes sorozataihoz.

## 1. lépés: Vegye fel az Aspose.Slides könyvtárat

Először is bele kell foglalnia az Aspose.Slides könyvtárat a projektbe. Ezt úgy teheti meg, hogy hozzáadja a könyvtár JAR fájlját a projekt osztályútvonalához. Ez a lépés biztosítja, hogy elérje az összes szükséges osztályt és módszert a PowerPoint-prezentációk használatához.

```java
import com.aspose.slides.*;
```

## 2. lépés: Hozzon létre egy prezentációt

 Most hozzunk létre egy új PowerPoint-prezentációt az Aspose.Slides segítségével. A segítségével megadhatja azt a könyvtárat, ahová a bemutatót menteni szeretné`dataDir` változó.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 3. lépés: Adjon hozzá egy diagramot

Ebben a lépésben diagramot adunk a bemutatóhoz. Példaként egy fürtözött oszlopdiagramot fogunk használni. Igényei alapján különböző diagramtípusokat választhat.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## 4. lépés: Konfigurálja a diagram adatsort

Ezután konfiguráljuk a diagram adatsorait. A „Negatív megfordítása” funkció bemutatásához létrehozunk egy mintaadatkészletet pozitív és negatív értékekkel.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// Adatpontok hozzáadása a sorozathoz
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## 5. lépés: Alkalmazza a „Fordítsa meg, ha negatív”

Most alkalmazzuk az „Invert If Negative” funkciót az egyik adatpontra. Ez vizuálisan megfordítja az adott adatpont színét, ha az negatív.

```java
series.get_Item(0).setInvertIfNegative(false); // Alapértelmezés szerint ne fordítsa meg
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Fordítsa meg a harmadik adatpont színét
```

## 6. lépés: Mentse el a bemutatót

Végül mentse a prezentációt a megadott könyvtárba.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## A Java Slides egyes sorozatainak megfordításának teljes forráskódja, ha negatív

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan kell használni a „Negatívum megfordítása” funkciót a Java Slides egyes sorozataihoz az Aspose.Slides for Java használatával. Ez a funkció lehetővé teszi a negatív adatpontok kiemelését a diagramokon, így a prezentációk látványosabbak és informatívabbak.

## GYIK

### Mi a célja az Aspose.Slides for Java "Invert If Negative" funkciójának?

Az Aspose.Slides for Java "Invert If Negative" funkciója lehetővé teszi a negatív adatpontok vizuális megkülönböztetését a diagramokon. A konkrét adatpontok kiemelésével elősegíti, hogy prezentációi informatívabbak és vonzóbbak legyenek.

### Hogyan vehetem fel az Aspose.Slides könyvtárat a Java projektembe?

Az Aspose.Slides könyvtár Java-projektbe való felvételéhez hozzá kell adnia a könyvtár JAR fájlját a projekt osztályútvonalához. Ez lehetővé teszi a PowerPoint-prezentációk használatához szükséges összes osztályhoz és módszerhez való hozzáférést.

### Használhatok különböző diagramtípusokat a „Negatív megfordítása” funkcióval?

Igen, különböző diagramtípusokat használhat a „Negatív megfordítása” funkcióval. Ebben az oktatóanyagban egy fürtözött oszlopdiagramot használtunk példaként, de a funkciót különféle diagramtípusokra alkalmazhatja az igényeinek megfelelően.

### Testreszabható az invertált adatpontok megjelenése?

Igen, testreszabhatja az invertált adatpontok megjelenését. Az Aspose.Slides for Java opciókat biztosít az adatpontok színének és stílusának szabályozására, amikor azokat az "Invert If Negative" beállítás miatt megfordítják.

### Hol érhetem el az Aspose.Slides for Java dokumentációját?

 Az Aspose.Slides for Java dokumentációját a következő címen érheti el[itt](https://reference.aspose.com/slides/java/).