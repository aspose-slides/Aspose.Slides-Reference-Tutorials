---
title: A .NET-hez készült Aspose.Slides diagram trendvonalainak felfedezése
linktitle: Chart Trend Vonalak
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ebből a lépésről lépésre szóló útmutatóból megtudhatja, hogyan adhat hozzá különböző trendvonalakat a diagramokhoz az Aspose.Slides for .NET segítségével. Növelje könnyedén adatvizualizációs készségeit!
type: docs
weight: 12
url: /hu/net/advanced-chart-customization/chart-trend-lines/
---

Az adatvizualizáció és -megjelenítés világában a diagramok beépítése hatékony módja lehet az információk hatékony közvetítésének. Az Aspose.Slides for .NET funkciókban gazdag eszközkészletet biztosít a diagramokkal való munkavégzéshez, beleértve a trendvonalak hozzáadását a diagramokhoz. Ebben az oktatóanyagban az Aspose.Slides for .NET segítségével lépésről lépésre elmélyítjük a trendvonalak diagramhoz való hozzáadásának folyamatát. 

## Előfeltételek

Mielőtt elkezdenénk dolgozni az Aspose.Slides for .NET-szel, meg kell győződnie arról, hogy a következő előfeltételeket teljesíti:

1.  Aspose.Slides for .NET: A könyvtár eléréséhez és használatához telepíteni kell az Aspose.Slides for .NET-et. A könyvtárat a[letöltési oldal](https://releases.aspose.com/slides/net/).

2. Fejlesztői környezet: Be kell állítania egy fejlesztői környezetet, lehetőleg integrált .NET fejlesztői környezetet, például a Visual Studio-t használva.

3. Alapvető C# ismerete: A C# programozás alapvető ismerete előnyös, mivel C#-t fogunk használni az Aspose.Slides for .NET-hez.

Most, hogy megvizsgáltuk az előfeltételeket, részletezzük lépésről lépésre a trendvonalak diagramhoz való hozzáadásának folyamatát.

## Névterek importálása

Először győződjön meg arról, hogy a szükséges névtereket importálta a C# projektbe. Ezek a névterek elengedhetetlenek az Aspose.Slides for .NET programhoz.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## 1. lépés: Hozzon létre egy prezentációt

Ebben a lépésben létrehozunk egy üres prezentációt, amellyel dolgozni szeretnénk.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";

// Hozzon létre könyvtárat, ha még nincs jelen.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Üres prezentáció létrehozása
Presentation pres = new Presentation();
```

## 2. lépés: Adjon hozzá egy diagramot a diához

Ezután hozzáadunk egy fürtözött oszlopdiagramot egy diához.

```csharp
// Csoportosított oszlopdiagram létrehozása
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## 3. lépés: Adjon hozzá trendvonalakat a diagramhoz

Most különféle típusú trendvonalakat adunk a diagramsorozathoz.

### Exponenciális trendvonal hozzáadása

```csharp
// Exponenciális trendvonal hozzáadása az 1. diagramsorozathoz
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Lineáris trendvonal hozzáadása

```csharp
// Lineáris trendvonal hozzáadása az 1. diagramsorozathoz
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Logaritmikus trendvonal hozzáadása

```csharp
// Logaritmikus trendvonal hozzáadása a 2. diagramsorozathoz
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Mozgóátlag trendvonal hozzáadása

```csharp
// Mozgóátlag trendvonal hozzáadása a 2. diagramsorozathoz
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Polinom trendvonal hozzáadása

```csharp
// Polinomiális trendvonal hozzáadása a 3. diagramsorozathoz
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Power Trend Line hozzáadása

```csharp
// Hatékonysági trendvonal hozzáadása a 3. diagramsorozathoz
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## 4. lépés: Mentse el a bemutatót

Miután hozzáadta a trendvonalakat a diagramhoz, mentse a bemutatót.

```csharp
// Prezentáció mentése
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen hozzáadott különböző trendvonalakat diagramjához az Aspose.Slides for .NET segítségével.

## Következtetés

Az Aspose.Slides for .NET egy sokoldalú könyvtár, amely lehetővé teszi diagramok egyszerű létrehozását és kezelését. Ennek a lépésről lépésre szóló útmutatónak a követésével különböző típusú trendvonalakat adhat hozzá diagramjaihoz, javítva az adatok vizuális megjelenítését.

### GYIK

### Hol találom az Aspose.Slides for .NET dokumentációját?
 Hozzáférhet a dokumentációhoz[itt](https://reference.aspose.com/slides/net/).

### Hogyan tölthetem le az Aspose.Slides-t .NET-hez?
 Az Aspose.Slides for .NET letölthető a letöltési oldalról[itt](https://releases.aspose.com/slides/net/).

### Létezik ingyenes próbaverzió az Aspose.Slides for .NET számára?
 Igen, ingyenesen kipróbálhatja az Aspose.Slides for .NET alkalmazást, ha felkeresi[ez a link](https://releases.aspose.com/).

### Hol vásárolhatom meg az Aspose.Slides-t .NET-hez?
 Az Aspose.Slides for .NET megvásárlásához keresse fel a vásárlási oldalt[itt](https://purchase.aspose.com/buy).

### Szükségem van ideiglenes licencre az Aspose.Slides for .NET számára?
 Ideiglenes licencet szerezhet be az Aspose.Slides for .NET-hez a következő webhelyről:[ez a link](https://purchase.aspose.com/temporary-license/).