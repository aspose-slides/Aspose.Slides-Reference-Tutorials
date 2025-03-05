---
title: Aspose.Slides – Az alakzatok zökkenőmentes összekapcsolása a .NET-ben
linktitle: Alakzatok összekapcsolása csatlakozókkal a prezentációban
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Fedezze fel az Aspose.Slides for .NET erejét, amely könnyedén összekapcsolja az alakzatokat prezentációiban. Emelje fel diákjait dinamikus csatlakozókkal.
type: docs
weight: 29
url: /hu/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---
## Bevezetés
A prezentációk dinamikus világában az alakzatok összekötőkkel történő összekapcsolásának lehetősége kifinomultabbá teszi a diákat. Az Aspose.Slides for .NET lehetővé teszi a fejlesztők számára, hogy ezt zökkenőmentesen elérjék. Ez az oktatóanyag végigvezeti Önt a folyamaton, és az egyes lépéseket lebontja a világos megértés érdekében.
## Előfeltételek
Mielőtt belevágnánk az oktatóanyagba, győződjön meg arról, hogy rendelkezik a következőkkel:
- C# és .NET keretrendszer alapismeretei.
-  Aspose.Slides for .NET telepítve. Ha nem, töltse le[itt](https://releases.aspose.com/slides/net/).
- Felállított fejlesztői környezet.
## Névterek importálása
A C# kódban kezdje a szükséges névterek importálásával:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Állítsa be a Dokumentumkönyvtárat
Kezdje a dokumentum könyvtárának meghatározásával:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Példányos bemutató osztály
Hozzon létre egy példányt a Presentation osztályból a PPTX fájl megjelenítéséhez:
```csharp
using (Presentation input = new Presentation())
{
    // Alakzatgyűjtemény elérése a kiválasztott diához
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Adjon hozzá alakzatokat a diához
Adja hozzá a szükséges alakzatokat a diához, például Ellipszist és Téglalapot:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Adja hozzá a csatlakozó alakját
Vegyen fel egy csatlakozó alakzatot a dia alakzatgyűjteményébe:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Csatlakoztassa az alakzatokat a csatlakozóval
Adja meg a csatlakozóval összekapcsolandó alakzatokat:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. A csatlakozó átirányítása
Hívja az átirányítási metódust az alakzatok közötti automatikus legrövidebb út beállításához:
```csharp
connector.Reroute();
```
## 7. Mentse a bemutatót
Mentse el prezentációját az összekapcsolt alakzatok megtekintéséhez:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Következtetés
Gratulálunk! Sikeresen összekapcsolta az alakzatokat a bemutatódiákban lévő csatlakozókkal az Aspose.Slides for .NET segítségével. Fejlessze prezentációit ezzel a fejlett funkcióval, és ragadja meg közönségét.
## GYIK
### Az Aspose.Slides for .NET kompatibilis a legújabb .NET keretrendszerrel?
Igen, az Aspose.Slides for .NET rendszeresen frissül a legújabb .NET-keretrendszer-verziókkal való kompatibilitás biztosítása érdekében.
### Összekapcsolhatok kettőnél több alakzatot egyetlen csatlakozóval?
Természetesen több alakzatot is összekapcsolhat az összekötő logika kiterjesztésével a kódban.
### Vannak korlátozások a csatlakoztatható alakzatokra vonatkozóan?
Az Aspose.Slides for .NET támogatja a különféle alakzatok összekapcsolását, beleértve az alapvető alakzatokat, az intelligens művészetet és az egyéni alakzatokat.
### Hogyan szabhatom testre a csatlakozó megjelenését?
Tekintse meg az Aspose.Slides dokumentációt a csatlakozó megjelenésének testreszabásának módszereiről, például a vonalstílusról és a színről.
### Létezik közösségi fórum az Aspose.Slides támogatásához?
 Igen, segítséget találhat és megoszthatja tapasztalatait a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).