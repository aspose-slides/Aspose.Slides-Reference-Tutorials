---
date: '2026-03-07'
description: Tanulja meg, hogyan készítsen fánkdiagramot Java-ban az Aspose.Slides
  segítségével. Ez a lépésről‑lépésre útmutató lefedi a Maven Aspose Slides függőség
  beállítását, a diagram konfigurálását és a prezentációk mentését.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Gyűrűdiagram létrehozása Java-val az Aspose.Slides útmutatóval
url: /hu/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Doughnut diagram létrehozása Java-val az Aspose.Slides útmutató

## Bevezetés

A **doughnut chart** programozott létrehozása nyers számokat egy figyelemfelkeltő vizuálissá alakíthat, amely azonnal elmesél egy történetet. Java-ban a **Aspose.Slides** egyszerűvé teszi ezt a folyamatot, lehetővé téve, hogy prezentációra kész diagramokat generálj anélkül, hogy megnyitnád a PowerPointot. Ebben az útmutatóban lépésről lépésre megtanulod, hogyan **create doughnut chart java** – a Maven Aspose Slides függőség beállításától a sorok, kategóriák testreszabásáig, végül a prezentáció mentéséig.

A útmutató végére képes leszel dinamikus doughnut diagramokat beágyazni bármely PPTX fájlba, ami tökéletes jelentésekhez, műszerfalakhoz vagy automatizált diavetítésekhez.

### Gyors válaszok
- **Milyen könyvtárat használnak?** Aspose.Slides for Java  
- **Elsődleges feladat?** Create doughnut chart java in a PPTX file  
- **Hogyan adhatod hozzá a könyvtárat?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimum Java verzió?** JDK 16 or higher  
- **Testreszabhatom a színeket és címkéket?** Yes, the API provides full formatting control  

## Mi az a Doughnut Chart és miért használjuk?

A doughnut chart a kördiagram egy változata, amelynek középső része üres, lehetővé téve több adat sor megjelenítését koncentrikus gyűrűkben. Ez ideálissá teszi a teljes egész részeinek több kategóriában történő összehasonlítására – például értékesítés régiónként több negyedév alatt vagy költségvetési elosztás részlegek szerint.

## Miért használjuk az Aspose.Slides for Java-t?

- **No Office installation required** – Nincs Office telepítés szükséges – PPTX fájlok generálása bármely szerveren.  
- **Rich API** – Gazdag API – teljes irányítás a diagramtípusok, adatpontok és stílusok felett.  
- **High performance** – Magas teljesítmény – nagy prezentációkhoz optimalizálva.  
- **Cross‑platform** – Keresztplatformos – működik Windows, Linux és macOS rendszereken.

## Előkövetelmények

- **Required Libraries:**  
  - Aspose.Slides for Java version 25.4 vagy újabb.  

- **Environment Setup:**  
  - JDK 16 vagy újabb.  
  - Kedvenc IDE-d (IntelliJ IDEA, Eclipse, NetBeans, stb.).  

- **Knowledge Prerequisites:**  
  - Alap Java programozás.  
  - Maven vagy Gradle ismerete a függőségkezeléshez.

## Maven Aspose Slides függőség

Add the following Maven dependency to your `pom.xml`. This is the **maven aspose slides dependency** you need to pull the library into your project.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Ha inkább Gradle-t használsz, használd az alábbi ekvivalens kódrészletet.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

A JAR fájlt közvetlenül a hivatalos kiadási oldalról is letöltheted:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Licenc beszerzése

A kiértékelési vízjel eltávolításához és a teljes funkciók eléréséhez:

- **Free trial** – Kezd egy ideiglenes licenccel.  
- **Temporary license** – Kérj egyet a [Aspose weboldalról](https://purchase.aspose.com/temporary-license/).  
- **Commercial license** – Vásárolj kereskedelmi licencet a termelési használathoz.

Alkalmazd a licencet a kódban:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementációs útmutató

### Prezentáció inicializálása és Doughnut diagram hozzáadása

Először hozz létre vagy tölts be egy prezentációt, és adj hozzá egy doughnut diagramot az első diára.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### A diagram adatkönyvtárának beállítása és a meglévő adatok törlése

Ezután szerezd meg a diagramot támogató munkafüzetet, és töröld az esetleges alapértelmezett sorokat vagy kategóriákat.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Sorok hozzáadása a diagramhoz

Most legfeljebb 15 sort adunk hozzá. Minden sor testreszabható – itt állítjuk be a kitörést, a doughnut‑lyuk méretét és az első szelet szögét.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Kategóriák és adatpontok hozzáadása

15 kategóriát hozunk létre, és minden sorhoz egy adatpontot töltünk fel. Az utolsó sor speciális címkeformázást kap.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### A prezentáció mentése

Végül írd a frissített prezentációt a lemezre.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Gyakori problémák és megoldások

- **License not found** – Ellenőrizd, hogy a `license.lic` útvonala helyes-e, és a fájl olvasható.  
- **Chart appears blank** – Győződj meg róla, hogy a meglévő sorok/kategóriák törlésre kerültek az új hozzáadása előtt.  
- **Incorrect colors** – `FillType.Solid` legyen beállítva mind a kitöltés, mind a vonal formátumához.  
- **Performance with many series** – Korlátozd a sorok/kategóriák számát, vagy használd újra a munkafüzet celláit.

## Gyakran ismételt kérdések

**Q: Létrehozhatok doughnut diagramot előre létező PPTX fájl nélkül?**  
A: Igen, példányosítsd a `new Presentation()`-t, hogy egy üres diakészlettel kezdj.

**Q: Az Aspose.Slides támogatja a PDF‑be exportálást?**  
A: Teljesen. A diagram létrehozása után hívd a `pres.save("output.pdf", SaveFormat.Pdf);`-t.

**Q: Hogyan változtathatom meg a doughnut lyuk méretét?**  
A: Használd a `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` metódust, ahol a value 0‑100 között van.

**Q: Lehetséges adatcímkéket hozzáadni minden sorhoz, nem csak az utolsóhoz?**  
A: Igen, helyezd a címke‑formázó blokkot az `if (i == ...)` feltétel kívülre, és alkalmazd minden `dataPoint`-ra.

**Q: Mely Java verziók támogatottak?**  
A: Az Aspose.Slides 25.4 a JDK 16‑ot és újabbakat támogatja. Régebbi JDK-khoz a megfelelő osztályozó szükséges.

---

**Utoljára frissítve:** 2026-03-07  
**Tesztelve ezzel:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}