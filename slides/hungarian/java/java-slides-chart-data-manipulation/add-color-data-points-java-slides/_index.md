---
"description": "Tanuld meg, hogyan adhatsz színt adatpontokhoz Java diákon az Aspose.Slides for Java használatával."
"linktitle": "Szín hozzáadása adatpontokhoz Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Szín hozzáadása adatpontokhoz Java diákban"
"url": "/hu/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Szín hozzáadása adatpontokhoz Java diákban


## Bevezetés a Java diák adatpontjainak színezésébe

Ebben az oktatóanyagban bemutatjuk, hogyan adhatsz színt a Java diák adatpontjaihoz az Aspose.Slides for Java segítségével. Ez a lépésről lépésre bemutatott útmutató forráskód-példákat is tartalmaz, amelyek segítenek a feladat elvégzésében.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- Java fejlesztői környezet
- Aspose.Slides Java könyvtárhoz

## 1. lépés: Új prezentáció létrehozása

Először is létrehozunk egy új prezentációt az Aspose.Slides for Java használatával. Ez a prezentáció fog szolgálni a diagramunk tárolójaként.

```java
Presentation pres = new Presentation();
```

## 2. lépés: Napkitöréses diagram hozzáadása

Most adjunk hozzá egy Sunburst diagramot a prezentációhoz. Megadjuk a diagram típusát, pozícióját és méretét.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## 3. lépés: Hozzáférés az adatpontokhoz

diagram adatpontjainak módosításához hozzá kell férnünk a `IChartDataPointCollection` objektum.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## 4. lépés: Adatpontok testreszabása

Ebben a lépésben meghatározott adatpontokat fogunk testre szabni. Itt az adatpontok színét módosítjuk és a címkebeállításokat konfiguráljuk.

```java
// 0. adatpont testreszabása
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// 9. adatpont testreszabása
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## 5. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a testreszabott diagrammal.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Ennyi! Sikeresen színt adtál hozzá bizonyos adatpontokhoz egy Java dián az Aspose.Slides for Java használatával.

## Teljes forráskód a Java diák adatpontjainak színezéséhez

```java
Presentation pres = new Presentation();
try
{
	// A dokumentumok könyvtárának elérési útja.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//TENNIVALÓ
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultad, hogyan adhatsz színt a Java diák adatpontjaihoz az Aspose.Slides for Java segítségével. A diagramokat és prezentációkat a saját igényeidnek megfelelően tovább testreszabhatod.

## GYIK

### Hogyan tudom megváltoztatni más adatpontok színét?

Más adatpontok színének módosításához a 4. lépésben bemutatotthoz hasonló megközelítést követhet. Nyissa meg a testreszabni kívánt adatpontot, és módosítsa a szín- és címkebeállításait.

### Testreszabhatom a diagram más aspektusait?

Igen, testreszabhatja a diagram különböző aspektusait, beleértve a betűtípusokat, címkéket, címeket és egyebeket. Lásd a [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/) részletes testreszabási lehetőségekért.

### Hol találok további példákat és dokumentációt?

További példákat és részletes dokumentációt az Aspose.Slides Java-ban való használatáról a következő címen talál: [Aspose.Slides dokumentáció](https://reference.aspose.com/slides/java/) weboldal.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}