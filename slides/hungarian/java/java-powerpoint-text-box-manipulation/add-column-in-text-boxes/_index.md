---
title: Adjon hozzá oszlopot a szövegdobozokhoz az Aspose.Slides for Java segítségével
linktitle: Adjon hozzá oszlopot a szövegdobozokhoz az Aspose.Slides for Java segítségével
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat oszlopokat a PowerPoint szövegmezőihez az Aspose.Slides for Java segítségével. Fejlessze prezentációit ezzel a lépésenkénti útmutatóval.
weight: 10
url: /hu/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan lehet javítani a szövegdobozokat oszlopok hozzáadásával az Aspose.Slides for Java segítségével. Az Aspose.Slides egy hatékony Java-könyvtár, amely lehetővé teszi a fejlesztők számára PowerPoint-prezentációk programozott létrehozását, kezelését és konvertálását anélkül, hogy Microsoft Office-ra lenne szükség. Oszlopok hozzáadása a szövegmezőkhöz nagymértékben javíthatja a diákon belüli tartalom olvashatóságát és rendszerezését, így a prezentációk vonzóbbá és professzionálisabbá válhatnak.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java programozási alapismeretek.
- JDK (Java Development Kit) telepítve van a gépére.
-  Aspose.Slides for Java könyvtár. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## Csomagok importálása
A kezdéshez importálnia kell a szükséges Aspose.Slides osztályokat a Java fájlba. A következőképpen teheti meg:
```java
import com.aspose.slides.*;
```
## 1. lépés: A bemutató és a dia inicializálása
Először hozzon létre egy új PowerPoint-prezentációt, és inicializálja az első diát.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Szerezd meg a prezentáció első diáját
    ISlide slide = presentation.getSlides().get_Item(0);
```
## 2. lépés: AutoShape (téglalap) hozzáadása
Ezután adjon hozzá egy téglalap típusú automatikus alakzatot a diához.
```java
    // Adjon hozzá egy téglalap típusú automatikus alakzatot
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## 3. lépés: Adja hozzá a szövegkeretet a téglalaphoz
Most adjon hozzá egy TextFrame-et a téglalap automatikus alakzathoz, és állítsa be a kezdeti szöveget.
```java
    // Szövegkeret hozzáadása a téglalaphoz
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## 4. lépés: Állítsa be az oszlopok számát
Adja meg a szövegkereten belüli oszlopok számát.
```java
    // Szerezze be a TextFrame szövegformátumát
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Adja meg az oszlopok számát a TextFrame-ben
    format.setColumnCount(3);
```
## 5. lépés: Állítsa be az oszlopközt
Állítsa be az oszlopok közötti távolságot a TextFrame-ben.
```java
    // Adja meg az oszlopok közötti távolságot
    format.setColumnSpacing(10);
```
## 6. lépés: Mentse el a bemutatót
Végül mentse a módosított prezentációt egy PowerPoint fájlba.
```java
    // A létrehozott prezentáció mentése
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Következtetés
Ha követi ezeket a lépéseket, az Aspose.Slides for Java segítségével könnyedén hozzáadhat oszlopokat a PowerPoint-prezentációk szövegmezőihez. Ez a funkció lehetővé teszi a diák szerkezetének és olvashatóságának javítását, ezáltal látványosabbá és professzionálisabbá téve azokat.
## GYIK
### Hozzáadhatok háromnál több oszlopot egy szövegmezőhöz?
Igen, az Aspose.Slides segítségével tetszőleges számú oszlopot megadhat programozottan.
### Az Aspose.Slides kompatibilis a Java 11-gyel?
Igen, az Aspose.Slides támogatja a Java 11 és újabb verzióit.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Slides számára?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Az Aspose.Slides programhoz telepíteni kell a Microsoft Office-t?
Nem, az Aspose.Slides alkalmazáshoz nem szükséges a Microsoft Office telepítése a gépen.
### Hol találok további dokumentációt az Aspose.Slides for Java-ról?
 A részletes dokumentáció elérhető[itt](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
