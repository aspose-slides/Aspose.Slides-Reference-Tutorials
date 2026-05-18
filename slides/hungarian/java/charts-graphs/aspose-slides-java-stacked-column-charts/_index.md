---
date: '2026-02-22'
description: Tanulja meg, hogyan készítsen halmozott oszlopdiagramot Java-ban az Aspose.Slides
  használatával. Ez az útmutató bemutatja az Aspose Slides Maven függőséget, a százalékos
  halmozott diagram hozzáadását, a diagram adatcímkéinek formázását, valamint a prezentáció
  PPTX formátumban való mentését.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Hogyan készítsünk rétegezett oszlopdiagramot Java-ban az Aspose.Slides használatával
  – Átfogó útmutató
url: /hu/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan hozzunk létre halmozott oszlopdiagramot Java-ban az Aspose.Slides segítségével – Átfogó útmutató

## Introduction

Emelje prezentációit a következtető adatvizualizációk beépítésével az Aspose.Slides for Java erejével. Ebben az útmutatóban **halmozott oszlopdiagramot** fog létrehozni, amely professzionális megjelenést kölcsönöz, legyen szó üzleti jelentésekről vagy projektstatisztikák bemutatásáról. A tutorial végére képes lesz:

- Beállítani a környezetet az Aspose Slides Maven függőséggel
- Egy prezentációt létrehozni a semmiből
- **Százalékos halmozott diagram** hozzáadása és megjelenésének testreszabása
- **Diagram adatcímkék formázása** és **függőleges tengely formátumának módosítása**
- **Prezentáció mentése PPTX formátumban** egyetlen kódsorral

Lépjünk végig minden lépésen, hogy azonnal elkezdhesse a hatásos prezentációk építését.

## Quick Answers
- **Milyen könyvtárra van szükségem?** `aspose-slides` Maven/Gradle függőség (lásd alább a „aspose slides maven dependency” részt)  
- **Melyik diagramtípust használjuk?** `ChartType.PercentsStackedColumn` a százalékos‑halmozott oszlopdiagramhoz  
- **Hogyan változtathatom meg a tengely számformátumát?** Használja az `IAxis.setNumberFormat()` metódust, és kapcsolja ki a forráshoz való kötést  
- **Testreszabhatom az adatcímkéket?** Igen – iteráljon a `IChartDataPoint` objektumokon, és állítson be egy egyedi `ITextFrame`‑et  
- **Hogyan mentem a fájlt?** Hívja a `presentation.save("output.pptx", SaveFormat.Pptx)` metódust

## What is a stacked column chart?
A halmozott oszlopdiagram több adat sorozatot jelenít meg egymásra rakva függőleges oszlopokban. A **százalékos‑halmozott** változat esetén minden oszlop mindig 100 %-ot ér el, így könnyen összehasonlítható a különböző kategóriák arányos hozzájárulása.

## Why use Aspose.Slides for Java?
Az Aspose.Slides egy tisztán Java‑alapú API, amely bármely platformon működik Microsoft Office telepítése nélkül. Finomhangolt vezérlést biztosít a diagramobjektumok felett, számos formátumot támogat, és programozottan képes prezentációkat generálni – tökéletes automatizált jelentéskészítéshez vagy szerveroldali dokumentumgeneráláshoz.

## Prerequisites
- **Java Development Kit (JDK):** 8 vagy újabb  
- **IDE:** IntelliJ IDEA, Eclipse vagy bármely Java‑kompatibilis szerkesztő  
- **Build Tool:** Maven vagy Gradle (opcionális, de ajánlott)  
- **Alapvető Java ismeretek** – ismernie kell az osztályokat és metódusokat  

## Setting Up Aspose.Slides for Java
A projekt elindításához adja hozzá az Aspose.Slides könyvtárat.

### Aspose Slides Maven Dependency
Adja hozzá a következőt a `pom.xml`‑hez (ez a **aspose slides maven dependency**, amire szüksége lesz):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Alternative
Ha a Gradlet részesíti előnyben, illessze be ezt a sort a `build.gradle`‑ba:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Alternatívaként töltse le a legújabb JAR‑t a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### License Acquisition
Kezdhet ingyenes próbaverzióval az Aspose.Slides funkcióinak felfedezéséhez. A kiértékelési korlátozások eltávolításához fontolja meg egy ideiglenes vagy megvásárolt licenc beszerzését.

