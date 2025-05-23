---
"description": "Tanuld meg, hogyan hozhatsz létre méretezési tényezős bélyegképeket Java nyelven az Aspose.Slides for Java segítségével. Könnyen követhető útmutató lépésről lépésre."
"linktitle": "Méretezési tényező bélyegképének létrehozása"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Méretezési tényező bélyegképének létrehozása"
"url": "/hu/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Méretezési tényező bélyegképének létrehozása

## Bevezetés
Ebben az oktatóanyagban végigvezetünk egy méretezési tényező miniatűr létrehozásának folyamatán az Aspose.Slides for Java használatával. Kövesd az alábbi lépésenkénti utasításokat a kívánt eredmény eléréséhez.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételekkel rendelkezik:
- Java fejlesztőkészlet (JDK) telepítve van a rendszerére.
- Az Aspose.Slides Java könyvtár letöltve és beállítva a Java projektedben.
- Java programozási nyelv alapismeretek.

## Csomagok importálása
Először importáld a Java kódodba az Aspose.Slides használatához szükséges csomagokat. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Most pedig bontsuk le a bemutatott példát több lépésre:
## 1. lépés: Állítsa be a dokumentumkönyvtárat
Adja meg a dokumentumkönyvtár elérési útját, ahol a PowerPoint-bemutatófájl található.
```java
String dataDir = "Your Document Directory";
```
Csere `"Your Document Directory"` a tényleges dokumentumkönyvtár elérési útjával.
## 2. lépés: A prezentációs objektum példányosítása
Hozz létre egy példányt a Presentation osztályból a PowerPoint bemutatófájl reprezentálására.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Biztosítsa a cserét `"HelloWorld.pptx"` a PowerPoint-bemutatófájl nevével.
## 3. lépés: Teljes méretű kép létrehozása
Hozzon létre egy teljes méretű képet a kívánt diaról a prezentációból.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Ez a kód a prezentáció első diáján található első alakzat miniatűrképét kéri le.
## 4. lépés: Kép mentése
Mentse el a létrehozott képet PNG formátumban lemezre.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Biztosítsa a cserét `"Scaling Factor Thumbnail_out.png"` a kívánt kimeneti fájlnévvel.

## Következtetés
Összefoglalva, sikeresen létrehoztál egy méretezési tényező miniatűrt az Aspose.Slides for Java használatával. A megadott lépéseket követve könnyedén integrálhatod ezt a funkciót a Java alkalmazásaidba.
## GYIK
### Használhatom az Aspose.Slides-t Java-ban bármilyen Java IDE-vel?
Igen, az Aspose.Slides for Java bármilyen Java integrált fejlesztői környezettel (IDE) használható, például Eclipse-szel, IntelliJ IDEA-val vagy NetBeans-szel.
### Van ingyenes próbaverzió az Aspose.Slides for Java-hoz?
Igen, igénybe veheti az Aspose.Slides ingyenes próbaverzióját Java-hoz a következő címen: [weboldal](https://releases.aspose.com/).
### Hol találok támogatást az Aspose.Slides Java-hoz?
Az Aspose.Slides Java-alapú verziójához támogatást találsz a következő címen: [Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
### Hogyan vásárolhatom meg az Aspose.Slides-t Java-hoz?
Az Aspose.Slides for Java programot a következő címen vásárolhatja meg: [vásárlási oldal](https://purchase.aspose.com/buy).
### Szükségem van ideiglenes licencre az Aspose.Slides Java-ban való használatához?
Igen, ideiglenes jogosítványt szerezhet be a [ideiglenes licencoldal](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}