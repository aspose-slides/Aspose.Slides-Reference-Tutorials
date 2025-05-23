---
"description": "Tanuld meg, hogyan adhatsz hozzá oszlopokat szövegdobozokhoz PowerPointban az Aspose.Slides for Java használatával. Dobd fel prezentációidat ezzel a lépésről lépésre szóló útmutatóval."
"linktitle": "Oszlop hozzáadása szövegdobozokhoz az Aspose.Slides segítségével Java-ban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Oszlop hozzáadása szövegdobozokhoz az Aspose.Slides segítségével Java-ban"
"url": "/hu/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Oszlop hozzáadása szövegdobozokhoz az Aspose.Slides segítségével Java-ban

## Bevezetés
Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan lehet a szövegdobozokat oszlopok hozzáadásával javítani az Aspose.Slides for Java használatával. Az Aspose.Slides egy hatékony Java könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PowerPoint-bemutatókat hozzanak létre, szerkeszszenek és konvertáljanak programozottan, Microsoft Office nélkül. Az oszlopok hozzáadása a szövegdobozokhoz nagymértékben javíthatja a diákon belüli tartalom olvashatóságát és szervezését, így a prezentációk lebilincselőbbek és professzionálisabbak lesznek.
## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételekkel rendelkezünk:
- Java programozási alapismeretek.
- JDK (Java Development Kit) telepítve a gépedre.
- Aspose.Slides Java könyvtárhoz. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## Csomagok importálása
A kezdéshez importálnod kell a szükséges Aspose.Slides osztályokat a Java fájlodba. Így teheted meg:
```java
import com.aspose.slides.*;
```
## 1. lépés: A prezentáció és a dia inicializálása
Először hozz létre egy új PowerPoint bemutatót, és inicializáld az első diát.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // A prezentáció első diájának lekérése
    ISlide slide = presentation.getSlides().get_Item(0);
```
## 2. lépés: Automatikus alakzat hozzáadása (téglalap)
Ezután adjon hozzá egy Téglalap típusú AutoShape-et a diához.
```java
    // Téglalap típusú AutoShape hozzáadása
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## 3. lépés: TextFrame hozzáadása a téglalaphoz
Most adj hozzá egy TextFrame-et a Rectangle AutoShape-hez, és állítsd be a kezdeti szövegét.
```java
    // TextFrame hozzáadása a téglalaphoz
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## 4. lépés: Oszlopok számának beállítása
Adja meg a TextFrame oszlopainak számát.
```java
    // TextFrame szövegformátumának lekérése
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Adja meg az oszlopok számát a TextFrame-ben
    format.setColumnCount(3);
```
## 5. lépés: Oszlopköz beállítása
Állítsa be az oszlopok közötti térközt a TextFrame-ben.
```java
    // Oszlopok közötti térköz megadása
    format.setColumnSpacing(10);
```
## 6. lépés: Mentse el a prezentációt
Végül mentse el a módosított prezentációt egy PowerPoint fájlba.
```java
    // Létrehozott prezentáció mentése
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Következtetés
következő lépéseket követve könnyedén hozzáadhatsz oszlopokat a PowerPoint-bemutatók szövegdobozaihoz az Aspose.Slides for Java segítségével. Ez a funkció lehetővé teszi a diák szerkezetének és olvashatóságának javítását, így vizuálisan vonzóbbá és professzionálisabbá teheted őket.
## GYIK
### Hozzáadhatok háromnál több oszlopot egy szövegmezőhöz?
Igen, az Aspose.Slides használatával programozottan tetszőleges számú oszlopot megadhatsz.
### Az Aspose.Slides kompatibilis a Java 11-gyel?
Igen, az Aspose.Slides támogatja a Java 11-es és újabb verzióit.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Slides-hoz?
Ideiglenes jogosítványt szerezhet [itt](https://purchase.aspose.com/temporary-license/).
### Az Aspose.Slides használatához telepíteni kell a Microsoft Office-t?
Nem, az Aspose.Slides használatához nem szükséges a Microsoft Office telepítése a gépre.
### Hol találok további dokumentációt az Aspose.Slides for Java-ról?
Részletes dokumentáció elérhető [itt](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}