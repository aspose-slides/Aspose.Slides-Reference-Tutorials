---
title: Határok alakzatának bélyegképének létrehozása
linktitle: Határok alakzatának bélyegképének létrehozása
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre korlátos alakzat-bélyegképeket az Aspose.Slides for Java segítségével. Ez a lépésenkénti oktatóanyag végigvezeti a folyamaton.
weight: 10
url: /hu/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Bevezetés
Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi a Java fejlesztők számára PowerPoint prezentációk programozott létrehozását, kezelését és konvertálását. Ebben az oktatóanyagban megtanuljuk, hogyan hozhat létre bélyegképet egy határokkal rendelkező alakzatról az Aspose.Slides for Java segítségével.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:
1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Aspose.Slides for Java könyvtár letöltve és hozzáadva a projekthez. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## Csomagok importálása
Győződjön meg róla, hogy importálja a szükséges csomagokat a Java kódban:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## 1. lépés: Állítsa be projektjét
Hozzon létre egy új Java-projektet a kívánt IDE-ben, és adja hozzá az Aspose.Slides for Java könyvtárat a projekt függőségeihez.
## 2. lépés: Példányosítson egy prezentációs objektumot
 Példányosítás a`Presentation` objektumot a PowerPoint bemutatófájl elérési útjának megadásával.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## 3. lépés: Határok alakzatának bélyegképének létrehozása
Most hozzunk létre egy bélyegképet egy határokkal rendelkező alakzatról a prezentációból.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan hozhat létre bélyegképet egy határokkal rendelkező alakzatról az Aspose.Slides for Java használatával. Ha követi ezeket a lépéseket, könnyedén generálhat bélyegképeket a PowerPoint-prezentációkban programozottan.
## GYIK
### Létrehozhatok bélyegképeket adott formákhoz egy dián belül?
Igen, az Aspose.Slides for Java segítségével elérheti az egyes alakzatokat egy dián belül, és bélyegképeket hozhat létre hozzájuk.
### Az Aspose.Slides for Java kompatibilis a PowerPoint-fájlok összes verziójával?
Az Aspose.Slides for Java különféle PowerPoint fájlformátumokat támogat, beleértve a PPT-t, PPTX-et, PPS-t, PPSX-et és még sok mást.
### Testreszabhatom a generált miniatűrök megjelenését?
Igen, igénye szerint módosíthatja a miniatűrök tulajdonságait, például méretét és minőségét.
### Az Aspose.Slides for Java támogatja a miniatűrök generálásán kívül más funkciókat is?
Igen, az Aspose.Slides for Java kiterjedt funkcionalitást biztosít a PowerPoint-prezentációkkal való munkavégzéshez, beleértve a diakezelést, a szövegkivonást és a diagramkészítést.
### Elérhető az Aspose.Slides for Java próbaverziója?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
