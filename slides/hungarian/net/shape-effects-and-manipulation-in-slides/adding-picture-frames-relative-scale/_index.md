---
title: Képkeretek hozzáadása oktatóanyag az Aspose.Slides .NET segítségével
linktitle: Képkeretek hozzáadása relatív léptékmagassággal az Aspose.Slides-ben
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá relatív méretarányú képkereteket az Aspose.Slides for .NET-hez. Kövesse ezt a lépésről lépésre szóló útmutatót a zökkenőmentes prezentációkhoz.
weight: 17
url: /hu/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Az Aspose.Slides for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy .NET-alkalmazásaikban könnyedén hozzanak létre, kezeljenek és alakítsanak át PowerPoint-prezentációkat. Ebben az oktatóanyagban a relatív méretarányú képkeretek hozzáadásának folyamatát mutatjuk be az Aspose.Slides for .NET segítségével. Kövesse ezt a lépésenkénti útmutatót prezentációkészítési készségeinek fejlesztéséhez.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
- C# programozási nyelv alapismerete.
- Visual Studio vagy bármely más preferált C# fejlesztői környezet telepítve.
- Aspose.Slides for .NET könyvtár hozzáadva a projekthez.
## Névterek importálása
Kezdje a szükséges névterek importálásával a C# kódba. Ez a lépés biztosítja, hogy hozzáférjen az Aspose.Slides könyvtár által biztosított osztályokhoz és funkciókhoz.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## 1. lépés: Állítsa be projektjét
Kezdje egy új C# projekt létrehozásával a kívánt fejlesztői környezetben. Ügyeljen arra, hogy az Aspose.Slides for .NET könyvtárat a projekthez adva hivatkozzon rá.
## 2. lépés: Töltse be a bemutatót és a képet
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    //Kép betöltése a bemutató képgyűjteménybe adandó
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
Ebben a lépésben létrehozunk egy új prezentációs objektumot, és betöltjük azt a képet, amelyet hozzá szeretnénk adni a bemutatóhoz.
## 3. lépés: Képkeret hozzáadása a diához
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Most adjon hozzá egy képkeretet a bemutató első diájához. Igényeinek megfelelően állítsa be a paramétereket, például az alaktípust, a pozíciót és a méreteket.
## 4. lépés: Állítsa be a skála relatív szélességét és magasságát
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Állítsa be a képkeret relatív skálamagasságát és szélességét a kívánt méretezési hatás eléréséhez.
## 5. lépés: Mentse a bemutatót
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Végül mentse el a prezentációt a hozzáadott képkerettel a megadott kimeneti formátumban.
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan adhat hozzá relatív méretarányú képkereteket az Aspose.Slides for .NET segítségével. Kísérletezzen különböző képekkel, pozíciókkal és léptékekkel, hogy tetszetős prezentációkat készítsen az Ön igényei szerint.
## Gyakran Ismételt Kérdések
### Használhatom az Aspose.Slides for .NET programot más programozási nyelvekkel?
Az Aspose.Slides elsősorban a .NET nyelveket támogatja, de felfedezhet más Aspose-termékeket a különböző platformokkal való kompatibilitás érdekében.
### Hol találom az Aspose.Slides for .NET részletes dokumentációját?
 Utal[dokumentáció](https://reference.aspose.com/slides/net/) átfogó információkért és példákért.
### Létezik ingyenes próbaverzió az Aspose.Slides for .NET számára?
 Igen, kaphat a[ingyenes próbaverzió](https://releases.aspose.com/) hogy értékelje a könyvtár képességeit.
### Hogyan kaphatok támogatást az Aspose.Slides for .NET-hez?
 Meglátogatni a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11) hogy kérjen segítséget a közösségtől és az Aspose szakértőitől.
### Hol vásárolhatom meg az Aspose.Slides-t .NET-hez?
 Az Aspose.Slides for .NET megvásárolható itt[vásárlási oldal](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
