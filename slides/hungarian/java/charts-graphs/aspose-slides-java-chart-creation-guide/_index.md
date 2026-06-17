---
date: '2026-06-03'
description: Ismerje meg, hogyan hozhat létre klaszteres oszlopdiagramot Java-ban
  az Aspose.Slides használatával. Ez az útmutató bemutatja a Maven függőséget, a diagram
  létrehozásának lépéseit és az adatok kezelését.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Klaszteres oszlopdiagram létrehozása Java-ban az Aspose.Slides használatával
url: /hu/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Klaszterezett oszlopdiagram létrehozása Java-ban az Aspose.Slides segítségével

## Hogyan hozzunk létre diagramot Java-ban: Bevezetés
A dinamikus prezentációk létrehozása gyakran magában foglalja az adatok diagramokkal történő megjelenítését. Az **Aspose.Slides for Java** segítségével könnyedén **klaszterezett oszlopdiagram** objektumokat hozhat létre, növelheti a tisztaságot, és erőteljesebb hatást érhet el a közönségén. Ez az útmutató végigvezet a könyvtár beállításán, a klaszterezett oszlopdiagram hozzáadásán, a sorozatok kezelésén, és a negatív adatpontok feltételes invertálásán.

**Mit fog megtanulni**
- Hogyan állítsuk be az Aspose.Slides for Java-t.
- Lépések a **klaszterezett oszlopdiagram** létrehozásához a prezentációban.
- Technikák a diagram sorozatok és adatpontok kezeléséhez.
- Módszerek a negatív adatpontok feltételes invertálására a jobb megjelenítés érdekében.
- Hogyan mentse a prezentációt biztonságosan.

## Gyors válaszok
- **Melyik könyvtárat használják?** Aspose.Slides for Java.  
- **Melyik diagramtípust mutatják be?** Klaszterezett oszlopdiagram.  
- **Invertálhatom a negatív értékeket?** Igen, az `invertIfNegative` használatával.  
- **Milyen Java verzió szükséges?** JDK 16 vagy újabb.  
- **Szükséges licenc a termeléshez?** Igen, egy érvényes Aspose licenc.

## Mi az a klaszterezett oszlopdiagram?
A klaszterezett oszlopdiagram egy vizuális ábrázolás, amely minden kategóriához több adat sorozatot helyez egymás mellé, lehetővé téve a gyors összehasonlítást a csoportok között. Tökéletes pénzügyi jelentésekhez, értékesítési műszerfalakhoz, és bármely olyan helyzethez, ahol egyszerre több mutatót kell összevetni.

## Miért használja az Aspose.Slides-t diagramkészítéshez?
Az Aspose.Slides lehetővé teszi, hogy programozottan generáljon és teljesen testreszabjon diagramokat, kiküszöbölve a manuális PowerPoint szerkesztés szükségességét. Támogat **70+ bemeneti és kimeneti formátumot**, és képes **akár 10 000 diát** tartalmazó prezentációkat feldolgozni anélkül, hogy az egész fájlt a memóriába töltené, ezáltal magas teljesítményt biztosítva a nagyszabású jelentésekhez.

## Előfeltételek
1. **Szükséges könyvtárak**  
   - Aspose.Slides for Java (25.4 vagy újabb verzió).  

2. **Környezet**  
   - JDK 16 vagy újabb.  
   - Maven vagy Gradle a függőségkezeléshez.  

3. **Ismeretek**  
   - Alapvető Java programozás.  
   - Ismeret a build eszközökkel (Maven/Gradle).  

