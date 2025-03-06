---
title: Betűtípus-tulajdonságok az egyes jelmagyarázatokhoz a Java Slides-ben
linktitle: Betűtípus-tulajdonságok az egyes jelmagyarázatokhoz a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Az Aspose.Slides for Java segítségével javíthatja a PowerPoint bemutatókat egyéni betűstílusokkal, -méretekkel és -színekkel a Java Slides egyes jelmagyarázataihoz.
weight: 12
url: /hu/java/customization-and-formatting/font-properties-individual-legend-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Bevezetés a Java Slides egyéni jelmagyarázatának betűtípus-tulajdonságaiba

Ebben az oktatóanyagban megvizsgáljuk, hogyan állíthat be betűtípus-tulajdonságokat egy egyedi jelmagyarázathoz a Java Slides programban az Aspose.Slides for Java segítségével. A betűtípus tulajdonságainak testreszabásával látványosabbá és informatívabbá teheti legendáit PowerPoint-prezentációiban.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár integrálva van a projektjébe. Letöltheti a[Aspose.Slides a Java dokumentációhoz](https://reference.aspose.com/slides/java/).

## 1. lépés: A prezentáció inicializálása és a diagram hozzáadása

Először is kezdjük azzal, hogy inicializálunk egy PowerPoint-prezentációt, és adjunk hozzá egy diagramot. Ebben a példában fürtözött oszlopdiagramot fogunk használni illusztrációként.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");

try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    // A kód többi része ide kerül
} finally {
    if (pres != null) pres.dispose();
}
```

 Cserélje ki`"Your Document Directory"` azzal a tényleges könyvtárral, ahol a PowerPoint-dokumentum található.

## 2. lépés: A Legend betűtípus tulajdonságainak testreszabása

Most pedig szabjuk testre a diagramon belüli egyedi jelmagyarázat-bejegyzés betűtípus-tulajdonságait. Ebben a példában a második jelmagyarázat bejegyzést (1. index) célozzuk meg, de az indexet saját igényei szerint módosíthatja.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

A kód egyes sorai a következők:

- `get_Item(1)` lekéri a második jelmagyarázat bejegyzést (1. index). Módosíthatja az indexet, hogy egy másik jelmagyarázat-bejegyzést célozzon meg.
- `setFontBold(NullableBool.True)` félkövérre állítja a betűtípust.
- `setFontHeight(20)` a betűméretet 20 pontra állítja.
- `setFontItalic(NullableBool.True)` a betűtípust dőltre állítja.
- `setFillType(FillType.Solid)` meghatározza, hogy a jelmagyarázat bejegyzés szövegének tömör kitöltésűnek kell lennie.
- `getSolidFillColor().setColor(Color.BLUE)` a kitöltési színt kékre állítja. Cserélheted`Color.BLUE` a kívánt színnel.

## 3. lépés: Mentse el a módosított prezentációt

Végül mentse a módosított bemutatót egy új fájlba a változtatások megőrzése érdekében.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

 Cserélje ki`"output.pptx"` a kívánt kimeneti fájlnévvel.

Ez az! Sikeresen testreszabta a betűtípus tulajdonságait egy Java Slides prezentációban lévő egyedi jelmagyarázat bejegyzéshez az Aspose.Slides for Java segítségével.

## Java Slides egyéni jelmagyarázatának betűtípus-tulajdonságainak teljes forráskódja

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
	tf.getPortionFormat().setFontBold(NullableBool.True);
	tf.getPortionFormat().setFontHeight(20);
	tf.getPortionFormat().setFontItalic(NullableBool.True);
	tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet személyre szabni a betűtípus tulajdonságait egy egyedi jelmagyarázathoz a Java Slides programban az Aspose.Slides for Java segítségével. A betűstílusok, -méretek és -színek beállításával fokozhatja PowerPoint-prezentációinak vizuális vonzerejét és tisztaságát.

## GYIK

### Hogyan tudom megváltoztatni a betűtípus színét?

 A betűszín megváltoztatásához használja a`tf.getPortionFormat().getFontColor().setColor(yourColor)` a kitöltés színének megváltoztatása helyett. Cserélje ki`yourColor` a kívánt betűszínnel.

### Hogyan módosíthatok más jelmagyarázat tulajdonságokat?

Módosíthatja a jelmagyarázat különféle egyéb tulajdonságait, például a pozíciót, a méretet és a formátumot. Tekintse meg az Aspose.Slides for Java dokumentációját a jelmagyarázatokkal való munkavégzésről szóló részletes információkért.

### Alkalmazhatom ezeket a változtatásokat több jelmagyarázat bejegyzésre?

 Igen, végigpörgetheti a jelmagyarázat bejegyzéseit, és ezeket a változtatásokat több bejegyzésre is alkalmazhatja az index módosításával`get_Item(index)` és megismételjük a testreszabási kódot.

Ne felejtse el dobni a prezentációs objektumot, ha végzett az erőforrások felszabadításával:

```java
if (pres != null) pres.dispose();
```
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
