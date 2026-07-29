---
date: '2026-07-27'
description: Hogyan testreszabjuk a diagramot az Aspose.Slides for Java használatával.
  Tanulja meg PowerPoint diagram létrehozását, a szórás sorozat stílusozását, és a
  prezentációk hatékony mentését.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Hogyan testreszabjuk a diagramot az Aspose.Slides for Java segítségével.
  Ez az útmutató bemutatja, hogyan hozhatunk létre PowerPoint diagramot, hogyan stílusozhatjuk
  a szórás pontokat, és hogyan exportálhatjuk a prezentációkat.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Hogyan testreszabjuk a diagramot: Szórásdiagram Aspose Java-ban'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Hogyan testreszabjuk a diagramot: Szórásdiagram Aspose Java-ban'
url: /hu/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Az Aspose szórt diagram testreszabása Java-ban

Ebben az útmutatóban megtudja, **hogyan testreszabja a diagramot** — különösen egy szórt diagramot — a hatékony Aspose.Slides for Java könyvtár segítségével. Végigvezetünk a projekt beállításán, egy szórt diagram létrehozásán, a sorozattípusok és jelölők finomhangolásán, majd a prezentáció mentésén. A végére képes lesz programozottan professzionális megjelenésű szórt diagramokat generálni, és minden vizuális részletet a márkájához vagy a jelentési igényekhez igazítani.

## Gyors válaszok
- **Milyen könyvtárra van szükségem?** Aspose.Slides for Java (v25.4+).  
- **Mely Java verzió támogatott?** JDK 8 vagy újabb.  
- **Módosíthatom a jelölő alakzatát?** Igen – használja a `MarkerStyleType`-ot csillagok, körök stb. kiválasztásához.  
- **Hogyan menthetem a fájlt?** Hívja a `pres.save("output.pptx", SaveFormat.Pptx)`-t.  
- **Szükséges licenc?** Egy ingyenes próba a fejlesztéshez működik; a termeléshez kereskedelmi licenc szükséges.

## Hogyan testreszabjuk a diagramot Java-ban az Aspose.Slides segítségével?
`Presentation` egy Aspose.Slides osztály, amely egy teljes PowerPoint fájlt reprezentál a memóriában. Töltsön be egy új `Presentation`-t, adjon hozzá egy szórt diagramot az első diára, konfigurálja a sorozat- és jelölőstílusokat, majd hívja a `save`-t. Ez az egyetlen munkafolyamat néhány Java sorban teljesen formázott diagramot hoz létre, amely bármely PowerPoint prezentációba beilleszthető.

## Mi az a „customize scatter chart aspose”?
Az Aspose-szal történő szórt diagram testreszabása azt jelenti, hogy programozottan definiálja a diagram adatait, megjelenését és viselkedését – minden pont koordinátájától a jelölő szimbólumokig – anélkül, hogy manuálisan megnyitná a PowerPointot. Ez a megközelítés ideális automatizált jelentéskészítéshez, adat‑vezérelt prezentációkhoz, vagy bármely olyan helyzethez, ahol ismételhető, magas minőségű vizualizációra van szükség.

## Miért testreszabjuk a szórt diagramokat az Aspose.Slides segítségével?
Az Aspose.Slides teljes programozott vezérlést biztosít a fejlesztőknek a diagram megjelenése felett, lehetővé téve a magas minőségű vizualizációk automatizált létrehozását, a jelentési folyamatokba való zökkenőmentes integrációt, és minden vizuális elem testreszabását anélkül, hogy manuálisan megnyitná a PowerPointot, ami időt takarít meg és biztosítja a konzisztenciát a prezentációk között.

- **Teljes irányítás** – módosítsa a sorozattípusokat, jelölőstílusokat, színeket és egyebeket Java kóddal.  
- **Automatizálás** – generáljon tucatnyi diagramot valós időben műszerfalakhoz vagy kötegelt jelentésekhez.  
- **Kereszt‑platform** – működik minden Java‑t támogató operációs rendszeren, Office telepítés nélkül.  
- **Teljesítmény** – könnyű API, amely **150+ diagram típust** dolgoz fel, és több száz oldalas prezentációkat kezel anélkül, hogy a teljes fájlt a memóriába töltené.

## Előfeltételek

A követéshez győződjön meg róla, hogy rendelkezik:

- **Aspose.Slides for Java** (v25.4 vagy újabb).  
- **Java Development Kit (JDK)** 8 + telepítve.  
- Maven vagy Gradle a függőségkezeléshez (vagy manuálisan letöltheti a JAR‑t).  
- Alapvető Java ismeretek és a választott build eszköz ismerete.

