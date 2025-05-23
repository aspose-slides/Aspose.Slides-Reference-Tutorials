---
"description": "Tanuld meg, hogyan adhatsz hozzá hibasávokat PowerPoint-diagramokhoz Java-ban az Aspose.Slides segítségével. Lépésről lépésre útmutató forráskóddal a hibasávok testreszabásához."
"linktitle": "Hibasávok hozzáadása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Hibasávok hozzáadása Java diákban"
"url": "/hu/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Hibasávok hozzáadása Java diákban


## Bevezetés a hibasávok hozzáadásához Java diákban az Aspose.Slides használatával

Ebben az oktatóanyagban bemutatjuk, hogyan adhatunk hozzá hibasávokat egy PowerPoint dián lévő diagramhoz az Aspose.Slides for Java segítségével. A hibasávok értékes információkat nyújtanak a diagram adatpontjainak változékonyságáról vagy bizonytalanságáról. Létrehozunk egy buborékdiagramot, és hibasávokat adunk hozzá. Kezdjük is!

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java projektedben. A könyvtárat letöltheted innen: [Aspose weboldal](https://downloads.aspose.com/slides/java).

## 1. lépés: Hozz létre egy üres prezentációt

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
```

Ebben a lépésben létrehozunk egy üres prezentációt, ahová hozzáadjuk a hibasávokkal ellátott diagramunkat.

## 2. lépés: Buborékdiagram létrehozása

```java
// Buborékdiagram létrehozása
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Itt létrehozunk egy buborékdiagramot, és megadjuk annak helyét és méreteit a dián.

## 3. lépés: Hibasávok hozzáadása és a formátum beállítása

```java
// Hibasávok hozzáadása és formátumuk beállítása
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

Ebben a lépésben hibasávokat adunk a diagramhoz, és beállítjuk a formátumukat. A hibasávokat testreszabhatja az értékek, típusok és egyéb tulajdonságok módosításával.

- `errBarX` az X tengely mentén található hibasávokat jelöli.
- `errBarY` az Y tengely mentén található hibasávokat jelöli.
- Láthatóvá tesszük mind az X, mind az Y hibasávokat.
- `setValueType` meghatározza a hibasávok értéktípusát (pl. Fix vagy Százalék).
- `setValue` beállítja a hibasávok értékét.
- `setType` meghatározza a hibasávok típusát (pl. Plusz vagy Mínusz).
- A hibasáv vonalak szélességét a következővel állítottuk be: `getFormat().getLine().setWidth(2)`.
- `setEndCap` meghatározza, hogy szerepeljenek-e végzárók a hibasávokon.

## 4. lépés: Mentse el a prezentációt

```java
// Prezentáció mentése
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Végül a hozzáadott hibasávokkal ellátott prezentációt egy megadott helyre mentjük.

Ez minden! Sikeresen hozzáadtad a hibasávokat egy PowerPoint dián lévő diagramhoz az Aspose.Slides for Java használatával.

## Teljes forráskód a hibasávok hozzáadásához Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
try
{
	// Buborékdiagram létrehozása
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Hibasávok hozzáadása és formátumuk beállítása
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

Ebben az oktatóanyagban azt vizsgáltuk meg, hogyan javíthatjuk PowerPoint-bemutatóinkat hibasávok hozzáadásával a diagramokhoz az Aspose.Slides for Java segítségével. A hibasávok értékes betekintést nyújtanak az adatok változékonyságába és bizonytalanságaiba, így a bemutatók informatívabbak és vizuálisan vonzóbbak.

## GYIK

### Hogyan tudom tovább testreszabni a hibasávok megjelenését?

A hibasávokat testreszabhatja a tulajdonságaik, például a vonalstílus, a szín és a szélesség módosításával, ahogy azt a 3. lépésben bemutattuk.

### Hozzáadhatok hibasávokat különböző diagramtípusokhoz?

Igen, hibasávokat adhatsz hozzá az Aspose.Slides for Java által támogatott különféle diagramtípusokhoz. Egyszerűen hozd létre a kívánt diagramtípust, és kövesd a hibasáv testreszabási lépéseit.

### Hogyan tudom beállítani a diagram pozícióját és méretét a dián?

A diagram pozícióját és méreteit a paraméterek módosításával szabályozhatja. `addChart` módszer, ahogy a 2. lépésben látható.

### Hol találok további információt az Aspose.Slides for Java-ról?

Hivatkozhat a [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/) részletes információkat a könyvtár használatáról.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}