---
title: Egyéni sorok hozzáadása a Java Slides-hez
linktitle: Egyéni sorok hozzáadása a Java Slides-hez
second_title: Aspose.Slides Java PowerPoint Processing API
description: Javítsa Java-diáit egyéni vonalakkal. Útmutató lépésről lépésre az Aspose.Slides for Java használatához. Tanuljon meg vonalakat hozzáadni és testreszabni a prezentációkban a hatásos látvány érdekében.
type: docs
weight: 10
url: /hu/java/customization-and-formatting/adding-custom-lines-java-slides/
---

## Bevezetés az egyéni sorok hozzáadásához a Java Slides-ben

Ebből az oktatóanyagból megtudhatja, hogyan adhat egyéni sorokat Java-diáihoz az Aspose.Slides for Java segítségével. Egyéni vonalak segítségével javíthatja a diák vizuális megjelenítését és kiemelheti az adott tartalmat. Ennek eléréséhez lépésről lépésre útmutatást adunk a forráskóddal együtt. Kezdjük el!

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides a Java számára könyvtár be van állítva a Java projektben. A könyvtár letölthető a honlapról:[Aspose.Slides for Java](https://releases.aspose.com/slides/java/)

## 1. lépés: Inicializálja a prezentációt

Először is létre kell hoznia egy új prezentációt. Ebben a példában egy üres prezentációt fogunk létrehozni.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Adjon hozzá egy diagramot

Ezután hozzáadunk egy diagramot a diához. Ebben a példában fürtözött oszlopdiagramot adunk hozzá. Kiválaszthatja az igényeinek megfelelő diagramtípust.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## 3. lépés: Adjon hozzá egyéni sort

 Most adjunk hozzá egy egyéni vonalat a diagramhoz. Létrehozunk egy`IAutoShape` típusú`ShapeType.Line` és helyezze el a diagramon belül.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## 4. lépés: A vonal testreszabása

Testreszabhatja a vonal megjelenését a tulajdonságainak beállításával. Ebben a példában a vonal színét pirosra állítjuk.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## 5. lépés: Mentse el a prezentációt

Végül mentse a prezentációt a kívánt helyre.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Teljes forráskód egyéni sorok hozzáadásához a Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
	shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
	shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
	pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Gratulálunk! Sikeresen hozzáadott egy egyéni sort a Java diához az Aspose.Slides for Java segítségével. Tovább szabhatja a vonal tulajdonságait a kívánt vizuális effektusok eléréséhez.

## GYIK

### Hogyan változtathatom meg a vonal színét?

A vonal színének megváltoztatásához használja a következő kódot:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

 Cserélje ki`YOUR_COLOR` a kívánt színnel.

### Hozzáadhatok egyéni vonalakat más alakzatokhoz?

 Igen, egyéni vonalakat is hozzáadhat különféle alakzatokhoz, nem csak diagramokhoz. Egyszerűen hozzon létre egy`IAutoShape` és az Ön igényei szerint testreszabhatja.

### Hogyan tudom megváltoztatni a vonal vastagságát?

 A vonalvastagságot a beállításával módosíthatja`Width` a sorformátum tulajdonsága. Például:
```java
shape.getLineFormat().setWidth(2); // Állítsa be a vonalvastagságot 2 pontra
```

### Lehetséges több sort is hozzáadni egy diához?

Igen, több sort is hozzáadhat egy diához az oktatóanyagban említett lépések megismétlésével. Minden sor önállóan testreszabható.