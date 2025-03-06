---
title: Információk elrejtése a diagramból a Java Slides alkalmazásban
linktitle: Információk elrejtése a diagramból a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan rejtheti el a diagramelemeket a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Testreszabhatja a prezentációkat az átláthatóság és az esztétika érdekében lépésről lépésre szóló útmutatás és forráskód segítségével.
weight: 13
url: /hu/java/customization-and-formatting/hide-information-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Bevezetés az információk elrejtéséhez a diagramból a Java Slides alkalmazásban

Ebben az oktatóanyagban megvizsgáljuk, hogyan rejthet el különféle elemeket egy diagramon a Java Slides alkalmazásban az Aspose.Slides for Java API használatával. Ezzel a kóddal testreszabhatja diagramjait a prezentációkhoz.

## 1. lépés: A környezet beállítása

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár hozzáadva van a projekthez. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## 2. lépés: Hozzon létre egy új prezentációt

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 3. lépés: Diagram hozzáadása a diához

Hozzáadunk egy jelölőkkel ellátott vonaldiagramot a diához, majd elrejtjük a diagram különböző elemeit.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## 4. lépés: A diagram címének elrejtése

A diagram címét a következőképpen rejtheti el:

```java
chart.setTitle(false);
```

## 5. lépés: Az értékek tengelyének elrejtése

Az értéktengely (függőleges tengely) elrejtéséhez használja a következő kódot:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## 6. lépés: A kategóriatengely elrejtése

A kategóriatengely (vízszintes tengely) elrejtéséhez használja ezt a kódot:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## 7. lépés: Jelmagyarázat elrejtése

A diagram jelmagyarázatát így rejtheti el:

```java
chart.setLegend(false);
```

## 8. lépés: A főbb rácsvonalak elrejtése

A vízszintes tengely főbb rácsvonalainak elrejtéséhez a következő kódot használhatja:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## 9. lépés: Távolítsa el a sorozatot

Ha az összes sorozatot el szeretné távolítani a diagramból, használhat egy ehhez hasonló hurkot:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## 10. lépés: A diagramsorozat testreszabása

A diagramsorozatot igény szerint testreszabhatja. Ebben a példában megváltoztatjuk a jelölő stílusát, az adatcímke pozícióját, a jelölő méretét, a vonal színét és a kötőjel stílusát:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## 11. lépés: Mentse el a prezentációt

Végül mentse a prezentációt egy fájlba:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

Ez az! Sikeresen elrejtett különböző elemeket egy diagramon a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. A diagramokat és a prezentációkat tovább szabhatja saját igényei szerint.

## Teljes forráskód az információk elrejtéséhez a diagramból a Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//A diagram címének elrejtése
	chart.setTitle(false);
	///Értékek elrejtése tengely
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Kategória tengely láthatósága
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Rejtős legenda
	chart.setLegend(false);
	//MajorGridLines elrejtése
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Sorozatvonal színének beállítása
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Következtetés

Ebben a lépésenkénti útmutatóban megvizsgáltuk, hogyan rejthetünk el különféle elemeket egy diagramon a Java Slides alkalmazásban az Aspose.Slides for Java API használatával. Ez hihetetlenül hasznos lehet, ha testre kell szabnia a diagramokat a prezentációkhoz, és vizuálisan vonzóbbá kell tennie őket, vagy az Ön egyedi igényeihez kell szabnia.

## GYIK

### Hogyan szabhatom tovább a diagramelemek megjelenését?

Testreszabhatja a diagramelemek különféle tulajdonságait, például a vonalszínt, a kitöltési színt, a jelölőstílust és egyebeket a diagramsorozat, a jelölők, a címkék és a formátum megfelelő tulajdonságainak elérésével.

### Elrejthetek bizonyos adatpontokat a diagramban?

Igen, elrejthet bizonyos adatpontokat a diagramsorozat adatainak manipulálásával. Elrejtheti az adatpontokat, vagy nullára állíthatja az adatpontokat.

### Hogyan adhatok hozzá további sorozatokat a diagramhoz?

 A diagram segítségével további sorozatokat adhat hozzá`IChartData.getSeries().add` módszerrel és az új sorozat adatpontjainak megadásával.

### Lehetséges a diagram típusának dinamikus megváltoztatása?

Igen, dinamikusan módosíthatja a diagram típusát, ha létrehoz egy új, a kívánt típusú diagramot, és átmásolja az adatokat a régi diagramról az újba.

### Hogyan módosíthatom programozottan a diagram címét és tengelycímkéit?

Beállíthatja a diagram és a tengelyek címét és címkéit, ha hozzáfér a megfelelő tulajdonságaikhoz, és beállítja a kívánt szöveget és formázást.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
