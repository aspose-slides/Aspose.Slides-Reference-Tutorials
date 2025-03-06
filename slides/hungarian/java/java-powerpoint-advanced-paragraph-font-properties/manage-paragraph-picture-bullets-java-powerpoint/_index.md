---
title: Bekezdéskép-felsorolások kezelése Java PowerPointban
linktitle: Bekezdéskép-felsorolások kezelése Java PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat egyéni képsorokat a PowerPoint diákhoz az Aspose.Slides for Java segítségével. Kövesse ezt a részletes, lépésenkénti útmutatót a zökkenőmentes integráció érdekében.
type: docs
weight: 11
url: /hu/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---
## Bevezetés
vonzó és tetszetős prezentációk készítése a modern üzleti világban kulcsfontosságú készség. A Java fejlesztők kihasználhatják az Aspose.Slides-t, hogy a PowerPoint diák testreszabott képsoraival javítsák prezentációikat. Ez az oktatóanyag lépésről lépésre végigvezeti a folyamaton, biztosítva, hogy magabiztosan adhasson képjeleket prezentációihoz.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
- Java Development Kit (JDK) telepítve
- Integrált fejlesztői környezet (IDE), például az Eclipse vagy az IntelliJ IDEA
- Aspose.Slides for Java könyvtár
- Java programozási alapismeretek
- Képfájl a golyós képhez
 Az Aspose.Slides for Java könyvtár letöltéséhez látogassa meg a[letöltési oldal](https://releases.aspose.com/slides/java/) . A dokumentációhoz ellenőrizze a[dokumentáció](https://reference.aspose.com/slides/java/).
## Csomagok importálása
Először győződjön meg arról, hogy importálta a projekthez szükséges csomagokat. Adja hozzá a következő importálásokat a Java fájl elejéhez:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Bontsuk fel a folyamatot kezelhető lépésekre.
## 1. lépés: Állítsa be projektkönyvtárát
Hozzon létre egy új könyvtárat a projekthez. Ez a könyvtár tartalmazza a Java fájlt, az Aspose.Slides könyvtárat és a felsorolás képfájlját.
```java
String dataDir = "Your Document Directory";
```
## 2. lépés: Inicializálja a prezentációt
 Inicializálja a`Presentation` osztály. Ez az objektum képviseli a PowerPoint bemutatót.
```java
Presentation presentation = new Presentation();
```
## 3. lépés: Nyissa meg az első diát
Nyissa meg a prezentáció első diáját. A diák nulla indexeltek, így az első dia 0 indexű.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## 4. lépés: Töltse be a Bullet képet
Töltse be a golyókhoz használni kívánt képet. Ezt a képet el kell helyezni a projektkönyvtárba.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## 5. lépés: Adjon hozzá egy AutoShape-ot a diához
Adjon hozzá egy AutoShape-ot a diához. Az alakzat tartalmazza a szöveget az egyéni felsoroláspontokkal.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## 6. lépés: Nyissa meg a szövegkeretet
Hozzáférés az AutoShape szövegkeretéhez a bekezdések kezeléséhez.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## 7. lépés: Távolítsa el az alapértelmezett bekezdést
Távolítsa el az alapértelmezett bekezdést, amely automatikusan hozzáadódik a szövegkerethez.
```java
textFrame.getParagraphs().removeAt(0);
```
## 8. lépés: Hozzon létre egy új bekezdést
Hozzon létre egy új bekezdést, és állítsa be a szövegét. Ez a bekezdés tartalmazza az egyéni képjeleket.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## 9. lépés: Állítsa be a felsorolás stílusát és képét
Állítsa be a felsorolásjel stílusát a korábban betöltött egyéni kép használatához.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## 10. lépés: Állítsa be a golyó magasságát
Állítsa be a golyó magasságát, hogy biztosan jól nézzen ki a prezentációban.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## 11. lépés: Adja hozzá a bekezdést a szövegkerethez
Adja hozzá az újonnan létrehozott bekezdést az AutoShape szövegkeretéhez.
```java
textFrame.getParagraphs().add(paragraph);
```
## 12. lépés: Mentse el a prezentációt
Végül mentse a prezentációt PPTX és PPT fájlként is.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Következtetés
 És megvan! Ha követi ezeket a lépéseket, az Aspose.Slides for Java segítségével egyszerűen hozzáadhat egyéni képsorokat PowerPoint-prezentációihoz. Ez a nagy teljesítményű könyvtár a funkciók széles skáláját kínálja, amelyek segítségével professzionális és tetszetős prezentációkat hozhat létre. Ne felejtse el felfedezni a[dokumentáció](https://reference.aspose.com/slides/java/)fejlettebb funkciókért és testreszabási lehetőségekért.
## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi a Java fejlesztők számára PowerPoint prezentációk programozott létrehozását, módosítását és kezelését.
### Használhatok bármilyen képet a képgolyókhoz?
Igen, bármilyen képet használhat a képsorokhoz, amennyiben az elérhető a projektkönyvtárból.
### Szükségem van licencre az Aspose.Slides for Java használatához?
 Az Aspose.Slides for Java teljes funkcióihoz licenc szükséges. Ideiglenes jogosítványt szerezhet be[itt](https://purchase.aspose.com/temporary-license/) vagy vásároljon teljes licencet[itt](https://purchase.aspose.com/buy).
### Hozzáadhatok több bekezdést különböző listajelstílusokkal egyetlen AutoShape-ban?
Igen, több bekezdést is hozzáadhat különböző listajelstílusokkal egyetlen AutoShape-hoz, ha minden bekezdést külön-külön hoz létre és konfigurál.
### Hol találhatok további példákat és támogatást?
 További példákat találhat a[dokumentáció](https://reference.aspose.com/slides/java/) és támogatást kaphat az Aspose közösségtől[fórumok](https://forum.aspose.com/c/slides/11).