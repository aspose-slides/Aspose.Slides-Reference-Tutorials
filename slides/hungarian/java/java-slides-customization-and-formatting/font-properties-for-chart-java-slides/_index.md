---
title: A Java Slides diagramjának betűtípus tulajdonságai
linktitle: A Java Slides diagramjának betűtípus tulajdonságai
second_title: Aspose.Slides Java PowerPoint Processing API
description: Javítsa a diagram betűtípus-tulajdonságait a Java Slides-ben az Aspose.Slides for Java segítségével. Testreszabhatja a betűméretet, stílust és színt a hatásos prezentációk érdekében.
weight: 11
url: /hu/java/customization-and-formatting/font-properties-for-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# A Java Slides diagramjának betűtípus tulajdonságai


## Bevezetés a Java Slides diagramjának betűtípus tulajdonságaiba

Ez az útmutató végigvezeti Önt a Java Slides diagramok betűtípus-tulajdonságainak beállításán az Aspose.Slides segítségével. Testreszabhatja a diagram szövegének betűméretét és megjelenését, hogy növelje prezentációinak vizuális vonzerejét.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java API be van építve a projektbe. Ha még nem tette meg, letöltheti a[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/).

## 1. lépés: Hozzon létre egy prezentációt

Először hozzon létre egy új prezentációt a következő kóddal:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Adjon hozzá egy diagramot

Most adjunk hozzá egy fürtözött oszlopdiagramot a prezentációhoz:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 400);
```

Itt egy fürtözött oszlopdiagramot adunk az első diához koordinátákon (100, 100), amelynek szélessége 500 egység és magassága 400 egység.

## 3. lépés: A betűtípus tulajdonságainak testreszabása

Ezután testre szabjuk a diagram betűtípus-tulajdonságait. Ebben a példában 20-ra állítjuk a betűméretet az összes diagram szövegéhez:

```java
chart.getTextFormat().getPortionFormat().setFontHeight(20);
```

Ez a kód 20 pontra állítja a betűméretet a diagramon belüli összes szöveg esetében.

## 4. lépés: Adatcímkék megjelenítése

Adatcímkéket is megjeleníthet a diagramon a következő kóddal:

```java
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

Ez a kódsor lehetővé teszi az adatcímkéket a diagram első sorozatához, megjelenítve az értékeket a diagram oszlopain.

## 5. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a testreszabott diagram betűtípus tulajdonságaival:

```java
pres.save(dataDir + "FontPropertiesForChart.pptx", SaveFormat.Pptx);
```

Ez a kód elmenti a prezentációt a megadott könyvtárba „FontPropertiesForChart.pptx” fájlnévvel.

## A Java Slides diagramjának betűtípus-tulajdonságainak teljes forráskódja

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

Ebben az oktatóanyagban megtanulta, hogyan szabhatja testre egy diagram betűtípus-tulajdonságait a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Ezekkel a technikákkal javíthatja diagramjai és prezentációi megjelenését. Fedezze fel a további lehetőségeket a[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/).

## GYIK

### Hogyan tudom megváltoztatni a betűtípus színét?

 A diagram szövegének betűszínének módosításához használja a`chart.getTextFormat().getPortionFormat().setFontColor(Color.RED);` , csere`Color.RED` a kívánt színnel.

### Módosíthatom a betűtípus stílusát (félkövér, dőlt stb.)?

 Igen, módosíthatja a betűtípus stílusát. Használat`chart.getTextFormat().getPortionFormat().setFontBold(true);` hogy a betűtípus félkövér legyen. Hasonlóképpen használhatja`setFontItalic(true)` hogy dőlt legyen.

### Hogyan szabhatom testre a betűtípus tulajdonságait adott diagramelemekhez?

Ha testre szeretné szabni a betűtípus tulajdonságait bizonyos diagramelemekhez, például a tengelycímkékhez vagy a jelmagyarázat szövegéhez, elérheti ezeket az elemeket, és beállíthatja a betűtípus tulajdonságait a fentiekhez hasonló módszerekkel.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
