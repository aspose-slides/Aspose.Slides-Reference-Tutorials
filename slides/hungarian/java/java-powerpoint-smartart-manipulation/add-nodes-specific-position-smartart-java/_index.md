---
title: Adjon hozzá csomópontokat a SmartArt adott pozíciójához Java használatával
linktitle: Adjon hozzá csomópontokat a SmartArt adott pozíciójához Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Fedezze fel, hogyan adhat hozzá csomópontokat a SmartArt adott pozícióihoz Java és Aspose.Slides segítségével. Hozzon létre dinamikus prezentációkat könnyedén.
weight: 16
url: /hu/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Ebben az oktatóanyagban végigvezetjük a SmartArt adott pozícióihoz csomópontok hozzáadásának folyamatán Java és Aspose.Slides használatával. A SmartArt a PowerPoint egyik funkciója, amely lehetővé teszi tetszetős diagramok és diagramok létrehozását.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Aspose.Slides for Java könyvtár letöltve. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).
3. Java programozási nyelv alapismerete.

## Csomagok importálása
Először is importáljuk a szükséges csomagokat a Java kódunkban:
```java
import com.aspose.slides.*;
import java.io.File;
```
## 1. lépés: Hozzon létre egy bemutatópéldányt
Kezdje a Prezentáció osztály példányának létrehozásával:
```java
Presentation pres = new Presentation();
```
## 2. lépés: Nyissa meg a bemutató diát
Nyissa meg a diát, ahová a SmartArt elemet hozzá szeretné adni:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 3. lépés: SmartArt alakzat hozzáadása
SmartArt alakzat hozzáadása a diához:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## 4. lépés: Nyissa meg a SmartArt-csomópontot
Nyissa meg a SmartArt csomópontot a kívánt indexen:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## 5. lépés: Adjon hozzá gyermekcsomópontot egy adott pozícióhoz
Új gyermekcsomópont hozzáadása a szülőcsomópont egy adott pozíciójához:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## 6. lépés: Szöveg hozzáadása a csomóponthoz
Állítsa be az újonnan hozzáadott csomópont szövegét:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## 7. lépés: Mentse el a bemutatót
Mentse el a módosított prezentációt:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Következtetés
Ebben az oktatóanyagban megtanulta, hogyan adhat hozzá csomópontokat a SmartArt adott pozícióihoz Java és Aspose.Slides használatával. Ha követi ezeket a lépéseket, a SmartArt-alakzatokat programozottan módosíthatja dinamikus bemutatók létrehozásához.
## GYIK
### Hozzáadhatok több csomópontot egyszerre?
Igen, több csomópontot is felvehet programozottan a kívánt pozíciók feletti iterációval.
### Az Aspose.Slides kompatibilis a PowerPoint összes verziójával?
Az Aspose.Slides különféle PowerPoint formátumokat támogat, biztosítva a kompatibilitást a legtöbb verzióval.
### Testreszabhatom a SmartArt csomópontok megjelenését?
Igen, testreszabhatja a csomópontok megjelenését, beleértve a méretüket, színüket és stílusukat.
### Az Aspose.Slides támogat más programozási nyelveket?
Igen, az Aspose.Slides több programozási nyelvhez biztosít könyvtárakat, beleértve a .NET-t és a Python-t is.
### Elérhető az Aspose.Slides próbaverziója?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
