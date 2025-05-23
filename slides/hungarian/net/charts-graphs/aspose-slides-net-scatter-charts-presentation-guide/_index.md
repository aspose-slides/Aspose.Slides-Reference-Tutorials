---
"date": "2025-04-15"
"description": "Ismerje meg, hogyan teheti még jobbá prezentációit szóródási diagramokkal az Aspose.Slides for .NET segítségével. Kövesse ezt az átfogó útmutatót a diagramok hatékony létrehozásához és testreszabásához."
"title": "Pontdiagramok hozzáadása prezentációkhoz az Aspose.Slides .NET használatával – lépésről lépésre útmutató"
"url": "/hu/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Pontdiagramok hozzáadása prezentációkhoz az Aspose.Slides .NET használatával: lépésről lépésre útmutató

## Bevezetés
Szeretnéd könnyedén integrálni a szóródási diagramokat a prezentációidba, így még jobbá teheted őket? Az Aspose.Slides for .NET erejével a diagramok létrehozása és testreszabása gyerekjáték. Ez az oktatóanyag végigvezet azon, hogyan adhatsz szóródási diagramokat a diákhoz az Aspose.Slides for .NET segítségével. Ezen technikák elsajátításával hatékonyabban fogod bemutatni az adatokat, és vizuálisan vonzó prezentációkat hozhatsz létre.

**Amit tanulni fogsz:**
- Az Aspose.Slides beállítása .NET-hez a projektben
- Új prezentáció létrehozása és az első diához való hozzáférés
- Simított vonalakkal rendelkező pontdiagramok hozzáadása diákhoz
- Meglévő sorozatok törlése és újak hozzáadása a diagramokhoz
- Adatpontok és jelölőstílusok módosítása a jobb megjelenítés érdekében
- A prezentáció mentése egy megadott könyvtárba

Kezdjük az előfeltételek áttekintésével.

## Előfeltételek
Az Aspose.Slides for .NET implementálása előtt győződjön meg arról, hogy rendelkezik a következőkkel:
- **Aspose.Slides .NET könyvtárhoz**: 23.7-es vagy újabb verzió.
- **Fejlesztői környezet**Visual Studio 2019 vagy újabb verzió .NET Framework 4.6.1+ vagy .NET Core/5+ verzióval.
- **Alapvető C# ismeretek**Jártasság az objektumorientált programozásban C# nyelven.

## Az Aspose.Slides beállítása .NET-hez
Az Aspose.Slides használatának megkezdéséhez telepítenie kell a könyvtárat a projektjébe. Így teheti meg:

**.NET parancssori felület használata:**
```bash
dotnet add package Aspose.Slides
```

**A csomagkezelő konzol használata:**
```powershell
Install-Package Aspose.Slides
```

**NuGet csomagkezelő felhasználói felület:**
- Keresd meg az „Aspose.Slides” fájlt, és telepítsd a legújabb verziót.

