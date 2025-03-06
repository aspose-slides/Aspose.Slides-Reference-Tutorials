---
title: Lenyűgöző vázlatos formák létrehozása az Aspose.Slides segítségével
linktitle: Vázlatos alakzatok létrehozása prezentációs diákban az Aspose.Slides segítségével
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan adhat kreatív vázlatos alakzatokat prezentációi diákjaihoz az Aspose.Slides for .NET segítségével. Fokozza a vizuális vonzerőt erőfeszítés nélkül!
weight: 13
url: /hu/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Üdvözöljük lépésről lépésre bemutatott útmutatónkban, amely bemutatja az Aspose.Slides for .NET segítségével vázolt alakzatokat bemutató diákban. Ha egy kis kreativitást szeretne adni prezentációihoz, a vázlatos formák egyedi és kézzel rajzolt esztétikát biztosítanak. Ebben az oktatóanyagban végigvezetjük a folyamaton, egyszerű lépésekre bontva a zökkenőmentes élmény érdekében.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
-  Aspose.Slides for .NET: Győződjön meg arról, hogy telepítve van a .NET Aspose.Slides könyvtára. Letöltheti[itt](https://releases.aspose.com/slides/net/).
- Fejlesztői környezet: Hozzon létre egy .NET fejlesztői környezetet a kívánt IDE-vel.
## Névterek importálása
Kezdje a szükséges névterek importálásával a .NET-projektben. Ez a lépés biztosítja, hogy hozzáférjen az Aspose.Slides használatához szükséges osztályokhoz és funkciókhoz.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## 1. lépés: Állítsa be a projektet
Kezdje új .NET-projekt létrehozásával vagy egy meglévő megnyitásával. Ügyeljen arra, hogy az Aspose.Slides-t szerepeltesse a projektreferenciákban.
## 2. lépés: Az Aspose.Slides inicializálása
Inicializálja az Aspose.Slides-t a következő kódrészlet hozzáadásával. Ez beállítja a prezentációt, és megadja a prezentációs fájl és a miniatűr kép kimeneti útvonalait.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Folytassa a következő lépésekkel...
}
```
## 3. lépés: Vázolt alakzat hozzáadása
Most adjunk hozzá egy vázlatos formát a diához. Ebben a példában egy téglalapot adunk hozzá szabadkézi vázlateffektussal.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Alakítsa át az alakzatot szabadkézi stílus vázlatává
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## 4. lépés: Indexkép létrehozása
A vázolt alakzat megjelenítéséhez hozzon létre egy bélyegképet a diáról. Mentse el az indexképet PNG-fájlként.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## 5. lépés: Mentse a bemutatót
Mentse el a prezentációs fájlt a vázolt alakzattal.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Ez az! Sikeresen létrehozott egy prezentációt felvázolt alakzatokkal az Aspose.Slides for .NET segítségével.
## Következtetés
Ha vázlatos formákat ad a prezentáció diákjaihoz, az javíthatja a vizuális vonzerőt és bevonhatja a közönséget. Az Aspose.Slides for .NET segítségével a folyamat egyszerűvé válik, így könnyedén szabadjára engedheti kreativitását.
## GYIK
### 1. Testreszabhatom a vázolt hatást?
 Igen, az Aspose.Slides for .NET különféle testreszabási lehetőségeket kínál a vázlatos effektusokhoz. Utal[dokumentáció](https://reference.aspose.com/slides/net/) részletes információkért.
### 2. Van-e ingyenes próbaverzió?
 Biztosan! Megtekintheti az Aspose.Slides .NET-hez készült ingyenes próbaverzióját[itt](https://releases.aspose.com/).
### 3. Hol kaphatok támogatást?
 Bármilyen segítségre vagy kérdésre keresse fel a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
### 4. Hogyan vásárolhatom meg az Aspose.Slides-t .NET-hez?
 Az Aspose.Slides for .NET megvásárlásához látogassa meg a[vásárlási oldal](https://purchase.aspose.com/buy).
### 5. Kínálnak ideiglenes licenceket?
 Igen, rendelkezésre állnak ideiglenes licencek[itt](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
