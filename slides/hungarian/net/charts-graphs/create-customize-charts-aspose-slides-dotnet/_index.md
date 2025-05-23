---
"date": "2025-04-15"
"description": "Tanuld meg, hogyan hozhatsz létre és szabhatsz testre diagramokat az Aspose.Slides for .NET segítségével, beleértve a százalékok adatcímkékként való megjelenítését is. Kövesd ezt a lépésenkénti útmutatót."
"title": "Diagramok létrehozása és testreszabása az Aspose.Slides .NET segítségével – Százalékok megjelenítése címkékként"
"url": "/hu/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagramok létrehozása és testreszabása az Aspose.Slides .NET segítségével: Százalékok megjelenítése címkékként

## Bevezetés

Az adatok hatékony bemutatása számos területen kulcsfontosságú, és a diagramok létfontosságú szerepet játszanak azáltal, hogy összetett információkat világos vizuális megjelenítéssé alakítanak. A tökéletes diagram létrehozása olyan testreszabási feladatokat foglal magában, mint például a százalékok megjelenítése a címkéken – ezt a feladatot az Aspose.Slides for .NET segítségével könnyebbé teszi. Ez a könyvtár leegyszerűsíti a diagramok létrehozásának és módosításának folyamatát a PowerPoint-bemutatókon belül.

Ebben az oktatóanyagban megtanulod, hogyan használhatod az Aspose.Slides for .NET programot halmozott oszlopdiagramok létrehozására a semmiből, és hogyan szabhatod testre azokat százalékos értékek adatcímkékként való megjelenítésével. A következő lépéseket követve pontos és vizuálisan vonzó adatábrázolással gazdagíthatod a diákat.

**Amit tanulni fogsz:**
- Az Aspose.Slides inicializálása .NET-hez
- Halmozott oszlopdiagram létrehozása
- Százalékok kiszámítása és megjelenítése az adatfeliratokon
- A diagramteljesítmény optimalizálásának ajánlott gyakorlatai

Mielőtt belevágnánk a megvalósításba, győződjünk meg arról, hogy minden elő van készítve a kezdéshez.

## Előfeltételek

A bemutató hatékony követéséhez győződjön meg róla, hogy rendelkezik a következőkkel:
- **.NET Core SDK** telepítve a gépedre.
- C# és .NET alkalmazásfejlesztés alapjai.
- Visual Studio vagy hasonló IDE C# kód írásához és futtatásához.

Diagramok létrehozásához szükséged lesz az Aspose.Slides for .NET programra, ezért győződj meg róla, hogy az alább leírtak szerint van beállítva.

## Az Aspose.Slides beállítása .NET-hez

Az Aspose.Slides for .NET egy hatékony könyvtár, amely lehetővé teszi a PowerPoint-bemutatók programozott kezelését. Így adhatod hozzá a projektedhez:

### Telepítés

**.NET parancssori felület:**
```bash
dotnet add package Aspose.Slides
```

**Csomagkezelő konzol:**
```powershell
Install-Package Aspose.Slides
```

**NuGet csomagkezelő felhasználói felület:** 
- Nyisd meg a NuGet csomagkezelőt, és keresd meg az „Aspose.Slides” kifejezést. Telepítsd a legújabb verziót.

### Licencszerzés

