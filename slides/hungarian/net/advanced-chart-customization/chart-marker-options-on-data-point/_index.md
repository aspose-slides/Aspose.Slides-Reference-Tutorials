---
"description": "Tanuld meg, hogyan gazdagíthatod PowerPoint-diagramjaidat az Aspose.Slides for .NET segítségével. Testreszabhatod az adatpont-jelölőket képekkel. Készíthetsz lebilincselő prezentációkat."
"linktitle": "Diagramjelölő beállítások az adatponton"
"second_title": "Aspose.Slides .NET PowerPoint feldolgozási API"
"title": "Diagramjelölő opciók használata adatpontokon az Aspose.Slides .NET-ben"
"url": "/hu/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramjelölő opciók használata adatpontokon az Aspose.Slides .NET-ben


Prezentációk és adatvizualizációk készítésekor az Aspose.Slides for .NET számos hatékony funkciót kínál diagramok létrehozásához, testreszabásához és kezeléséhez. Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan használhatjuk a diagramjelölő opciókat adatpontokon a diagramprezentációk javítása érdekében. Ez a lépésről lépésre szóló útmutató végigvezeti Önt a folyamaton, az előfeltételektől és a névterek importálásától kezdve az egyes példák több lépésre bontásáig.

## Előfeltételek

Mielőtt belemerülnénk a diagramjelölők adatpontokon való használatába, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

- Aspose.Slides .NET-hez: Győződjön meg róla, hogy telepítve van az Aspose.Slides .NET-hez. Letöltheti innen: [weboldal](https://releases.aspose.com/slides/net/).

- Minta prezentáció: Ebben az oktatóanyagban egy „Test.pptx” nevű minta prezentációt fogunk használni. Ennek a prezentációnak a dokumentumkönyvtáradban kell lennie.

Most pedig kezdjük a szükséges névterek importálásával.

## Névterek importálása

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Importáltuk a szükséges névtereket és inicializáltuk a prezentációnkat. Most pedig folytassuk a diagramjelölő opciók használatával az adatpontokon.

## 1. lépés: Az alapértelmezett diagram létrehozása

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Az alapértelmezett diagram létrehozása
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Létrehozunk egy alapértelmezett „LineWithMarkers” típusú diagramot a dián a megadott helyen és méretben.

## 2. lépés: Az alapértelmezett diagramadat-munkalap indexének lekérése

```csharp
// Az alapértelmezett diagramadat-munkalap indexének lekérése
int defaultWorksheetIndex = 0;
```

Itt megkapjuk az alapértelmezett diagramadat-munkalap indexét.

## 3. lépés: A diagramadat-munkalap beszerzése

```csharp
// A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Lekérjük a diagramadatokkal foglalkozó munkafüzetet, hogy diagramadatokkal dolgozhassunk.

## 4. lépés: A diagramsorozat módosítása

```csharp
// Demósorozat törlése
chart.ChartData.Series.Clear();

// Új sorozat hozzáadása
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Ebben a lépésben eltávolítjuk a meglévő demó sorozatokat, és hozzáadunk egy új, „1. sorozat” nevű sorozatot a diagramhoz.

## 5. lépés: Képkitöltés beállítása adatpontokhoz

```csharp
// Jelölők képének beállítása
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Vegyük az első slágerlista-sorozatot
IChartSeries series = chart.ChartData.Series[0];

// Új adatpontok hozzáadása képkitöltéssel
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Képjelölőket állítunk be az adatpontokhoz, így testreszabhatja az egyes adatpontok megjelenését a diagramon.

## 6. lépés: A diagramsorozat-jelölő méretének módosítása

```csharp
// Diagramsorozat-jelölő méretének módosítása
series.Marker.Size = 15;
```

Itt a diagramsorozat-jelölő méretét állítjuk be, hogy vizuálisan vonzóbb legyen.

## 7. lépés: A prezentáció mentése

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Végül mentjük a prezentációt az új diagrambeállításokkal.

## Következtetés

Az Aspose.Slides for .NET segítségével lenyűgöző diagramos prezentációkat hozhatsz létre különféle testreszabási lehetőségekkel. Ebben az oktatóanyagban a diagramjelölők adatpontokon való használatára összpontosítottunk az adatok vizuális ábrázolásának javítása érdekében. Az Aspose.Slides for .NET segítségével prezentációidat a következő szintre emelheted, még lebilincselőbbé és informatívabbá teheted őket.

Ha bármilyen kérdése van, vagy segítségre van szüksége az Aspose.Slides for .NET programmal kapcsolatban, látogasson el a következő oldalra: [Aspose.Slides dokumentáció](https://reference.aspose.com/slides/net/) vagy forduljon a [Aspose közösség](https://forum.aspose.com/) támogatásért.

## Gyakran Ismételt Kérdések (GYIK)

### Használhatok egyéni képeket adatpontok jelölőjeként az Aspose.Slides for .NET-ben?
Igen, egyéni képeket használhatsz adatpontok jelölőjeként az Aspose.Slides for .NET-ben, ahogy azt ebben az oktatóanyagban is bemutatjuk.

### Hogyan tudom megváltoztatni a diagram típusát az Aspose.Slides for .NET programban?
A diagram típusát egy másik megadásával módosíthatja `ChartType` a diagram létrehozásakor, például „Oszlop”, „Kördiagram” vagy „Terület”.

### Kompatibilis az Aspose.Slides for .NET a PowerPoint legújabb verzióival?
Az Aspose.Slides for .NET-et úgy tervezték, hogy különféle PowerPoint formátumokkal működjön, és rendszeresen frissül a legújabb PowerPoint verziókkal való kompatibilitás fenntartása érdekében.

### Hol találok további oktatóanyagokat és forrásokat az Aspose.Slides for .NET-hez?
További oktatóanyagokat és forrásokat találhatsz a következő helyen: [Aspose.Slides dokumentáció](https://reference.aspose.com/slides/net/).

### Van elérhető próbaverzió az Aspose.Slides .NET-hez?
Igen, kipróbálhatja az Aspose.Slides for .NET programot egy ingyenes próbaverzió letöltésével innen: [itt](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}