---
title: Állítsa be a bekezdés behúzását a Java PowerPointban
linktitle: Állítsa be a bekezdés behúzását a Java PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be bekezdésbehúzásokat a PowerPoint diákon programozottan az Aspose.Slides for Java segítségével. Fokozza a prezentáció formázását könnyedén.
weight: 16
url: /hu/java/java-powerpoint-text-paragraph-management/set-paragraph-indent-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be a bekezdés behúzását a Java PowerPointban

## Bevezetés
Ebből az oktatóanyagból megtudhatja, hogyan kezelheti programozottan a PowerPoint-prezentációkat az Aspose.Slides for Java használatával. Konkrétan a bekezdések behúzásának beállítására fogunk összpontosítani a diákon belül. Az Aspose.Slides for Java hatékony API-készletet biztosít, amely lehetővé teszi a fejlesztők számára PowerPoint-prezentációk létrehozását, módosítását, konvertálását és kezelését anélkül, hogy a Microsoft Office Automationra támaszkodna.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy az alábbiakat beállította:
- Java Development Kit (JDK) telepítve a gépére.
-  Aspose.Slides for Java könyvtár letöltve. től szerezheti be[itt](https://releases.aspose.com/slides/java/).
- A Java programozási nyelv alapvető ismerete.
## Csomagok importálása
Először importálja a szükséges csomagokat az Aspose.Slides funkció eléréséhez:
```java
import com.aspose.slides.*;
import java.io.File;
```
Vessen egy pillantást a bekezdések behúzásának lépésről lépésre történő beállítására egy PowerPoint dián az Aspose.Slides for Java segítségével.
## 1. lépés: Hozzon létre egy prezentációs objektumot
 Példányosítsa a`Presentation` osztályban, hogy elkezdjen dolgozni egy új PowerPoint prezentációval.
```java
// Példányos bemutató osztály
Presentation pres = new Presentation();
```
## 2. lépés: Nyissa meg a diát
A prezentáció első diájának előhívása. Szükség szerint módosíthatja a különböző diákat index alapján.
```java
// Szerezd meg az első diát
ISlide slide = pres.getSlides().get_Item(0);
```
## 3. lépés: Téglalap alakzat hozzáadása
Adjon hozzá egy téglalap alakzatot a diához, amely a szöveget behúzott bekezdésekkel tartalmazza.
```java
// Téglalap alakzat hozzáadása
IAutoShape rect = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 500, 150);
```
## 4. lépés: Szöveg hozzáadása a téglalaphoz
Hozzon létre egy szövegkeretet a téglalap alakzaton belül, és állítsa be a szöveg tartalmát.
```java
// Szövegkeret hozzáadása a téglalaphoz
ITextFrame textFrame = rect.addTextFrame("This is first line \rThis is second line \rThis is third line");
```
## 5. lépés: Állítsa be a szöveg automatikus illeszkedését
Állítsa be a szöveg automatikus illeszkedését úgy, hogy az illeszkedjen az alakzathatárok közé.
```java
// Állítsa be a szöveget az alakzathoz
textFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## 6. lépés: Állítsa be a bekezdés behúzását
Nyissa meg a szövegkereten belüli minden bekezdést, és állítsa be a behúzást.
```java
// Szerezze be az első bekezdést a szövegkeretben, és állítsa be annak behúzását
IParagraph para1 = textFrame.getParagraphs().get_Item(0);
para1.getParagraphFormat().setIndent(30);
// Szerezze be a második bekezdést a szövegkeretbe, és állítsa be annak behúzását
IParagraph para2 = textFrame.getParagraphs().get_Item(1);
para2.getParagraphFormat().setIndent(40);
//Szerezze be a harmadik bekezdést a szövegkeretbe, és állítsa be annak behúzását
IParagraph para3 = textFrame.getParagraphs().get_Item(2);
para3.getParagraphFormat().setIndent(50);
```
## 7. lépés: Mentse el a bemutatót
Végül mentse a módosított prezentációt lemezre.
```java
// Írja ki a prezentációt lemezre
String dataDir = "Your_Document_Directory_Path/";
pres.save(dataDir + "IndentedPresentation.pptx", SaveFormat.Pptx);
```
## Következtetés
Ha követi ezeket a lépéseket, az Aspose.Slides for Java segítségével egyszerűen beállíthat bekezdések behúzásait a PowerPoint dián. Ez a képesség lehetővé teszi a dián belüli szöveg formázásának és megjelenítésének programozott vezérlését.

## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy hatékony könyvtár a PowerPoint prezentációk programozott használatához.
### Hol találom az Aspose.Slides for Java dokumentációját?
 A dokumentációt megtalálod[itt](https://reference.aspose.com/slides/java/).
### Hogyan tölthetem le az Aspose.Slides for Java programot?
 Letöltheti innen[itt](https://releases.aspose.com/slides/java/).
### Létezik ingyenes próbaverzió az Aspose.Slides for Java számára?
 Igen, ingyenes próbaverziót kaphat a webhelyen[itt](https://releases.aspose.com/).
### Hol kaphatok támogatást az Aspose.Slides for Java számára?
 Támogatást kaphat a közösségi fórumon[itt](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