Az Aspose.Slides teljes kihasználásához kezdje egy ingyenes próbaverzióval. Hosszabb használat esetén érdemes lehet ideiglenes licencet beszerezni, vagy megvásárolni egyet a következő címről: [Aspose](https://purchase.aspose.com/buy)Kövesd az irányelveiket a licenced beállításához a projektkörnyezetedben.

### Alapvető inicializálás

Telepítés után inicializálja a `Presentation` osztály a diák létrehozásának megkezdéséhez:
```csharp
using Aspose.Slides;

// Presentation osztálypéldány inicializálása
tPresentation presentation = new Presentation();
```

Most pedig térjünk át a diagramkészítő és testreszabási funkció megvalósítására az Aspose.Slides for .NET használatával.

## Megvalósítási útmutató

### Halmozott oszlopdiagram létrehozása

célunk egy halmozott oszlopdiagram létrehozása és testreszabása százalékos értékek adatcímkékként való megjelenítésével. Így teheti meg:

#### A prezentáció inicializálása

Kezdje egy példány létrehozásával `Presentation`:
```csharp
using Aspose.Slides;

// Presentation osztálypéldány inicializálása
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Diagram hozzáadása a diához

Halmozott oszlopdiagram hozzáadása az első diához a megadott koordinátákkal és méretekkel:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Ez a vonal létrehoz egy `StackedColumn` diagram a (20, 20) pozícióban, 400 szélességgel és magassággal.

#### Összesített értékek kiszámítása százalékos számításhoz

A százalékos értékek megjelenítéséhez számítsa ki az egyes kategóriák teljes értékét az összes sorozatban:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Összeadja az összes sorozat értékeit minden kategóriában
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Adatcímkék testreszabása százalékos értékek megjelenítéséhez

Ezután ismételje meg az egyes sorozatokat, és szabja testre az adatcímkéket:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Százalék kiszámítása
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Tiszta szöveg az átfedés elkerülése érdekében
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Címkeformátum konfigurálása az alapértelmezett adatfeliratok elrejtéséhez
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Ez a szakasz kiszámítja az egyes adatpontok százalékos értékét, és egyéni címkeként állítja be azokat, biztosítva, hogy ne legyen átfedés az alapértelmezett címkékkel.

#### Mentse el a prezentációt

Végül mentse el a prezentációt az eredmény megtekintéséhez:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Gyakorlati alkalmazások

A százalékos értékek diagramokon való megjelenítése különösen hasznos lehet az alábbi esetekben:
1. **Pénzügyi jelentéstétel:** A portfólió eloszlásának vagy a befektetési hozamok százalékos formában történő megjelenítése.
2. **Értékesítési elemzés:** A piaci részesedési adatokat százalékos formában jelenítse meg a régiók közötti teljesítmény kiemelése érdekében.
3. **Felmérés eredményei:** A jobb vizuális összehasonlítás érdekében százalékos formában jelenítse meg a felmérésre adott válaszokat.
4. **Projektmenedzsment:** Használjon százalékos arányokat tartalmazó kördiagramokat az erőforrás-elosztás szemléltetésére.
5. **Oktatás:** Magyarázd el a statisztikai fogalmakat világos, százalékos alapú vizuális ábrázolás segítségével.

Ezen testreszabott diagramok integrálása olyan rendszerekbe, mint a CRM vagy az ERP, javíthatja az irányítópultok és jelentések minőségét, segítve a döntéshozatali folyamatokat.

## Teljesítménybeli szempontok

Az Aspose.Slides for .NET használatakor, különösen nagy adathalmazok esetén:
- **Memóriakezelés:** A memória felszabadításához megfelelően szabaduljon meg a prezentációs objektumoktól. `using` nyilatkozatok, ahol alkalmazható.
- **Hatékony adatkezelés:** A számításokat lehetőség szerint ciklusokon kívül végezzük a számítási terhelés csökkentése érdekében.
- **Terheléselosztás:** Webes alkalmazások esetén gondoskodjon arról, hogy a szerver erőforrásai megfelelően legyenek kiépítve az egyidejű diagramgenerálási kérelmekhez.

## Következtetés

Ez az oktatóanyag az Aspose.Slides for .NET használatával diagramok létrehozását és testreszabását ismertette százalékos értékek címkékként való megjelenítésével. Ezen technikák elsajátításával részletes és vizuálisan vonzó adatábrázolásokkal gazdagíthatja prezentációit.

Következő lépésként fedezd fel az Aspose.Slides-ban elérhető egyéb diagramtípusokat és testreszabási lehetőségeket. Kísérletezz különböző adathalmazokkal, hogy hatékony vizuális elemekké alakítsd őket, amelyek világosan közvetítik az információkat.

## GYIK szekció

**1. kérdés: Hogyan kezelhetek nagy adathalmazokat diagramok létrehozásakor az Aspose.Slides for .NET segítségével?**
A1: Nagy adathalmazok esetén optimalizálja a számításokat és használjon hatékony memóriakezelési technikákat. Bontsa le a feldolgozási feladatokat a memória túlterhelésének elkerülése érdekében.

**2. kérdés: Használhatom az Aspose.Slides for .NET-et egy webes alkalmazásban?**
A2: Igen, integrálható ASP.NET alkalmazásokba. Az optimális teljesítmény érdekében gondoskodjon a megfelelő szervererőforrás-elosztásról.

**3. kérdés: Lehetséges az Aspose.Slides segítségével létrehozott diagramokat más formátumokba exportálni?**
V3: Természetesen! A testreszabott diagramokat tartalmazó prezentációkat különféle formátumokba, például PDF-be és képfájlokba exportálhatja a könyvtár képességeinek használatával.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}