---
date: '2026-07-17'
description: Ismerje meg, hogyan lehet elforgatni a kördiagramot, testreszabni a kördiagram
  színeit, és PDF-be exportálni a diát az Aspose.Slides for Java segítségével – egy
  átfogó adatvizualizációs útmutató.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Forgassa el a kördiagramot és testreszabja a kördiagram színeit az
  Aspose.Slides for Java segítségével. Ismerje meg, hogyan exportálhatja a diát PDF-be,
  és hogyan dolgozhat a diagram adatlapjával.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Kördiagram elforgatása és színek testreszabása Java-ban – Aspose.Slides
  útmutató
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Hogyan forgassuk el a kördiagramot és testreszabjuk a színeket Java-ban az
  Aspose.Slides segítségével
url: /hu/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tortadiagramok létrehozása az Aspose.Slides for Java-val: Teljes útmutató

## Bevezetés
Ebben az útmutatóban megtanulja, hogyan **forgassa el a tortadiagram** elemeit, testre szabja az egyes szeletek színét, és exportálja a végső diát PDF‑be – mindezt az Aspose.Slides for Java segítségével. Akár értékesítési műszerfalat, pénzügyi jelentést vagy bármilyen adat‑vezérelt prezentációt készít, ezen technikák elsajátítása lehetővé teszi, hogy tiszta, szemrevaló vizuális elemeket nyújtson Microsoft Office használata nélkül. Készítsük elő az eszközöket, és vágjunk bele.

## Gyors válaszok
- **Melyik osztály indít új prezentációt?** `Presentation` a `com.aspose.slides`‑ből.  
- **Melyik API hívás ad hozzá egy tortadiagramot?** `slide.addChart(ChartType.Pie, …)`.  
- **Hogyan adhat egyedi színt minden szeletnek?** Hívja a `series.setColorVaried(true)`‑t, és állítson be szilárd kitöltéseket adatpontonként.  
- **Melyik metódus forgatja el a diagramot?** `chart.setRotationAngle(double)` – használjon 0‑tól 360‑ig terjedő fokokat.  
- **Exportálható a dia PDF‑be?** Igen, hívja a `presentation.save("output.pdf", SaveFormat.Pdf)`‑t.  

## Mi az a „tortadiagram színek testreszabása”?
A tortadiagram színeinek testreszabása azt jelenti, hogy minden szeletnek különböző kitöltőszínt rendelünk, ezáltal javítva az olvashatóságot és a vizuális hatást. Az Aspose.Slides‑ben ezt úgy érheti el, hogy engedélyezi a változatos színeket, majd egyes adatpontokhoz szilárd kitöltőszíneket állít be. Ez a megközelítés biztosítja, hogy minden adatcsoport egyértelműen kiemelkedjen a prezentációban.

## Miért használja az Aspose.Slides for Java‑t tortadiagramok létrehozásához?
Az Aspose.Slides **150+ diagramtípust** támogat, és egy 300 oldalas prezentációt kevesebb, mint **5 másodperc** alatt képes megjeleníteni egy tipikus szerveren, mindezt Microsoft Office telepítése nélkül. A könyvtár Windows, Linux és macOS rendszereken fut, így platform‑független rugalmasságot biztosít bármely Java‑alapú adat‑vizualizációs projekthez.

## Előfeltételek
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 vagy újabb
- IDE, például IntelliJ IDEA, Eclipse vagy NetBeans
- Alapvető Java ismeretek és Maven vagy Gradle ismerete

## Az Aspose.Slides for Java beállítása
Adja hozzá a könyvtárat a build konfigurációjához.

**Maven**  
Adja hozzá ezt a kódrészletet a `pom.xml` fájlhoz:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Adja hozzá a következőt a `build.gradle` fájlhoz:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Közvetlen letöltés**  
Ha manuális megközelítést részesít előnyben, töltse le a legújabb JAR‑t a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### Licenc beszerzési lépések
- **Free Trial** – fedezze fel az összes funkciót költség nélkül.  
- **Temporary License** – meghosszabbítja a próbaverzió korlátait rövid időre.  
- **Purchase** – szerezzen be egy állandó licencet a termeléshez.  

**Alapvető inicializálás és beállítás**  
A `Presentation` osztály egy PowerPoint fájlt reprezentál a memóriában, és módszereket biztosít a diák manipulálásához.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Megvalósítási útmutató
Az alábbi lépésről‑lépésre útmutató mindent lefed a dia létrehozásától a végső tortadiagram forgatásáig.

