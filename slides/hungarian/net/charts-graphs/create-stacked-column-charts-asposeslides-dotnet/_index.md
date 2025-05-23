---
"date": "2025-04-15"
"description": "Tanuld meg, hogyan készíthetsz vizuálisan meggyőző, százalékos alapú, halmozott oszlopdiagramokat az Aspose.Slides for .NET segítségével. Kövesd ezt a lépésről lépésre szóló útmutatót a világos adatvizualizáció érdekében."
"title": "Százalékalapú halmozott oszlopdiagramok létrehozása .NET-ben az Aspose.Slides használatával"
"url": "/hu/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Százalékalapú halmozott oszlopdiagram létrehozása az Aspose.Slides for .NET használatával

## Bevezetés

Az adatvizualizáció területén az információk világos és hatékony bemutatása kulcsfontosságú a hatékony döntéshozatalhoz. Az összetett adathalmazok intuitív megjelenítéséhez a százalékos alapú halmozott oszlopdiagramok ideálisak. Ez az útmutató végigvezeti Önt ezen diagramok létrehozásán az Aspose.Slides for .NET segítségével, amely egy robusztus, prezentációs fájlok kezelésére tervezett könyvtár.

Ezt az oktatóanyagot követve megtanulhatod:
- Diagramadatok beállítása és számformátumok konfigurálása.
- Sorozatok hozzáadása és megjelenésük testreszabása.
- A címkék formázása az olvashatóság javítása érdekében.

Készen állsz a belevágásra? Kezdjük a szükséges előfeltételekkel!

## Előfeltételek

Százalékalapú halmozott oszlopdiagramok létrehozása előtt győződjön meg arról, hogy a környezete megfelelően van beállítva. Szüksége lesz:

### Szükséges könyvtárak, verziók és függőségek
- **Aspose.Slides .NET-hez**Győződjön meg róla, hogy ez a könyvtár telepítve van.

### Környezeti beállítási követelmények
- Fejlesztői környezet telepítve a .NET SDK-val.
- Visual Studio vagy bármilyen kompatibilis IDE C# kód futtatásához.

### Előfeltételek a tudáshoz
- C# programozás alapjainak ismerete.
- Jártasság a .NET projektek beállításában és csomagkezelésében.

## Az Aspose.Slides beállítása .NET-hez

Az Aspose.Slides segítségével diagramok készítésének megkezdéséhez először telepítse a könyvtárat az alábbi módszerek egyikével:

**.NET parancssori felület**
```bash
dotnet add package Aspose.Slides
```

**Csomagkezelő**
```powershell
Install-Package Aspose.Slides
```

**NuGet csomagkezelő felhasználói felület**
- Keresd meg az „Aspose.Slides” fájlt, és telepítsd a legújabb verziót.

### Licencbeszerzés lépései

