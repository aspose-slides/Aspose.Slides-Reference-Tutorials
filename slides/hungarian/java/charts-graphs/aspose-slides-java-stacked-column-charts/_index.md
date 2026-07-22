---
date: '2026-07-22'
description: Ismerje meg az Aspose Slides Maven Dependency-t, hogy Java-ban stacked
  column chart-et hozzon létre, adatcímkéket adjon hozzá, módosítsa a függőleges tengely
  számformátumát, és exportálja az eredményt PPTX fájlként.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Az Aspose Slides Maven Dependency lehetővé teszi, hogy Java-ban stacked
  column chart-et építsen, testreszabja az adatcímkéket, állítsa be a függőleges tengely
  formátumát, és PPTX‑ként mentse – mindezt tömör, termelésre kész kóddal.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Stacked Column Chart Java-ban'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Stacked Column Chart Java-ban'
url: /hu/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven függőség: Halmozott oszlopdiagram Java-ban

## Bevezetés

Emelje prezentációit azáltal, hogy átfogó adatvizualizációkat épít be az **Aspose.Slides for Java** erejével. Ebben az útmutatóban **halmozott oszlopdiagramot** hoz létre, amely professzionális megjelenést kölcsönöz, legyen szó üzleti jelentésekről vagy projektstatisztikák bemutatásáról. A tutorial végére képes lesz:

- Beállítani a környezetet az **Aspose Slides Maven függőség** használatával
- Prezentációt létrehozni a semmiből
- **Százalékos halmozott diagramot** hozzáadni és megjelenését testre szabni
- **Diagram adatcímkéket formázni** és **a függőleges tengely számformátumát módosítani**
- **A prezentációt PPTX formátumban menteni** egyetlen kódsorral

## Gyors válaszok
- **Milyen könyvtárra van szükségem?** Adja hozzá az `aspose-slides` Maven/Gradle függőséget (lásd az alább található “Aspose Slides Maven függőség” részt).  
- **Melyik diagramtípus hoz létre halmozott nézetet?** Használja a `ChartType.PercentsStackedColumn` értéket a százalékos halmozott oszlopdiagramhoz.  
- **Hogyan változtathatom meg a tengely számformátumát?** Hívja meg az `IAxis.setNumberFormat()` metódust, és állítsa be a `setNumberFormatLinkedToSource(false)` értéket.  
- **Testreszabhatom az adatcímkéket?** Igen – iteráljon minden `IChartDataPoint` elemen, és rendelje hozzá a saját `ITextFrame` objektumát.  
- **Hogyan mentem a fájlt?** Hívja meg a `presentation.save("output.pptx", SaveFormat.Pptx)` metódust.

## Mi az a halmozott oszlopdiagram?
A halmozott oszlopdiagram több adat sorozatot jelenít meg függőlegesen egymásra helyezve minden kategória oszlopában, a **százalékos halmozott** változat pedig minden oszlopot 100 %-ra normalizál, így könnyen összehasonlíthatóak az arányok. Ez a formátum lehetővé teszi a nézők számára, hogy gyorsan felmérjék, egyes komponensek hogyan járulnak hozzá az egészhez különböző kategóriákban, így a trendek és relatív méretek azonnal átláthatóak.

## Miért használjuk az Aspose.Slides for Java-t?
Az Aspose.Slides for Java lehetővé teszi PowerPoint fájlok generálását, szerkesztését és konvertálását **Microsoft Office nélkül**, és **50+ kimeneti formátumot** támogat Windows, Linux és macOS rendszereken. A könyvtár teljes egészében JRE-en fut, ami szerveroldali automatizálást és nagy áteresztőképességű jelentéskészítést tesz lehetővé. Emellett finomhangolt vezérlést biztosít a diagram objektumok, diák elrendezései és dokumentum tulajdonságai felett, így ideális vállalati szintű prezentációk generálásához.

## Előfeltételek
- **Java Development Kit (JDK):** 8 vagy újabb  
- **IDE:** IntelliJ IDEA, Eclipse vagy bármely Java‑kompatibilis szerkesztő  
- **Build Tool:** Maven vagy Gradle (opcionális, de ajánlott)  
- **Alapvető Java ismeretek** – ismernie kell az osztályokat és metódusokat  

## Az Aspose.Slides for Java beállítása
A kezdéshez adja hozzá az Aspose.Slides könyvtárat a projektjéhez.

### Aspose Slides Maven függőség
Adja hozzá a következőket a `pom.xml` fájlhoz (ez a **aspose slides maven dependency**, amire szüksége lesz):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle alternatíva
Ha a Gradlet részesíti előnyben, illessze be ezt a sort a `build.gradle` fájlba:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Alternatívaként töltse le a legújabb JAR‑t a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### Licenc beszerzése
Kezdhet egy ingyenes próbaverzióval, hogy felfedezze az Aspose.Slides funkcióit. A kiértékelési korlátozások eltávolításához fontolja meg egy ideiglenes vagy megvásárolt licenc beszerzését.

