---
title: Képletek kiszámítása a Java Slides-ben
linktitle: Képletek kiszámítása a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan számíthat ki képleteket a Java Slides programban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal dinamikus PowerPoint prezentációkhoz.
weight: 10
url: /hu/java/data-manipulation/calculate-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Képletek kiszámítása a Java Slides-ben


## Bevezetés a képletek kiszámításába Java Slides-ben az Aspose.Slides használatával

Ebben az útmutatóban bemutatjuk, hogyan lehet képleteket kiszámítani a Java Slides alkalmazásban az Aspose.Slides for Java API használatával. Az Aspose.Slides egy hatékony könyvtár a PowerPoint-prezentációkkal való munkavégzéshez, és olyan funkciókat kínál, amelyek segítségével diagramokat lehet kezelni és képletszámításokat végezni a diákon belül.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Java fejlesztői környezet
-  Aspose.Slides for Java könyvtár (letöltheti a[itt](https://releases.aspose.com/slides/java/)
- Java programozási alapismeretek

## 1. lépés: Hozzon létre egy új prezentációt

Először hozzunk létre egy új PowerPoint-prezentációt, és adjunk hozzá egy diát. Ebben a példában egyetlen diával fogunk dolgozni.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## 2. lépés: Adjon hozzá egy diagramot a diához

Most adjunk hozzá egy fürtözött oszlopdiagramot a diához. Ezt a diagramot használjuk a képletszámítások bemutatására.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## 3. lépés: Állítsa be a képleteket és az értékeket

Ezután az Aspose.Slides API segítségével képleteket és értékeket állítunk be a diagram adatcelláihoz. Kiszámoljuk ezeknek a celláknak a képleteit.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Állítsa be a képletet az A1 cellához
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Állítsa be az A2 cella értékét
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Állítsa be a képletet a B2 cellához
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Állítsa be a képletet a C2 cellához
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Állítsa be újra az A1 cella képletét
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## 4. lépés: Mentse el a bemutatót

Végül mentsük el a módosított prezentációt a kiszámított képletekkel.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Teljes forráskód a Java Slides képletek kiszámításához

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebben az útmutatóban megtanultuk, hogyan lehet képleteket kiszámítani a Java Slides programban az Aspose.Slides for Java segítségével. Létrehoztunk egy új prezentációt, hozzáadtunk egy diagramot, képleteket és értékeket állítottunk be a diagram adatcelláihoz, és elmentettük a prezentációt a kiszámított képletekkel.

## GYIK

### Hogyan állíthatok be képleteket diagram adatcellákhoz?

 A diagram adatcellákhoz képleteket állíthat be a`setFormula` a metódusa`IChartDataCell` az Aspose-ban.Diák.

### Hogyan állíthatok be értékeket a diagram adatcelláihoz?

 A diagram adatcellák értékét a segítségével állíthatja be`setValue` a metódusa`IChartDataCell` az Aspose-ban.Diák.

### Hogyan számíthatok ki képleteket a munkafüzetben?

 Képleteket számíthat ki egy munkafüzetben a`calculateFormulas` a metódusa`IChartDataWorkbook` az Aspose-ban.Diák.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
