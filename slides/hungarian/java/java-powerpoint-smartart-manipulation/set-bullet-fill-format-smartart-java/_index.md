---
"description": "Tanuld meg, hogyan állíthatod be a felsorolásjeles kitöltési formátumot SmartArtban Java használatával az Aspose.Slides segítségével. Lépésről lépésre útmutató a hatékony prezentációkezeléshez."
"linktitle": "Felsoroláskitöltés formátumának beállítása SmartArt-ban Java használatával"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Felsoroláskitöltés formátumának beállítása SmartArt-ban Java használatával"
"url": "/hu/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Felsoroláskitöltés formátumának beállítása SmartArt-ban Java használatával

## Bevezetés
A Java programozás területén a prezentációk hatékony kezelése gyakori követelmény, különösen a SmartArt elemek kezelésekor. Az Aspose.Slides Java-hoz egy hatékony eszköz az ilyen feladatokhoz, számos funkciót kínálva a prezentációk programozott kezeléséhez. Ebben az oktatóanyagban lépésről lépésre bemutatjuk a felsorolásjeles kitöltési formátum beállításának folyamatát a SmartArtban Java használatával az Aspose.Slides segítségével.
## Előfeltételek
Mielőtt belekezdenénk ebbe az oktatóanyagba, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:
### Java fejlesztőkészlet (JDK)
Telepítenie kell a JDK-t a rendszerére. Letöltheti innen: [weboldal](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) és kövesse a telepítési utasításokat.
### Aspose.Slides Java-hoz
Töltsd le és telepítsd az Aspose.Slides for Java programot a következő címről: [letöltési link](https://releases.aspose.com/slides/java/)Kövesse az adott operációs rendszer dokumentációjában található telepítési utasításokat.

## Csomagok importálása
Kezdésként importáld a szükséges csomagokat a Java projektedbe:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Bontsuk le a bemutatott példát több lépésre, hogy világosan megértsük, hogyan állíthatjuk be a felsorolásjelek kitöltésének formátumát SmartArt-ban Java használatával az Aspose.Slides segítségével.
## 1. lépés: Prezentációs objektum létrehozása
```java
Presentation presentation = new Presentation();
```
Először is hozzunk létre egy új példányt a Presentation osztályból, amely egy PowerPoint bemutatót reprezentál.
## 2. lépés: SmartArt hozzáadása
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Ezután adjon hozzá egy SmartArt alakzatot a diához. Ez a kódsor inicializálja az új SmartArt alakzatot a megadott méretekkel és elrendezéssel.
## 3. lépés: A SmartArt Node elérése
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Most nyissa meg az első csomópontot (vagy bármelyik kívánt csomópontot) a SmartArt alakzaton belül a tulajdonságainak módosításához.
## 4. lépés: Felsorolásjeles kitöltési formátum beállítása
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Itt ellenőrizzük, hogy a felsorolásjeles kitöltési formátum támogatott-e. Ha igen, betöltünk egy képfájlt, és beállítjuk azt a SmartArt csomópont felsorolásjeles kitöltéseként.
## 5. lépés: Prezentáció mentése
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Végül mentse el a módosított prezentációt egy megadott helyre.

## Következtetés
Gratulálunk! Sikeresen megtanultad, hogyan állíthatod be a felsorolásjeles kitöltési formátumot a SmartArtban Java használatával az Aspose.Slides segítségével. Ez a képesség új lehetőségek tárházát nyitja meg a dinamikus és vizuálisan vonzó prezentációk készítése előtt Java alkalmazásokban.
## GYIK
### Használhatom az Aspose.Slides for Java programot prezentációk készítéséhez a nulláról?
Abszolút! Az Aspose.Slides átfogó API-kat biztosít prezentációk létrehozásához, módosításához és kezeléséhez, teljes egészében kódon keresztül.
### Kompatibilis az Aspose.Slides a PowerPoint különböző verzióival?
Igen, az Aspose.Slides biztosítja a kompatibilitást a Microsoft PowerPoint különböző verzióival, lehetővé téve a zökkenőmentes integrációt a munkafolyamatba.
### Testreszabhatom a SmartArt elemeket a felsorolásjelek kitöltésének formátumán túl is?
Valóban, az Aspose.Slides lehetővé teszi a SmartArt alakzatok minden aspektusának testreszabását, beleértve az elrendezést, a stílust, a tartalmat és egyebeket.
### Van elérhető próbaverzió az Aspose.Slides for Java-hoz?
Igen, az Aspose.Slides funkcióit ingyenes próbaverzióval is felfedezheti. Egyszerűen töltse le innen: [weboldal](https://releases.aspose.com/slides/java/) és kezdje el a felfedezést.
### Hol találok támogatást az Aspose.Slides Java-hoz?
Bármilyen kérdés vagy segítség esetén látogassa meg az Aspose.Slides fórumot a következő címen: [ez a link](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}