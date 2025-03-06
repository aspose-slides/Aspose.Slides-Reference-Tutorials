---
title: Speciális diagram testreszabása az Aspose.Slides-ben
linktitle: Speciális diagram testreszabása az Aspose.Slides-ben
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg a grafikonok speciális testreszabását az Aspose.Slides for .NET alkalmazásban. Hozzon létre látványos diagramokat lépésről lépésre.
weight: 10
url: /hu/net/advanced-chart-customization/advanced-chart-customization/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Speciális diagram testreszabása az Aspose.Slides-ben


A tetszetős és informatív diagramok létrehozása számos alkalmazásban az adatmegjelenítés elengedhetetlen része. Az Aspose.Slides for .NET robusztus eszközöket kínál a diagramok testreszabásához, lehetővé téve a diagramok minden aspektusának finomhangolását. Ebben az oktatóanyagban az Aspose.Slides for .NET használatával fejlett diagram-testreszabási technikákat fedezünk fel.

## Előfeltételek

Mielőtt belevágna az Aspose.Slides for .NET segítségével végzett diagramok speciális testreszabásába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1. Aspose.Slides for .NET Library: Az Aspose.Slides könyvtárat telepíteni kell és megfelelően konfigurálni kell a .NET-projektben. Letöltheti innen[itt](https://releases.aspose.com/slides/net/).

2. .NET fejlesztői környezet: Be kell állítania egy .NET fejlesztői környezetet, beleértve a Visual Studio-t vagy bármely más választott IDE-t.

3. Alapvető C# ismerete: Hasznos lesz a C# programozási nyelv ismerete, hiszen C# kódot fogunk írni az Aspose.Slides programhoz.

Most bontsuk le a speciális diagram testreszabását több lépésre, amelyek végigvezetik Önt a folyamaton.

## 1. lépés: Hozzon létre egy prezentációt

Először hozzon létre egy új prezentációt az Aspose.Slides segítségével.

```csharp
// A dokumentumok könyvtárának elérési útja.
string dataDir = "Your Document Directory";

// Hozzon létre könyvtárat, ha még nincs jelen.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Példányos bemutató
Presentation pres = new Presentation();
```

Ebben a lépésben új prezentációt kezdeményezünk, amely megtartja a diagramunkat.

## 2. lépés: Nyissa meg az első diát

Ezután nyissa meg a bemutató első diáját, amelyhez hozzá szeretné adni a diagramot.

```csharp
// Az első dia elérése
ISlide slide = pres.Slides[0];
```

Ez a kódrészlet lehetővé teszi, hogy a bemutató első diájával dolgozzon.

## 3. lépés: Mintadiagram hozzáadása

Most adjunk hozzá egy mintadiagramot a diához. Ebben a példában vonaldiagramot hozunk létre markerekkel.

```csharp
// A minta diagram hozzáadása
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Itt adjuk meg a diagram típusát (LineWithMarkers), valamint annak helyzetét és méreteit a dián.

## 4. lépés: A diagram címének beállítása

Adjunk meg egy címet a diagramnak, hogy kontextust biztosítsunk.

```csharp
// A diagram címének beállítása
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

Ez a kód címet ad a diagramhoz, megadva annak szövegét, megjelenését és betűstílusát.

## 5. lépés: A főbb rácsvonalak testreszabása

Most pedig szabjuk testre az értéktengely főbb rácsvonalait.

```csharp
// A főbb rácsvonalak formátumának beállítása az értéktengelyhez
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Ez a lépés konfigurálja a főbb rácsvonalak megjelenését az értéktengelyen.

## 6. lépés: A kisebb rácsvonalak testreszabása

Hasonlóképpen testreszabhatjuk a kisebb rácsvonalakat az értéktengelyhez.

```csharp
// Kisebb rácsvonalak formátumának beállítása az értéktengelyhez
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Ez a kód beállítja a kisebb rácsvonalak megjelenését az értéktengelyen.

## 7. lépés: Határozza meg az értéktengely számformátumát

Szabja testre az értéktengely számformátumát.

```csharp
// Beállítási érték tengelyszám formátum
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Ez a lépés lehetővé teszi az értéktengelyen megjelenő számok formázását.

## 8. lépés: Állítsa be a diagram maximális és minimális értékét

Határozza meg a diagram maximális és minimális értékét.

```csharp
// Beállítási diagram maximum, minimum értékek
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

Itt adhatja meg a diagram tengelyének megjelenítendő értéktartományt.

## 9. lépés: Az értéktengely szövegtulajdonságainak testreszabása

Az értéktengely szövegtulajdonságait is testreszabhatja.

```csharp
// Értéktengely szövegtulajdonságainak beállítása
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Ez a kód lehetővé teszi az értéktengely-címkék betűstílusának és megjelenésének beállítását.

## 10. lépés: Adja hozzá az értéktengely címét

Ha a diagram címet igényel az értéktengelyhez, akkor ezzel a lépéssel felveheti azt.

```csharp
// Beállítási érték tengely címe
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

Ebben a lépésben beállíthat egy címet az értéktengelyhez.

## 11. lépés: A főbb rácsvonalak testreszabása a kategóriatengelyhez

Most koncentráljunk a kategóriatengely főbb rácsvonalaira.

```csharp
// A főbb rácsvonalak formátumának beállítása a kategória tengelyhez
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Ez a kód konfigurálja a főbb rácsvonalak megjelenését a kategória tengelyén.

## 12. lépés: A kisebb rácsvonalak testreszabása a kategóriatengelyhez

Az értéktengelyhez hasonlóan testreszabhatja a kisebb rácsvonalakat a kategóriatengelyhez.

```csharp
// Kisebb rácsvonalak formátumának beállítása a kategória tengelyhez
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Itt állíthatja be a kisebb rácsvonalak megjelenését a kategória tengelyén.

## 13. lépés: A kategóriatengely szövegtulajdonságainak testreszabása

Szabja testre a kategóriatengely-címkék szövegtulajdonságait.

```csharp
// Kategória tengely szövegtulajdonságainak beállítása
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Ez a kód lehetővé teszi a kategóriatengely-címkék betűstílusának és megjelenésének beállítását.

## 14. lépés: Adja hozzá a kategória tengely címét

Szükség esetén címet is hozzáadhat a kategóriatengelyhez.

```csharp
// Kategória címének beállítása
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

Ebben a lépésben beállíthat egy címet a kategóriatengelyhez.

## 15. lépés: További testreszabások

További testreszabási lehetőségeket is felfedezhet, például a legendákat, a diagram hátfalát, a padlót és a terület színeit. Ezek a testreszabások lehetővé teszik diagramja vizuális vonzerejének fokozását.

```csharp
// További testreszabások (opcionális)

// Jelmagyarázatok szövegtulajdonságainak beállítása
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Állítsa be a diagram jelmagyarázatait átfedő diagram nélkül
chart.Legend.Overlay = true;

// Az első sorozat ábrázolása a másodlagos értéktengelyen (ha szükséges)
// Chart.ChartData.Series[0].PlotOnSecondAxis = igaz;

// Beállítási táblázat hátsó fal színe
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// A táblázat padlószínének beállítása
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// telekterület színének beállítása
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Mentse el a bemutatót
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Ezek a további testreszabások nem kötelezőek, és a diagram tervezési követelményei alapján alkalmazhatók.

## Következtetés

Ebben a lépésről lépésre bemutatott útmutatóban megvizsgáltuk a diagramok speciális testreszabását az Aspose.Slides for .NET használatával. Megtanulta, hogyan hozhat létre prezentációt, hogyan adhat hozzá diagramot és finomhangolhatja a megjelenését, beleértve a rácsvonalakat, tengelycímkéket és egyéb vizuális elemeket. Az Aspose.Slides által biztosított hatékony testreszabási lehetőségekkel olyan diagramokat hozhat létre, amelyek hatékonyan továbbítják adatait, és bevonják a közönséget.

 Ha bármilyen kérdése van, vagy bármilyen kihívásba ütközik az Aspose.Slides for .NET programozása során, bátran tekintse meg a dokumentációt[itt](https://reference.aspose.com/slides/net/) vagy kérjen segítséget az Aspose.Slides-ben[fórum](https://forum.aspose.com/).

## GYIK

### A .NET mely verzióit támogatja az Aspose.Slides for .NET?
Az Aspose.Slides for .NET különféle .NET-verziókat támogat, beleértve a .NET-keretrendszert és a .NET Core-t. A támogatott verziók teljes listáját a dokumentációban találja.

### Létrehozhatok diagramokat adatforrásokból, például Excel-fájlokból az Aspose.Slides for .NET használatával?
Igen, az Aspose.Slides for .NET lehetővé teszi diagramok létrehozását külső adatforrásokból, például Excel-táblázatokból. A dokumentációban részletes példákat találhat.

### Hogyan adhatok egyéni adatcímkéket diagramsorozatomhoz?
 Ha egyéni adatcímkéket szeretne hozzáadni diagramsorozatához, elérheti a`DataLabels` a sorozat tulajdonságait, és szükség szerint testreszabhatja a címkéket. A kódmintákat és példákat a dokumentációban találja.

### Exportálható a diagram különböző fájlformátumokba, például PDF vagy képformátumokba?
Igen, az Aspose.Slides for .NET lehetőséget biztosít a diagramokkal ellátott prezentáció exportálására különféle formátumokba, beleértve a PDF- és képformátumokat. A könyvtár segítségével elmentheti munkáját a kívánt kimeneti formátumban.

### Hol találok további oktatóanyagokat és példákat az Aspose.Slides for .NET-hez?
 Rengeteg oktatóanyagot, kódpéldát és dokumentációt találhat az Aspose.Slides oldalon[weboldal](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
