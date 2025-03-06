---
title: Diagram adatcella képletek Java Slides
linktitle: Diagram adatcella képletek Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be diagramadatcella-képleteket Java PowerPoint prezentációkban az Aspose.Slides for Java segítségével. Dinamikus diagramok létrehozása képletekkel.
weight: 11
url: /hu/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Bevezetés a Chart Data Cell Formulákba az Aspose.Slides for Java programban

Ebben az oktatóanyagban megvizsgáljuk, hogyan dolgozhatunk diagram-adatcella-képletekkel az Aspose.Slides for Java használatával. Az Aspose.Slides segítségével diagramokat hozhat létre és kezelhet PowerPoint-prezentációkban, beleértve az adatcellák képleteinek beállítását.

## Előfeltételek

 Mielőtt elkezdené, ellenőrizze, hogy telepítve van-e az Aspose.Slides for Java könyvtár. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Hozzon létre egy PowerPoint-bemutatót

Először hozzunk létre egy új PowerPoint-prezentációt, és adjunk hozzá egy diagramot.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Adjon hozzá egy diagramot az első diához
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Szerezze be a munkafüzetet a diagramadatokhoz
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Folytassa az adatcella-műveletekkel
    // ...
    
    // Mentse el a bemutatót
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## 2. lépés: Állítsa be az adatcellák képleteit

Most állítsunk be képleteket a diagram adott adatcelláihoz. Ebben a példában két különböző cellához állítunk be képleteket.

### 1. cella: A1 jelölés használata

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

A fenti kódban beállítunk egy képletet a B2 cellához A1 jelöléssel. A képlet kiszámítja az F2 és H5 cellák összegét, és az eredményhez hozzáad 1-et.

### 2. cella: R1C1 jelölés használata

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Itt beállítunk egy képletet a C2 cellához az R1C1 jelöléssel. A képlet kiszámítja a maximális értéket az R2C6 és R5C8 tartományban, majd elosztja 3-mal.

## 3. lépés: Számítsa ki a képleteket

A képletek beállítása után feltétlenül ki kell számítani őket a következő kóddal:

```java
workbook.calculateFormulas();
```

Ez a lépés biztosítja, hogy a diagram tükrözze a képletek alapján frissített értékeket.

## 4. lépés: Mentse el a bemutatót

Végül mentse a módosított prezentációt egy fájlba.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Java Slides diagramadat-cellaképleteinek teljes forráskódja

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan dolgozhatunk diagram adatcella-képletekkel az Aspose.Slides for Java programban. Szóba került a PowerPoint-prezentáció létrehozása, a diagramok hozzáadása, az adatcellák képletei beállítása, a képletek kiszámítása és a prezentáció mentése. Mostantól ezeket a képességeket kihasználva dinamikus és adatvezérelt diagramokat hozhat létre prezentációiban.

## GYIK

### Hogyan adhatok hozzá diagramot egy adott diához?

 Ha diagramot szeretne hozzáadni egy adott diához, használja a`getSlides().get_Item(slideIndex)` módszerrel elérheti a kívánt diát, majd használja a`addChart` módszer a diagram hozzáadásához.

### Használhatok különböző típusú képleteket az adatcellákban?

Igen, az adatcella-képletekben különféle típusú képleteket használhat, beleértve a matematikai műveleteket, függvényeket és más cellákra való hivatkozásokat.

### Hogyan változtathatom meg a diagram típusát?

 A diagram típusát a gombbal módosíthatja`setChartType` módszer a`IChart` objektumot, és megadja a kívántat`ChartType`.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
