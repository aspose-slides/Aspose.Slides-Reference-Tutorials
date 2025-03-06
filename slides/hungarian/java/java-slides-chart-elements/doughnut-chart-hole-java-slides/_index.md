---
title: Donut Chart Hole a Java Slides-ben
linktitle: Donut Chart Hole a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Hozzon létre fánkdiagramokat egyéni furatméretekkel a Java Slides-ben az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal a diagram testreszabásához.
weight: 11
url: /hu/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Donut Chart Hole a Java Slides-ben


## A fánkdiagram bemutatása lyukkal a Java diákban

Ebben az oktatóanyagban végigvezetjük Önt egy lyukú fánkdiagram létrehozásán az Aspose.Slides for Java segítségével. Ez a lépésről lépésre végigvezeti a folyamaton, forráskód-példákkal.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben. Letöltheti a[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/).

## 1. lépés: Importálja a szükséges könyvtárakat

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2. lépés: Inicializálja a prezentációt

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
```

## 3. lépés: Hozd létre a fánkdiagramot

```java
try {
    // Hozzon létre egy fánkdiagramot az első dián
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Állítsa be a lyuk méretét a fánkdiagramon (százalékban)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Mentse a prezentációt lemezre
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Dobja el a bemutató objektumot
    if (presentation != null) presentation.dispose();
}
```

## 4. lépés: Futtassa a kódot

 Futtassa a Java-kódot az IDE-ben vagy a szövegszerkesztőben, hogy meghatározott lyukméretű fánkdiagramot hozzon létre. Mindenképpen cserélje ki`"Your Document Directory"` azzal a tényleges elérési úttal, ahová a prezentációt menteni szeretné.

## Java Slides Donut Chart Hole teljes forráskódja

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Prezentáció írása lemezre
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

 Ebben az oktatóanyagban megtanulta, hogyan hozhat létre lyukas fánkdiagramot az Aspose.Slides for Java segítségével. A lyuk méretét testreszabhatja a`setDoughnutHoleSize` metódus paraméter.

## GYIK

### Hogyan változtathatom meg a diagram szegmenseinek színét?

 A diagramszegmensek színének megváltoztatásához használhatja a`setDataPointsInLegend` módszer a`IChart` objektumot, és állítsa be a kívánt színt minden adatponthoz.

### Hozzáadhatok címkéket a fánkdiagram szegmenseihez?

 Igen, a fánkdiagram szegmenseihez címkéket adhat hozzá a`setDataPointsLabelValue` módszer a`IChart` tárgy.

### Lehet-e címet adni a diagramhoz?

 Biztosan! A diagram segítségével címet adhat hozzá`setTitle` módszer a`IChart` objektumot, és megadja a kívánt címszöveget.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
