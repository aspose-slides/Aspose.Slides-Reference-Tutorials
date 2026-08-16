---
date: '2026-08-16'
description: Tanulja meg, hogyan adjon hozzá fánkdiagramokat Java-ban az Aspose.Slides
  használatával. Ez a lépésről‑lépésre útmutató bemutatja a Maven függőség beállítását,
  a diagram konfigurációt, a színeket, a címkéket és a PPTX mentését.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Hogyan adjon hozzá fánkdiagramokat Java-ban az Aspose.Slides használatával.
  Kövesse ezt az útmutatót a Maven beállításához, a színek és címkék testreszabásához,
  valamint PPTX fájlok generálásához.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Hogyan adjon hozzá fánkdiagramot Java-ban az Aspose.Slides használatával
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Hogyan adjon hozzá fánkdiagramot Java-ban az Aspose.Slides használatával
url: /hu/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan adjunk hozzá fánkdiagramot Java-ban az Aspose.Slides segítségével

## Bevezetés

A **doughnut chart** programozott létrehozása lehetővé teszi, hogy a nyers számok szemrevaló, azonnal történetet mesélő vizualissá váljanak. Java-ban a **Aspose.Slides** egyszerűvé teszi ezt a folyamatot, lehetővé téve, hogy prezentációkész diagramokat generálj anélkül, hogy valaha megnyitnád a PowerPointot. Ebben az útmutatóban lépésről lépésre megtanulod, **hogyan adj hozzá doughnut** diagramokat egy PPTX fájlhoz – a Maven Aspose Slides függőség beállításától a sorozatok, kategóriák, színek és címkék testreszabásáig, végül a prezentáció mentéséig.

A útmutató végére képes leszel dinamikus doughnut diagramokat beágyazni bármely PPTX fájlba, ami tökéletes jelentésekhez, műszerfalakhoz vagy automatizált diakészletekhez.

### Gyors válaszok
- **Melyik könyvtárat használják?** Aspose.Slides for Java  
- **Elsődleges feladat?** Add a doughnut chart in a PPTX file  
- **Hogyan adhatod hozzá a könyvtárat?** Use the Maven Aspose Slides dependency (or Gradle)  
- **Minimum Java verzió?** JDK 16 or higher  
- **Testreszabhatom a színeket és címkéket?** Yes, the API provides full formatting control  

## Mi az a doughnut diagram és miért használjuk?

A doughnut diagram a kördiagram egy változata, amely középen üres helyet hagy, lehetővé téve több adat sorozat megjelenítését koncentrikus gyűrűkként. **Az a rész‑egész arányt ábrázolja több kategóriában, miközben a középső területet további információk számára tartja szabadon.** Ez ideálissá teszi a régiók szerinti értékesítési adatok több negyedév alatti összehasonlításához, a költségvetési elosztások osztályok szerint, vagy bármely olyan esethez, ahol hierarchikus arányadatot kell bemutatni.

## Miért használjuk az Aspose.Slides for Java‑t?

Doughnut diagramot hozzáadhatsz anélkül, hogy a Microsoft Office-t telepítenéd, és a könyvtár **több mint 50 + bemeneti és kimeneti formátumot** támogat, miközben 500 diát meghaladó prezentációkat kezel. Az Aspose.Slides **akár 3‑szoros gyorsabb renderelést** biztosít a natív Office automatizáláshoz képest ugyanazon a hardveren, és Windows, Linux és macOS rendszereken is működik. Ezek a számszerű előnyök azt jelentik, hogy nagy diakészleteket generálhatsz fej nélküli szervereken is előre látható teljesítménnyel.

## Előfeltételek

- **Szükséges könyvtárak**  
  - Aspose.Slides for Java 25.4 or later (the library that enables you to add doughnut charts).  

- **Környezet**  
  - JDK 16 or higher installed on your machine.  
  - An IDE such as IntelliJ IDEA, Eclipse or NetBeans.  

- **Ismeretek**  
  - Basic Java syntax and object‑oriented concepts.  
  - Familiarity with Maven or Gradle for dependency management.  

## Maven Aspose Slides függőség

Add hozzá a következő Maven függőséget a `pom.xml` fájlodhoz. Ez a **maven aspose slides függőség**, amelyre szükséged van a könyvtár projektbe való beillesztéséhez.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Ha a Gradle-t részesíted előnyben, használd az alábbi ekvivalens kódrészletet.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

