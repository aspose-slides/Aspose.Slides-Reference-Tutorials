---
title: Diagramelrendezési típus rendezése SmartArtban Java használatával
linktitle: Diagramelrendezési típus rendezése SmartArtban Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Sajátítsa el a diagramelrendezési típusok rendszerezését a SmartArt programban Java segítségével az Aspose.Slides-szel, így könnyedén javíthatja a prezentáció látványvilágát.
weight: 13
url: /hu/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Bevezetés
Ebben az oktatóanyagban végigvezetjük a diagramelrendezési típusok megszervezésének folyamatát a SmartArt programban Java használatával, különösen az Aspose.Slides könyvtár kihasználásával. A prezentációkban található SmartArt nagymértékben javíthatja az adatok vizuális vonzerejét és tisztaságát, így elengedhetetlen a manipuláció uralása.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1. Java Development Kit (JDK) telepítve a rendszerére.
2.  Az Aspose.Slides könyvtár letöltve és beállítva. Ha még nem tette meg, töltse le innen[itt](https://releases.aspose.com/slides/java/).
3. A Java programozás alapvető ismerete.

## Csomagok importálása
Először is importálja a szükséges csomagokat:
```java
import com.aspose.slides.*;
```
Bontsuk fel a példát több lépésre:
## 1. lépés: Inicializálja a bemutató objektumot
```java
Presentation presentation = new Presentation();
```
Hozzon létre egy új prezentációs objektumot.
## 2. lépés: Adja hozzá a SmartArt elemet a diához
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Adja hozzá a SmartArt elemet a kívánt diához meghatározott méretekkel és elrendezéstípussal.
## 3. lépés: Állítsa be a szervezeti diagram elrendezését
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Állítsa be a szervezeti diagram elrendezési típusát. Ebben a példában a Balra függő elrendezést használjuk.
## 4. lépés: Mentse a bemutatót
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Mentse el a prezentációt a szervezett diagramelrendezéssel.

## Következtetés
diagramelrendezési típusok SmartArt programban a Java használatával való elsajátítása lehetővé teszi, hogy vizuálisan vonzó prezentációkat készítsen egyszerűen. Az Aspose.Slides segítségével a folyamat leegyszerűsödik és hatékony, így Ön a hatásos tartalom elkészítésére összpontosíthat.
## GYIK
### Az Aspose.Slides kompatibilis a különböző Java fejlesztői környezetekkel?
Igen, az Aspose.Slides kompatibilis a különböző Java fejlesztői környezetekkel, rugalmasságot biztosítva a fejlesztők számára.
### Testreszabhatom a SmartArt elemek megjelenését az Aspose.Slides segítségével?
Természetesen az Aspose.Slides kiterjedt testreszabási lehetőségeket kínál a SmartArt-elemekhez, lehetővé téve számukra, hogy azokat az Ön igényeihez igazítsák.
### Az Aspose.Slides átfogó dokumentációt kínál a fejlesztők számára?
Igen, a fejlesztők elolvashatják az Aspose.Slides for Java részletes dokumentációját, amely betekintést nyújt annak funkcióiba és használatába.
### Elérhető az Aspose.Slides próbaverziója?
Igen, hozzáférhet az Aspose.Slides ingyenes próbaverziójához, hogy a vásárlási döntés meghozatala előtt felfedezze annak funkcióit.
### Hol kérhetek támogatást az Aspose.Slides-hez kapcsolódó lekérdezésekhez?
 Az Aspose.Slides-szal kapcsolatos segítségért vagy kérdésért keresse fel a támogatási fórumot[itt](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
