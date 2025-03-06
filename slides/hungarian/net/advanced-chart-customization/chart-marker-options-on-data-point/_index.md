---
title: Diagramjelölő-beállítások használata az adatponton az Aspose.Slides .NET-ben
linktitle: Diagramjelölő beállításai az adatponton
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan javíthatja PowerPoint diagramjait az Aspose.Slides for .NET segítségével. Testreszabhatja az adatpontjelzőket képekkel. Hozzon létre vonzó prezentációkat.
weight: 11
url: /hu/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Diagramjelölő-beállítások használata az adatponton az Aspose.Slides .NET-ben


Amikor prezentációkkal és adatvizualizációval dolgozik, az Aspose.Slides for .NET hatékony funkciók széles skáláját kínálja diagramok létrehozásához, testreszabásához és kezeléséhez. Ebben az oktatóanyagban megvizsgáljuk, hogyan használhatja a diagramjelölő-beállításokat az adatpontokon a diagrambemutatók javítása érdekében. Ez a lépésenkénti útmutató végigvezeti a folyamaton, kezdve az előfeltételektől és a névterek importálásától az egyes példák több lépésre bontásáig.

## Előfeltételek

Mielőtt belemerülnénk a diagramjelölő-beállítások használatába az adatpontokon, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

-  Aspose.Slides for .NET: Győződjön meg arról, hogy az Aspose.Slides for .NET telepítve van. Letöltheti a[weboldal](https://releases.aspose.com/slides/net/).

- Prezentációs minta: Ehhez az oktatóanyaghoz a „Test.pptx” nevű mintabemutatót használjuk. Ennek a bemutatónak a dokumentumkönyvtárában kell lennie.

Most kezdjük a szükséges névterek importálásával.

## Névterek importálása

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Importáltuk a szükséges névtereket, és inicializáltuk a bemutatónkat. Most folytassuk a diagramjelölő opciók használatát az adatpontokon.

## 1. lépés: Az alapértelmezett diagram létrehozása

```csharp

// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Az alapértelmezett diagram létrehozása
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Létrehozunk egy alapértelmezett "LineWithMarkers" típusú diagramot a dián egy megadott helyen és méretben.

## 2. lépés: Az alapértelmezett diagramadat-munkalapindex beszerzése

```csharp
// Az alapértelmezett diagramadat-munkalapindex lekérése
int defaultWorksheetIndex = 0;
```

Itt megkapjuk az alapértelmezett diagram adatlap indexét.

## 3. lépés: A diagram adatlap beszerzése

```csharp
// A diagram adatlapjának lekérése
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Lekérjük a diagramadatok munkafüzetét, hogy dolgozzon a diagramadatokkal.

## 4. lépés: A diagramsorozat módosítása

```csharp
// Demósorozat törlése
chart.ChartData.Series.Clear();

// Új sorozat hozzáadása
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Ebben a lépésben eltávolítunk minden meglévő demósorozatot, és hozzáadunk egy új „Series 1” nevű sorozatot a diagramhoz.

## 5. lépés: Képkitöltés beállítása adatpontokhoz

```csharp
// Állítsa be a képet a jelölőkhöz
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Vegyük az első diagramsorozatot
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

Az adatpontokhoz képjelzőket állítunk be, amelyek lehetővé teszik az egyes adatpontok diagramon való megjelenésének testreszabását.

## 6. lépés: A diagramsorozat-jelölő méretének módosítása

```csharp
// A diagramsorozat-jelölő méretének módosítása
series.Marker.Size = 15;
```

Itt beállítjuk a diagramsorozat-jelölő méretét, hogy vizuálisan vonzó legyen.

## 7. lépés: A prezentáció mentése

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Végül elmentjük a prezentációt az új diagrambeállításokkal.

## Következtetés

Az Aspose.Slides for .NET lehetővé teszi, hogy lenyűgöző diagramprezentációkat készítsen különféle testreszabási lehetőségekkel. Ebben az oktatóanyagban arra összpontosítottunk, hogy az adatpontokon diagramjelölő-beállításokat használjunk, hogy javítsuk az adatok vizuális megjelenítését. A .NET-hez készült Aspose.Slides segítségével prezentációit a következő szintre emelheti, így vonzóbbá és informatívabbá teheti azokat.

Ha bármilyen kérdése van, vagy segítségre van szüksége az Aspose.Slides for .NET-hez kapcsolódóan, keresse fel a[Aspose.Slides dokumentáció](https://reference.aspose.com/slides/net/) vagy nyúljon a[Aspose közösség](https://forum.aspose.com/) támogatásért.

## Gyakran Ismételt Kérdések (GYIK)

### Használhatok egyéni képeket adatpontok jelölőiként az Aspose.Slides for .NET-ben?
Igen, az Aspose.Slides for .NET alkalmazásban egyéni képeket használhat adatpontok jelölőiként, amint az ebben az oktatóanyagban látható.

### Hogyan módosíthatom a diagram típusát az Aspose.Slides for .NET-ben?
 A diagram típusát egy másik megadásával módosíthatja`ChartType` a diagram létrehozásakor, például „Sáv”, „Korta” vagy „Terület”.

### Az Aspose.Slides for .NET kompatibilis a PowerPoint legújabb verzióival?
Az Aspose.Slides for .NET úgy lett kialakítva, hogy különböző PowerPoint-formátumokkal működjön, és rendszeresen frissítik a legújabb PowerPoint-verziókkal való kompatibilitás fenntartása érdekében.

### Hol találok további oktatóanyagokat és forrásokat az Aspose.Slides for .NET-hez?
 További oktatóanyagokat és forrásokat fedezhet fel a[Aspose.Slides dokumentáció](https://reference.aspose.com/slides/net/).

### Elérhető az Aspose.Slides .NET-hez készült próbaverziója?
 Igen, kipróbálhatja az Aspose.Slides for .NET alkalmazást, ha letölt egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
