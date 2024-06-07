---
title: Egyéni hiba hozzáadása a Java Slides-hez
linktitle: Egyéni hiba hozzáadása a Java Slides-hez
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan adhat egyéni hibasávokat a Java Slides PowerPoint diagramjaihoz az Aspose.Slides segítségével. Lépésről lépésre útmutató forráskóddal az adatok pontos megjelenítéséhez.
type: docs
weight: 11
url: /hu/java/chart-data-manipulation/add-custom-error-java-slides/
---

## Bevezetés az egyéni hibasávok hozzáadásához Java Slides-ben az Aspose.Slides használatával

Ebből az oktatóanyagból megtudhatja, hogyan adhat egyéni hibasávokat egy PowerPoint-prezentáció diagramjához az Aspose.Slides for Java segítségével. A hibasávok hasznosak a diagram adatpontjaiban lévő változékonyság vagy bizonytalanság megjelenítéséhez.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Aspose.Slides for Java könyvtár telepítve és konfigurálva a projektben.
- Java fejlesztői környezet beállítva.

## 1. lépés: Hozzon létre egy üres prezentációt

Először hozzon létre egy üres PowerPoint-prezentációt.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
```

## 2. lépés: Buborékdiagram hozzáadása

Ezután egy buborékdiagramot adunk a bemutatóhoz.

```java
// Buborékdiagram készítése
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## 3. lépés: Adjon hozzá egyéni hibasávokat

Most adjunk egyéni hibasávokat a diagramsorozathoz.

```java
// Egyéni hibasávok hozzáadása és formátumuk beállítása
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## 4. lépés: Állítsa be a hibasávok adatait

Ebben a lépésben hozzáférünk a diagramsorozat adatpontjaihoz, és minden ponthoz beállítjuk az egyéni hibasávok értékeit.

```java
// Diagramsorozat adatpontjainak elérése és hibasávok értékeinek beállítása az egyes pontokhoz
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Hibasávok beállítása diagramsorozat-pontokhoz
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## 5. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt az egyéni hibasávokkal.

```java
// Prezentáció mentése
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen hozzáadott egyéni hibasávokat egy PowerPoint-prezentáció diagramjához az Aspose.Slides for Java segítségével.

## A Java Slides egyéni hibájának hozzáadása teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
try
{
	// Buborékdiagram készítése
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Egyéni hibasávok hozzáadása és formátumának beállítása
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Diagramsorozat adatpont elérése és hibasávok értékeinek beállítása az egyes pontokhoz
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Hibasávok beállítása diagramsorozat-pontokhoz
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Prezentáció mentése
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebben az átfogó oktatóanyagban megtanulta, hogyan javíthatja PowerPoint-prezentációit egyéni hibasávok hozzáadásával a diagramokhoz az Aspose.Slides for Java segítségével. A hibasávok értékes betekintést nyújtanak az adatok változékonyságába és bizonytalanságába, így a diagramok informatívabbak és látványosabbak.

## GYIK

### Hogyan szabhatom testre a hibasávok megjelenését?

 Testreszabhatja a hibasávok megjelenését a tulajdonságok módosításával`IErrorBarsFormat` objektum, például vonalstílus, vonalszín és hibasáv szélessége.

### Hozzáadhatok hibasávokat más diagramtípusokhoz?

Igen, felvehet hibasávokat az Aspose.Slides for Java által támogatott különféle diagramtípusokhoz, beleértve a sávdiagramokat, vonaldiagramokat és szóródiagramokat.

### Hogyan állíthatok be különböző hibasáv-értékeket az egyes adatpontokhoz?

Az adatpontok között hurkolhat, és minden ponthoz egyéni hibasáv-értékeket állíthat be, a fenti kód szerint.

### Lehetséges-e elrejteni a hibasávokat bizonyos adatpontokhoz?

Igen, szabályozhatja az egyes adatpontok hibasávjainak láthatóságát a`setVisible` tulajdona a`IErrorBarsFormat` tárgy.