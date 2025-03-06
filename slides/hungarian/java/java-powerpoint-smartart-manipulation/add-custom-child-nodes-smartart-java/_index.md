---
title: Adjon hozzá egyéni gyermekcsomópontokat a SmartArthoz Java használatával
linktitle: Adjon hozzá egyéni gyermekcsomópontokat a SmartArthoz Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá egyéni gyermekcsomópontokat a SmartArthoz a PowerPoint-prezentációkban Java és Aspose.Slides használatával. Fokozza könnyedén diákjait professzionális grafikával.
weight: 11
url: /hu/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
A SmartArt a PowerPoint hatékony funkciója, amely lehetővé teszi a felhasználók számára, hogy gyorsan és egyszerűen készítsenek professzionális megjelenésű grafikákat. Ebben az oktatóanyagban megtanuljuk, hogyan adhatunk egyéni gyermekcsomópontokat a SmartArthoz Java és Aspose.Slides használatával.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszeren.
2.  Aspose.Slides for Java: Töltse le és telepítse az Aspose.Slides for Java-t innen[itt](https://releases.aspose.com/slides/java/).

## Csomagok importálása
kezdéshez importálja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.slides.*;
```
## 1. lépés: Töltse be a prezentációt
Töltse be azt a PowerPoint-prezentációt, ahol egyéni gyermekcsomópontokat szeretne hozzáadni a SmartArthoz:
```java
String dataDir = "Your Document Directory";
// Töltse be a kívánt prezentációt
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## 2. lépés: Adja hozzá a SmartArt elemet a diához
Most adjuk hozzá a SmartArt-ot a diához:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## 3. lépés: Mozgassa a SmartArt alakzatot
Helyezze át a SmartArt alakzatot egy új pozícióba:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## 4. lépés: Változtassa meg az alakzat szélességét
Módosítsa a SmartArt alakzat szélességét:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## 5. lépés: Változtassa meg az alakzat magasságát
A SmartArt alakzat magasságának módosítása:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## 6. lépés: Forgassa el az alakzatot
A SmartArt alakzat elforgatása:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## 7. lépés: Mentse el a bemutatót
Végül mentse el a módosított prezentációt:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan adhatunk egyéni gyermekcsomópontokat a SmartArthoz Java és Aspose.Slides használatával. Ha követi ezeket a lépéseket, testreszabott grafikákkal javíthatja prezentációit, ezáltal vonzóbbá és professzionálisabbá teheti azokat.
## GYIK
### Hozzáadhatok különböző típusú SmartArt-elrendezéseket az Aspose.Slides for Java használatával?
Igen, az Aspose.Slides for Java különféle SmartArt-elrendezéseket támogat, így kiválaszthatja azt, amelyik a legjobban megfelel prezentációs igényeinek.
### Az Aspose.Slides for Java kompatibilis a PowerPoint különböző verzióival?
Az Aspose.Slides for Java úgy lett kialakítva, hogy zökkenőmentesen működjön együtt a PowerPoint különböző verzióival, így biztosítva a platformok közötti kompatibilitást és konzisztenciát.
### Testreszabhatom a SmartArt alakzatok megjelenését programozottan?
Teljesen! Az Aspose.Slides for Java segítségével programozottan testreszabhatja a SmartArt-alakzatok megjelenését, méretét, színét és elrendezését a tervezési preferenciáknak megfelelően.
### Az Aspose.Slides for Java dokumentációt és támogatást nyújt?
Igen, az Aspose webhelyén átfogó dokumentációt és hozzáférést találhat a közösségi támogatási fórumokhoz.
### Elérhető az Aspose.Slides for Java próbaverziója?
 Igen, letöltheti az Aspose.Slides for Java ingyenes próbaverzióját a webhelyről, hogy a vásárlás előtt felfedezze annak funkcióit és képességeit.[itt](https://releases.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
