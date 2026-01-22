---
date: '2026-01-22'
description: Tanulja meg, hogyan testreszabhatja a kördiagram színeit és adhat hozzá
  diagramcímet az Aspose.Slides for Java segítségével. Tartalmazza a Maven Aspose
  Slides beállítását és a pptx prezentáció mentésének módját.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: 'Hogyan testreszabjuk a kördiagram színeit Java-ban az Aspose.Slides segítségével:
  Teljes útmutató'
url: /hu/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Pie-diagramok létrehozása az Aspose.Slides for Java segítségével: Hogyan **testreszabjuk a kördiagram színeit** – Teljes útmutató

## Bevezetés
Az adat‑központú történetek bemutatása sokkal egyszerűbb, ha **testreszabhatja a kördiagram színeit**, hogy azok illeszkedjenek a márkájához vagy kiemeljék a kulcsfontosságú értékeket. Ebben az útmutatóban pontosan megmutatjuk, hogyan hozhat létre egy kördiagramot, adjon hozzá diagramcímet, dolgozzon a kördiagram adatpontjaival, és finomhangolja az egyes szeletek színeit az Aspose.Slides for Java segítségével. A végére megtanulja, hogyan **mentse el a pptx prezentációt**, és hogyan integrálja a könyvtdiagramokat (how Maven Asposeleges fájl mentése PPTX prezentációként.

Kezdjük is!

## Gyors válaszok
- **Hogyan adhatok hozzá diagramcímet?** Használja a `chart.getChartTitle().addTextFrameForOverriding("Your Title")` metódust.
- **Melyik build eszköz a legalkalmasabb?** Mind a Maven, mind a Gradle támogatott; a Maven Aspose Slides a leggyakoribb.
- **Megváltoztathatom a szelet színeit?** Igen – állítsa be a `setColorVaried(true)` értéket, és módosítsa az egyes `DataPoint` kitöltését.
- **Milyen formátumban mentődik a fájl?** Használja a `presentation.save("MyChart.pptx", SaveFormat.Pptx)` parancsot.
- **Szükségem van licencre?** Egy ingyenes próba verzió elegendő fejlesztéshez; a termeléshez állandó licenc szükséges.

## Előfeltételek
- **Aspose.Slides for Java** ≥ 25.4 (ajánlott a legújabb verzió).
- **JDK 16+** telepítve és konfigurálva.
- Egy IDE, például IntelliJ IDEA, Eclipse vagy NetBeans.
- Alapvető Java ismeretek és Maven vagy Gradle tapasztalat.

## Aspose.Slides for Java beállítása
Az Aspose.Slides használatához adja hozzá a könyvtárat a projektjéhez.

**Maven** (maven aspose slides)  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Közvetlen letöltés**  
Ha nem szeretne build eszközt használni, töltse le a legújabb kiadást a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### Licenc beszerzésének lépései
- **Ingyenes próba** – kezdje el kísérletezni licenc nélkül.
- **Ideiglenes licenc** – meghosszabbítja a próbaidőszakot.
- **Vásárlás** – teljes licenc beszerzése a termelési környezethez.

### Alapvető inicializálás
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementációs útmutató
Az alábbiakban lépésről‑lépésre bemutatjuk a kódot, pontosan úgy, ahogy az eredeti könyvtár elvárja.

### 1. lépés: Prezentáció és dia inicializálása
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
islide slides = presentation.getSlides().get_Item(0);
```

### 2. lépés: Kördiagram hozzáadása a diára
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### 3. lépés: Diagramcím hozzáadása
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### 4. lépés: Adatcímkék megjelenítése az első sorozathoz
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### 5. lépés: Diagram adatlapjának előkészítése
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### 6. lépés: Kategóriák hozzáadása (kördiagram adatpontok)
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### 7. lépés: Sorozat hozzáadása és adatpontok feltöltése
```java
import com.aspose.slides.*;

// Add a new series and set its name.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### 8. lépés: **Kördiagram színeinek testreszabása** – A tutorial központi része
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### 9. lépés: Egyedi adatcímkék konfigurálása
```java
import com.aspose.slides.*;

// Configure custom labels.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### 10. lépés: Forgatási szög beállítása és **Prezentáció mentése PPTX‑ként**
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Gyakori problémák és hibaelhárítás
- **A színek hiányoznak exportálás után** – Győződjön meg róla, hogy a `setColorVaried(true)` hívás a egyedi adatpontok módosítása előtt történik.
- **Az adatpontok nem, (lásd 5. lépés).
- **A licenc nem érvényesül** – Töltse be a licencfájlt a `Presentation` objektum létrehozása előtt, hogy elkerülje a próba‑vízjelek megjelenését.

## Gyakran ismételt kérdések

**Q: Használhatom ezt a kódot régebbi JA: A könyvtár JDK 16 vagy újabb verziót igényel; régebbi verziók nem támogatottak.

**Q: Hogyan változtathatom meg a diagramcímet a létrehozás után?**  
A: Hívja a `chart.getChartTitle().addTextFrameForOverriding("New Title")` metódust, és szükség szerint állítsa be a szövegformátumot.

**Q: Lehet-e más formátumba exportálni, mint PPTX?**  
A: Igen – az Aspose.Slides támogatja a PDF, ODP és több képfájltípus exportálását a `SaveFormat` enum segítségével.

**Q: Hogyan animálhatom a kördiagram szeleteit?**  
A: Használja a `SlideShow` API‑t a diaátmenetek vagy alakzat‑animációk hozzáadásához a diagram létrehozása után.

**Q: A Maven függőség tartalmazza az összes transzitív könyvtárat?**  
A: A Maven Aspose Slides csomag automatikusan letölti a szükséges függőségeket; külön lépésre nincs szükség.

## Összegzés
Most már rendelkezik egy teljes, termelés‑kész példával, amely megmutatja, **hogyan testreszabjuk a kördiagram színeit**, hogyan adjon hozzá diagramcímet, hogyan dolgozzon a kördiagram adatpontjaival, és **hogyan mentse el a pptx prezentációt** az Aspose.Slides for Java segítségével. Nyugodtan kísérletezzen különböző színpalettákkal, adatkészletekkel és forgatási szögekkel, hogy a márkája stílusához illeszkedjen.

---

**Utoljára frissítve:** 2026-01-22  
**Tesztelt verzió:** Aspose.Slides 25.4 (JDK 16)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}