## Az Aspose.Slides for Java beállítása
### Maven telepítés
Adja hozzá a következő függőséget a `pom.xml` fájlhoz:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle telepítés
Adja hozzá a következő sort a `build.gradle` fájlhoz:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Alternatívaként töltse le a legújabb verziót a [Aspose.Slides for Java kiadások](https://releases.aspose.com/slides/java/) oldalról.

### Licenc beszerzése
- **Ingyenes próba:** Fedezze fel a funkciókat licenc nélkül.  
- **Ideiglenes licenc:** Használja értékelés során.  
- **Teljes licenc:** Vásárolja meg a termelési telepítésekhez.

### Alapvető inicializálás
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Hogyan adhatok hozzá klaszterezett oszlopdiagramot egy diára?
`Presentation` a fő osztály, amely egy PowerPoint fájlt képvisel. Töltsön be egy új `Presentation`-t, adjon hozzá egy diát, és hívja meg a `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)` metódust. Ez az egyetlen hívás létrehozza a teljesen működő klaszterezett oszlopdiagramot a megadott koordinátákon. Ezután elérheti a diagram objektumot a sorozatok, adatpontok és vizuális stílusok módosításához.

## Lépésről‑lépésre útmutató

### 1. lépés: Prezentáció létrehozása és klaszterezett oszlopdiagram hozzáadása
`Presentation` osztály egy PowerPoint dokumentumot képvisel, és lehetővé teszi diák létrehozását.  
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### 2. lépés: Diagram sorozatok kezelése
Most töröljük az esetleges alapértelmezett sorozatokat, hozzáadunk egy újat, és feltöltjük pozitív és negatív értékekkel.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### 3. lépés: Negatív adatpontok feltételes invertálása
`invertIfNegative` metódus lehetővé teszi a negatív értékek invertálását egy diagram sorozatban.  
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

## Gyakori hibák és tippek
- **Elfelejtette eldobni a `Presentation` objektumot?** Mindig hívja meg a `dispose()`-t egy `finally` blokkban a natív erőforrások felszabadításához.  
- **A negatív értékek nem jelennek meg invertálva?** Győződjön meg róla, hogy a `invertIfNegative(true)` **a** adatpont hozzáadása **után** kerül meghívásra.  
- **Diagram méret problémák:** A koordináták (X, Y) és a méretek (szélesség, magasság) pontban vannak megadva; állítsa őket a diák elrendezéséhez.  

## Gyakran ismételt kérdések

**Q:** Létrehozhatok más diagramtípusokat ugyanazzal a megközelítéssel?  
A: Igen, egyszerűen cserélje le a `ChartType.ClusteredColumn`-t bármely más `ChartType` enum értékre (pl. `Line`, `Pie`).  

**Q:** Szükségem van licencre a fejlesztői build-ekhez?  
A: Ideiglenes vagy értékelő licenc szükséges a teljes funkciók eléréséhez; egyébként a könyvtár próba módban működik vízjel korlátozásokkal.  

**Q:** Hogyan exportáljam a prezentációt PDF-be a diagramok hozzáadása után?  
A: `SaveFormat.Pdf` PDF formátumot ad meg a prezentáció mentéséhez. Használja a `pres.save("output.pdf", SaveFormat.Pdf);` kódot a diagramkezelés befejezése után.  

**Q:** Lehetőség van egyedi oszlopok (szín, keret) stílusának beállítására?  
A: `IChartDataPoint` egy diagram egyetlen adatpontját jelöli, és lehetővé teszi a formázást. Minden `IChartDataPoint` olyan opciókat biztosít, mint a `getFillFormat().setFillType(FillType.Solid)` és a `getLineFormat()`.  

**Q:** Mi a teendő, ha a prezentáció mentése után kell frissíteni a diagram adatokat?  
A: Töltse be újra a prezentációt a `new Presentation("file.pptx")` segítségével, módosítsa a diagram adatokat, és mentse újra.

---

**Utolsó frissítés:** 2026-06-03  
**Tesztelve:** Aspose.Slides for Java 25.4 (JDK 16)  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre halmozott oszlopdiagramot Java-ban az Aspose.Slides segítségével – Átfogó útmutató](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Hogyan hozzunk létre diagramot Java-ban az Aspose.Slides segítségével – A diagramkészítés és validálás elsajátítása](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Diagramok létrehozása és formázása Java-ban az Aspose.Slides használatával: Átfogó útmutató](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}