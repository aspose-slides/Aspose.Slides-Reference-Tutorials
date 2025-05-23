---
"description": "Tanuld meg, hogyan adhatsz hozzá felső és alsó indexű szöveget Java PowerPoint prezentációkhoz az Aspose.Slides for Java segítségével. Tökéletes a diák javításához."
"linktitle": "Felső és alsó indexű szöveg hozzáadása Java PowerPointban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Felső és alsó indexű szöveg hozzáadása Java PowerPointban"
"url": "/hu/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Felső és alsó indexű szöveg hozzáadása Java PowerPointban

## Bevezetés
lebilincselő és informatív PowerPoint-bemutatók készítéséhez gyakran formázási funkciók, például felső és alsó indexű szöveg használata szükséges. Ez az oktatóanyag végigvezeti Önt a felső és alsó indexű szöveg Java PowerPoint-bemutatókba való beépítésének folyamatán az Aspose.Slides for Java használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:
- Java fejlesztőkészlet (JDK) telepítve van a rendszerére.
- Aspose.Slides Java könyvtárhoz. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).
- Integrált fejlesztői környezet (IDE), például IntelliJ IDEA vagy Eclipse, Java fejlesztéshez beállítva.
- Alapfokú jártasság a Java programozásban és a PowerPoint prezentációkban.

## Csomagok importálása
Először importáld a szükséges csomagokat az Aspose.Slides for Java-ból:
```java
import com.aspose.slides.*;
```
## 1. lépés: A prezentáció beállítása
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 2. lépés: Hozzáférés a diavetítéshez
```java
// Az első dia betöltése
ISlide slide = presentation.getSlides().get_Item(0);
```
## 3. lépés: Szövegdoboz létrehozása
```java
// Hozzon létre egy alakzatot szövegdobozként való használatra
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## 4. lépés: Felső indexű szöveg hozzáadása
```java
// Hozz létre egy bekezdést a fő szöveghez
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Hozzon létre egy részt a felső indexű szöveghez
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Escape karakter beállítása felső indexhez
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// A fő bekezdés hozzáadása felső indexszel a szövegmezőhöz
textFrame.getParagraphs().add(mainParagraph);
```
## 5. lépés: Alsó index szövegének hozzáadása
```java
// Újabb bekezdés létrehozása az alsó indexű szöveghez
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Hozz létre egy részt az alsó index szövegéhez
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Alsó indexhez tartozó escape karakter beállítása
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Alsó indexű bekezdés hozzáadása a szövegmezőhöz
textFrame.getParagraphs().add(subscriptParagraph);
```
## 6. lépés: Mentse el a prezentációt
```java
// Mentse el a prezentációt
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Következtetés
Ebben az oktatóanyagban azt vizsgáltuk meg, hogyan teheted jobbá Java PowerPoint prezentációidat felső és alsó indexű szöveggel az Aspose.Slides for Java segítségével. A következő lépéseket követve vizuálisan vonzóbb és informatívabb diákat hozhatsz létre, amelyek hatékonyan közvetítik a tartalmadat.

## GYIK
### Mi az Aspose.Slides Java-hoz?
Az Aspose.Slides for Java egy robusztus könyvtár, amely lehetővé teszi a fejlesztők számára PowerPoint-bemutatók programozott létrehozását, kezelését és konvertálását.
### Hol találok további dokumentációt az Aspose.Slides for Java-ról?
Részletes dokumentáció található [itt](https://reference.aspose.com/slides/java/).
### Hogyan szerezhetek ideiglenes licencet az Aspose.Slides for Java-hoz?
Ideiglenes jogosítványt szerezhetsz [itt](https://purchase.aspose.com/temporary-license/).
### Kipróbálhatom ingyen az Aspose.Slides-t Java-ban?
Igen, letölthet egy ingyenes próbaverziót innen [itt](https://releases.aspose.com/).
### Hol kaphatok támogatást az Aspose.Slides for Java-hoz?
Támogatásért és beszélgetésekért látogassa meg a [Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}