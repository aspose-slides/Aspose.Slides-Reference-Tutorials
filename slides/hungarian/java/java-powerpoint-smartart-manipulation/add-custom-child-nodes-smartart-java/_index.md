---
"description": "Tanuld meg, hogyan adhatsz hozzá egyéni gyermekcsomópontokat SmartArt-elemekhez PowerPoint-bemutatókban Java használatával az Aspose.Slides segítségével. Emeld diáidat professzionális grafikákkal könnyedén."
"linktitle": "Egyéni gyermekcsomópontok hozzáadása SmartArt-ban Java használatával"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Egyéni gyermekcsomópontok hozzáadása SmartArt-ban Java használatával"
"url": "/hu/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Egyéni gyermekcsomópontok hozzáadása SmartArt-ban Java használatával

## Bevezetés
A SmartArt egy hatékony funkció a PowerPointban, amely lehetővé teszi a felhasználók számára, hogy professzionális megjelenésű grafikákat készítsenek gyorsan és egyszerűen. Ebben az oktatóanyagban megtanuljuk, hogyan adhatunk hozzá egyéni gyermekcsomópontokat a SmartArthoz Java használatával az Aspose.Slides segítségével.
## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg róla, hogy a következőkkel rendelkezünk:
1. Java fejlesztőkészlet (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszerén.
2. Aspose.Slides Java-hoz: Töltse le és telepítse az Aspose.Slides Java-hoz programot innen: [itt](https://releases.aspose.com/slides/java/).

## Csomagok importálása
Kezdéshez importáld a szükséges csomagokat a Java projektedbe:
```java
import com.aspose.slides.*;
```
## 1. lépés: Töltse be a prezentációt
Töltse be a PowerPoint bemutatót, ahová egyéni gyermekcsomópontokat szeretne hozzáadni a SmartArt-elemhez:
```java
String dataDir = "Your Document Directory";
// Töltse be a kívánt prezentációt
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## 2. lépés: SmartArt hozzáadása diához
Most adjunk hozzá SmartArt-ot a diához:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## 3. lépés: SmartArt alakzat mozgatása
A SmartArt alakzat áthelyezése új helyre:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## 4. lépés: Alakzat szélességének módosítása
A SmartArt alakzat szélességének módosítása:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## 5. lépés: Alakzat magasságának módosítása
A SmartArt alakzat magasságának módosítása:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## 6. lépés: Forgasd el az alakzatot
A SmartArt alakzat elforgatása:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## 7. lépés: Mentse el a prezentációt
Végül mentse el a módosított prezentációt:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan adhatunk hozzá egyéni gyermekcsomópontokat SmartArt-hoz Java használatával az Aspose.Slides segítségével. Ezeket a lépéseket követve testreszabott grafikákkal gazdagíthatjuk prezentációinkat, így azok vonzóbbak és professzionálisabbak lesznek.
## GYIK
### Hozzáadhatok különböző típusú SmartArt elrendezéseket az Aspose.Slides for Java használatával?
Igen, az Aspose.Slides Java-hoz támogatja a különféle SmartArt-elrendezéseket, így kiválaszthatod a prezentációs igényeidnek leginkább megfelelőt.
### Kompatibilis az Aspose.Slides for Java a PowerPoint különböző verzióival?
Az Aspose.Slides for Java úgy lett kialakítva, hogy zökkenőmentesen működjön a PowerPoint különböző verzióival, biztosítva a platformok közötti kompatibilitást és konzisztenciát.
### Testreszabhatom programozottan a SmartArt alakzatok megjelenését?
Abszolút! Az Aspose.Slides Java verziójával programozottan testreszabhatod a SmartArt alakzatok megjelenését, méretét, színét és elrendezését a saját tervezési preferenciáidnak megfelelően.
### Az Aspose.Slides for Java biztosít dokumentációt és támogatást?
Igen, átfogó dokumentációt találsz, és hozzáférhetsz a közösségi támogató fórumokhoz az Aspose weboldalán.
### Van elérhető próbaverzió az Aspose.Slides for Java-hoz?
Igen, letöltheti az Aspose.Slides Java-hoz készült ingyenes próbaverzióját a weboldalról, hogy felfedezhesse a funkcióit és képességeit a vásárlás előtt. [itt](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}