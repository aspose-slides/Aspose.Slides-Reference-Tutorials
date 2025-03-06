---
title: Állítsa be az egyéni felsorolásjelek számát a Java PowerPointban
linktitle: Állítsa be az egyéni felsorolásjelek számát a Java PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be egyéni felsorolásszámokat a Java PowerPointban az Aspose.Slides segítségével, amely programozottan javítja a prezentáció tisztaságát és szerkezetét.
weight: 15
url: /hu/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be az egyéni felsorolásjelek számát a Java PowerPointban

## Bevezetés
A mai digitális korban a dinamikus prezentációk készítése kulcsfontosságú az ötletek és adatok hatékony kommunikálásához. Az Aspose.Slides for Java hatékony eszközkészletet biztosít a PowerPoint-prezentációk programozott kezeléséhez, és kiterjedt funkciókat kínál a prezentáció-készítési folyamat javítására. Ez a cikk az egyéni felsorolásszámok beállításával foglalkozik Java PowerPoint prezentációkban az Aspose.Slides használatával. Akár tapasztalt fejlesztő, akár újonc, ez az oktatóanyag lépésről lépésre végigvezeti Önt a folyamaton, és biztosítja, hogy hatékonyan tudja kihasználni ezt a képességet.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket beállította fejlesztői környezetében:
- Java Development Kit (JDK) telepítve
- Integrált fejlesztési környezet (IDE), például az IntelliJ IDEA vagy az Eclipse
-  Aspose.Slides for Java könyvtár. Letöltheti innen[itt](https://releases.aspose.com/slides/java/)
- A Java programozási nyelv és az objektumorientált fogalmak alapvető ismerete

## Csomagok importálása
Először is importálja a szükséges Aspose.Slides osztályokat és egyéb Java szabványkönyvtárakat:
```java
import com.aspose.slides.*;
```
## 1. lépés: Hozzon létre egy prezentációs objektumot
Kezdje új PowerPoint-prezentáció létrehozásával az Aspose.Slides segítségével.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## 2. lépés: Adjon hozzá egy automatikus alakzatot szöveggel
Szúrjon be egy automatikus alakzatot (téglalapot) a diára, és nyissa meg a szövegkeretet.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## 3. lépés: Távolítsa el az alapértelmezett bekezdést
Távolítsa el az alapértelmezett meglévő bekezdést a szövegkeretből.
```java
textFrame.getParagraphs().removeAt(0);
```
## 4. lépés: Számozott felsorolásjelek hozzáadása
Adjon hozzá bekezdéseket egyedi számozott felsorolásjelekkel, meghatározott számoktól kezdve.
```java
// Példabekezdés 2-től kezdődő felsorolással
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Példabekezdés 3-tól kezdődő felsorolással
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Példabekezdés 7-től kezdődő felsorolással
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## 5. lépés: Mentse el a prezentációt
Végül mentse a módosított prezentációt a kívánt helyre.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Következtetés
Összefoglalva, az Aspose.Slides for Java leegyszerűsíti az egyéni felsorolásszámok programozott beállítását a PowerPoint-prezentációkban. Az oktatóanyagban ismertetett lépések követésével hatékonyan javíthatja prezentációinak vizuális tisztaságát és szerkezetét.
## GYIK
### Tovább szabhatom a golyók megjelenését?
Igen, az Aspose.Slides kiterjedt lehetőségeket kínál a golyók típusának, méretének, színének és egyebek testreszabásához.
### Az Aspose.Slides kompatibilis a PowerPoint összes verziójával?
Az Aspose.Slides támogatja a PowerPoint formátumokat 97-2003-tól a legújabb verziókig.
### Hogyan kaphatok technikai támogatást az Aspose.Slides-hez?
 Látogatás[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11) technikai segítségért.
### Kipróbálhatom az Aspose.Slides-t vásárlás előtt?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### Hol vásárolhatok Aspose.Slides-t?
 Az Aspose.Slides-t itt vásárolhatja meg[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
