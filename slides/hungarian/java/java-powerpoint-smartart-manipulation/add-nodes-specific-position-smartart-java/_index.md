---
"description": "Ismerd meg, hogyan adhatsz hozzá csomópontokat adott pozíciókhoz a SmartArt-ban Java használatával az Aspose.Slides segítségével. Készíts dinamikus prezentációkat könnyedén."
"linktitle": "Csomópontok hozzáadása adott pozícióban SmartArt-ban Java használatával"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Csomópontok hozzáadása adott pozícióban SmartArt-ban Java használatával"
"url": "/hu/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Csomópontok hozzáadása adott pozícióban SmartArt-ban Java használatával

## Bevezetés
Ebben az oktatóanyagban végigvezetünk azon, hogyan adhatsz hozzá csomópontokat adott pozíciókhoz a SmartArtban Java használatával az Aspose.Slides segítségével. A SmartArt egy PowerPoint funkció, amely lehetővé teszi vizuálisan vonzó diagramok és táblázatok létrehozását.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:
1. Java fejlesztőkészlet (JDK) telepítve van a rendszerére.
2. Aspose.Slides Java könyvtárhoz letöltve. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).
3. Java programozási nyelv alapismerete.

## Csomagok importálása
Először importáljuk a szükséges csomagokat a Java kódunkba:
```java
import com.aspose.slides.*;
import java.io.File;
```
## 1. lépés: Prezentációs példány létrehozása
Kezdjük a Presentation osztály egy példányának létrehozásával:
```java
Presentation pres = new Presentation();
```
## 2. lépés: A prezentációs diához való hozzáférés
Nyissa meg azt a diát, amelyhez hozzá szeretné adni a SmartArt-elemet:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 3. lépés: SmartArt alakzat hozzáadása
SmartArt alakzat hozzáadása a diához:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## 4. lépés: A SmartArt Node elérése
Nyissa meg a SmartArt csomópontot a kívánt indexben:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## 5. lépés: Gyermekcsomópont hozzáadása adott pozícióban
Új gyermekcsomópont hozzáadása a szülőcsomópont egy adott pozíciójához:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## 6. lépés: Szöveg hozzáadása a csomóponthoz
Állítsa be az újonnan hozzáadott csomópont szövegét:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## 7. lépés: Mentse el a prezentációt
Mentse el a módosított prezentációt:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Következtetés
Ebben az oktatóanyagban megtanultad, hogyan adhatsz hozzá csomópontokat adott pozíciókhoz a SmartArt-ban Java használatával az Aspose.Slides segítségével. Ezeket a lépéseket követve programozottan manipulálhatod a SmartArt alakzatokat dinamikus bemutatók létrehozásához.
## GYIK
### Hozzáadhatok egyszerre több csomópontot?
Igen, programozottan több csomópontot is hozzáadhatsz a kívánt pozíciókon való iterációval.
### Az Aspose.Slides kompatibilis a PowerPoint összes verziójával?
Az Aspose.Slides számos PowerPoint formátumot támogat, így a legtöbb verzióval kompatibilis.
### Testreszabhatom a SmartArt-csomópontok megjelenését?
Igen, testreszabhatja a csomópontok megjelenését, beleértve a méretüket, színüket és stílusukat.
### Az Aspose.Slides támogat más programozási nyelveket is?
Igen, az Aspose.Slides több programozási nyelvhez biztosít könyvtárakat, beleértve a .NET-et és a Pythont is.
### Van elérhető próbaverzió az Aspose.Slides-hoz?
Igen, letölthet egy ingyenes próbaverziót innen [itt](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}