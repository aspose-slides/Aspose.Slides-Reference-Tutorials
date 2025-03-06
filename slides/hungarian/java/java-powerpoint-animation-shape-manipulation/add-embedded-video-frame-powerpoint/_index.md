---
title: Adjon hozzá beágyazott videokeretet a PowerPointban
linktitle: Adjon hozzá beágyazott videokeretet a PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ebből a lépésről lépésre mutató oktatóanyagból megtudhatja, hogyan ágyazhat be videokockákat a PowerPointba az Aspose.Slides for Java segítségével. Egyszerűen javíthatja prezentációit.
weight: 21
url: /hu/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Ha videókat ad hozzá PowerPoint-prezentációihoz, vonzóbbá és informatívabbá teheti azokat. Az Aspose.Slides for Java használatával egyszerűen beágyazhat videókat közvetlenül a diákba. Ebben az oktatóanyagban lépésről lépésre végigvezetjük a folyamaton, biztosítva, hogy megértse a kód minden részét és működését. Akár tapasztalt fejlesztő vagy, akár csak kezdő, ez az útmutató segít a prezentációk tökéletesítésében beágyazott videókkal.
## Előfeltételek
Mielőtt belemerülne a kódba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a gépen.
2. Aspose.Slides for Java: Töltse le és telepítse az Aspose.Slides for Java könyvtárat.
3. Integrált fejlesztői környezet (IDE): A jobb fejlesztési élmény érdekében használjon olyan IDE-t, mint az IntelliJ IDEA vagy az Eclipse.
4. Videofájl: rendelkezzen egy videofájllal, amelyet be szeretne ágyazni a PowerPoint-bemutatóba.
## Csomagok importálása
Először is importálnia kell a szükséges csomagokat az Aspose.Slides használatához. Ezek az importálások segítenek a diák, a videók és a prezentációs fájlok kezelésében.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## 1. lépés: Állítsa be környezetét
A kódolás megkezdése előtt győződjön meg arról, hogy a környezet megfelelően van beállítva. Ez magában foglalja a szükséges könyvtárak létrehozását és a videofájl előkészítését.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Hozzon létre könyvtárat, ha még nincs jelen.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## 2. lépés: Példányos bemutató osztály
 Hozzon létre egy példányt a`Presentation` osztály. Ez az osztály a PowerPoint-fájlt képviseli.
```java
// Példányos bemutató osztály, amely a PPTX-et képviseli
Presentation pres = new Presentation();
```
## 3. lépés: Szerezd meg az első diát
Nyissa meg a prezentáció első diáját, amelybe beágyazza a videót.
```java
// Szerezd meg az első diát
ISlide sld = pres.getSlides().get_Item(0);
```
## 4. lépés: Adja hozzá a videót a bemutatóhoz
A videofájl beágyazása a prezentációba. Győződjön meg arról, hogy a videó elérési útja megfelelően van megadva.
```java
// Videó beágyazása a prezentációba
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## 5. lépés: Adjon hozzá videokeretet a diához
Hozzon létre egy videokockát a dián, és állítsa be a méreteit és helyzetét.
```java
// Videókeret hozzáadása
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## 6. lépés: Állítsa be a videokeret tulajdonságait
Állítsa a videót a videokockára, és konfigurálja a lejátszási beállításokat, például a lejátszási módot és a hangerőt.
```java
// Állítsa be a videót Video Frame-re
vf.setEmbeddedVideo(vid);
// Állítsa be a videó lejátszási módját és hangerejét
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## 7. lépés: Mentse el a bemutatót
Mentse a prezentációt a beágyazott videóval a megadott könyvtárba.
```java
// Írja ki a PPTX fájlt a lemezre
pres.save(resultPath, SaveFormat.Pptx);
```
## 8. lépés: Tisztítsa meg az erőforrásokat
Végül dobja el a prezentációs objektumot, hogy erőforrásokat szabadítson fel.
```java
// Dobja el a bemutató objektumot
if (pres != null) pres.dispose();
```
## Következtetés
A videó beágyazása a PowerPoint-prezentációkba az Aspose.Slides for Java használatával egyszerű folyamat. Az ebben az útmutatóban ismertetett lépések követésével lenyűgöző videótartalommal javíthatja bemutatóit. Ne feledje, a gyakorlás teszi a mestert, ezért próbáljon meg különböző videókat beágyazni, és módosítsa a tulajdonságaikat, hogy megtudja, mi a legmegfelelőbb az Ön igényeinek.
## GYIK
### Beágyazhatok több videót egyetlen diába?
Igen, több videót is beágyazhat egyetlen diába, ha több videókockát ad hozzá.
### Hogyan szabályozhatom a videó lejátszását?
 A lejátszást a gombbal vezérelheti`setPlayMode` és`setVolume` módszerei a`IVideoFrame` osztály.
### Milyen videóformátumokat támogat az Aspose.Slides?
Az Aspose.Slides különféle videoformátumokat támogat, beleértve az MP4-et, az AVI-t és a WMV-t.
### Szükségem van engedélyre az Aspose.Slides használatához?
Igen, az Aspose.Slides használatához érvényes licenc szükséges. Az értékeléshez ideiglenes engedélyt kaphat.
### Testreszabhatom a videókockák méretét és helyzetét?
Igen, a videokocka hozzáadásakor a megfelelő paraméterek beállításával testreszabhatja a méretet és a pozíciót.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
