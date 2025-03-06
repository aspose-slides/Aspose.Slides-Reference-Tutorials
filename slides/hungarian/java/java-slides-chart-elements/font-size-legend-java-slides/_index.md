---
title: Betűméret-magyarázat a Java Slides-ben
linktitle: Betűméret-magyarázat a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Javítsa a PowerPoint prezentációkat az Aspose.Slides for Java segítségével. Lépésről lépésre szóló útmutatónkból megtudhatja, hogyan szabhatja személyre a jelmagyarázat betűméretét és még sok mást.
weight: 13
url: /hu/java/chart-elements/font-size-legend-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Betűméret-magyarázat a Java Slides-ben


## A Java Slides betűméret-magyarázatának bemutatása

Ebből az oktatóanyagból megtudhatja, hogyan szabhatja testre a jelmagyarázat betűméretét egy PowerPoint dián az Aspose.Slides for Java segítségével. Ennek a feladatnak a megvalósításához lépésről lépésre útmutatást és forráskódot adunk.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Inicializálja a prezentációt

Először importálja a szükséges osztályokat, és inicializálja a PowerPoint bemutatót.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Cserélje ki`"Your Document Directory"` a PowerPoint-fájl tényleges elérési útjával.

## 2. lépés: Adjon hozzá egy diagramot

Ezután hozzáadunk egy diagramot a diához, és beállítjuk a jelmagyarázat betűméretét.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 Ebben a kódban az első dián fürtözött oszlopdiagramot hozunk létre, és a jelmagyarázat szövegének betűméretét 20 pontra állítjuk. Beállíthatja a`setFontHeight`értékét a betűméret igény szerinti módosításához.

## 3. lépés: A tengelyértékek testreszabása

Most pedig szabjuk testre a diagram függőleges tengelyértékeit.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Itt beállítjuk a függőleges tengely minimális és maximális értékét. Az értékeket az adatkövetelményeknek megfelelően módosíthatja.

## 4. lépés: Mentse el a bemutatót

Végül mentse a módosított prezentációt egy új fájlba.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Ez a kód a módosított prezentációt "output.pptx" néven menti a megadott könyvtárba.

## A Java Slides betűméret-magyarázatának teljes forráskódja

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

Sikeresen testreszabta a jelmagyarázat betűméretét egy Java PowerPoint dián az Aspose.Slides for Java segítségével. Tovább fedezheti az Aspose.Slides interaktív és tetszetős prezentációinak képességeit.

## GYIK

### Hogyan változtathatom meg a jelmagyarázat szövegének betűméretét a diagramban?

A diagramon szereplő jelmagyarázat szövegének betűméretének módosításához a következő kódot használhatja:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 Ebben a kódban létrehozunk egy diagramot, és a jelmagyarázat szövegének betűméretét 20 pontra állítjuk. Beállíthatja a`setFontHeight` értéket a betűméret módosításához.

### Testreszabhatom a jelmagyarázat egyéb tulajdonságait egy diagramban?

Igen, az Aspose.Slides segítségével testreszabhatja a diagramon szereplő jelmagyarázat különféle tulajdonságait. A testreszabható általános tulajdonságok közé tartozik a szöveg formázása, pozíciója, láthatósága és még sok más. Például a jelmagyarázat pozíciójának megváltoztatásához használhatja:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Ez a kód beállítja, hogy a jelmagyarázat a diagram alján jelenjen meg. További testreszabási lehetőségekért tekintse meg az Aspose.Slides dokumentációját.

### Hogyan állíthatok be minimális és maximális értéket a diagram függőleges tengelyéhez?

A diagram függőleges tengelyének minimális és maximális értékének beállításához a következő kódot használhatja:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Itt letiltjuk az automatikus tengelyméretezést, és megadjuk a függőleges tengely minimális és maximális értékét. Állítsa be a diagramadatokhoz szükséges értékeket.

### Hol találhatok további információt és dokumentációt az Aspose.Slides-hez?

 Az Aspose.Slides for Java-hoz átfogó dokumentációt és API-referenciákat találhat az Aspose dokumentációs webhelyén. Látogatás[itt](https://reference.aspose.com/slides/java/) a könyvtár használatával kapcsolatos részletes információkért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
