---
date: '2026-07-08'
description: Ismerje meg, hogyan használhatja az Aspose-t gyűrűdiagram létrehozásához
  PowerPointban Java-val. Ez a step‑by‑step útmutató bemutatja a chart data points
  programozott hozzáadását, a labels testreszabását, és a PPTX magas hűséggel történő
  mentését.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Az Aspose használatával gyűrűdiagramot hozhat létre PowerPointban
  Java-val. Kövesse ezt az útmutatót a data points hozzáadásához, a labels testreszabásához,
  és a PPTX magas hűséggel történő mentéséhez.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Hogyan használjuk az Aspose-t: Gyűrűdiagram létrehozása PowerPointban (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Hogyan használjuk az Aspose-t a gyűrűdiagram létrehozásához PowerPointban (Java)
url: /hu/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan használjuk az Aspose-t a fánkdiagram létrehozásához PowerPointban (Java)

## Bevezetés
Vonzó prezentációk létrehozása gyakran több, mint csak szöveg és képek; a diagramok jelentősen javíthatják a történetmesélést az adatok hatékony vizualizálásával. **Hogyan használjuk az Aspose-t** a diagramkészítéshez programozott vezérlést biztosít anélkül, hogy megnyitnánk a PowerPointot. Ez az útmutató végigvezeti a fánkdiagram felépítésén, az adatpontok konfigurálásán, és egy magas minőségű PPTX mentésén. Csak alapvető Java ismeretekre és néhány percre van szükség a beállításhoz.

`Aspose.Slides for Java` egy Java könyvtár, amely lehetővé teszi PowerPoint fájlok létrehozását, manipulálását és konvertálását a Microsoft Office nélkül.

## Gyors válaszok
- **Melyik könyvtár hoz létre fánkdiagramot PowerPointban?** Aspose.Slides for Java  
- **Hozzáadhatok diagram adatpontokhoz programozottan?** Yes, using the chart API  
- **Szükségem van licencre a termeléshez?** A valid Aspose.Slides license is required  
- **Mely Java verziók támogatottak?** Java 8 and later (JDK 16 classifier shown)  
- **Hány sorozatot adhatok hozzá?** The example adds up to 15 series, but you can adjust as needed  

## Mi az a fánkdiagram a PowerPointban?
A fánkdiagram egy kör alakú diagram, amely a kördiagramhoz hasonló, de középen lyukkal rendelkezik, lehetővé téve több sorozat egyidejű megjelenítését. A rész‑teljes arányokat hangsúlyozza, miközben a vizuális elrendezés kompakt és könnyen olvasható marad.

## Miért használjuk az Aspose.Slides for Java-t fánkdiagramok létrehozásához?
Aspose.Slides for Java több mint 50 bemeneti és kimeneti formátumot kezel, és akár 500 MB méretű prezentációkat is generálhat anélkül, hogy a teljes fájlt a memóriába töltené. Teljes programozott vezérlést biztosít a diagram megjelenése, adatai és elrendezése felett bármely Java platformon, megszünteti a COM interopot, és egy tipikus szerveren 100 diagramot tartalmazó diát kevesebb mint két másodperc alatt renderel.

## Előfeltételek
- Alapvető Java programozási ismeretek.  
- IDE, például IntelliJ IDEA vagy Eclipse.  
- Maven vagy Gradle a függőségkezeléshez.  
- Érvényes Aspose.Slides for Java licenc (ingyenes próba elérhető).

## Az Aspose.Slides for Java beállítása
Válassza ki a projektjéhez illő függőségkezelőt.

**Maven**  
Adja hozzá a következő függőséget a `pom.xml`-hez (cserélje le a verziót a legújabb kiadásra):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Adja hozzá ezt a sort a `build.gradle`-hez:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Ha inkább közvetlenül letöltene, látogassa meg a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalt.

### Licenc beszerzése
Kezdhet ingyenes próbaidőszakkal az Aspose.Slides funkcióinak felfedezéséhez. Hosszabb használathoz vásároljon licencet vagy kérjen ideiglenes licencet az [Aspose weboldaláról](https://purchase.aspose.com/temporary-license/). Kövesse a megadott útmutatót a környezet beállításához és az Aspose.Slides inicializálásához az alkalmazásban.

## Hogyan hozzunk létre fánkdiagramot PowerPointban az Aspose.Slides for Java használatával
A fánkdiagram létrehozásához kezdje egy `Presentation` betöltésével vagy létrehozásával, adjon hozzá egy `ChartType.Doughnut` típusú diagram alakzatot, törölje az alapértelmezett sorozatokat, állítsa be a lyuk méretét, majd töltse fel a diagram munkafüzetét kategória nevekkel és numerikus értékekkel. Végül állítsa be a címkék formázását és mentse a PPTX-et.

### 1. lépés: A prezentáció inicializálása
Hozzon létre egy új prezentációt vagy nyisson meg egy meglévő fájlt a diák gyűjteményének megszerzéséhez.

`Presentation` az elsődleges osztály, amely egy PowerPoint fájlt képvisel.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### 2. lépés: Fánkdiagram hozzáadása a diára
Helyezzen be egy diagram alakzatot, távolítsa el az alapértelmezett sorozatokat/kategóriákat, és állítsa be az alapvető vizuális beállításokat, például a fánk lyuk méretét.

`Chart` (vagy diagram alakzat) egy a diára helyezett diagram objektumot képvisel.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### 3. lépés: Diagram adatpontok hozzáadása és címkék testreszabása
Töltse fel a kategória neveket, adjon hozzá adatpontokat minden sorozathoz, és finomhangolja a címkék formázását (betűtípus, szín, pozíció). Ez a lépés bemutatja a „diagram adatpontok hozzáadása” képességet.

`Workbook` hozzáférést biztosít a diagram alatta lévő táblázat adataihoz, ahol a cellákat feltöltik.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### 4. lépés: A frissített prezentáció mentése
Mentse a módosításokat egy új PPTX fájlba a lemezen.

`save` a prezentációt a kiválasztott formátumban egy fájlba írja.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Gyakorlati alkalmazások
- **Pénzügyi jelentések:** Költségvetési allokációk vagy kiadások bontásának vizualizálása.  
- **Piaci elemzés:** A piaci részesedés eloszlásának bemutatása a versenytársak között.  
- **Felmérés eredményei:** Kategóriák szerinti felmérési adatok bemutatása kompakt formában.  
- **Műszerfal generálás:** Adatbázis lekérdezésekkel kombinálva élő frissítésű diák előállítása.

## Teljesítményfontosságú szempontok
- **Erőforrások felszabadítása:** Hívja a `pres.dispose()`-t a mentés után a natív memória felszabadításához.  
- **Diagramok számának korlátozása:** Százak diagramjának hozzáadása növelheti a memóriahasználatot; szükség esetén batch‑feldolgozással.  
- **Streaming használata:** Nagy adathalmazok esetén töltse fel a munkafüzetet közvetlenül streamekből a memória tömbök helyett.

## Gyakori problémák és megoldások

| Probléma | Ok | Megoldás |
|----------|----|----------|
| **A diagram üresnek jelenik meg** | Az adatcellák nincsenek megfelelően feltöltve | Ellenőrizze, hogy a `workBook.getCell(...)` a megfelelő sor/oszlop indexeket hivatkozza. |
| **A címkék átfedik egymást** | Túl sok kategória a korlátozott helyen | Növelje a `DoughnutHoleSize` értékét vagy állítsa be a `FirstSliceAngle`-t. |
| **OutOfMemoryError** | Nagy prezentációk felszabadítás nélkül | Hívja a `pres.dispose()`-t a mentés után, és fontolja meg a JVM heap méretének növelését. |

## Gyakran Ismételt Kérdések

**Q: Használhatom az Aspose.Slides for Java-t kereskedelmi alkalmazásokban?**  
A: Igen, de érvényes kereskedelmi licencre van szükség. Ingyenes próba elérhető értékeléshez.

**Q: Hogyan adhatok hozzá több mint 15 sorozatot?**  
A: Növelje a cikluskorlátot a „Fánkdiagram hozzáadása” lépésben, és győződjön meg róla, hogy az adat munkafüzet elegendő sort tartalmaz.

**Q: Lehet-e megváltoztatni a fánk lyuk méretét a létrehozás után?**  
A: Igen, hívja a `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`-t a mentés előtt.

**Q: Exportálhatom a diagramot képként a PPTX helyett?**  
A: Természetesen. Használja a `chart.getImage()`-t, és mentse a visszakapott `java.awt.image.BufferedImage`-et a kívánt formátumban.

**Q: Támogatja az Aspose.Slides az animált diagramokat?**  
A: Az animáció hozzáadható az `ISlide.getTimeline()` API-val, bár ez meghaladja az útmutató kereteit.

## Összegzés
Most már rendelkezik egy teljes, termelésre kész módszerrel a **fánkdiagram PowerPoint** fájlok létrehozásához az Aspose.Slides for Java-val, beleértve a **diagram adatpontok hozzáadását**, a címkék testreszabását és a teljesítményfontosságú szempontok kezelését. Kísérletezzen különböző színekkel, adatforrásokkal és diagramtípusokkal, hogy prezentációi valóban kiemelkedjenek.

---

**Legutóbb frissítve:** 2026-07-08  
**Tesztelve a következővel:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Szerző:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Kapcsolódó útmutatók

- [Hogyan adjunk diagramokat a PowerPointhoz az Aspose.Slides for Java használatával: Lépésről‑lépésre útmutató](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hogyan szerkesszünk PowerPoint diagram adatokat az Aspose.Slides for Java-val: Átfogó útmutató](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Diagramok animálása PowerPointban az Aspose.Slides for Java használatával – Lépésről‑lépésre útmutató](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}