A JAR fájlt közvetlenül is letöltheted a hivatalos kiadási oldalról:  
[ Aspose.Slides for Java kiadások ](https://releases.aspose.com/slides/java/)

### Licenc beszerzése

Az értékelési vízjel eltávolításához és a teljes funkciókészlet feloldásához:

- **Ingyenes próba** – kezdj egy ideiglenes licenccel.  
- **Ideiglenes licenc** – kérj egyet az [Aspose weboldaláról](https://purchase.aspose.com/temporary-license/).  
- **Kereskedelmi licenc** – vásárolj a termelési használathoz.

Alkalmazd a licencet a kódban:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Implementációs útmutató

### Prezentáció inicializálása és doughnut diagram hozzáadása

A Presentation az Aspose.Slides osztály, amely egy PowerPoint prezentációt képvisel. Tölts be egy meglévő PPTX fájlt, vagy hozz létre egy új `Presentation` objektumot, majd adj hozzá egy doughnut diagramot az első diára.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### A diagram adatkönyvtárának konfigurálása és a meglévő adatok törlése

A munkafüzet egy belső táblázat, amely a diagram adatait tárolja. Szerezd meg a diagram mögötti munkafüzetet, majd töröld az esetleges alapértelmezett sorozatokat vagy kategóriákat, hogy tiszta lappal kezdhesd.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Sorozatok hozzáadása a diagramhoz

Egy sorozat a diagramon ábrázolt adatpontok gyűjteménye. Legfeljebb 15 sorozatot adhatsz hozzá. Minden sorozat testreszabható – itt beállítjuk a robbanást, a doughnut‑lyuk méretét és az első szelet szögét.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Kategóriák és adatpontok hozzáadása

A kategóriák a diagram tengelye mentén lévő adatpontok címkéi. Hozz létre 15 kategóriát, és töltsd fel minden sorozatot egy adatponttal. Az utolsó sorozat speciális címkeformázást kap.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Színek és adatcímkék testreszabása

`FillType.Solid` egy szilárd kitöltőszínt határoz meg a diagram elemeihez. Állíts be szilárd kitöltőszínt minden sorozathoz, és engedélyezd az adatcímkéket. Az utolsó sorozatnál a címke betűszínét is módosítjuk.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### A prezentáció mentése

`save` a prezentációt a kiválasztott formátumban egy fájlba írja. Írd a frissített prezentációt lemezre PPTX formátumban, vagy exportáld PDF‑be, ha szükséges.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Gyakori problémák és megoldások

- **Licenc nem található** – Ellenőrizd, hogy a `license.lic` útvonala helyes‑e és a fájl olvasható‑e.  
- **A diagram üresnek jelenik meg** – Győződj meg róla, hogy a meglévő sorozatokat/kategóriákat törölted az újak hozzáadása előtt.  
- **Helytelen színek** – Erősítsd meg, hogy a `FillType.Solid` be van állítva mind a kitöltés, mind a vonal formátumához.  
- **Teljesítmény sok sorozat esetén** – Korlátozd a sorozatok/kategóriák számát, vagy használd újra a munkafüzet cellákat a memóriahasználat kordozásához.  

## Gyakran ismételt kérdések

**Q: Létrehozhatok doughnut diagramot előre létező PPTX fájl nélkül?**  
A: Igen, példányosítsd a `new Presentation()`‑t, hogy egy üres diakészlettel kezdj, majd adj hozzá egy diagramot a fenti módon.

**Q: Támogatja az Aspose.Slides a PDF‑be exportálást?**  
A: Teljes mértékben. A diagram létrehozása után hívd a `pres.save("output.pdf", SaveFormat.Pdf);`‑t, hogy PDF‑verziót kapj a diáról.

**Q: Hogyan változtathatom meg a doughnut lyuk méretét?**  
A: Használd a `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);` metódust, ahol a `value` 0‑tól 100‑ig terjed.

**Q: Lehetséges adatcímkéket hozzáadni minden sorozathoz, nem csak az utolsóhoz?**  
A: Igen, helyezd a címke‑formázó blokkot az `if (i == ...)` feltétel kívülre, és alkalmazd minden `dataPoint`‑ra.

**Q: Mely Java verziók támogatottak?**  
A: Az Aspose.Slides 25.4 támogatja a JDK 16‑ot és újabbakat. Régebbi JDK‑khoz a megfelelő osztályozót kell megadni a Maven függőségben.

---

**Utoljára frissítve:** 2026-08-16  
**Tesztelve:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Szerző:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

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

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Kapcsolódó útmutatók

- [Hogyan adjunk hozzá diagramot a PowerPointhoz az Aspose.Slides for Java használatával: Lépésről‑lépésre útmutató](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hogyan testreszabjuk a kördiagram színeit Java-ban az Aspose.Slides‑el – Teljes útmutató](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [PowerPoint diagram kategóriák animálása az Aspose.Slides for Java‑val | Lépésről‑lépésre útmutató](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}