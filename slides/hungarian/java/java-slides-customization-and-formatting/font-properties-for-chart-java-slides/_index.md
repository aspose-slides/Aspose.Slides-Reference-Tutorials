---
"description": "Javítsa a diagramok betűtípus-tulajdonságait Java diákban az Aspose.Slides for Java segítségével. Testreszabhatja a betűméretet, stílust és színt a hatásos prezentációkhoz."
"linktitle": "Betűtípus-tulajdonságok diagramokhoz Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Betűtípus-tulajdonságok diagramokhoz Java diákban"
"url": "/hu/java/customization-and-formatting/font-properties-for-chart-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Betűtípus-tulajdonságok diagramokhoz Java diákban


## Bevezetés a Java diák diagramjainak betűtípus-tulajdonságaiba

Ez az útmutató végigvezet a Java Slides diagramok betűtípus-tulajdonságainak beállításán az Aspose.Slides használatával. Testreszabhatja a diagram szövegének betűméretét és megjelenését a prezentációk vizuális vonzerejének fokozása érdekében.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java API integrálva van a projektedbe. Ha még nem tetted meg, letöltheted innen: [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/).

## 1. lépés: Prezentáció létrehozása

Először hozz létre egy új prezentációt a következő kóddal:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Diagram hozzáadása

Most adjunk hozzá egy csoportos oszlopdiagramot a bemutatónkhoz:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Itt egy csoportos oszlopdiagramot adunk az első diához a (100, 100) koordinátákon, 500 egység szélességgel és 400 egység magassággal.

## 3. lépés: Betűtípus-tulajdonságok testreszabása

Ezután testreszabjuk a diagram betűtípus-tulajdonságait. Ebben a példában a diagram összes szövegének betűméretét 20-ra állítjuk be:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Ez a kód a diagramon belüli összes szöveg betűméretét 20 pontra állítja.

## 4. lépés: Adatcímkék megjelenítése

Az adatfeliratokat a diagramon a következő kóddal is megjelenítheti:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Ez a kódsor lehetővé teszi az adatfeliratok használatát a diagram első sorozatához, megjelenítve az értékeket a diagram oszlopaiban.

## 5. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a testreszabott diagrambetűtípus-tulajdonságokkal:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Ez a kód a megadott könyvtárba menti a prezentációt „FontPropertiesForChart.pptx” fájlnévvel.

## Teljes forráskód a Java diákban található diagramok betűtípus-tulajdonságaihoz

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
	chart.getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
	pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultad, hogyan szabhatod testre egy Java Slides diagram betűtípus-tulajdonságait az Aspose.Slides for Java használatával. Ezeket a technikákat alkalmazhatod a diagramok és prezentációk megjelenésének javítására. Fedezz fel további lehetőségeket a következőben: [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/).

## GYIK

### Hogyan tudom megváltoztatni a betűszínt?

A diagram szövegének betűszínének módosításához használja a `chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);`, helyettesítve `Color.RED` a kívánt színnel.

### Meg tudom változtatni a betűtípust (félkövér, dőlt stb.)?

Igen, megváltoztathatja a betűtípust. Használja `chart.getTextFormat().getPortionFormat().setFontBold(true);` a betűtípus félkövérré tételéhez. Hasonlóképpen használhatja a `setFontItalic(true)` hogy dőlt betűs legyen.

### Hogyan szabhatom testre a betűtípus tulajdonságait bizonyos diagramelemekhez?

Adott diagramelemek, például tengelyfeliratok vagy jelmagyarázat szövegének betűtípus-tulajdonságainak testreszabásához a fent bemutatotthoz hasonló módszerekkel érheti el ezeket az elemeket, és állíthatja be betűtípus-tulajdonságaikat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}