- **Ingyenes próba:** Korlátozott funkciók elérése költség nélkül.  
- **Ideiglenes licenc:** Kérje a [Aspose weboldalán](https://purchase.aspose.com/temporary-license/) keresztül.  
- **Megvásárlás:** Látogassa meg a vásárlási oldalt a teljes hozzáféréshez.

### Alapvető inicializálás
A `Presentation` az Aspose.Slides központi osztálya, amely egy PowerPoint fájlt reprezentál a memóriában. Az alábbi minimális kódrészlet bemutatja, hogyan hozhatunk létre egy `Presentation` objektumot:

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

## Implementációs útmutató

### Prezentáció létrehozása és dia hozzáadása
**Áttekintés:**  
Először egy üres prezentációt hozunk létre, és ellenőrizzük, hogy a dia létezik-e.

#### 1. lépés: Presentation objektum inicializálása
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

#### 2. lépés: Prezentáció mentése
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Százalékos halmozott oszlopdiagram hozzáadása a diára
**Áttekintés:**  
Most egy **százalékos halmozott diagramot** helyezünk el az első dián.

`ChartType.PercentsStackedColumn` egy százalékos halmozott oszlopdiagram típusát jelöli.

#### 1. lépés: Dia inicializálása és elérése
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

#### 2. lépés: Diagram hozzáadása a diára
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Diagram tengely számformátumának testreszabása
**Áttekintés:**  
A jobb olvashatóság érdekében **a függőleges tengely formátumát** módosítjuk, hogy százalékokat jelenítsen meg.

`IAxis` a diagram tengelyét reprezentáló interfész, amely lehetővé teszi a formátum- és skálázási beállításokat.

#### 1. lépés: Diagram hozzáadása és elérése
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

#### 2. lépés: Egyéni számformátum beállítása
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Sorozatok és adatpontok hozzáadása a diagramhoz
**Áttekintés:**  
Minta adat sorozatokkal töltjük fel a diagramot.

#### 1. lépés: Prezentáció és diagram inicializálása
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

#### 2. lépés: Adatsorok hozzáadása
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Sorozatok kitöltőszínének formázása
**Áttekintés:**  
Minden sorozatnak külön színt adunk, hogy a diagram könnyebben olvasható legyen.

#### 1. lépés: Diagram inicializálása és elérése
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

#### 2. lépés: Kitöltőszínek beállítása
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Adatcímkék formázása
**Áttekintés:**  
Most **a diagram adatcímkéket** formázzuk úgy, hogy egyedi szöveget jelenítsenek meg.

`IChartDataPoint` egy egyedi adatpontot képvisel egy diagram sorozatban, és az `ITextFrame` tartalmazza a címke szövegét.

#### 1. lépés: Diagram sorozatok és adatpontok elérése
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

#### 2. lépés: Adatcímkék testreszabása
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

## Gyakori problémák és megoldások
- **A diagram üres:** Győződjön meg róla, hogy legalább egy adat sorozatot és adatpontot hozzáadott a mentés előtt.  
- **A tengely számok nem jelennek meg százalékban:** Ne felejtse el beállítani a `verticalAxis.setNumberFormatLinkedToSource(false)` értéket; ellenkező esetben az egyéni formátum figyelmen kívül marad.  
- **Licenc kiértékelési üzenet:** Alkalmazzon érvényes licencfájlt a `Presentation` objektum létrehozása előtt, hogy elnyomja a kiértékelési bannert.

## Gyakran Ismételt Kérdések

**K: Használhatom ezt a kódot Java 11 vagy újabb verzióval?**  
V: Igen. A könyvtár támogatja a JDK 8+ verziókat; csak a megfelelő osztálycímkét (pl. `jdk16` a JDK 16 vagy újabb esetén) használja.

**K: Hogyan exportáljam a diagramot képként a PPTX helyett?**  
V: Használja a `chart.getImage().save("chart.png", ImageFormat.Png);` metódust a diagram diára való hozzáadása után.

**K: Lehetséges-e legendát hozzáadni a halmozott oszlopdiagramhoz?**  
V: Természetesen. Hívja meg a `chart.getChartTitle().addTextFrameForOverriding("My Chart");` metódust, és konfigurálja a `chart.getLegend()` elemet igény szerint.

**K: Mit tehetek, ha a prezentáció generálása után kell frissíteni az adatokat?**  
V: Módosíthatja a `ChartDataWorkbook` celláit, majd meghívhatja a `chart.refresh();` metódust a változások tükrözéséhez.

**K: Működik az Aspose.Slides Linux szervereken?**  
V: Igen. A könyvtár tisztán Java, és bármely, kompatibilis JRE‑t futtató operációs rendszeren működik.

## Következtetés
Ezzel az útmutatóval megtanulta, hogyan **hozzon létre halmozott oszlopdiagramot** Java-ban az **Aspose Slides Maven függőség** használatával, a környezet beállításától a finomhangolt vizuális stílusig. Kísérletezzen különböző adatkészletekkel, színekkel és címkeformátumokkal, hogy jelentései valóban kitűnjenek.

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre csoportosított oszlopdiagramot Java-ban az Aspose.Slides segítségével](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Hogyan állítsuk be a számformátumokat a diagram adatpontjaiban az Aspose.Slides for Java használatával](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Hogyan adjunk hozzá és konfiguráljunk diagramokat prezentációkban az Aspose.Slides for Java használatával](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}