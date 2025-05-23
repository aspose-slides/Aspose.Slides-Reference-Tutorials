---
"description": "Tanuld meg, hogyan állíthatsz be diagram adatcellák képleteit Java PowerPoint prezentációkban az Aspose.Slides for Java használatával. Hozz létre dinamikus diagramokat képletekkel."
"linktitle": "Diagramadatok cellaképletei Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Diagramadatok cellaképletei Java diákban"
"url": "/hu/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramadatok cellaképletei Java diákban


## Bevezetés a diagramadatok cellaképleteibe az Aspose.Slides Java-ban

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan dolgozhatunk diagram adatcella-képletekkel az Aspose.Slides for Java segítségével. Az Aspose.Slides segítségével diagramokat hozhat létre és kezelhet PowerPoint-bemutatókban, beleértve az adatcellák képleteinek beállítását is.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy telepítve van az Aspose.Slides for Java könyvtár. Letöltheted innen: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: PowerPoint-bemutató létrehozása

Először is hozzunk létre egy új PowerPoint bemutatót, és adjunk hozzá egy diagramot.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Diagram hozzáadása az első diához
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // A diagramadatokhoz tartozó munkafüzet beszerzése
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Folytassa az adatcella-műveletekkel
    // ...
    
    // Mentse el a prezentációt
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## 2. lépés: Képletek beállítása az adatcellákhoz

Most állítsunk be képleteket a diagram adott adatcelláihoz. Ebben a példában két különböző cellához fogunk képleteket beállítani.

### 1. cella: A1 jelölés használata

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

A fenti kódban az A1 jelölést használva beállítottunk egy képletet a B2 cellához. A képlet kiszámítja az F2-től H5-ig terjedő cellák összegét, és 1-et ad az eredményhez.

### 2. cella: R1C1 jelölés használata

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Itt egy képletet állítunk be a C2 cellához az R1C1 jelölés használatával. A képlet kiszámítja az R2C6 és R5C8 közötti tartományon belüli maximális értéket, majd elosztja azt 3-mal.

## 3. lépés: Képletek kiszámítása

A képletek beállítása után elengedhetetlen a következő kóddal kiszámítani őket:

```java
workbook.calculateFormulas();
```

Ez a lépés biztosítja, hogy a diagram a képleteken alapuló frissített értékeket tükrözze.

## 4. lépés: Mentse el a prezentációt

Végül mentse el a módosított prezentációt egy fájlba.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Teljes forráskód a Java diák diagramadat-cellaképleteihez

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

Ebben az oktatóanyagban azt vizsgáltuk meg, hogyan dolgozhatunk diagram adatcella-képletekkel az Aspose.Slides Java verziójában. Áttekintettük a PowerPoint-bemutatók létrehozását, diagramok hozzáadását, az adatcellák képleteinek beállítását, a képletek kiszámítását és a bemutató mentését. Mostantól kihasználhatod ezeket a képességeket dinamikus és adatvezérelt diagramok létrehozásához a bemutatóidban.

## GYIK

### Hogyan adhatok hozzá egy diagramot egy adott diához?

Ha egy adott diához szeretne diagramot hozzáadni, használhatja a `getSlides().get_Item(slideIndex)` módszerrel érheti el a kívánt diát, majd használja a `addChart` módszer a diagram hozzáadásához.

### Használhatok különböző típusú képleteket az adatcellákban?

Igen, az adatcellák képleteiben különféle típusú képleteket használhat, beleértve a matematikai műveleteket, függvényeket és más cellákra való hivatkozásokat.

### Hogyan tudom megváltoztatni a diagram típusát?

A diagram típusát a következővel módosíthatja: `setChartType` módszer a `IChart` objektum és a kívánt `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}