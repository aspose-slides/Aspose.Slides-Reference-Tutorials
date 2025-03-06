---
title: Relatív méretarányú képkeret hozzáadása a PowerPointban
linktitle: Relatív méretarányú képkeret hozzáadása a PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá relatív méretarányú képkereteket PowerPoint-prezentációkhoz az Aspose.Slides for Java segítségével, javítva ezzel a vizuális tartalmat.
weight: 15
url: /hu/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Ebből az oktatóanyagból megtudhatja, hogyan adhat hozzá relatív méretarányú képkeretet a PowerPoint prezentációkhoz az Aspose.Slides for Java segítségével.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
1. Java Development Kit (JDK) telepítve a rendszerére.
2. Aspose.Slides for Java könyvtár letöltve és hozzáadva a Java projekthez.

## Csomagok importálása
Kezdésként importálja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. lépés: Állítsa be projektjét
Először is győződjön meg arról, hogy be van állítva egy könyvtár a projekthez, és a Java környezet megfelelően van konfigurálva.
## 2. lépés: Prezentációs objektum példányosítása
Hozzon létre egy új prezentációs objektumot az Aspose.Slides segítségével:
```java
Presentation presentation = new Presentation();
```
## 3. lépés: Töltse be a hozzáadandó képet
Töltse be a prezentációhoz hozzáadni kívánt képet:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## 4. lépés: Képkeret hozzáadása a diához
Képkeret hozzáadása egy diához a prezentációban:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## 5. lépés: Állítsa be a skála relatív szélességét és magasságát
Állítsa be a képkeret relatív skálaszélességét és magasságát:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## 6. lépés: Mentse a bemutatót
Mentse el a prezentációt a hozzáadott képkerettel:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Következtetés
Ha követi ezeket a lépéseket, az Aspose.Slides for Java segítségével könnyedén hozzáadhat egy relatív méretarányú képkeretet a PowerPoint-prezentációkhoz. Kísérletezzen különböző léptékértékekkel, hogy elérje a képek kívánt megjelenését.

## GYIK
### Hozzáadhatok több képkeretet egyetlen diához ezzel a módszerrel?
Igen, több képkeretet is hozzáadhat egy diához, ha megismétli a folyamatot minden képnél.
### Az Aspose.Slides for Java kompatibilis a PowerPoint összes verziójával?
Az Aspose.Slides for Java kompatibilis a PowerPoint különféle verzióival, rugalmasságot biztosítva a prezentációk létrehozásában.
### Testreszabhatom a képkeret helyzetét és méretét?
 Abszolút beállíthatja a pozíció és a méret paramétereit a`addPictureFrame` igényeinek megfelelő módszert.
### Az Aspose.Slides for Java támogatja a JPEG-en kívül más képformátumokat is?
Igen, az Aspose.Slides for Java különféle képformátumokat támogat, beleértve a PNG-t, GIF-et, BMP-t stb.
### Elérhető közösségi fórum vagy támogatási csatorna az Aspose.Slides felhasználók számára?
Igen, felkeresheti az Aspose.Slides fórumot a könyvtárral kapcsolatos kérdésekért, vitákért vagy segítségért.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