### Prezentáció és dia inicializálása
Hozzon létre egy új `Presentation` példányt, és szerezze meg az első diát, amely a diagram vásznaként szolgál.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Tortadiagram hozzáadása a diához
Az `addChart` a megadott típusú diagram alakzatot adja hozzá a diához a megadott koordinátákon.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Diagram címének beállítása
A `setTitle` szöveges címet ad a diagramnak, és középre helyezi.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Adatcímkék konfigurálása a sorozathoz
A `setShowValue(true)` numerikus értékcímkéket engedélyez a sorozat minden adatpontján.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Diagram adatlap előkészítése
A `ChartDataWorkbook` tárolja a háttéradat táblát, amely a diagram sorozatait és kategóriáit táplálja.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Kategóriák hozzáadása a diagramhoz
Az `addCategory` új kategória címkét hoz létre a diagram adat sorozataihoz.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Sorozat hozzáadása és adatpontok feltöltése
`addSeries` adat sorozatot hoz létre, és a `addDataPointForBarSeries` numerikus értékeket illeszt be minden kategóriához.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Sorozat színeinek és szegélyeinek testreszabása
`setColorVaried(true)` engedélyezi az egyes szeletek színeit, és a `setFillFormat` szilárd kitöltést rendel minden adatponthoz.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Egyedi adatcímkék konfigurálása
A `setDataLabelFormat` testreszabja a címke megjelenését, pozícióját és betűtípusát a tisztább diagram annotációk érdekében.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Forgatási szög beállítása és a prezentáció mentése
A `setRotationAngle` elforgatja a teljes tortadiagramot, a `save` pedig fájlba írja a prezentációt.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Hogyan forgassuk el a tortadiagramot?
Töltse be a diagram objektumot, hívja a `chart.setRotationAngle(45.0)`‑t (vagy bármilyen fokértéket), majd mentse a prezentációt. A tortadiagram forgatása módosítja a kezdőszöget, lehetővé téve egy adott szegmens kiemelését az adatok módosítása nélkül. Ez az egyetlen metódushívás minden `Chart` példányra működik az Aspose.Slides‑ben. A forgatást kombinálhatja a változatos szelet színekkel is, hogy a legfontosabb adatpontot emelje ki.

## Gyakori problémák és megoldások
| Probléma | Ok | Megoldás |
|----------|----|----------|
| **Minden szelet ugyanazt a színt kapja** | `setColorVaried(true)` nincs meghívva | Győződjön meg róla, hogy engedélyezi a változatos színeket a sorozatcsoporton. |
| **Az adatcímkék nem jelennek meg** | `showValue` jelző le van tiltva | Hívja a `setShowValue(true)`‑t a címkeformátumon. |
| **A forgatás nem hat** | Régebbi Aspose.Slides verzió használata | Frissítsen a 25.4 vagy újabb verzióra. |
| **Licenc kivétel futás közben** | Hiányzó vagy érvénytelen licencfájl | Töltse be a licencet a `License license = new License(); license.setLicense("Aspose.Slides.lic");` kóddal a `Presentation` létrehozása előtt. |

## Gyakran feltett kérdések

**K: Hogyan szerezhetek Aspose.Slides licencet Java‑hoz?**  
Válasz: Kérjen ingyenes próbaverziót az Aspose weboldaláról, majd vásároljon állandó licencet. Töltse be futás közben, ahogyan a Gyakori problémák táblázatban látható.

**K: Használhatom ezt a kódot régebbi JDK verziókkal?**  
Válasz: Az API JDK 16 vagy újabb verziót igényel; a régebbi verziók nem támogatottak.

**K: Lehetséges a diagramot képként exportálni PPTX helyett?**  
Válasz: Igen – a renderelés után hívja a `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`‑t.

**K: Mi van, ha több mint egy sorozatra van szükségem egy tortadiagramban?**  
Válasz: A tortadiagramok egyetlen adat sorozatra vannak tervezve; több sorozat esetén fontolja meg a gyűrűdiagram (doughnut) használatát.

**K: Fut-e az Aspose.Slides Linux szervereken?**  
Válasz: Természetesen – az Aspose.Slides for Java platform‑független, és bármely, kompatibilis JDK‑val rendelkező operációs rendszeren működik.

---

**Utoljára frissítve:** 2026-07-17  
**Tesztelve:** Aspose.Slides for Java 25.4 (JDK 16)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Hogyan hozzunk létre tortadiagramokat Java prezentációkban az Aspose.Slides használatával: Átfogó útmutató](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Mesteri tortadiagramok Java-ban az Aspose.Slides használatával: Átfogó útmutató](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Diagram szövegek forgatása Java-ban az Aspose.Slides használatával: Átfogó útmutató](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}