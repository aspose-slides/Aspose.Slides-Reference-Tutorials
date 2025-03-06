---
title: Létrehozza a méretezési tényező bélyegképét
linktitle: Létrehozza a méretezési tényező bélyegképét
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre méretezési tényező bélyegképeket Java nyelven az Aspose.Slides for Java használatával. Könnyen követhető útmutató lépésről lépésre.
weight: 12
url: /hu/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Bevezetés
Ebben az oktatóanyagban végigvezetjük a méretezési tényező bélyegképének létrehozásának folyamatán az Aspose.Slides for Java használatával. Kövesse ezeket az utasításokat lépésről lépésre a kívánt eredmény eléréséhez.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java Development Kit (JDK) telepítve a rendszerére.
- Aspose.Slides for Java könyvtár letöltve és beállítva a Java projektben.
- A Java programozási nyelv alapvető ismerete.

## Csomagok importálása
Először is importálja az Aspose.Slides használatához szükséges csomagokat a Java kódban. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Most bontsuk fel a példát több lépésre:
## 1. lépés: Állítsa be a dokumentumkönyvtárat
Határozza meg a dokumentumkönyvtár elérési útját, ahol a PowerPoint bemutatófájl található.
```java
String dataDir = "Your Document Directory";
```
 Cserélje ki`"Your Document Directory"` a tényleges dokumentumkönyvtár elérési útjával.
## 2. lépés: Példányosítsa a prezentációs objektumot
Hozzon létre egy példányt a Prezentáció osztályból a PowerPoint bemutatófájl reprezentálására.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Győződjön meg a cseréről`"HelloWorld.pptx"` a PowerPoint bemutató fájl nevével.
## 3. lépés: Hozzon létre teljes léptékű képet
Készítsen teljes méretű képet a kívánt diáról a prezentációból.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Ez a kód lekéri a bemutató első diáján lévő első alakzat miniatűrjét.
## 4. lépés: Mentse el a képet
Mentse a generált képet a lemezre PNG formátumban.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Győződjön meg a cseréről`"Scaling Factor Thumbnail_out.png"` a kívánt kimeneti fájlnévvel.

## Következtetés
Összefoglalva, sikeresen létrehozott egy méretezési tényező bélyegképet az Aspose.Slides for Java segítségével. A megadott lépések követésével könnyedén integrálhatja ezt a funkciót Java-alkalmazásaiba.
## GYIK
### Használhatom az Aspose.Slides for Java programot bármilyen Java IDE-vel?
Igen, az Aspose.Slides for Java használható bármely Java Integrated Development Environment (IDE) környezettel, például az Eclipse-sel, az IntelliJ IDEA-val vagy a NetBeans-szel.
### Létezik ingyenes próbaverzió az Aspose.Slides for Java számára?
 Igen, igénybe veheti az Aspose.Slides for Java ingyenes próbaverzióját, ha felkeresi a[weboldal](https://releases.aspose.com/).
### Hol találok támogatást az Aspose.Slides for Java számára?
 Az Aspose.Slides for Java támogatását itt találja[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
### Hogyan vásárolhatom meg az Aspose.Slides for Java programot?
 Megvásárolhatja az Aspose.Slides for Java alkalmazást a[vásárlási oldal](https://purchase.aspose.com/buy).
### Szükségem van ideiglenes licencre az Aspose.Slides for Java használatához?
 Igen, ideiglenes engedélyt kaphat a[ideiglenes licenc oldal](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
