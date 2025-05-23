---
"description": "Dobd fel Java diáidat egyéni vonalakkal. Lépésről lépésre útmutató az Aspose.Slides használatához Java-ban. Tanuld meg, hogyan adhatsz hozzá és szabhatsz testre vonalakat a prezentációkban a hatásos vizuális megjelenítés érdekében."
"linktitle": "Egyéni sorok hozzáadása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Egyéni sorok hozzáadása Java diákban"
"url": "/hu/java/customization-and-formatting/adding-custom-lines-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Egyéni sorok hozzáadása Java diákban


## Bevezetés az egyéni sorok hozzáadásába Java diákban

Ebben az oktatóanyagban megtanulod, hogyan adhatsz hozzá egyéni vonalakat Java diáidhoz az Aspose.Slides for Java segítségével. Az egyéni vonalak segítségével javíthatod a diák vizuális megjelenítését és kiemelhetsz bizonyos tartalmakat. Lépésről lépésre bemutatjuk a megvalósításhoz szükséges utasításokat és forráskódot. Kezdjük is!

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár be van állítva a Java projektedben. A könyvtárat a következő weboldalról töltheted le: [Aspose.Slides Java-hoz](https://releases.aspose.com/slides/java/)

## 1. lépés: A prezentáció inicializálása

Először létre kell hoznod egy új prezentációt. Ebben a példában egy üres prezentációt fogunk létrehozni.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Diagram hozzáadása

Ezután egy diagramot adunk a diához. Ebben a példában egy csoportos oszlopdiagramot adunk hozzá. Kiválaszthatja az igényeinek megfelelő diagramtípust.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

## 3. lépés: Egyéni vonal hozzáadása

Most adjunk hozzá egy egyéni vonalat a diagramhoz. Létrehozunk egy `IAutoShape` típusú `ShapeType.Line` és pozicionáld a diagramon belül.

```java
IAutoShape shape = chart.getUserShapes().getShapes().addAutoShape(ShapeType.Line, 0, chart.getHeight() / 2, chart.getWidth(), 0);
```

## 4. lépés: A vonal testreszabása

A vonal megjelenését testreszabhatja a tulajdonságainak beállításával. Ebben a példában a vonal színét pirosra állítjuk.

```java
shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## 5. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a kívánt helyre.

```java
pres.save(dataDir + "AddCustomLines.pptx", SaveFormat.Pptx);
```

## Teljes forráskód egyéni sorok hozzáadásához Java diákban

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

Gratulálunk! Sikeresen hozzáadott egy egyéni vonalat a Java diájához az Aspose.Slides for Java segítségével. A vonal tulajdonságait tovább testreszabhatja a kívánt vizuális effektek eléréséhez.

## GYIK

### Hogyan tudom megváltoztatni a vonal színét?

A vonal színének megváltoztatásához használja a következő kódot:
```java
shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YOUR_COLOR);
```

Csere `YOUR_COLOR` a kívánt színnel.

### Hozzáadhatok egyéni vonalakat más alakzatokhoz?

Igen, nem csak diagramokhoz, hanem különféle alakzatokhoz is hozzáadhatsz egyéni vonalakat. Egyszerűen hozz létre egyet. `IAutoShape` és szabd testre az igényeidnek megfelelően.

### Hogyan tudom megváltoztatni a vonal vastagságát?

A vonal vastagságát a következő beállítással módosíthatja: `Width` a vonalformátum tulajdonsága. Például:
```java
shape.getLineFormat().setWidth(2); // Vonalvastagság beállítása 2 pontra
```

### Lehetséges több sort hozzáadni egy diához?

Igen, több sort is hozzáadhatsz egy diához az ebben az oktatóanyagban említett lépések megismétlésével. Minden sor külön testreszabható.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}