Kezdje az ingyenes próbaverziót egy ideiglenes licenc letöltésével innen: [Aspose weboldala](https://purchase.aspose.com/temporary-license/)A további használathoz érdemes teljes licencet vásárolni. 

A beállítás után indítsd el az Aspose.Slides-t a projektedben:
```csharp
using Aspose.Slides;
```

## Megvalósítási útmutató

Miután a környezet elkészült, bontsuk lépésekre a százalékos alapú halmozott oszlopdiagram létrehozását.

### Diagram létrehozása és konfigurálása

#### Áttekintés
Hozz létre egy példányt a `Presentation` osztály, ami elengedhetetlen a diákkal való munkához. Ezután adj hozzá és konfigurálj egy halmozott oszlopdiagramot a dián.

#### Halmozott oszlopdiagram hozzáadása
```csharp
// Hozz létre egy példányt a Presentation osztályból
document = new Presentation();

// Az első diára mutató hivatkozás lekérése
slide = document.Slides[0];

// Adjon hozzá PercentsStackedColumn diagramot a (20, 20) pozícióban, (500x400) méretben
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Számformátum konfigurálása
Győződjön meg arról, hogy az adatok százalékos formában jelennek meg:
```csharp
// Számformátum konfigurálása a függőleges tengelyhez
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Számformátum beállítása százalékra
```

#### Adatsorok és pontok hozzáadása
Törölje a meglévő sorozatadatokat, és adjon hozzá újakat:
```csharp
// Törölje a meglévő sorozatadatokat
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Access diagramadatokkal foglalkozó munkafüzet
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Új adatsor hozzáadása: „Reds”
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Állítsa a sorozat kitöltési színét pirosra
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Címkeformátum-tulajdonságok konfigurálása a „Reds” sorozathoz
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Százalékformátum beállítása
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Adj hozzá egy újabb sorozatot, a "Bluest"
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Állítsa a sorozat kitöltési színét kékre
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Százalékformátum beállítása
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### A prezentáció mentése
Mentse el a prezentációt egy fájlba:
```csharp
// Mentse el a prezentációt PPTX formátumban
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Hibaelhárítási tippek
- Győződjön meg arról, hogy az összes névtér importálása helyesen történt.
- Ellenőrizd az elgépeléseket a tulajdonságnevekben és a metódushívásokban.
- Ellenőrizze, hogy a mentési fájlok elérési útjai léteznek-e, és rendelkeznek-e a megfelelő engedélyekkel.

## Gyakorlati alkalmazások

Íme néhány olyan forgatókönyv, ahol a százalékos alapú halmozott oszlopdiagramok értékesek lehetnek:
1. **Értékesítési elemzés**: Vizualizálja a termék teljesítményét a különböző régiókban a teljes értékesítés arányában.
2. **Költségvetési elosztás**Mutassa be, hogyan osztják el a részlegek a költségvetésüket a vállalat teljes kiadásaihoz viszonyítva.
3. **Piackutatás**: Hasonlítsa össze a fogyasztói preferenciákat a különböző termékkategóriák esetében az idő múlásával.
4. **Oktatási adatok**: A tanulók osztályzatainak eloszlását jeleníti meg különböző tantárgyakból.
5. **Egészségügyi statisztikák**: A betegek demográfiai adatainak ábrázolása több egészségügyi állapot tekintetében.

## Teljesítménybeli szempontok

Az optimális teljesítmény érdekében vegye figyelembe:
- Az adatpontok számának korlátozása a szükségesre.
- Adatok előtöltése a futásidejű feldolgozás minimalizálása érdekében.
- Hatékony memóriakezelési gyakorlatok alkalmazása az Aspose.Slides for .NET segítségével.

## Következtetés

Gratulálunk! Sikeresen megtanultad, hogyan készíthetsz százalékos alapú halmozott oszlopdiagramot az Aspose.Slides for .NET segítségével. Ez az eszköz a prezentációk minőségét javítja azáltal, hogy összetett adatokat érthetőbbé és vizuálisan vonzóbbá tesz.

Következő lépések? Fedezzen fel más, az Aspose.Slides-ban elérhető diagramtípusokat, vagy integrálja ezt a funkciót nagyobb alkalmazásokba. Jó kódolást!

## GYIK szekció

**1. kérdés: Ingyenesen használhatom az Aspose.Slides-t?**
V1: Igen, ingyenes próbaverzióval tesztelheti az Aspose.Slides funkcióit.

**2. kérdés: Milyen diagramtípusokat támogat az Aspose.Slides for .NET?**
A2: Különféle diagramokat támogat, például kör-, sáv-, oszlop-, vonal- és egyebeket.

**3. kérdés: Hogyan kezdhetem el az Aspose.Slides for .NET használatát?**
3. válasz: Telepítse a függvénykönyvtárat NuGet vagy .NET CLI használatával a fent leírtak szerint. Az első diagram létrehozásához kövesse a dokumentációnkat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}