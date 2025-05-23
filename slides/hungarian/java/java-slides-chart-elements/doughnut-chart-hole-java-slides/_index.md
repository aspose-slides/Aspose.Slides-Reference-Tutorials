---
"description": "Egyedi lyukméretekkel rendelkező fánkdiagramok létrehozása Java diákban az Aspose.Slides for Java használatával. Lépésről lépésre útmutató forráskóddal a diagram testreszabásához."
"linktitle": "Fánkdiagram-lyuk Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Fánkdiagram-lyuk Java diákban"
"url": "/hu/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Fánkdiagram-lyuk Java diákban


## Bevezetés a lyukas fánkdiagram használatába Java diákon

Ebben az oktatóanyagban végigvezetünk egy lyukas fánkdiagram létrehozásán az Aspose.Slides Java verziójában. Ez a lépésről lépésre bemutatott útmutató forráskód-példákkal mutatja be a folyamatot.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java projektedben. Letöltheted innen: [Aspose.Slides Java dokumentációhoz](https://reference.aspose.com/slides/java/).

## 1. lépés: A szükséges könyvtárak importálása

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2. lépés: A prezentáció inicializálása

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
```

## 3. lépés: A fánkdiagram létrehozása

```java
try {
    // Fánkdiagram létrehozása az első dián
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // A fánkdiagram lyukméretének beállítása (százalékban)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Mentse a prezentációt lemezre
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // A prezentációs objektum eltávolítása
    if (presentation != null) presentation.dispose();
}
```

## 4. lépés: Futtassa a kódot

Futtassa a Java kódot az IDE-ben vagy szövegszerkesztőben egy fánkdiagram létrehozásához a megadott lyukmérettel. Ügyeljen arra, hogy a következőt cserélje ki: `"Your Document Directory"` a prezentáció mentésének tényleges elérési útjával.

## Teljes forráskód a fánkdiagram lyukhoz Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
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

Ebben az oktatóanyagban megtanultad, hogyan hozhatsz létre lyukkal ellátott fánkdiagramot az Aspose.Slides for Java segítségével. A lyuk méretét testreszabhatod a `setDoughnutHoleSize` metódus paraméter.

## GYIK

### Hogyan tudom megváltoztatni a diagram szegmenseinek színét?

A diagramszegmensek színének módosításához használhatja a `setDataPointsInLegend` módszer a `IChart` objektumot, és állítsa be a kívánt színt minden adatponthoz.

### Hozzáadhatok címkéket a fánkdiagram szegmenseihez?

Igen, a fánkdiagram szegmenseihez hozzáadhat címkéket a `setDataPointsLabelValue` módszer a `IChart` objektum.

### Lehetséges címet adni a diagramhoz?

Természetesen! Címet adhatsz a diagramhoz a `setTitle` módszer a `IChart` objektumot, és megadja a kívánt címszöveget.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}