## Az Aspose.Slides for Java beállítása

Integrálja a könyvtárat a projektjébe az alábbi módszerek egyikével.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Vagy töltse le a legújabb kiadást a [Aspose Releases](https://releases.aspose.com/slides/java/) oldalról.

#### License Acquisition
- **Ingyenes próba** – 30‑napos értékelés.  
- **Ideiglenes licenc** – meghosszabbított tesztidő.  
- **Teljes licenc** – termelési használat prémium támogatással.

## Lépésről‑lépésre útmutató a szórt diagram testreszabásához Aspose-szal

### 1️⃣ Prepare a folder for your presentation files
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Miért fontos:* Az kimeneti mappa létezésének biztosítása megakadályozza a `FileNotFoundException`-t, amikor később menti a PPTX‑et.

### 2️⃣ Create a new presentation and grab the first slide
`Presentation` egy PowerPoint dokumentumot képvisel, és hozzáférést biztosít a diákhoz és alakzatokhoz. A `Presentation` osztály egy teljes PowerPoint fájlt reprezentál a memóriában.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Add a scatter chart with smooth lines
`ChartType.ScatterWithSmoothLines` egy szórt diagramot hoz létre, ahol a pontok sima vonalakkal vannak összekötve.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Clear any default series and add your own
`IChartSeries` egy diagramon belüli adat sorozatot képvisel.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Populate the first series with data points
`addDataPointForScatterSeries` egyetlen X‑Y pontot ad hozzá egy szórt sorozathoz.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Customize series type and marker appearance
`Marker` szabályozza a diagram sorozat egyes adatpontjaihoz használt vizuális szimbólumot.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Save the presentation
`save` a prezentációt a megadott formátumban egy fájlba írja.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Gyakori felhasználási esetek testreszabott szórt diagramokhoz
- **Pénzügyi műszerfalak** – részvényár és volumen ábrázolása.  
- **Tudományos kutatás** – kísérleti mérések megjelenítése hibajelölőkkel.  
- **Projektmenedzsment** – tervezett és tényleges erőfeszítés összehasonlítása feladatok szerint.  

## Teljesítmény tippek
- Hívja a `pres.dispose()`-t a mentés után a natív memória felszabadításához.  
- Nagy adathalmazok esetén először töltse fel a munkafüzetet, majd kötse a sorozatot, hogy elkerülje az ismétlődő UI frissítéseket.  
- Több sorozat hozzáadásakor használjon egyetlen `IChartDataWorkbook` példányt a memóriahasználat alacsonyan tartásához.

## Gyakran Ismételt Kérdések

**Q: Hogyan változtathatom meg a jelölők színét?**  
A: Használja a `series.getMarker().getFillFormat().setFillColor(Color)`-t, ahol a `Color` egy `java.awt.Color` példány, például `Color.RED`.

**Q: Hozzáadhatok több mint két sorozatot egy szórt diagramhoz?**  
A: Igen. Hívja a `chart.getChartData().getSeries().add(...)`-t minden további sorozathoz, és ennek megfelelően töltse fel a pontokat.

**Q: Lehet egyedi jelmagyarázatot beállítani minden sorozathoz?**  
A: Természetesen. Sorozat létrehozása után hívja a `series.getLegend().setText("Your Legend Text")`-t az alapértelmezett név felülírásához.

**Q: Hogyan exportálhatom a diagramot képként a PPTX helyett?**  
A: Hívja a `chart.getImage().save("chart.png", ImageFormat.Png)`-t a diagram konfigurálása után. Ez egy önálló PNG fájlt hoz létre.

**Q: Mi van, ha animálni szeretném a szórt pontokat?**  
A: Az Aspose.Slides támogatja az animációs hatásokat. Használja a `chart.getTimeline().getMainSequence().addEffect(...)`-t, hogy belépő vagy hangsúlyozó animációkat adjon a diagramhoz vagy egyes sorozatokhoz.

---

**Utolsó frissítés:** 2026-07-27  
**Tesztelve ezzel:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [PowerPoint diagramok létrehozása és testreszabása Java-ban az Aspose.Slides használatával](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Hogyan hozzunk létre buborék diagramot PowerPointban az Aspose.Slides for Java segítségével (Tutorial)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Diagramok létrehozása és testreszabása trendvonalakkal az Aspose.Slides for Java-ban](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}