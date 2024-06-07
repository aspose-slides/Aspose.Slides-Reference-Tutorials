---
title: Hibasávok hozzáadása a Java Slides-hez
linktitle: Hibasávok hozzáadása a Java Slides-hez
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá hibasávokat a PowerPoint diagramokhoz Java nyelven az Aspose.Slides segítségével. Lépésről lépésre útmutató forráskóddal a hibasávok testreszabásához.
type: docs
weight: 13
url: /hu/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Bevezetés a hibasávok hozzáadásához Java Slides-ben az Aspose.Slides használatával

Ebben az oktatóanyagban bemutatjuk, hogyan lehet hibasávokat hozzáadni egy PowerPoint dián lévő diagramhoz az Aspose.Slides for Java segítségével. A hibasávok értékes információkkal szolgálnak a diagram adatpontjainak változékonyságáról vagy bizonytalanságáról. Létrehozunk egy buborékdiagramot, és hibasávokat adunk hozzá. Kezdjük el!

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben. A könyvtár letölthető a[Aspose honlapja](https://downloads.aspose.com/slides/java).

## 1. lépés: Hozzon létre egy üres prezentációt

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
```

Ebben a lépésben létrehozunk egy üres prezentációt, ahol hozzáadjuk a diagramunkat hibasávokkal.

## 2. lépés: Hozzon létre egy buborékdiagramot

```java
// Buborékdiagram készítése
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Itt létrehozunk egy buborékdiagramot, és megadjuk a helyzetét és méreteit a dián.

## 3. lépés: Hibasávok hozzáadása és formátum beállítása

```java
// Hibasávok hozzáadása és formátumának beállítása
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

Ebben a lépésben hibasávokat adunk a diagramhoz, és beállítjuk a formátumukat. A hibasávokat értékek, típusok és egyéb tulajdonságok módosításával testreszabhatja.

- `errBarX` hibasávokat jelöl az X tengely mentén.
- `errBarY` hibasávokat jelöl az Y tengely mentén.
- Mind az X, mind az Y hibasávot láthatóvá tesszük.
- `setValueType` megadja a hibasávok értéktípusát (pl. Fix vagy Percentage).
- `setValue` beállítja a hibasávok értékét.
- `setType` meghatározza a hibasávok típusát (pl. plusz vagy mínusz).
-  A hibasáv vonalainak szélességét a segítségével állítjuk be`getFormat().getLine().setWidth(2)`.
- `setEndCap` megadja, hogy szerepeljenek-e zárófejek a hibasávokon.

## 4. lépés: Mentse el a bemutatót

```java
// Prezentáció mentése
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Végül elmentjük a prezentációt a hozzáadott hibasávokkal egy megadott helyre.

Ez az! Sikeresen hozzáadott hibasávokat egy PowerPoint-dián lévő diagramhoz az Aspose.Slides for Java segítségével.

## Teljes forráskód a Java Slides hibasávok hozzáadásához

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
try
{
	// Buborékdiagram készítése
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Hibasávok hozzáadása és formátumának beállítása
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Prezentáció mentése
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan javíthatja PowerPoint-prezentációit az Aspose.Slides for Java segítségével hibasávok hozzáadásával a diagramokhoz. A hibasávok értékes betekintést nyújtanak az adatok változékonyságába és bizonytalanságába, így a prezentációk informatívabbak és látványosabbak.

## GYIK

### Hogyan szabhatom tovább a hibasávok megjelenését?

Testreszabhatja a hibasávokat tulajdonságaik, például vonalstílus, szín és szélesség módosításával, a 3. lépésben bemutatott módon.

### Hozzáadhatok hibasávokat a különböző diagramtípusokhoz?

Igen, az Aspose.Slides for Java által támogatott különféle diagramtípusokhoz hozzáadhat hibasávokat. Egyszerűen hozza létre a kívánt diagramtípust, és kövesse ugyanazokat a hibasáv testreszabási lépéseket.

### Hogyan állíthatom be a diagram helyzetét és méretét a dián?

 diagram helyzetét és méreteit a paraméterek beállításával szabályozhatja`addChart` módszert a 2. lépésben látható módon.

### Hol találhatok további információt az Aspose.Slides for Java programról?

 Hivatkozhat a[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/) a könyvtár használatával kapcsolatos részletes információkért.