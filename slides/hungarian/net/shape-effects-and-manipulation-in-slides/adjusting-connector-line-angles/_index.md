---
title: Állítsa be a csatlakozóvonal szögeit a PowerPointban az Aspose.Slides segítségével
linktitle: Csatlakozóvonal szögeinek beállítása a bemutató diákban az Aspose.Slides segítségével
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan állíthatja be a csatlakozóvonalak szögét a PowerPoint diákban az Aspose.Slides for .NET segítségével. Tökéletesítse prezentációit precízen és egyszerűen.
weight: 28
url: /hu/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
tetszetős prezentációs diák létrehozása gyakran a csatlakozóvonalak pontos beállítását igényli. Ebben az oktatóanyagban megvizsgáljuk, hogyan állíthatjuk be a csatlakozási vonalak szögét a bemutatódiákon az Aspose.Slides for .NET segítségével. Az Aspose.Slides egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak PowerPoint fájlokkal, és széleskörű lehetőségeket biztosítanak prezentációk létrehozásához, módosításához és manipulálásához.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# programozási nyelv alapismerete.
- Visual Studio vagy bármely más C# fejlesztői környezet telepítve.
-  Aspose.Slides a .NET könyvtárhoz. Letöltheti[itt](https://releases.aspose.com/slides/net/).
- Egy PowerPoint-prezentációs fájl beállítani kívánt csatlakozóvonalakkal.
## Névterek importálása
A kezdéshez feltétlenül adja meg a szükséges névtereket a C# kódban:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## 1. lépés: Állítsa be projektjét
Hozzon létre egy új C#-projektet a Visual Studióban, és telepítse az Aspose.Slides NuGet csomagot. Állítsa be a projekt szerkezetét az Aspose.Slides könyvtárra való hivatkozással.
## 2. lépés: Töltse be a prezentációt
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 Töltse be a PowerPoint bemutató fájlt a`Presentation`tárgy. Cserélje ki a "Saját dokumentumkönyvtár" elemet a fájl tényleges elérési útjával.
## 3. lépés: Nyissa meg a diát és az alakzatokat
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Nyissa meg a bemutató első diáját, és inicializáljon egy változót a dián lévő alakzatok megjelenítéséhez.
## 4. lépés: Iterálás alakzatokon keresztül
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Kód a csatlakozóvezetékek kezeléséhez
}
```
Végighurkolja a dián lévő egyes alakzatokat a csatlakozóvonalak azonosításához és feldolgozásához.
## 5. lépés: Állítsa be a csatlakozóvonal szögeit
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Kód az AutoShapes kezeléséhez
}
else if (shape is Connector)
{
    // Kód a csatlakozók kezeléséhez
}
Console.WriteLine(dir);
```
 Határozza meg, hogy az alakzat AutoShape vagy Connector, és állítsa be a csatlakozóvonal szögeit a mellékelt segítségével`getDirection` módszer.
##  6. lépés: Határozza meg a`getDirection` Method
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Kód az irány kiszámításához
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
 Végezze el a`getDirection` módszer a csatlakozóvonal szögének kiszámítására annak méretei és tájolása alapján.
## Következtetés
Ezekkel a lépésekkel programozottan beállíthatja a csatlakozóvonalak szögeit a PowerPoint-prezentációban az Aspose.Slides for .NET segítségével. Ez az oktatóanyag alapot nyújt diákjai vizuális vonzerejének fokozásához.
## GYIK
### Az Aspose.Slides Windows és webes alkalmazásokhoz egyaránt alkalmas?
Igen, az Aspose.Slides Windows és webes alkalmazásokban is használható.
### Letölthetem az Aspose.Slides ingyenes próbaverzióját a vásárlás előtt?
 Igen, letölthet egy ingyenes próbaverziót[itt](https://releases.aspose.com/).
### Hol találom az Aspose.Slides for .NET átfogó dokumentációját?
 A dokumentáció elérhető[itt](https://reference.aspose.com/slides/net/).
### Hogyan szerezhetek ideiglenes licencet az Aspose.Slides számára?
 Kaphat ideiglenes engedélyt[itt](https://purchase.aspose.com/temporary-license/).
### Létezik támogatási fórum az Aspose.Slides számára?
 Igen, felkeresheti a támogatási fórumot[itt](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
