---
title: Hangkeretek hozzáadása prezentációs diákhoz az Aspose.Slides segítségével
linktitle: Hangkeretek hozzáadása prezentációs diákhoz az Aspose.Slides segítségével
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Javítsa a prezentációkat az Aspose.Slides for .NET segítségével! Tanuljon meg zökkenőmentesen hangkockákat hozzáadni, és még soha nem vonzza le közönségét.
weight: 14
url: /hu/net/shape-effects-and-manipulation-in-slides/adding-audio-frames/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
A prezentációk dinamikus világában az audioelemek beépítése jelentősen javíthatja a közönség általános élményét. Az Aspose.Slides for .NET lehetővé teszi a fejlesztők számára, hogy zökkenőmentesen integrálják az audio kereteket a prezentációs diákba, új réteget adva hozzá az elköteleződéshez és az interaktivitáshoz. Ez a részletes útmutató végigvezeti az Aspose.Slides for .NET segítségével hangkeretek hozzáadásának folyamatán.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételeket teljesítette:
1.  Aspose.Slides for .NET Library: Töltse le és telepítse az Aspose.Slides for .NET könyvtárat a[letöltési link](https://releases.aspose.com/slides/net/).
2. Fejlesztési környezet: Győződjön meg arról, hogy rendelkezik működő fejlesztői környezettel a .NET-hez, például a Visual Studio-hoz.
3. Dokumentumkönyvtár: Hozzon létre egy könyvtárat, ahol a dokumentumokat tárolja, és jegyezze fel az elérési utat.
## Névterek importálása
Kezdje a .NET-alkalmazásban az Aspose.Slides funkció eléréséhez szükséges névterek importálásával:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## 1. lépés: Prezentáció és dia létrehozása
```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation())
{
    ISlide sld = pres.Slides[0];
    // A dia létrehozásához szükséges kód itt található
}
```
## 2. lépés: Töltse be az audiofájlt
```csharp
FileStream fstr = new FileStream(dataDir + "sampleaudio.wav", FileMode.Open, FileAccess.Read);
```
## 3. lépés: Adjon hozzá audio keretet
```csharp
IAudioFrame audioFrame = sld.Shapes.AddAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## 4. lépés: Állítsa be az audio tulajdonságait
```csharp
audioFrame.PlayAcrossSlides = true;
audioFrame.RewindAudio = true;
audioFrame.PlayMode = AudioPlayModePreset.Auto;
audioFrame.Volume = AudioVolumeMode.Loud;
```
## 5. lépés: Mentse a bemutatót
```csharp
pres.Save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```
Az alábbi lépések követésével sikeresen integrálta a hangkockákat a prezentációjába az Aspose.Slides for .NET segítségével.
## Következtetés
Hangelemek beépítése prezentációiba javítja az általános nézői élményt, dinamikusabbá és vonzóbbá teszi a tartalmat. Az Aspose.Slides for .NET leegyszerűsíti ezt a folyamatot, és lehetővé teszi a fejlesztők számára, hogy néhány sornyi kóddal zökkenőmentesen integrálják a hangkockákat.
## GYIK
### Az Aspose.Slides for .NET kompatibilis a különböző hangformátumokkal?
Az Aspose.Slides for .NET különféle hangformátumokat támogat, beleértve a WAV-ot, MP3-at és egyebeket. A teljes listát a dokumentációban találja.
### Szabályozhatom a hozzáadott hangkeret lejátszási beállításait?
Igen, az Aspose.Slides rugalmasságot biztosít a lejátszási beállítások, például a hangerő, a lejátszási mód és egyebek konfigurálásában.
### Elérhető az Aspose.Slides .NET-hez próbaverziója?
 Igen, felfedezheti az Aspose.Slides for .NET szolgáltatásait a[ingyenes próbaverzió](https://releases.aspose.com/).
### Hol találok támogatást az Aspose.Slides for .NET számára?
 Meglátogatni a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11) segítséget kérni és kapcsolatba lépni a közösséggel.
### Hogyan vásárolhatom meg az Aspose.Slides-t .NET-hez?
 A könyvtárat megvásárolhatja a[Aspose bolt](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
