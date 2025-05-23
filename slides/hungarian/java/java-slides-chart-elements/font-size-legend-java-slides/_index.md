---
"description": "Turbózd fel a PowerPoint prezentációidat az Aspose.Slides Java verziójával. Tanuld meg, hogyan szabhatod testre a jelmagyarázatok betűméretét és sok mást lépésről lépésre szóló útmutatónkban."
"linktitle": "Betűméret-jelmagyarázat Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Betűméret-jelmagyarázat Java diákban"
"url": "/hu/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Betűméret-jelmagyarázat Java diákban


## Bevezetés a betűméret-jelmagyarázatba Java diákban

Ebben az oktatóanyagban megtanulod, hogyan szabhatod testre a PowerPoint-diák jelmagyarázatának betűméretét az Aspose.Slides for Java segítségével. Lépésről lépésre bemutatjuk a feladat elvégzéséhez szükséges utasításokat és forráskódot.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java projektedben. A könyvtárat letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: A prezentáció inicializálása

Először importálja a szükséges osztályokat, és inicializálja a PowerPoint-bemutatóját.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Csere `"Your Document Directory"` a PowerPoint-fájl tényleges elérési útjával.

## 2. lépés: Diagram hozzáadása

Ezután hozzáadunk egy diagramot a diához, és beállítjuk a jelmagyarázat betűméretét.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

Ebben a kódban egy csoportos oszlopdiagramot hozunk létre az első dián, és a jelmagyarázat szövegének betűméretét 20 pontra állítjuk. Módosíthatja a `setFontHeight` értékkel módosíthatja a betűméretet szükség szerint.

## 3. lépés: Tengelyértékek testreszabása

Most pedig szabjuk testre a diagram függőleges tengelyének értékeit.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Itt állítjuk be a függőleges tengely minimális és maximális értékeit. Az értékeket az adatigényeknek megfelelően módosíthatja.

## 4. lépés: Mentse el a prezentációt

Végül mentse el a módosított prezentációt egy új fájlba.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Ez a kód a módosított prezentációt „output.pptx” néven menti a megadott könyvtárba.

## Teljes forráskód a Java diák betűméret-jelmagyarázatához

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Sikeresen testre szabtad a Java PowerPoint dia jelmagyarázatának betűméretét az Aspose.Slides for Java segítségével. Tovább is felfedezheted az Aspose.Slides képességeit interaktív és vizuálisan vonzó prezentációk készítéséhez.

## GYIK

### Hogyan tudom megváltoztatni a jelmagyarázat szövegének betűméretét egy diagramban?

A diagram jelmagyarázatának betűméretének megváltoztatásához a következő kódot használhatja:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

Ebben a kódban létrehozunk egy diagramot, és a jelmagyarázat szövegének betűméretét 20 pontra állítjuk. Beállíthatod a `setFontHeight` érték a betűméret módosításához.

### Testreszabhatom a jelmagyarázat egyéb tulajdonságait egy diagramban?

Igen, az Aspose.Slides segítségével testreszabhatja a diagram jelmagyarázatának különböző tulajdonságait. Néhány gyakori tulajdonság, amelyet testreszabhat, például a szöveg formázása, pozíciója, láthatósága és egyebek. Például a jelmagyarázat pozíciójának módosításához használhatja a következőket:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Ez a kód beállítja, hogy a jelmagyarázat a diagram alján jelenjen meg. További testreszabási lehetőségekért tekintse meg az Aspose.Slides dokumentációját.

### Hogyan állíthatom be a diagram függőleges tengelyének minimum és maximum értékeit?

A diagram függőleges tengelyének minimális és maximális értékeinek beállításához a következő kódot használhatja:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Itt letiltjuk az automatikus tengelyméretezést, és megadjuk a függőleges tengely minimális és maximális értékeit. Szükség szerint módosítsa az értékeket a diagram adataihoz.

### Hol találok további információt és dokumentációt az Aspose.Slides-ről?

Az Aspose.Slides for Java átfogó dokumentációját és API-referenciáit az Aspose dokumentációs weboldalán találja. Látogassa meg a következőt: [itt](https://reference.aspose.com/slides/java/) részletes információkat a könyvtár használatáról.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}