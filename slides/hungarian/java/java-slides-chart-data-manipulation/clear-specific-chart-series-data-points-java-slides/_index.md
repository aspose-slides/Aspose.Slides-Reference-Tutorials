---
title: Adott diagramsorozat adatpontok adatainak törlése a Java diákban
linktitle: Adott diagramsorozat adatpontok adatainak törlése a Java diákban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan törölhet adott adatpontokat egy diagramsorozatból a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal a hatékony adatvizualizációs kezeléshez.
weight: 15
url: /hu/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Adott diagramsorozat adatpontok adatainak törlése a Java diákban


## Bevezetés a specifikus diagramsorozat adatpontjainak törléséhez a Java diákban

Ebben az oktatóanyagban végigvezetjük az Aspose.Slides for Java segítségével adott adatpontok törlésének folyamatán egy PowerPoint-prezentáció diagramsorozatából. Ez akkor lehet hasznos, ha bizonyos adatpontokat szeretne eltávolítani a diagramból, hogy frissítse vagy módosítsa az adatvizualizációt.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár integrálva van a projektjébe. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Töltse be a prezentációt

 Először is be kell töltenünk a PowerPoint bemutatót, amely tartalmazza a módosítani kívánt diagramot. Cserélje ki`"Your Document Directory"` a prezentációs fájl tényleges elérési útjával.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## 2. lépés: Nyissa meg a diagramot

Ezután a diáról hozzáférünk a diagramhoz. Ebben a példában feltételezzük, hogy a diagram az első dián van (a 0 indexnél). A diamutatót igény szerint módosíthatja.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## 3. lépés: Adott adatpontok törlése

Most ismételjük a diagram első sorozatának adatpontjait, és töröljük azok X és Y értékeit.

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

 Ez a kód az első sorozat (0. index) minden adatpontján áthalad, és mind az X, mind az Y értékeket beállítja`null`hatékonyan törli az adatpontokat.

## 4. lépés: Távolítsa el a törölt adatpontokat

Annak érdekében, hogy a törölt adatpontokat eltávolítsuk a sorozatból, a teljes sorozatot töröljük.

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

Ez a kód törli az összes adatpontot az első sorozatból.

## 5. lépés: Mentse el a módosított prezentációt

Végül a módosított prezentációt egy új fájlba mentjük.

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a specifikus diagramsorozat adatpontjainak törléséhez a Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
try
{
	ISlide sl = pres.getSlides().get_Item(0);
	IChart chart = (IChart) sl.getShapes().get_Item(0);
	for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints())
	{
		dataPoint.getXValue().getAsCell().setValue(null);
		dataPoint.getYValue().getAsCell().setValue(null);
	}
	chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
	pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

 Ebből az útmutatóból megtanulta, hogyan törölhet meghatározott adatpontokat egy PowerPoint-prezentáció diagramsorozatából az Aspose.Slides for Java használatával. Ez akkor lehet hasznos, ha dinamikusan kell frissítenie vagy módosítania kell a diagramadatokat a Java-alkalmazásokban. Ha további kérdése van, vagy további segítségre van szüksége, kérjük, tekintse meg a[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/).

## GYIK

### Hogyan távolíthatok el konkrét adatpontokat egy diagramsorozatból az Aspose.Slides for Java alkalmazásban?

Ha konkrét adatpontokat szeretne eltávolítani egy diagramsorozatból az Aspose.Slides for Java alkalmazásban, kövesse az alábbi lépéseket:

1. Töltse be a prezentációt.
2. Nyissa meg a diagramot a dián.
3. Ismételje meg a kívánt sorozat adatpontjait, és törölje azok X és Y értékeit.
4. Törölje a teljes sorozatot a törölt adatpontok eltávolításához.
5. Mentse el a módosított bemutatót.

### Törölhetek adatpontokat több sorozatból ugyanazon a diagramon?

Igen, ugyanabban a diagramban több sorozatból is törölheti az adatpontokat az egyes sorozatok adatpontjainak iterációjával és egyenkénti törlésével.

### Van mód az adatpontok törlésére egy feltétel vagy kritérium alapján?

Igen, törölheti az adatpontokat egy feltétel alapján, ha feltételes logikát ad hozzá az adatpontokon keresztül iteráló hurokhoz. Ellenőrizheti az adatpontok értékeit, és eldöntheti, hogy törli-e azokat, vagy sem a kritériumok alapján.

### Hogyan adhatok új adatpontokat egy diagramsorozathoz az Aspose.Slides for Java segítségével?

 Ha új adatpontokat szeretne hozzáadni egy diagramsorozathoz, használja a`addDataPoint` sorozat módszere. Egyszerűen hozzon létre új adatpontokat, és adja hozzá őket a sorozathoz ezzel a módszerrel.

### Hol találhatok további információt az Aspose.Slides for Java programról?

 Átfogó dokumentációt és példákat találhat a[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
