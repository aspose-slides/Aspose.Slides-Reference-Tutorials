---
title: Bekezdésjelek hozzáadása a PowerPointban Java használatával
linktitle: Bekezdésjelek hozzáadása a PowerPointban Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá bekezdéssorokat a PowerPoint-diákhoz az Aspose.Slides for Java segítségével. Ez az oktatóprogram lépésről lépésre végigvezeti a kódpéldákon.
weight: 15
url: /hu/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Bevezetés
Bekezdésjelek hozzáadása javítja a PowerPoint-prezentációk olvashatóságát és szerkezetét. Az Aspose.Slides for Java robusztus eszközöket biztosít a prezentációk programozott manipulálásához, beleértve a szöveg formázásának lehetőségét különféle felsorolásjelekkel. Ebből az oktatóanyagból megtudhatja, hogyan integrálhat pontokat PowerPoint diákba Java kóddal, az Aspose.Slides segítségével.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
- Java programozási alapismeretek.
- JDK (Java Development Kit) telepítve van a rendszerére.
-  Aspose.Slides for Java könyvtár. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## Csomagok importálása
A kezdéshez importálja a szükséges Aspose.Slides csomagokat a Java projektbe:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 1. lépés: Állítsa be projektjét
Először hozzon létre egy új Java-projektet, és adja hozzá az Aspose.Slides for Java könyvtárat a projekt összeállítási útvonalához.
## 2. lépés: Inicializáljon egy prezentációt
Egy prezentációs objektum inicializálása (`Presentation`) a diákkal való munka megkezdéséhez.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Prezentációs példány létrehozása
Presentation pres = new Presentation();
```
## 3. lépés: Nyissa meg a Dia és a szövegkeretet
Nyissa meg a csúszdát (`ISlide`és szövegkerete (`ITextFrame`), ahol golyókat szeretne hozzáadni.
```java
// Az első dia elérése
ISlide slide = pres.getSlides().get_Item(0);
// Autoshape hozzáadása és elérése
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// A létrehozott automatikus alakzat szövegkeretének elérése
ITextFrame txtFrm = aShp.getTextFrame();
```
## 4. lépés: Bekezdések létrehozása és formázása felsorolásjelekkel
Bekezdések létrehozása (`Paragraph`), és állítsa be a felsorolásjelek stílusát, behúzását és szövegét.
```java
// Bekezdés létrehozása
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Újabb bekezdés létrehozása
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## 5. lépés: Mentse el a prezentációt
Mentse el a módosított bemutatót egy PowerPoint fájlba (`PPTX`).
```java
// A prezentáció megírása PPTX fájlként
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## 6. lépés: Tisztítsa meg az erőforrásokat
Az erőforrások felszabadításához dobja el a bemutató objektumot.
```java
// Dobja el a bemutató objektumot
if (pres != null) {
    pres.dispose();
}
```

## Következtetés
Bekezdésjelek hozzáadása a PowerPointban az Aspose.Slides for Java használatával egyszerű a mellékelt kódpéldák segítségével. A felsorolásjel-stílusokat és a formázást zökkenőmentesen testreszabhatja prezentációs igényeinek megfelelően.

## GYIK
### Testreszabhatom a felsorolás színeit?
Igen, az Aspose.Slides API segítségével beállíthat egyéni színeket a felsorolásokhoz.
### Hogyan adhatok hozzá beágyazott felsorolásokat?
A felsorolásjelek beágyazása azt jelenti, hogy bekezdéseket adunk hozzá a bekezdésekhez, és ennek megfelelően módosítjuk a behúzást.
### Létrehozhatok különböző golyóstílusokat a különböző diákhoz?
Igen, programozottan alkalmazhat egyedi felsorolásjel-stílusokat a különböző diákra.
### Az Aspose.Slides kompatibilis a Java 11-gyel?
Igen, az Aspose.Slides támogatja a Java 11 és újabb verzióit.
### Hol találok további példákat és dokumentációt?
 Látogatás[Aspose.Slides a Java dokumentációhoz](https://reference.aspose.com/slides/java/) átfogó útmutatókért és példákért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
