---
"description": "Tanuld meg, hogyan törölhetsz bizonyos adatpontokat egy Java Slides diagramsorozatból az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal a hatékony adatvizualizáció-kezeléshez."
"linktitle": "Törölje a megadott diagramsorozat-adatpontokat Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Törölje a megadott diagramsorozat-adatpontokat Java diákban"
"url": "/hu/java/chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Törölje a megadott diagramsorozat-adatpontokat Java diákban


## Bevezetés a Java diákban található specifikus diagramsorozat-adatpontok törléséhez

Ebben az oktatóanyagban végigvezetünk azon, hogyan törölhetsz bizonyos adatpontokat egy PowerPoint-bemutató diagramsorozatából az Aspose.Slides for Java használatával. Ez akkor lehet hasznos, ha bizonyos adatpontokat el szeretnél távolítani egy diagramból az adatvizualizáció frissítése vagy módosítása érdekében.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg róla, hogy az Aspose.Slides for Java könyvtár integrálva van a projektedbe. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Töltse be a prezentációt

Először is be kell töltenünk a módosítani kívánt diagramot tartalmazó PowerPoint bemutatót. Csere `"Your Document Directory"` a prezentációs fájl tényleges elérési útjával.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "TestChart.pptx");
```

## 2. lépés: Hozzáférés a diagramhoz

Ezután a diáról fogjuk elérni a diagramot. Ebben a példában feltételezzük, hogy a diagram az első dián található (a 0. indexű dia). A diaindexet szükség szerint módosíthatja.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = (IChart) slide.getShapes().get_Item(0);
```

## 3. lépés: Törölje a megadott adatpontokat

Most végigmegyünk a diagram első sorozatának adatpontjain, és töröljük az X és Y értékeiket.

```java
for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
    dataPoint.getXValue().getAsCell().setValue(null);
    dataPoint.getYValue().getAsCell().setValue(null);
}
```

Ez a kód végigmegy az első sorozat (0. index) minden adatpontján, és az X és Y értékeket is a következőre állítja be: `null`, gyakorlatilag törli az adatpontokat.

## 4. lépés: Törölt adatpontok eltávolítása

Annak érdekében, hogy a törölt adatpontok eltávolításra kerüljenek a sorozatból, a teljes sorozatot törölni fogjuk.

```java
chart.getChartData().getSeries().get_Item(0).getDataPoints().clear();
```

Ez a kód törli az első sorozat összes adatpontját.

## 5. lépés: Mentse el a módosított prezentációt

Végül a módosított prezentációt egy új fájlba mentjük.

```java
pres.save(dataDir + "ClearSpecificChartSeriesDataPointsData.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a Java diákban található, egyértelmű, specifikus diagramsorozat-adatpontok adataihoz

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

Ebben az útmutatóban megtanulta, hogyan törölhet bizonyos adatpontokat egy PowerPoint-bemutató diagramsorozatából az Aspose.Slides for Java használatával. Ez akkor lehet hasznos, ha dinamikusan kell frissítenie vagy módosítania a diagram adatait a Java-alkalmazásaiban. Ha további kérdései vannak, vagy további segítségre van szüksége, kérjük, tekintse meg a következőt: [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/).

## GYIK

### Hogyan távolíthatok el bizonyos adatpontokat egy diagramsorozatból az Aspose.Slides for Java programban?

Ha el szeretne távolítani bizonyos adatpontokat egy diagramsorozatból az Aspose.Slides for Java programban, kövesse az alábbi lépéseket:

1. Töltsd be a prezentációt.
2. Nyissa meg a dián található diagramot.
3. Iterálja a kívánt sorozat adatpontjait, és törölje azok X és Y értékeit.
4. Törölje a teljes sorozatot a törölt adatpontok eltávolításához.
5. Mentse el a módosított prezentációt.

### Törölhetek adatpontokat több sorozatból ugyanabban a diagramban?

Igen, törölhet adatpontokat több sorozatból ugyanazon a diagramon belül úgy, hogy végigmegy az egyes sorozatok adatpontjain, és egyenként törli őket.

### Van mód az adatpontok törlésére feltétel vagy kritérium alapján?

Igen, törölhet adatpontokat egy feltétel alapján úgy, hogy feltételes logikát ad hozzá a ciklushoz, amely végigmegy az adatpontokon. Ellenőrizheti az adatpontok értékeit, és a kritériumok alapján eldöntheti, hogy törli-e őket vagy sem.

### Hogyan adhatok hozzá új adatpontokat egy diagramsorozathoz az Aspose.Slides for Java használatával?

Új adatpontok hozzáadásához egy diagramsorozathoz használhatja a `addDataPoint` a sorozat metódusa. Egyszerűen hozzon létre új adatpontokat, és adja hozzá azokat a sorozathoz ezzel a metódussal.

### Hol találok további információt az Aspose.Slides for Java-ról?

Átfogó dokumentációt és példákat talál a következő helyen: [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}