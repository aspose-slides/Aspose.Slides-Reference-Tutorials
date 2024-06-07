---
title: Aspose.Slides – Beágyazott videók hozzáadása a .NET-bemutatókhoz
linktitle: Aspose.Slides – Beágyazott videók hozzáadása a .NET-bemutatókhoz
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Javítsa prezentációit beágyazott videókkal az Aspose.Slides for .NET segítségével. Kövesse lépésenkénti útmutatónkat a zökkenőmentes integráció érdekében.
type: docs
weight: 19
url: /hu/net/image-and-video-manipulation-in-slides/adding-embedded-video-frame/
---
## Bevezetés
A prezentációk dinamikus világában a multimédiás elemek integrálása jelentősen fokozhatja az elköteleződést. Az Aspose.Slides for .NET hatékony megoldást kínál a beágyazott videokockák prezentációs diákjaiba való beépítésére. Ez az oktatóanyag végigvezeti Önt a folyamaton, lebontva az egyes lépéseket a zökkenőmentes élmény érdekében.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következőkkel:
-  Aspose.Slides for .NET Library: Töltse le és telepítse a könyvtárat a[kiadási oldal](https://releases.aspose.com/slides/net/).
- Médiatartalom: Legyen egy videofájlja (pl. "Wildlife.mp4"), amelyet be szeretne ágyazni a prezentációjába.
## Névterek importálása
Kezdje a szükséges névterek importálásával a .NET-projektben:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## 1. lépés: Állítsa be a könyvtárakat
Győződjön meg arról, hogy a projekt rendelkezik a dokumentum- és médiafájlokhoz szükséges könyvtárakkal:
```csharp
string dataDir = "Your Document Directory";
string videoDir = "Your Media Directory";
string resultPath = Path.Combine(dataDir, "VideoFrame_out.pptx");
// Hozzon létre könyvtárat, ha még nincs jelen.
bool IsExists = Directory.Exists(dataDir);
if (!IsExists)
    Directory.CreateDirectory(dataDir);
```
## 2. lépés: Példányos bemutató osztály
Hozzon létre egy példányt a Presentation osztályból a PPTX fájl megjelenítéséhez:
```csharp
using (Presentation pres = new Presentation())
{
    // Szerezd meg az első diát
    ISlide sld = pres.Slides[0];
```
## 3. lépés: Videó beágyazása a prezentáció belsejébe
A következő kóddal ágyazhat be egy videót a bemutatóba:
```csharp
IVideo vid = pres.Videos.AddVideo(new FileStream(videoDir + "Wildlife.mp4", FileMode.Open), LoadingStreamBehavior.ReadStreamAndRelease);
```
## 4. lépés: Videókeret hozzáadása
Most adjon hozzá egy videokockát a diához:
```csharp
IVideoFrame vf = sld.Shapes.AddVideoFrame(50, 150, 300, 350, vid);
```
## 5. lépés: Állítsa be a videó tulajdonságait
Állítsa be a videót a videokockára, és állítsa be a lejátszási módot és a hangerőt:
```csharp
vf.EmbeddedVideo = vid;
vf.PlayMode = VideoPlayModePreset.Auto;
vf.Volume = AudioVolumeMode.Loud;
```
## 6. lépés: Mentse el a bemutatót
Végül mentse a PPTX fájlt a lemezre:
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Ismételje meg ezeket a lépéseket minden olyan videónál, amelyet be szeretne ágyazni a prezentációjába.
## Következtetés
Gratulálunk! Sikeresen hozzáadott egy beágyazott videokeretet prezentációjához az Aspose.Slides for .NET használatával. Ez a dinamikus funkció új magasságokba emelheti prezentációit, és magával ragadhatja közönségét a diákba zökkenőmentesen integrált multimédiás elemekkel.
## GYIK
### Beágyazhatok videókat a prezentáció bármely diájába?
 Igen, az index módosításával bármelyik diát kiválaszthatja`pres.Slides[index]`.
### Mely videóformátumok támogatottak?
Az Aspose.Slides számos videóformátumot támogat, beleértve az MP4-et, az AVI-t és a WMV-t.
### Testreszabhatom a videókockák méretét és helyzetét?
 Teljesen! Állítsa be a paramétereket`AddVideoFrame(x, y, width, height, video)` szükség szerint.
### Van korlátozás a beágyazható videók számának?
A beágyazott videók számát általában a prezentációs szoftver kapacitása korlátozza.
### Hogyan kérhetek további segítséget vagy oszthatok meg tapasztalataimat?
 Meglátogatni a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11) közösségi támogatásra és beszélgetésekre.