---
"description": "Javítsa PowerPoint-bemutatóit egyéni betűtípusokkal, méretekkel és színekkel az egyes jelmagyarázatokhoz Java diákban az Aspose.Slides for Java használatával."
"linktitle": "Betűtípus-tulajdonságok az egyes jelmagyarázatokhoz Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Betűtípus-tulajdonságok az egyes jelmagyarázatokhoz Java diákban"
"url": "/hu/java/customization-and-formatting/font-properties-individual-legend-java-slides/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Betűtípus-tulajdonságok az egyes jelmagyarázatokhoz Java diákban


## Bevezetés a Java diákban található egyedi jelmagyarázatok betűtípus-tulajdonságaiba

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan állíthatunk be betűtípus-tulajdonságokat egy adott jelmagyarázathoz Java diákban az Aspose.Slides for Java használatával. A betűtípus-tulajdonságok testreszabásával vizuálisan vonzóbbá és informatívabbá teheti a jelmagyarázatokat a PowerPoint-bemutatókban.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár integrálva van a projektedbe. Letöltheted innen: [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/).

## 1. lépés: A prezentáció inicializálása és a diagram hozzáadása

Először is, kezdjük egy PowerPoint bemutató inicializálásával és egy diagram hozzáadásával. Ebben a példában egy csoportos oszlopdiagramot fogunk használni illusztrációként.

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

Csere `"Your Document Directory"` a PowerPoint-dokumentum tényleges mappájával.

## 2. lépés: A jelmagyarázat betűtípus-tulajdonságainak testreszabása

Most szabjuk testre a diagramon belüli egyes jelmagyarázat-bejegyzések betűtípus-tulajdonságait. Ebben a példában a második jelmagyarázat-bejegyzést (1. index) célozzuk meg, de az indexet az Ön igényei szerint módosíthatja.

```java
IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
tf.getPortionFormat().setFontBold(NullableBool.True);
tf.getPortionFormat().setFontHeight(20);
tf.getPortionFormat().setFontItalic(NullableBool.True);
tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```

Íme, mit csinál az egyes kódsorok:

- `get_Item(1)` lekéri a második jelmagyarázat-bejegyzést (1. index). Az indexet módosíthatja, hogy egy másik jelmagyarázat-bejegyzést célozzon meg.
- `setFontBold(NullableBool.True)` félkövérre állítja a betűtípust.
- `setFontHeight(20)` 20 pontra állítja a betűméretet.
- `setFontItalic(NullableBool.True)` dőlt betűtípust állít be.
- `setFillType(FillType.Solid)` meghatározza, hogy a jelmagyarázat bejegyzés szövegének tömör kitöltéssel kell rendelkeznie.
- `getSolidFillColor().setColor(Color.BLUE)` kékre állítja a kitöltőszínt. Lecserélheti `Color.BLUE` a kívánt színnel.

## 3. lépés: Mentse el a módosított prezentációt

Végül mentse el a módosított prezentációt egy új fájlba a módosítások megőrzése érdekében.

```java
pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
```

Csere `"output.pptx"` a kívánt kimeneti fájlnévvel.

Ennyi! Sikeresen testre szabtad egy Java Slides prezentáció egy adott jelmagyarázat-bejegyzésének betűtípus-tulajdonságait az Aspose.Slides for Java használatával.

## Teljes forráskód a Java diákban található egyedi jelmagyarázatok betűtípus-tulajdonságaihoz

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

Ebben az oktatóanyagban megtanultuk, hogyan szabhatjuk testre az egyes jelmagyarázatok betűtípus-tulajdonságait Java Slides-ben az Aspose.Slides for Java használatával. A betűtípusok, méretek és színek módosításával javíthatjuk PowerPoint-bemutatóink vizuális vonzerejét és érthetőségét.

## GYIK

### Hogyan tudom megváltoztatni a betűszínt?

A betűszín megváltoztatásához használja a `tf.getPortionFormat().getFontColor().setColor(yourColor)` a kitöltőszín megváltoztatása helyett. Cserélje ki `yourColor` a kívánt betűszínnel.

### Hogyan módosíthatom a jelmagyarázat egyéb tulajdonságait?

jelmagyarázat számos egyéb tulajdonságát is módosíthatja, például a pozícióját, méretét és formátumát. A jelmagyarázatokkal való munkavégzésről részletes információkat az Aspose.Slides for Java dokumentációjában talál.

### Alkalmazhatom ezeket a módosításokat több jelmagyarázat-bejegyzésre is?

Igen, végigmehetsz a jelmagyarázat-bejegyzéseken, és ezeket a módosításokat több bejegyzésre is alkalmazhatod az index módosításával. `get_Item(index)` és a testreszabási kód megismétlése.

Ne felejtsd el megszabadulni a prezentációs objektumtól, ha készen állsz az erőforrások felszabadítására:

```java
if (pres != null) pres.dispose();
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}