### Licencszerzés
Ingyenes próbaverzióval kezdhet, vagy ideiglenes licencet kérhet az összes funkció megismeréséhez. A vásárláshoz kövesse az alábbi lépéseket:
1. Látogatás [Vásárolja meg az Aspose.Slides-t](https://purchase.aspose.com/buy) teljes licenc vásárlásához.
2. Ideiglenes engedélyért látogasson el a következő oldalra: [Ideiglenes licencoldal](https://purchase.aspose.com/temporary-license/).

Miután megszerezted a licencfájlt, add hozzá a projektedhez a következő paranccsal:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Megvalósítási útmutató
A megvalósítást logikai részekre bontjuk a funkciók alapján.

### Bemutató létrehozása és dia hozzáadása
Ez a szakasz bemutatja, hogyan hozhat létre egy prezentációt, és hogyan érheti el annak első diáját.

#### Áttekintés
Kezdje egy példány létrehozásával a `Presentation` osztály, amely a PowerPoint-fájlt jelöli. A diák elérése egyszerű ezzel az objektummodellel.

#### Megvalósítási lépések
**1. lépés: A prezentáció inicializálása**
```csharp
using Aspose.Slides;

// Új prezentáció létrehozása
t Presentation pres = new Presentation();
```
Ez a kód inicializál egy új prezentációs dokumentumot.

**2. lépés: Az első dia elérése**
```csharp
// A prezentáció első diájának elérése
ISlide slide = pres.Slides[0];
```
Itt, `pres.Slides[0]` legelső diához ér. 

### Pontdiagram hozzáadása a diához
Most adjunk hozzá egy pontdiagramot a bemutatónkhoz.

#### Áttekintés
Diagramok hozzáadásával vizuálisan ábrázolhatja az adatokat a prezentációkban. Az Aspose.Slides segítségével egyszerűen beilleszthet különféle típusú diagramokat, beleértve a szóródási diagramokat is.

#### Megvalósítási lépések
**1. lépés: Pontdiagram létrehozása és hozzáadása**
```csharp
using Aspose.Slides.Charts;

// Alapértelmezett szóródási diagram létrehozása és hozzáadása sima vonalakkal
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Ez a kódrészlet egy pontdiagramot ad hozzá a megadott pozícióban és méretben.

### Adatsorok törlése és hozzáadása a diagram adataihoz
#### Áttekintés
Lehetséges, hogy testre kell szabnia a diagramot a meglévő sorozatok törlésével és újak hozzáadásával. Ez a szakasz ezt a funkciót tárgyalja.

#### Megvalósítási lépések
**1. lépés: Diagramadatok munkafüzetének elérése**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Törölje a meglévő sorozatokat
chart.ChartData.Series.Clear();
```
Ez a kód törli a meglévő adatokat, hogy új sorozatokkal kezdhessen.

**2. lépés: Új sorozat hozzáadása**
```csharp
// Adjon hozzá egy új sorozatot, melynek neve „1. sorozat”
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Adj hozzá egy másik sorozatot, melynek neve „2. sorozat”
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Ezek a lépések két új sorozatot adnak a diagramhoz.

### Első sorozat adatpontjainak és jelölőstílusának módosítása
#### Áttekintés
Testreszabhatja az adatpontokat és a jelölők stílusát a szóródási diagramok jobb megjelenítése érdekében.

#### Megvalósítási lépések
**1. lépés: Adatpontok elérése és hozzáadása**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Adja össze az (1, 3) és (2, 10) adatpontokat
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**2. lépés: Jelölő stílusának módosítása**
```csharp
// Sorozattípus módosítása és jelölőstílus módosítása
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Második sorozat adatpontjainak és jelölőstílusának módosítása
#### Áttekintés
Hasonlóképpen, testreszabhatja a második sorozatot a prezentációs igényeinek megfelelően.

#### Megvalósítási lépések
**1. lépés: Több adatpont elérése és hozzáadása**
```csharp
// Hozzáférés a második slágerlistához
series = chart.ChartData.Series[1];

// Több adatpont hozzáadása
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**2. lépés: Jelölő stílusának módosítása**
```csharp
// Jelölő méretének és szimbólumának módosítása a második sorozathoz
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Prezentáció mentése
Végül mentse el a prezentációt egy megadott könyvtárba.

#### Megvalósítási lépések
**1. lépés: Könyvtár definiálása**
Győződjön meg róla, hogy a kimeneti könyvtár létezik. Ha nem, hozza létre:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Mentse el a prezentációt
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Ez a kód a prezentációs fájlt egy megadott helyre menti.

## Következtetés
Sikeresen hozzáadtad a szóródási diagramokat a prezentációidhoz az Aspose.Slides for .NET használatával. Folytasd a könyvtárban elérhető további funkciók és testreszabási lehetőségek felfedezését az adatvizualizációs készségeid fejlesztése érdekében.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}