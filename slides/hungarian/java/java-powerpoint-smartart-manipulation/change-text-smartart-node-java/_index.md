---
title: Szöveg módosítása a SmartArt-csomóponton Java használatával
linktitle: Szöveg módosítása a SmartArt-csomóponton Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Fedezze fel, hogyan frissítheti a SmartArt csomópont szövegét a PowerPointban Java használatával az Aspose.Slides segítségével, javítva a prezentáció testreszabását.
weight: 22
url: /hu/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
A SmartArt a PowerPointban egy hatékony szolgáltatás a tetszetős diagramok létrehozásához. Az Aspose.Slides for Java átfogó támogatást nyújt a SmartArt elemek programozott kezeléséhez. Ebben az oktatóanyagban végigvezetjük a SmartArt-csomóponton lévő szöveg Java használatával történő módosításának folyamatán.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
- Java Development Kit (JDK) telepítve a rendszerére.
- Aspose.Slides for Java könyvtár letöltve és hivatkozva a Java projektben.
- A Java programozás alapvető ismerete.

## Csomagok importálása
Először importálja a szükséges csomagokat az Aspose.Slides funkció eléréséhez a Java kódon belül.
```java
import com.aspose.slides.*;
```
Bontsuk fel a példát több lépésre:
## 1. lépés: Inicializálja a bemutató objektumot
```java
Presentation presentation = new Presentation();
```
 Hozzon létre egy új példányt a`Presentation` osztályban PowerPoint prezentációval dolgozhat.
## 2. lépés: Adja hozzá a SmartArt elemet a diához
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 Adja hozzá a SmartArt elemet az első diához. Ebben a példában a`BasicCycle` elrendezés.
## 3. lépés: Nyissa meg a SmartArt-csomópontot
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Hivatkozás a SmartArt második gyökércsomópontjára.
## 4. lépés: Állítsa be a szöveget a csomóponton
```java
node.getTextFrame().setText("Second root node");
```
Állítsa be a kiválasztott SmartArt-csomópont szövegét.
## 5. lépés: Mentse a bemutatót
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Mentse el a módosított bemutatót egy megadott helyre.

## Következtetés
Ebben az oktatóanyagban bemutattuk, hogyan lehet szöveget módosítani egy SmartArt csomóponton Java és Aspose.Slides használatával. Ezzel a tudással dinamikusan manipulálhatja a SmartArt-elemeket PowerPoint-prezentációiban, javítva azok vizuális vonzerejét és tisztaságát.
## GYIK
### Módosíthatom a SmartArt elrendezését, miután hozzáadtam a diához?
 Igen, módosíthatja az elrendezést a`SmartArt.setAllNodes(LayoutType)` módszer.
### Az Aspose.Slides kompatibilis a Java 11-gyel?
Igen, az Aspose.Slides for Java kompatibilis a Java 11 és újabb verzióival.
### Testreszabhatom a SmartArt-csomópontok megjelenését programozottan?
Természetesen az Aspose.Slides API segítségével módosíthatja a különféle tulajdonságokat, például a színt, a méretet és a formát.
### Az Aspose.Slides támogat más típusú SmartArt-elrendezéseket?
Igen, az Aspose.Slides a SmartArt-elrendezések széles skáláját támogatja, így kiválaszthatja azt, amelyik a legjobban megfelel prezentációs igényeinek.
### Hol találok további forrásokat és támogatást az Aspose.Slides számára?
 Meglátogathatja a[Aspose.Slides dokumentáció](https://reference.aspose.com/slides/java/) részletes API-referenciákért és oktatóanyagokért. Ezenkívül segítséget kérhet a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11) vagy fontolja meg a vásárlást a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) szakmai támogatásért.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
