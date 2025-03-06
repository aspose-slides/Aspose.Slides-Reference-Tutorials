---
title: Adjon hozzá felső és alsó indexet a Java PowerPointban
linktitle: Adjon hozzá felső és alsó indexet a Java PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá felső és alsó indexet a Java PowerPoint prezentációkhoz az Aspose.Slides for Java segítségével. Tökéletes a csúszdák feljavításához.
weight: 13
url: /hu/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
A lebilincselő és informatív PowerPoint-prezentációk létrehozása gyakran olyan formázási funkciókat igényel, mint a felső és alsó index. Ez az oktatóanyag végigvezeti Önt a felső és alsó indexek szövegének Java PowerPoint prezentációiba való beépítésén az Aspose.Slides for Java segítségével.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
- Java Development Kit (JDK) telepítve a rendszerére.
-  Aspose.Slides for Java könyvtár. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).
- Integrált fejlesztői környezet (IDE), például az IntelliJ IDEA vagy az Eclipse, amely Java fejlesztéshez van beállítva.
- Alapvető ismeretek a Java programozásban és a PowerPoint bemutatókban.

## Csomagok importálása
Először is importálja a szükséges csomagokat az Aspose.Slides for Java-ból:
```java
import com.aspose.slides.*;
```
## 1. lépés: Állítsa be a prezentációt
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 2. lépés: Nyissa meg a diát
```java
// Szerezd meg az első diát
ISlide slide = presentation.getSlides().get_Item(0);
```
## 3. lépés: Hozzon létre egy szövegdobozt
```java
// Hozzon létre egy automatikus alakzatot, amely szövegdobozként szolgál
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## 4. lépés: Adjon hozzá felső index szöveget
```java
// Hozzon létre egy bekezdést a fő szöveghez
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Hozzon létre egy részt a felső index szövegéhez
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Állítsa be a szökést a felső indexhez
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Adja hozzá a fő bekezdést felső indexszel a szövegdobozhoz
textFrame.getParagraphs().add(mainParagraph);
```
## 5. lépés: Adjon hozzá alsó index szöveget
```java
// Hozzon létre egy másik bekezdést az alsó index szövegéhez
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Hozzon létre egy részt az alsó index szövegéhez
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Megszökés beállítása alsó indexhez
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Adja hozzá az alsó index bekezdést a szövegmezőhöz
textFrame.getParagraphs().add(subscriptParagraph);
```
## 6. lépés: Mentse el a bemutatót
```java
// Mentse el a bemutatót
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Következtetés
Ebben az oktatóanyagban megvizsgáltuk, hogyan javíthatja Java PowerPoint prezentációit felső- és alsó indexekkel az Aspose.Slides for Java segítségével. Ha követi ezeket a lépéseket, látványosabb és informatívabb diákat hozhat létre, amelyek hatékonyan kommunikálják a tartalmat.

## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy robusztus könyvtár, amely lehetővé teszi a fejlesztők számára PowerPoint-prezentációk programozott létrehozását, kezelését és konvertálását.
### Hol találok további dokumentációt az Aspose.Slides for Java-ról?
 A részletes dokumentáció megtalálható[itt](https://reference.aspose.com/slides/java/).
### Hogyan szerezhetek ideiglenes licencet az Aspose.Slides for Java számára?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Kipróbálhatom ingyenesen az Aspose.Slides for Java programot?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### Hol kaphatok támogatást az Aspose.Slides for Java számára?
 Támogatásért és megbeszélésekért keresse fel a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
