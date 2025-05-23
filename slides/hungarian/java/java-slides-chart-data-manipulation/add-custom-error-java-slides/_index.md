---
"description": "Tanuld meg, hogyan adhatsz hozzá egyéni hibasávokat PowerPoint-diagramokhoz Java Slides-ben az Aspose.Slides használatával. Lépésről lépésre útmutató forráskóddal a precíz adatvizualizációhoz."
"linktitle": "Egyéni hiba hozzáadása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Egyéni hiba hozzáadása Java diákban"
"url": "/hu/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Egyéni hiba hozzáadása Java diákban


## Bevezetés az egyéni hibasávok hozzáadásához Java diákban az Aspose.Slides használatával

Ebben az oktatóanyagban megtanulod, hogyan adhatsz hozzá egyéni hibasávokat egy PowerPoint-bemutató diagramjához az Aspose.Slides for Java segítségével. A hibasávok hasznosak az adatpontok változékonyságának vagy bizonytalanságának megjelenítésére egy diagramon.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:

- Az Aspose.Slides for Java könyvtár telepítve és konfigurálva van a projektedben.
- Java fejlesztői környezet beállítása.

## 1. lépés: Hozz létre egy üres prezentációt

Először hozz létre egy üres PowerPoint bemutatót.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
```

## 2. lépés: Buborékdiagram hozzáadása

Ezután hozzáadunk egy buborékdiagramot a prezentációhoz.

```java
// Buborékdiagram létrehozása
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## 3. lépés: Egyéni hibasávok hozzáadása

Most adjunk hozzá egyéni hibasávokat a diagramsorozathoz.

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

## 4. lépés: Hibasáv-adatok beállítása

Ebben a lépésben hozzáférünk a diagramsorozat adatpontjaihoz, és beállítjuk az egyéni hibasávok értékeit minden ponthoz.

```java
// Diagramsorozat adatpontjainak elérése és az egyes pontok hibasávjainak értékeinek beállítása
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Diagramsorozat pontjainak hibasávjainak beállítása
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

Ez minden! Sikeresen hozzáadtál egyéni hibasávokat egy PowerPoint-bemutató diagramjához az Aspose.Slides for Java használatával.

## Teljes forráskód az egyéni hiba hozzáadásához Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Üres prezentáció létrehozása
Presentation presentation = new Presentation();
try
{
	// Buborékdiagram létrehozása
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Egyéni hibasávok hozzáadása és formátumuk beállítása
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Diagramsorozat adatpontjainak elérése és az egyes pontok hibasávjainak értékeinek beállítása
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Diagramsorozat pontjainak hibasávjainak beállítása
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

Ebben az átfogó oktatóanyagban megtanultad, hogyan teheted jobbá PowerPoint-bemutatóidat egyéni hibasávok hozzáadásával a diagramokhoz az Aspose.Slides for Java segítségével. A hibasávok értékes betekintést nyújtanak az adatok változékonyságába és bizonytalanságába, így a diagramok informatívabbá és vizuálisan vonzóbbá válnak.

## GYIK

### Hogyan szabhatom testre a hibasávok megjelenését?

A hibasávok megjelenését testreszabhatja a tulajdonságaik módosításával. `IErrorBarsFormat` objektum, például vonalstílus, vonalszín és hibasáv szélessége.

### Hozzáadhatok hibasávokat más diagramtípusokhoz?

Igen, hibasávokat adhatsz hozzá az Aspose.Slides for Java által támogatott különféle diagramtípusokhoz, beleértve az oszlopdiagramokat, vonaldiagramokat és szóródási diagramokat.

### Hogyan állíthatok be különböző hibasáv értékeket az egyes adatpontokhoz?

Végigjárhatja az adatpontokat, és egyéni hibasáv-értékeket állíthat be minden ponthoz, a fenti kódban látható módon.

### Lehetséges elrejteni a hibasávokat bizonyos adatpontoknál?

Igen, az egyes adatpontok hibasávjainak láthatóságát a következő beállítással szabályozhatja: `setVisible` a tulajdona `IErrorBarsFormat` objektum.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}