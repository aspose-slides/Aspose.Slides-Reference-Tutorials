---
title: Állítsa be a helyi betűtípus magassági értékeit a PowerPointban Java használatával
linktitle: Állítsa be a helyi betűtípus magassági értékeit a PowerPointban Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthatja be a betűmagasságot a PowerPoint-prezentációkban Java használatával az Aspose.Slides segítségével. Könnyedén javíthatja a szöveg formázását a diákban.
weight: 17
url: /hu/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Ebből az oktatóanyagból megtudhatja, hogyan módosíthatja a betűmagasságot különböző szinteken a PowerPoint-prezentációkban az Aspose.Slides for Java segítségével. A betűméretek szabályozása elengedhetetlen a tetszetős és strukturált prezentációk létrehozásához. Lépésről lépésre bemutatjuk a különböző szövegelemek betűmagasságának beállítását.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
- Java Development Kit (JDK) telepítve a rendszerére
-  Aspose.Slides for Java könyvtár. Letöltheti[itt](https://releases.aspose.com/slides/java/).
- A Java programozás és a PowerPoint prezentációk alapvető ismerete
## Csomagok importálása
Ügyeljen arra, hogy a szükséges Aspose.Slides csomagokat tartalmazza a Java fájl:
```java
import com.aspose.slides.*;
```
## 1. lépés: Inicializáljon egy prezentációs objektumot
Először hozzon létre egy új PowerPoint prezentációs objektumot:
```java
Presentation pres = new Presentation();
```
## 2. lépés: Adjon hozzá egy alakzatot és szövegkeretet
Adjon hozzá egy automatikus alakzatot szövegkerettel az első diához:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## 3. lépés: Szövegrészek létrehozása
Különböző betűmagasságú szövegrészek meghatározása:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## 4. lépés: Állítsa be a betűmagasságot
Betűmagasság beállítása különböző szinteken:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## 5. lépés: Mentse el a prezentációt
Mentse el a módosított prezentációt egy fájlba:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Következtetés
Ez az oktatóanyag bemutatja, hogyan állíthatja be programozottan a betűmagasságot a PowerPoint diákon belül az Aspose.Slides for Java segítségével. A betűméretek különböző szinteken (prezentációszintű, bekezdésben és részben) történő manipulálásával pontos szabályozást érhet el a prezentációk szövegformázása felett.
## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy hatékony API a PowerPoint prezentációk programozott kezeléséhez.
### Hol találom az Aspose.Slides for Java dokumentációját?
 A dokumentációt megtalálod[itt](https://reference.aspose.com/slides/java/).
### Kipróbálhatom az Aspose.Slides for Java programot vásárlás előtt?
 Igen, ingyenes próbaverziót kaphat[itt](https://releases.aspose.com/).
### Hogyan kaphatok támogatást az Aspose.Slides for Java számára?
 Támogatásért keresse fel a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
### Hol vásárolhatok licencet az Aspose.Slides for Java-hoz?
 Vásárolhat licencet[itt](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