- **Free Trial:** Korlátozott funkciók ingyenes hozzáférése, költség nélkül.  
- **Temporary License:** Kérje a [Aspose weboldalán](https://purchase.aspose.com/temporary-license/)  
- **Purchase:** Látogassa meg a vásárlási oldalt a teljes hozzáférésért.

### Basic Initialization
Itt egy minimális kódrészlet, amely megmutatja, hogyan hozhat létre egy `Presentation` objektumot:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementation Guide

### Creating a Presentation and Adding a Slide
**Overview:**  
Először egy üres prezentációt hozunk létre, és ellenőrizzük, hogy a dia létezik-e.

#### Step 1: Initialize Presentation Object
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Step 2: Save the Presentation
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Adding Percentage Stacked Column Chart to a Slide
**Overview:**  
Most egy **százalékos halmozott diagramot** helyezünk el az első dián.

#### Step 1: Initialize and Access Slide
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Step 2: Add Chart to Slide
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Customizing Chart Axis Number Format
**Overview:**  
A jobb olvashatóság érdekében **módosítjuk a függőleges tengely formátumát**, hogy százalékot jelenítsen meg.

#### Step 1: Add and Access Chart
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Step 2: Set Custom Number Format
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Adding Series and Data Points to Chart
**Overview:**  
A diagramot mintaadat-sorozatokkal töltjük fel.

#### Step 1: Initialize Presentation and Chart
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Step 2: Add Data Series
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatting Series Fill Color
**Overview:**  
Minden sorozatnak adjon egyedi színt, hogy a diagram könnyebben olvasható legyen.

#### Step 1: Initialize and Access Chart
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Step 2: Set Fill Colors
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatting Data Labels
**Overview:**  
Most **formázzuk a diagram adatcímkéket**, hogy egyedi szöveget jelenítsenek meg.

#### Step 1: Access Chart Series and Data Points
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Step 2: Customize Data Labels
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Common Issues and Solutions
- **A diagram üres:** Győződjön meg róla, hogy legalább egy adat sorozatot és adatpontot hozzáadott a mentés előtt.  
- **A tengely számok nem százalékok:** Ne felejtse el beállítani a `verticalAxis.setNumberFormatLinkedToSource(false)`‑t; különben a saját formátum figyelmen kívül marad.  
- **Licenc kiértékelési üzenet:** Alkalmazzon érvényes licencfájlt a `Presentation` objektum létrehozása előtt, hogy elnyomja a kiértékelési bannert.

## Frequently Asked Questions

**Q: Használhatom ezt a kódot Java 11 vagy újabb verzióval?**  
A: Igen. A könyvtár JDK 8+ verziókat támogat; csak a megfelelő klasszifikátort használja (pl. `jdk16` a JDK 16 vagy újabb esetén).

**Q: Hogyan exportáljam a diagramot képként a PPTX helyett?**  
A: Használja a `chart.getImage().save("chart.png", ImageFormat.Png);` metódust a diagram diára helyezése után.

**Q: Lehet-e legendát hozzáadni a halmozott oszlopdiagramhoz?**  
A: Természetesen. Hívja a `chart.getChartTitle().addTextFrameForOverriding("My Chart");`‑t, és konfigurálja a `chart.getLegend()`‑et igény szerint.

**Q: Mi a teendő, ha a generálás után frissíteni kell az adatokat?**  
A: Módosíthatja a `ChartDataWorkbook` cellákat, majd hívja a `chart.refresh();`‑t a változások tükrözéséhez.

**Q: Működik-e az Aspose.Slides Linux szervereken?**  
A: Igen. A könyvtár tisztán Java, és bármely, kompatibilis JRE‑t futtató operációs rendszeren működik.

## Conclusion
Ezzel az útmutatóval megtanulta, hogyan **hozzon létre halmozott oszlopdiagramot** tartalmazó prezentációkat az Aspose.Slides for Java segítségével, a környezet beállításától a finomhangolt vizuális stílusig. Kísérletezzen különböző adatkészletekkel, színekkel és címkeformátumokkal, hogy jelentései valóban kiemelkedjenek.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}