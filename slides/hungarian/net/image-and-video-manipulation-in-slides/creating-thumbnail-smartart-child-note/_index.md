---
title: Miniatűr létrehozása a SmartArt gyermekjegyzethez az Aspose.Slides programban
linktitle: Miniatűr létrehozása a SmartArt gyermekjegyzethez az Aspose.Slides programban
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre lenyűgöző SmartArt Child Note bélyegképeket az Aspose.Slides for .NET használatával. Emelje fel prezentációit dinamikus látványvilággal!
weight: 15
url: /hu/net/image-and-video-manipulation-in-slides/creating-thumbnail-smartart-child-note/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Miniatűr létrehozása a SmartArt gyermekjegyzethez az Aspose.Slides programban

## Bevezetés
dinamikus prezentációk terén az Aspose.Slides for .NET kiemelkedik hatékony eszközként, amely lehetővé teszi a fejlesztők számára a PowerPoint prezentációk programozott kezelését és fejlesztését. Az egyik érdekes funkció a SmartArt gyermekjegyzetekhez való bélyegképek létrehozásának képessége, amely egy réteg vizuális vonzerőt ad a prezentációkhoz. Ez a részletes útmutató végigvezeti a SmartArt Child Notes miniatűrök létrehozásának folyamatán az Aspose.Slides for .NET használatával.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
-  Aspose.Slides .NET-hez: Győződjön meg arról, hogy az Aspose.Slides könyvtár integrálva van a .NET-projektbe. Ha nem, töltse le a[kiadások oldala](https://releases.aspose.com/slides/net/).
- Fejlesztői környezet: Hozzon létre egy működő .NET fejlesztői környezetet, és rendelkezzen alapvető ismeretekkel a C# programozásról.
- Prezentációs minta: Hozzon létre vagy szerezzen be egy PowerPoint-prezentációt, amely SmartArt elemet tartalmaz alárendelt jegyzetekkel tesztelésre.
## Névterek importálása
Kezdje a szükséges névterek importálásával a C# projektbe. Ezek a névterek hozzáférést biztosítanak az Aspose.Slides használatához szükséges osztályokhoz és metódusokhoz.
```csharp
using System.Drawing;
using System.Drawing.Imaging;
using Aspose.Slides.SmartArt;
using Aspose.Slides;
```
## 1. lépés: Példányos bemutató osztály
 Kezdje a példányosítással`Presentation` osztály, amely azt a PPTX fájlt jelenti, amellyel dolgozni fog.
```csharp
string dataDir = "Your Documents Directory";
Presentation pres = new Presentation();
```
## 2. lépés: SmartArt hozzáadása
 Most adja hozzá a SmartArt-ot egy diához a prezentáción belül. Ebben a példában a`BasicCycle` elrendezés.
```csharp
ISmartArt smart = pres.Slides[0].Shapes.AddSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## 3. lépés: Csomópont-referencia beszerzése
Ha a SmartArt egy adott csomópontjával szeretne dolgozni, szerezze be annak hivatkozását az indexével.
```csharp
ISmartArtNode node = smart.Nodes[1];
```
## 4. lépés: Indexkép letöltése
A SmartArt csomóponton belüli gyermekjegyzet bélyegképének lekérése.
```csharp
Bitmap bmp = node.Shapes[0].GetThumbnail();
```
## 5. lépés: Mentse el az indexképet
Mentse el a létrehozott bélyegképet egy megadott könyvtárba.
```csharp
bmp.Save(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg", ImageFormat.Jpeg);
```
Ismételje meg ezeket a lépéseket a prezentáció minden SmartArt-csomópontjánál, szükség szerint testreszabva az elrendezést és a stílusokat.
## Következtetés
Összefoglalva, az Aspose.Slides for .NET lehetővé teszi a fejlesztők számára, hogy egyszerűen készítsenek lenyűgöző prezentációkat. A SmartArt Child Notes miniatűrök létrehozásának képessége fokozza prezentációinak vizuális vonzerejét, dinamikus és interaktív felhasználói élményt biztosítva.
## Gyakran Ismételt Kérdések
### K: Testreszabhatom a generált bélyegkép méretét és formátumát?
V: Igen, beállíthatja a miniatűr méreteit és formátumát a kód megfelelő paramétereinek módosításával.
### K: Az Aspose.Slides támogat más SmartArt-elrendezéseket?
V: Abszolút! Az Aspose.Slides számos SmartArt-elrendezést kínál, lehetővé téve a prezentációs igényeinek leginkább megfelelő kiválasztását.
### K: Rendelkezésre áll ideiglenes licenc tesztelési célokra?
 V: Igen, ideiglenes engedélyt szerezhet a következőtől[itt](https://purchase.aspose.com/temporary-license/) teszteléshez és értékeléshez.
### K: Hol kérhetek segítséget vagy csatlakozhatok az Aspose.Slides közösséghez?
 V: Látogassa meg a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11) kapcsolatba lépni a közösséggel, kérdéseket feltenni és megoldásokat találni.
### K: Megvásárolhatom az Aspose.Slides-t .NET-hez?
 V: Természetesen! Fedezze fel a vásárlási lehetőségeket[itt](https://purchase.aspose.com/buy) hogy az Aspose.Slidesben rejlő teljes potenciált kiaknázza projektjeiben.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
