---
title: Töltse le a diagram képét a Java Slides alkalmazásban
linktitle: Töltse le a diagram képét a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan szerezhet be diagramképeket a Java Slides programban az Aspose.Slides for Java segítségével. Ez a lépésenkénti útmutató forráskódot és tippeket ad a zökkenőmentes integrációhoz.
weight: 19
url: /hu/java/data-manipulation/get-chart-image-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Töltse le a diagram képét a Java Slides alkalmazásban


## Bevezetés a diagramkép letöltéséhez Java Slides-ben

Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi a PowerPoint prezentációk programozott kezelését. Ezzel a könyvtárral különféle elemeket hozhat létre, kezelhet és kinyerhet a prezentációkból, beleértve a diagramokat is. Az egyik gyakori követelmény a diagramképek beszerzése a diákról, és ebben az útmutatóban bemutatjuk, hogyan kell ezt megtenni.

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Java Development Kit (JDK) telepítve a rendszerére.
-  Aspose.Slides for Java könyvtár letöltve és konfigurálva a projektben. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Állítsa be projektjét

Kezdje azzal, hogy hozzon létre egy Java-projektet a kívánt integrált fejlesztőkörnyezetben (IDE). Győződjön meg arról, hogy hozzáadta az Aspose.Slides for Java könyvtárat a projekt függőségeihez.

## 2. lépés: Inicializálja a prezentációt

A kezdéshez inicializálnia kell egy PowerPoint bemutatót. Ebben a példában feltételezzük, hogy a dokumentumkönyvtárban van egy „test.pptx” nevű PowerPoint-fájl.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

## 3. lépés: Adjon hozzá egy diagramot, és szerezze be a képet

Ezután hozzáadhat egy diagramot egy diához, és megkaphatja a képét. Ebben a példában fürtözött oszlopdiagramot adunk hozzá.

```java
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    BufferedImage img = chart.getThumbnail();
    ImageIO.write(img, ".png", new File(dataDir + "image.png"));
} finally {
    if (pres != null) pres.dispose();
}
```

Ebben a kódrészletben fürtözött oszlopdiagramot hozunk létre a prezentáció első diáján, majd megkapjuk a miniatűr képét. A kép "image.png" néven kerül mentésre a megadott könyvtárba.

## Teljes forráskód a diagramkép letöltéséhez a Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	BufferedImage img = chart.getThumbnail();
	ImageIO.write(img, ".png", new File(dataDir + "image.png"));
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

A diagramképek beszerzése a Java Slides programból az Aspose.Slides for Java segítségével egyszerű folyamat. A mellékelt kóddal könnyedén integrálhatja ezt a funkciót Java-alkalmazásaiba, így hatékonyan dolgozhat a PowerPoint prezentációkkal.

## GYIK

### Hogyan telepíthetem az Aspose.Slides for Java programot?

 Az Aspose.Slides for Java telepítése egyszerű. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/slides/java/) és kövesse a dokumentációban található telepítési utasításokat.

### Testreszabhatom a diagramot a kép beszerzése előtt?

Igen, testreszabhatja a diagram megjelenését, adatait és egyéb tulajdonságait a kép beszerzése előtt. Az Aspose.Slides for Java kiterjedt lehetőségeket kínál a diagramok testreszabásához.

### Milyen egyéb funkciókat kínál az Aspose.Slides for Java?

Az Aspose.Slides for Java funkciók széles skáláját kínálja a PowerPoint prezentációkkal való munkavégzéshez, beleértve a diakészítést, a szövegkezelést, az alakzatok szerkesztését és még sok mást. Részletes információkért tekintse meg a dokumentációt.

### Az Aspose.Slides for Java alkalmas kereskedelmi használatra?

Igen, az Aspose.Slides for Java felhasználható kereskedelmi célokra. Olyan licencelési lehetőségeket biztosít, amelyek mind az egyéni fejlesztők, mind a vállalkozások számára kiszolgálnak.

### Elmenthetem a diagram képét más formátumban?

 Biztosan! A diagram képét különféle formátumokban, például JPEG vagy GIF formátumban mentheti, ha megadja a megfelelő fájlkiterjesztést a`ImageIO.write` módszer.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
