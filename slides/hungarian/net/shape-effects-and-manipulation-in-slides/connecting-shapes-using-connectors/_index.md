---
"description": "Fedezd fel az Aspose.Slides for .NET erejét, amellyel könnyedén összekapcsolhatsz alakzatokat a prezentációidban. Emeld diáid magas szintjét dinamikus összekötőkkel."
"linktitle": "Alakzatok összekapcsolása összekötőkkel a bemutatóban"
"second_title": "Aspose.Slides .NET PowerPoint feldolgozási API"
"title": "Aspose.Slides - Alakzatok zökkenőmentes összekapcsolása .NET-ben"
"url": "/hu/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides - Alakzatok zökkenőmentes összekapcsolása .NET-ben

## Bevezetés
A prezentációk dinamikus világában az alakzatok összekötőkkel való összekapcsolásának lehetősége kifinomultabbá teszi a diákat. Az Aspose.Slides for .NET lehetővé teszi a fejlesztők számára, hogy ezt zökkenőmentesen elérjék. Ez az oktatóanyag végigvezeti Önt a folyamaton, és lépésről lépésre lebontja a világos megértés érdekében.
## Előfeltételek
Mielőtt belemerülnénk az oktatóanyagba, győződjünk meg róla, hogy a következőkkel rendelkezünk:
- C# és .NET keretrendszer alapismeretek.
- Aspose.Slides for .NET telepítve van. Ha nincs, töltse le. [itt](https://releases.aspose.com/slides/net/).
- Beállított fejlesztői környezet.
## Névterek importálása
A C# kódodban kezdd a szükséges névterek importálásával:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Állítsa be a dokumentumkönyvtárat
Kezdjük a dokumentum könyvtárának meghatározásával:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Prezentációs osztály példányosítása
Hozz létre egy példányt a Presentation osztályból a PPTX fájlod reprezentálására:
```csharp
using (Presentation input = new Presentation())
{
    // A kijelölt diához tartozó alakzatgyűjtemény elérése
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Alakzatok hozzáadása a diához
Adja hozzá a szükséges alakzatokat a diához, például az Ellipszist és a Téglalapot:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Összekötő alakjának hozzáadása
Összekötő alakzatának hozzáadása a dia alakzatgyűjteményéhez:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Alakzatok összekötése összekötővel
Adja meg az összekötővel összekapcsolandó alakzatokat:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Csatlakozó átirányítása
Hívjuk meg a reroute metódust az alakzatok közötti automatikus legrövidebb útvonal beállításához:
```csharp
connector.Reroute();
```
## 7. Prezentáció mentése
Mentse el a bemutatót az összekapcsolt alakzatok megtekintéséhez:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Következtetés
Gratulálunk! Sikeresen összekapcsolta az alakzatokat a prezentációs diákon található összekötők segítségével az Aspose.Slides for .NET segítségével. Dobja fel prezentációit ezzel a fejlett funkcióval, és nyűgözze le közönségét.
## GYIK
### Az Aspose.Slides for .NET kompatibilis a legújabb .NET keretrendszerrel?
Igen, az Aspose.Slides for .NET rendszeresen frissül, hogy biztosítsa a kompatibilitást a legújabb .NET keretrendszer verziókkal.
### Összekapcsolhatok kettőnél több alakzatot egyetlen összekötővel?
Természetesen több alakzatot is összekapcsolhatsz a kódodban található összekötő logika kiterjesztésével.
### Vannak-e korlátozások az összekapcsolható alakzatokra vonatkozóan?
Az Aspose.Slides for .NET támogatja a különféle alakzatok összekapcsolását, beleértve az alapvető alakzatokat, a smart artokat és az egyéni alakzatokat.
### Hogyan tudom testreszabni a csatlakozó megjelenését?
Az Aspose.Slides dokumentációjában megtalálod a csatlakozók megjelenésének, például a vonalstílusnak és a színnek a testreszabására szolgáló módszereket.
### Van közösségi fórum az Aspose.Slides támogatásához?
Igen, segítséget kérhetsz és megoszthatod a tapasztalataidat a [Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}