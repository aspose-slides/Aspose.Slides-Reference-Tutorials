---
"description": "Tanuld meg, hogyan adhatsz hozzá bekezdésjeleket PowerPoint diákhoz az Aspose.Slides for Java használatával. Ez az oktatóanyag lépésről lépésre végigvezet a folyamaton kódpéldákkal."
"linktitle": "Bekezdésjelek hozzáadása PowerPointban Java használatával"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Bekezdésjelek hozzáadása PowerPointban Java használatával"
"url": "/hu/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Bekezdésjelek hozzáadása PowerPointban Java használatával

## Bevezetés
bekezdésjelek hozzáadása javítja a PowerPoint-bemutatók olvashatóságát és szerkezetét. Az Aspose.Slides Java-hoz készült változata robusztus eszközöket biztosít a prezentációk programozott kezeléséhez, beleértve a szöveg különböző felsorolásjelstílusokkal történő formázásának lehetőségét is. Ebben az oktatóanyagban megtanulod, hogyan integrálhatsz felsorolásjeleket a PowerPoint-diákba Java-kód használatával, kihasználva az Aspose.Slides előnyeit.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:
- Java programozási alapismeretek.
- JDK (Java Development Kit) telepítve a rendszeredre.
- Aspose.Slides Java könyvtárhoz. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## Csomagok importálása
A kezdéshez importáld a szükséges Aspose.Slides csomagokat a Java projektedbe:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## 1. lépés: A projekt beállítása
Először hozz létre egy új Java projektet, és add hozzá az Aspose.Slides for Java könyvtárat a projekted építési útvonalához.
## 2. lépés: Prezentáció inicializálása
Prezentációs objektum inicializálása (`Presentation`) a diákkal való munka megkezdéséhez.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Prezentációs példány létrehozása
Presentation pres = new Presentation();
```
## 3. lépés: A dia és a szövegkeret elérése
A dia elérése (`ISlide`) és a szövegkeretét (`ITextFrame`) ahová felsorolásjeleket szeretne hozzáadni.
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
Mentse el a módosított bemutatót egy PowerPoint-fájlba (`PPTX`).
```java
// Prezentáció írása PPTX fájlként
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## 6. lépés: Erőforrások tisztítása
Erőforrások felszabadításához dobja ki a prezentációs objektumot.
```java
// A prezentációs objektum eltávolítása
if (pres != null) {
    pres.dispose();
}
```

## Következtetés
PowerPointban az Aspose.Slides for Java használatával bekezdésjelek hozzáadása egyszerűen elvégezhető a megadott kódpéldák segítségével. A felsorolásjelek stílusát és formázását zökkenőmentesen testreszabhatja a prezentációs igényeinek megfelelően.

## GYIK
### Testreszabhatom a felsorolásjelek színeit?
Igen, az Aspose.Slides API segítségével egyéni színeket állíthatsz be a felsorolásjelekhez.
### Hogyan adhatok hozzá beágyazott felsorolásjeleket?
A felsorolásjelek beágyazása bekezdések bekezdéseken belüli hozzáadását, a behúzás ennek megfelelő beállítását jelenti.
### Létrehozhatok különböző felsorolásjeleket a különböző diákhoz?
Igen, programozottan alkalmazhat egyedi felsorolásjelstílusokat a különböző diákra.
### Az Aspose.Slides kompatibilis a Java 11-gyel?
Igen, az Aspose.Slides támogatja a Java 11-es és újabb verzióit.
### Hol találok további példákat és dokumentációt?
Látogatás [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/) átfogó útmutatókért és példákért.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}