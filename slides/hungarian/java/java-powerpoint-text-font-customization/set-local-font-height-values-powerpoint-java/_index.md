---
"description": "Tanuld meg, hogyan állíthatod be a betűmagasságot PowerPoint-bemutatókban Java használatával az Aspose.Slides segítségével. Könnyedén formázhatod a diákat."
"linktitle": "Helyi betűmagasság-értékek beállítása PowerPointban Java használatával"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Helyi betűmagasság-értékek beállítása PowerPointban Java használatával"
"url": "/hu/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Helyi betűmagasság-értékek beállítása PowerPointban Java használatával

## Bevezetés
Ebben az oktatóanyagban megtanulod, hogyan módosíthatod a betűmagasságokat PowerPoint-bemutatókon belül a különböző szinteken az Aspose.Slides for Java segítségével. A betűméretek szabályozása kulcsfontosságú a vizuálisan vonzó és strukturált prezentációk létrehozásához. Lépésről lépésre bemutatjuk, hogyan állíthatod be a betűmagasságot a különböző szövegelemekhez.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:
- Java fejlesztőkészlet (JDK) telepítve a rendszerére
- Aspose.Slides Java könyvtárhoz. Letöltheted [itt](https://releases.aspose.com/slides/java/).
- Alapfokú ismeretek a Java programozásban és a PowerPoint prezentációkban
## Csomagok importálása
Győződjön meg róla, hogy a Java fájljában szerepelnek a szükséges Aspose.Slides csomagok:
```java
import com.aspose.slides.*;
```
## 1. lépés: Prezentációs objektum inicializálása
Először hozz létre egy új PowerPoint bemutató objektumot:
```java
Presentation pres = new Presentation();
```
## 2. lépés: Alakzat és szövegkeret hozzáadása
Automatikus alakzat hozzáadása szövegkerettel az első diához:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## 3. lépés: Szövegrészek létrehozása
Szövegrészek meghatározása különböző betűmagasságokkal:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## 4. lépés: Betűmagasságok beállítása
Betűmagasságok beállítása különböző szinteken:
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
Ez az oktatóanyag bemutatta, hogyan állíthatja be a betűmagasságot PowerPoint diákon belül programozottan az Aspose.Slides for Java használatával. A betűméretek különböző szinteken (bemutató szintű, bekezdés és szakasz) történő kezelésével precízen szabályozhatja a szöveg formázását a prezentációiban.
## GYIK
### Mi az Aspose.Slides Java-hoz?
Az Aspose.Slides for Java egy hatékony API PowerPoint-bemutatók programozott kezeléséhez.
### Hol találok dokumentációt az Aspose.Slides Java-hoz?
A dokumentációt megtalálod [itt](https://reference.aspose.com/slides/java/).
### Kipróbálhatom az Aspose.Slides-t Java-ban vásárlás előtt?
Igen, kérhetsz ingyenes próbaverziót [itt](https://releases.aspose.com/).
### Hogyan kaphatok támogatást az Aspose.Slides for Java-hoz?
Támogatásért látogassa meg a [Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
### Hol vásárolhatok Aspose.Slides licencet Java-hoz?
Licenc vásárlása lehetséges [itt](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}