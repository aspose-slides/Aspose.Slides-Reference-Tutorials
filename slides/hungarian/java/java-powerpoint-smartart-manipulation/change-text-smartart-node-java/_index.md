---
"description": "Ismerje meg, hogyan frissítheti a SmartArt-csomópontok szövegét PowerPointban Java használatával az Aspose.Slides segítségével, amivel fokozhatja a prezentációk testreszabását."
"linktitle": "Szöveg módosítása a SmartArt Node-on Java használatával"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Szöveg módosítása a SmartArt Node-on Java használatával"
"url": "/hu/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Szöveg módosítása a SmartArt Node-on Java használatával

## Bevezetés
A PowerPoint SmartArt elemei hatékonyan használhatók vizuálisan vonzó diagramok készítéséhez. Az Aspose.Slides Java-verziója átfogó támogatást nyújt a SmartArt elemek programozott kezeléséhez. Ebben az oktatóanyagban végigvezetjük Önt a SmartArt-csomópontok szövegének Java használatával történő módosításának folyamatán.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:
- Java fejlesztőkészlet (JDK) telepítve van a rendszerére.
- Az Aspose.Slides Java könyvtár le van töltve és hivatkozva a Java projektedben.
- Java programozási alapismeretek.

## Csomagok importálása
Először importáld a szükséges csomagokat az Aspose.Slides funkcióinak eléréséhez a Java-kódodban.
```java
import com.aspose.slides.*;
```
Bontsuk a példát több lépésre:
## 1. lépés: A prezentációs objektum inicializálása
```java
Presentation presentation = new Presentation();
```
Hozzon létre egy új példányt a `Presentation` osztály egy PowerPoint prezentációval dolgozni.
## 2. lépés: SmartArt hozzáadása diához
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
Adjon hozzá SmartArt-ot az első diához. Ebben a példában a következőt használjuk: `BasicCycle` elrendezés.
## 3. lépés: A SmartArt Node elérése
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Hivatkozás lekérése a SmartArt második gyökércsomópontjára.
## 4. lépés: Szöveg beállítása a csomóponton
```java
node.getTextFrame().setText("Second root node");
```
Állítsa be a kijelölt SmartArt-csomópont szövegét.
## 5. lépés: Prezentáció mentése
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Mentse a módosított prezentációt egy megadott helyre.

## Következtetés
Ebben az oktatóanyagban bemutattuk, hogyan módosítható a szöveg egy SmartArt csomóponton Java és Aspose.Slides használatával. Ezzel a tudással dinamikusan manipulálhatja a SmartArt elemeket a PowerPoint-bemutatóiban, javítva azok vizuális vonzerejét és áttekinthetőségét.
## GYIK
### Módosíthatom a SmartArt elrendezését a diához való hozzáadás után?
Igen, a következőhöz férhet hozzá: `SmartArt.setAllNodes(LayoutType)` módszer.
### Az Aspose.Slides kompatibilis a Java 11-gyel?
Igen, az Aspose.Slides for Java kompatibilis a Java 11-es és újabb verzióival.
### Testreszabhatom programozottan a SmartArt-csomópontok megjelenését?
Természetesen az Aspose.Slides API segítségével módosíthatsz különböző tulajdonságokat, például a színt, a méretet és az alakot.
### Az Aspose.Slides támogat más típusú SmartArt elrendezéseket is?
Igen, az Aspose.Slides a SmartArt elrendezések széles skáláját támogatja, így kiválaszthatod a prezentációs igényeidnek leginkább megfelelőt.
### Hol találok további forrásokat és támogatást az Aspose.Slides-hez?
Meglátogathatod a [Aspose.Slides dokumentáció](https://reference.aspose.com/slides/java/) részletes API-referenciákért és oktatóanyagokért. Ezenkívül segítséget kérhet a következőtől: [Aspose.Slides fórum](https://forum.aspose.com/c/slides/11) vagy fontolja meg egy vásárlását [ideiglenes engedély](https://purchase.aspose.com/temporary-license/) szakmai támogatásért.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}