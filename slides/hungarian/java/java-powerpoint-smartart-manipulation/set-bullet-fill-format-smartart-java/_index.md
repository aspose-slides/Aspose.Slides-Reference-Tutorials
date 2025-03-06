---
title: Állítsa be a felsorolásjel-kitöltés formátumát a SmartArt alkalmazásban Java használatával
linktitle: Állítsa be a felsorolásjel-kitöltés formátumát a SmartArt alkalmazásban Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be felsorolásjel-kitöltési formátumot a SmartArt alkalmazásban Java és Aspose.Slides használatával. Lépésről lépésre útmutató a hatékony prezentációkezeléshez.
weight: 18
url: /hu/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be a felsorolásjel-kitöltés formátumát a SmartArt alkalmazásban Java használatával

## Bevezetés
Java programozás területén a prezentációk hatékony manipulálása általános követelmény, különösen a SmartArt elemek kezelésekor. Az Aspose.Slides for Java hatékony eszköz az ilyen feladatokhoz, és számos funkciót kínál a prezentációk programozott kezeléséhez. Ebben az oktatóanyagban lépésről lépésre bemutatjuk a felsorolásjelek kitöltési formátumának beállítását a SmartArtban Java és Aspose.Slides használatával.
## Előfeltételek
Mielőtt elkezdené ezt az oktatóanyagot, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
### Java fejlesztőkészlet (JDK)
 A JDK-t telepíteni kell a rendszerére. Letöltheti a[weboldal](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) és kövesse a telepítési utasításokat.
### Aspose.Slides a Java számára
 Töltse le és telepítse az Aspose.Slides for Java programot a[letöltési link](https://releases.aspose.com/slides/java/). Kövesse az adott operációs rendszerre vonatkozó dokumentációban található telepítési utasításokat.

## Csomagok importálása
Kezdésként importálja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Bontsuk le a példát több lépésre, hogy világosan megértsük, hogyan lehet beállítani a felsorolásjel-kitöltés formátumát a SmartArtban Java használatával az Aspose.Slides-szel.
## 1. lépés: Prezentációs objektum létrehozása
```java
Presentation presentation = new Presentation();
```
Először is hozzon létre egy új példányt a Prezentáció osztályból, amely egy PowerPoint bemutatót képvisel.
## 2. lépés: SmartArt hozzáadása
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Ezután adjon hozzá egy SmartArt alakzatot a diához. Ez a kódsor egy új SmartArt alakzatot inicializál meghatározott méretekkel és elrendezéssel.
## 3. lépés: Nyissa meg a SmartArt-csomópontot
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Most nyissa meg az első csomópontot (vagy bármely kívánt csomópontot) a SmartArt-alakzaton belül a tulajdonságainak módosításához.
## 4. lépés: Állítsa be a felsorolásjel-kitöltés formátumát
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Itt ellenőrizzük, hogy a felsorolásjel-kitöltés formátum támogatott-e. Ha igen, betöltünk egy képfájlt, és beállítjuk a SmartArt-csomópont felsorolásjel-kitöltéseként.
## 5. lépés: Mentse a bemutatót
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Végül mentse a módosított prezentációt egy megadott helyre.

## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan kell beállítani a felsorolásjel-kitöltés formátumát a SmartArtban Java és Aspose.Slides használatával. Ez a képesség a lehetőségek világát nyitja meg a dinamikus és tetszetős prezentációk számára a Java alkalmazásokban.
## GYIK
### Használhatom az Aspose.Slides for Java programot prezentációk létrehozására a semmiből?
Teljesen! Az Aspose.Slides átfogó API-kat biztosít a prezentációk teljes egészében kódon keresztüli létrehozásához, módosításához és manipulálásához.
### Az Aspose.Slides kompatibilis a PowerPoint különböző verzióival?
Igen, az Aspose.Slides biztosítja a kompatibilitást a Microsoft PowerPoint különféle verzióival, lehetővé téve a zökkenőmentes integrációt a munkafolyamatba.
### Testreszabhatom a SmartArt elemeket a felsorolásjel-kitöltés formátumon túl?
Az Aspose.Slides valóban lehetővé teszi a SmartArt-alakzatok minden aspektusának testreszabását, beleértve az elrendezést, a stílust, a tartalmat és egyebeket.
### Elérhető az Aspose.Slides for Java próbaverziója?
 Igen, az Aspose.Slides szolgáltatásait ingyenes próbaverzióval fedezheti fel. Egyszerűen töltse le a[weboldal](https://releases.aspose.com/slides/java/) és kezdje el felfedezni.
### Hol találok támogatást az Aspose.Slides for Java számára?
 Ha kérdése van, vagy segítségre van szüksége, keresse fel az Aspose.Slides fórumot a címen[ez a link](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
