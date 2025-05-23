---
"date": "2025-04-15"
"description": "Tanuld meg, hogyan hozhatsz létre dinamikus fánkdiagramokat az Aspose.Slides for .NET segítségével. Kövesd ezt az útmutatót a lépésenkénti utasításokért, beleértve a beállítást és a speciális funkciókat is."
"title": "Lépésről lépésre útmutató&#58; Fánkdiagram létrehozása az Aspose.Slides .NET segítségével | Táblázatok és grafikonok"
"url": "/hu/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Lépésről lépésre útmutató: Fánkdiagram létrehozása az Aspose.Slides .NET segítségével

## Bevezetés

Képzeld el, hogy feladatod az adatelemzési eredmények bemutatása a csapatodnak vagy az ügyfeleidnek, és szükséged van egy lebilincselő módra az információk vizualizálására. Íme a fánkdiagram – egy sokoldalú eszköz, amely a nyers számokat könnyen emészthető információkká alakítja. Az Aspose.Slides .NET-hez készült verziójával egyszerűen és hatékonyan hozhatsz létre egyéni fánkdiagramokat a prezentációd diáin. Ez az útmutató végigvezet az Aspose.Slides használatán, hogy vizuálisan vonzó fánkdiagramot hozz létre, testreszabott sorozatkonfigurációkkal.

**Amit tanulni fogsz:**
- Fejlesztői környezet beállítása az Aspose.Slides for .NET segítségével
- Fánkdiagramok létrehozása és testreszabása prezentációkban
- Speciális funkciók, például kategórianevek és vezető sorok megvalósítása
- Nagy adathalmazok teljesítményének optimalizálása

Nézzük át, milyen előfeltételekre van szükséged a kezdéshez.

## Előfeltételek

funkció megvalósítása előtt győződjön meg arról, hogy a fejlesztői környezet megfelelően van beállítva. Ez az oktatóanyag feltételezi a .NET programozás alapvető ismereteit, valamint a Visual Studio vagy hasonló IDE ismeretét.

### Szükséges könyvtárak és verziók
- **Aspose.Slides .NET-hez**: A legújabb verzióval való kompatibilitás ellenőrzésével biztosítsa a [hivatalos dokumentáció](https://reference.aspose.com/slides/net/).

### Környezeti beállítási követelmények
- Egy működő .NET környezet.
- Hozzáférés egy kódszerkesztőhöz, például a Visual Studio-hoz.

### Előfeltételek a tudáshoz
- C# és .NET keretrendszer alapismeretek.
- Ismerkedés a prezentációs szoftverek koncepcióival (opcionális, de hasznos).

## Az Aspose.Slides beállítása .NET-hez

Az Aspose.Slides használatának megkezdéséhez a projektedben telepítened kell azt a NuGet-en keresztül. Íme az elérhető metódusok:

**.NET parancssori felület használata:**
```bash
dotnet add package Aspose.Slides
```

**A csomagkezelő használata:**
```powershell
Install-Package Aspose.Slides
```

**NuGet csomagkezelő felhasználói felület:**
Keresd meg az „Aspose.Slides” fájlt, és telepítsd a legújabb verziót.

### Licencbeszerzés lépései

1. **Ingyenes próbaverzió**Kezdj egy [ingyenes próba](https://releases.aspose.com/slides/net/) az alapvető funkciók megismeréséhez.
2. **Ideiglenes engedély**: Ha tesztelési célból hozzáférne a teljes funkciókhoz, szerezzen be ideiglenes licencet a következő címen: [itt](https://purchase.aspose.com/temporary-license/).
3. **Vásárlás**Kereskedelmi célú felhasználáshoz vásároljon licencet a következő helyről: [Aspose weboldal](https://purchase.aspose.com/buy).

A telepítés és a licencelés után inicializáld az Aspose.Slides fájlt a projektedben:
```csharp
using Aspose.Slides;

// Az Aspose.Slides inicializálása .NET-hez
var presentation = new Presentation();
```

## Megvalósítási útmutató

### Új prezentáció létrehozása és fánkdiagram hozzáadása

#### Áttekintés
Először létrehozunk egy új prezentációt, és hozzáadunk egy fánkdiagramot az első diához. Ez a szakasz egy meglévő prezentáció betöltését, a diák elérését és a diagramok beszúrását tárgyalja.

**1. lépés: Bemutató betöltése vagy létrehozása**
Először is, add meg a dokumentum könyvtárát, és tölts be egy meglévő prezentációt:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Ha nincs meglévő fájlod, hozz létre egy újat a következővel: `new Presentation()`.

**2. lépés: Az első dia elérése**
Hozzáférés az első diához, ahová a diagramot fogjuk hozzáadni:
```csharp
ISlide slide = pres.Slides[0];
```

**3. lépés: Fánkdiagram hozzáadása**
Fánkdiagram hozzáadása megadott koordinátákkal és méretekkel:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Az adatmunkafüzet konfigurálása

#### Áttekintés
Ez a szakasz ismerteti, hogyan konfigurálhatja a fánkdiagramhoz társított adatmunkafüzetet.

**4. lépés: Hozzáférés a meglévő adatokhoz és azok törlése**
Nyissa meg a diagram adatmunkafüzetét. Ezután törölje a meglévő sorozatokat vagy kategóriákat:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**5. lépés: Jelmagyarázat letiltása és sorozat hozzáadása**
A jelmagyarázat letiltásával tisztán tarthatja a diagramot, majd adjon hozzá legfeljebb 15 adatsort egyéni konfigurációkkal:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Kategóriák és adatpontok hozzáadása

#### Áttekintés
Most töltsük fel a diagramot kategóriákkal és adatpontokkal az egyes sorozatokhoz.

**6. lépés: Kategóriák hozzáadása**
Ismételje meg a lépéseket 15 kategória hozzáadásához:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**7. lépés: Adatpontok feltöltése**
Adatpontok hozzáadása az aktuális kategórián belüli minden sorozathoz:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Megjelenés testreszabása
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Címkeformátum konfigurálása az utolsó sorozathoz
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Címkemegjelenítés konfigurálása
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### A prezentáció mentése

**8. lépés: Mentse el a fájlt**
Végül mentse el a prezentációt egy megadott könyvtárba:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}