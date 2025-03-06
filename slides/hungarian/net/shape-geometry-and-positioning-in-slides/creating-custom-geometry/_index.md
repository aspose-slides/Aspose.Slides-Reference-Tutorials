---
title: Egyéni geometria létrehozása C# nyelven az Aspose.Slides segítségével .NET-hez
linktitle: Egyéni geometria létrehozása geometriai alakzatban az Aspose.Slides segítségével
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre egyéni geometriát az Aspose.Slides for .NET programban. Emelje fel prezentációit egyedi formákkal. Lépésről lépésre útmutató C# fejlesztőknek.
weight: 15
url: /hu/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Egyéni geometria létrehozása C# nyelven az Aspose.Slides segítségével .NET-hez

## Bevezetés
prezentációk dinamikus világában az egyedi formák és geometriák hozzáadásával a tartalom kiemelhető, vonzóbbá és vizuálisan vonzóbbá válik. Az Aspose.Slides for .NET hatékony megoldást kínál az alakzatokon belüli egyéni geometriák létrehozására, lehetővé téve, hogy megszabaduljon a hagyományos tervektől. Ez az oktatóanyag végigvezeti az egyéni geometria létrehozásának folyamatán egy GeometryShape-ban az Aspose.Slides for .NET használatával.
## Előfeltételek
Mielőtt belevágna az oktatóanyagba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
- A C# programozási nyelv alapvető ismerete.
- A fejlesztői környezetébe telepített Aspose.Slides for .NET könyvtár.
- Visual Studio vagy bármely preferált C# fejlesztői környezet beállítása.
## Névterek importálása
A kezdéshez importálja a szükséges névtereket a C# projektbe:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## 1. lépés: Állítsa be projektjét
Hozzon létre egy új C# projektet a kívánt fejlesztői környezetben. Győződjön meg arról, hogy az Aspose.Slides for .NET megfelelően telepítve van.
## 2. lépés: Határozza meg a dokumentumkönyvtárat
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## 3. lépés: Állítsa be a külső és a belső csillag sugarát
```csharp
float R = 100, r = 50; // Külső és belső csillagsugár
```
## 4. lépés: Hozzon létre csillaggeometriai útvonalat
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## 5. lépés: Hozzon létre egy prezentációt
```csharp
using (Presentation pres = new Presentation())
{
    // Hozzon létre új formát
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Állítson be új geometriai útvonalat az alakzathoz
    shape.SetGeometryPath(starPath);
    // Mentse el a bemutatót
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## 6. lépés: Adja meg a CreateStarGeometry módszert
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan hozhat létre egyéni geometriát GeometryShape-ban az Aspose.Slides for .NET használatával. Ez a lehetőségek világát nyitja meg egyedi és vizuálisan lenyűgöző prezentációk létrehozásához.
## GYIK
### 1. Használhatom az Aspose.Slides for .NET fájlt más programozási nyelvekkel?
Igen, az Aspose.Slides különféle programozási nyelveket támogat, de ez az oktatóanyag a C#-ra összpontosít.
### 2. Hol találom az Aspose.Slides for .NET dokumentációját?
 Meglátogatni a[dokumentáció](https://reference.aspose.com/slides/net/) részletes információkért.
### 3. Elérhető ingyenes próbaverzió az Aspose.Slides for .NET számára?
 Igen, felfedezheti a[ingyenes próbaverzió](https://releases.aspose.com/) megtapasztalni a jellemzőket.
### 4. Hogyan kaphatok támogatást az Aspose.Slides for .NET-hez?
 Kérjen segítséget és lépjen kapcsolatba a közösséggel[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
### 5. Hol vásárolhatom meg az Aspose.Slides-t .NET-hez?
 Megvásárolhatja az Aspose.Slides-t .NET-hez[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
