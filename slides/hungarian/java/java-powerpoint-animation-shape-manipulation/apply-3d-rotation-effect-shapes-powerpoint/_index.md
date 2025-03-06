---
title: Alkalmazzon 3D forgatási effektust az alakzatokra a PowerPointban
linktitle: Alkalmazzon 3D forgatási effektust az alakzatokra a PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ezzel az átfogó, lépésenkénti oktatóanyaggal megtudhatja, hogyan alkalmazhat 3D-s forgatási effektusokat alakzatokon a PowerPointban az Aspose.Slides for Java segítségével.
weight: 12
url: /hu/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Készen áll arra, hogy PowerPoint prezentációit a következő szintre emelje? 3D-s forgatási effektusok hozzáadásával a diák dinamikusabbá és vonzóbbá válik. Akár tapasztalt fejlesztő, akár csak most kezdi, ez a lépésről lépésre bemutató oktatóanyag megmutatja, hogyan alkalmazhat 3D-s forgatási effektusokat a PowerPoint alakzataira az Aspose.Slides for Java segítségével. Egyből merüljünk bele!
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy a következők vannak a helyükön:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren. Letöltheti a[Oracle webhely](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Töltse le az Aspose.Slides for Java legújabb verzióját a[letöltési link](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Használjon olyan IDE-t, mint az IntelliJ IDEA vagy az Eclipse a kódoláshoz.
4.  Érvényes jogosítvány: Ha nincs jogosítványa, akkor a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) hogy kipróbálja a funkciókat.
## Csomagok importálása
Először is importáljuk a szükséges csomagokat a Java projektbe. Ezek az importálások segítenek a prezentációk és alakzatok kezelésében az Aspose.Slides segítségével.
```java
import com.aspose.slides.*;

```
## 1. lépés: Állítsa be projektjét
Mielőtt belemerülne a kódba, állítsa be projektkörnyezetét. Győződjön meg arról, hogy hozzáadta az Aspose.Slides for Java programot a projekt függőségeihez.
Az Aspose.Slides hozzáadása projektjéhez:
1.  Töltse le az Aspose.Slides JAR fájlokat a[letöltési oldal](https://releases.aspose.com/slides/java/).
2. Adja hozzá ezeket a JAR fájlokat a projekt felépítési útvonalához.
## 2. lépés: Hozzon létre egy új PowerPoint-bemutatót
Ebben a lépésben egy új PowerPoint bemutatót hozunk létre.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation pres = new Presentation();
```
Ez a kódrészlet inicializál egy új prezentációs objektumot, amelyhez hozzáadjuk az alakzatainkat.
## 3. lépés: Téglalap alakzat hozzáadása
Ezután adjunk hozzá egy téglalap alakzatot az első diához.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Ez a kód egy téglalap alakot ad hozzá az első dián a megadott pozícióhoz és mérethez.
## 4. lépés: Alkalmazza a 3D elforgatást a téglalapra
Most alkalmazzunk egy 3D-s elforgatási effektust a téglalap alakzatra.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Itt beállítjuk a mélységet, a kamera elforgatási szögeit, a kamera típusát és a világítás típusát, hogy téglalapunk 3D-s megjelenést kapjon.
## 5. lépés: Vonalforma hozzáadása
Adjunk hozzá egy másik alakzatot, ezúttal egy vonalat a diához.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Ez a kód vonal alakzatot helyez el a dián.
## 6. lépés: Alkalmazza a 3D elforgatást a vonalra
Végül 3D-s elforgatási effektust alkalmazunk a vonal alakjára.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
A téglalaphoz hasonlóan a vonalalak 3D tulajdonságait állítjuk be.
## 7. lépés: Mentse el a bemutatót
Az alakzatok hozzáadása és konfigurálása után mentse a bemutatót.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Ez a kód elmenti a prezentációt a megadott fájlnévvel a kívánt formátumban.
## Következtetés
 Gratulálunk! Sikeresen alkalmazta a 3D elforgatási effektusokat egy PowerPoint-prezentáció alakzataira az Aspose.Slides for Java segítségével. Ezen lépések követésével tetszetős és dinamikus prezentációkat hozhat létre. A további testreszabás és a fejlettebb funkciók megtekintéséhez tekintse meg a[Aspose.Slides dokumentáció](https://reference.aspose.com/slides/java/).
## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy hatékony API PowerPoint-prezentációk programozott létrehozásához, módosításához és manipulálásához.
### Kipróbálhatom ingyenesen az Aspose.Slides for Java programot?
 Igen, kaphat a[ingyenes próbaverzió](https://releases.aspose.com/) vagy a[ideiglenes engedély](https://purchase.aspose.com/temporary-license/) a funkciók tesztelésére.
### Milyen típusú alakzatokhoz adhatok hozzá 3D effektusokat az Aspose.Slides-ben?
3D effektusokat adhat hozzá különféle alakzatokhoz, például téglalapokhoz, vonalakhoz, ellipszisekhez és egyéni alakzatokhoz.
### Hogyan kaphatok támogatást az Aspose.Slides for Java számára?
 Meglátogathatja a[támogatói fórum](https://forum.aspose.com/c/slides/11) segítségért és bármilyen kérdés megbeszélésére.
### Használhatom az Aspose.Slides for Java programot kereskedelmi projektekben?
 Igen, de licencet kell vásárolnia. Vásárolhat egyet a[vásárlási oldal](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
