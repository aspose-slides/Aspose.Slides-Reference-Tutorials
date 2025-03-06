---
title: SmartArt gyermekjegyzet miniatűr létrehozása
linktitle: SmartArt gyermekjegyzet miniatűr létrehozása
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre SmartArt gyermekjegyzet-bélyegképeket Java nyelven az Aspose.Slides segítségével, így könnyedén javíthatja PowerPoint-prezentációit.
weight: 15
url: /hu/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan hozhat létre SmartArt gyermekjegyzet-bélyegképeket Java nyelven az Aspose.Slides használatával. Az Aspose.Slides egy hatékony Java API, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak PowerPoint-prezentációkkal, lehetővé téve számukra a diák könnyű létrehozását, módosítását és kezelését.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Aspose.Slides for Java könyvtár letöltve és konfigurálva a projektben. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/slides/java/).

## Csomagok importálása
Ügyeljen arra, hogy importálja a szükséges csomagokat a Java osztályba:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. lépés: Állítsa be projektjét
Győződjön meg arról, hogy be van állítva egy Java-projekt, és be van állítva az Aspose.Slides könyvtárral.
## 2. lépés: Hozzon létre egy prezentációt
 Példányosítsa a`Presentation` osztály, amely a PPTX fájlt képviseli:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## 3. lépés: SmartArt hozzáadása
SmartArt hozzáadása a bemutató diához:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## 4. lépés: Szerezzen be egy csomópont-referenciát
Szerezze meg egy csomópont hivatkozását az indexének használatával:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## 5. lépés: Indexkép letöltése
A SmartArt csomópont bélyegképének lekérése:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## 6. lépés: Mentse el az indexképet
Mentse el az indexképet egy fájlba:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Ismételje meg ezeket a lépéseket minden egyes SmartArt-csomóponthoz, ha szükséges a bemutatóban.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan hozhat létre SmartArt gyermekjegyzet-bélyegképeket Java nyelven az Aspose.Slides használatával. Ezzel a tudással programozottan javíthatja PowerPoint-prezentációit, és könnyedén hozzáadhat látványos elemeket.
## GYIK
### Használhatom az Aspose.Slides-t meglévő PowerPoint-fájlok kezelésére?
Igen, az Aspose.Slides lehetővé teszi a meglévő PowerPoint-fájlok módosítását, beleértve a diák és tartalmuk hozzáadását, eltávolítását vagy szerkesztését.
### Az Aspose.Slides támogatja a diák exportálását különböző fájlformátumokba?
Teljesen! Az Aspose.Slides támogatja a diák exportálását különféle formátumokba, többek között PDF-be, képekbe és HTML-be.
### Az Aspose.Slides alkalmas a vállalati szintű PowerPoint automatizálásra?
Igen, az Aspose.Slides a vállalati szintű PowerPoint automatizálási feladatok hatékony és megbízható kezelésére készült.
### Létrehozhatok összetett SmartArt-diagramokat programozottan az Aspose.Slides segítségével?
Biztosan! Az Aspose.Slides átfogó támogatást nyújt a különböző bonyolultságú SmartArt-diagramok létrehozásához és kezeléséhez.
### Az Aspose.Slides kínál technikai támogatást a fejlesztőknek?
 Igen, az Aspose.Slides dedikált technikai támogatást nyújt a fejlesztőknek a sajátjukon keresztül[fórum](https://forum.aspose.com/c/slides/11) és más csatornákon.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
