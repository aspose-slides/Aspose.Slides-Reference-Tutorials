---
date: '2026-02-24'
description: Ismerje meg, hogyan testreszabhatja a szórásdiagramot az Aspose.Slides
  for Java használatával. Ez az útmutató végigvezet a dinamikus szórásdiagramok létrehozásán,
  formázásán és mentésén a prezentációkban.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Scatter diagram testreszabása Aspose Java-ban
url: /hu/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose szórt diagram testreszabása Java-ban

Ebben az oktatóanyagról megtanulja, hogyan **customize scatter chart aspose** a hatékony Aspose.Slides for Java könyvtárral. Végigvezetünk a projekt beállításán, egy szórt diagram létrehozásán, a sorozattípusok és jelölők finomhangolásán, és végül a prezentáció mentésén. A végére programozottan képes lesz professzionális megjelenésű szórt diagramok generálására, és minden vizuális részletet a márkájához vagy jelentési igényeihez igazítani.

## Gyors válaszok
- **Milyen könyvtárra van szükségem?** Aspose.Slides for Java (v25.4+).  
- **Mely Java verzió támogatott?** JDK 8 vagy újabb.  
- **Módosíthatom a jelölő alakzatokat?** Igen – használja a `MarkerStyleType`-ot csillagok, körök stb. kiválasztásához.  
- **Hogyan mentem a fájlt?** Hívja a `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Szükséges licenc?** Egy ingyenes próba a fejlesztéshez működik; a termeléshez kereskedelmi licenc szükséges.

## Mi az a “customize scatter chart aspose”?
Az Aspose-szal történő szórt diagram testreszabása azt jelenti, hogy programozottan definiálja a diagram adatait, megjelenését és viselkedését – minden pont koordinátájától a jelölő szimbólumokig – anélkül, hogy manuálisan megnyitná a PowerPointot. Ez a megközelítés ideális automatizált jelentéskészítéshez, adat‑vezérelt prezentációkhoz, vagy bármely olyan helyzethez, ahol ismételhető, magas minőségű vizualizációra van szükség.

## Miért testreszabjuk a szórt diagramokat az Aspose.Slides segítségével?
- **Teljes ellenőrzés** – módosítsa a sorozattípusokat, jelölő stílusokat, színeket és egyebeket Java kóddal.  
- **Automatizálás** – helyben generáljon tucatnyi diagramot irányítópultokhoz vagy kötegelt jelentésekhez.  
- **Kereszt‑platform** – működik minden Java‑t támogató operációs rendszeren, Office telepítés nélkül.  
- **Teljesítmény** – könnyű API, amely hatékonyan kezeli a nagy adathalmazokat.

## Előkövetelmények

A követéshez győződjön meg róla, hogy rendelkezik:

- **Aspose.Slides for Java** (v25.4 vagy újabb).  
- **Java Development Kit (JDK)** 8 + telepítve.  
- Maven vagy Gradle a függőségkezeléshez (vagy manuálisan letöltheti a JAR‑t).  
- Alapvető Java ismeretek és a választott építőeszköz ismerete.

## Aspose.Slides for Java beállítása

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
- **Free Trial** – 30‑napos értékelés.  
- **Temporary License** – meghosszabbított tesztelési időszak.  
- **Full License** – termelési használat prémium támogatással.

## Lépés‑ről‑lépésre útmutató a Scatter Chart Aspose testreszabásához

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
*Miért fontos:* Az kimeneti mappa létezésének biztosítása megakadályozza a `FileNotFoundException` hibát, amikor később menti a PPTX‑et.

### 2️⃣ Create a new presentation and grab the first slide
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Egy új `Presentation` tiszta vásznat ad; az első dia lesz, ahová a diagramot helyezzük.

### 3️⃣ Add a scatter chart with smooth lines
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
A `ChartType.ScatterWithSmoothLines` sima vonalú szórt diagramot hoz létre, ami tökéletes a trendek megjelenítéséhez.

### 4️⃣ Clear any default series and add your own
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
Az alapértelmezett sorozat eltávolítása teljes ellenőrzést ad a megjelenített adatok felett.

### 5️⃣ Populate the first series with data points
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` egy X‑érték cellát és egy Y‑érték cellát vesz, és pont‑ról‑pontra építi fel a szórt diagramot.

### 6️⃣ Customize series type and marker appearance
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
Itt **customize the scatter chart aspose** a vonalak egyenesre váltásával, a jelölők nagyításával és különböző szimbólumok (csillag vs. kör) kiválasztásával a vizuális tisztaság érdekében.

### 7️⃣ Save the presentation
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
A `Pptx` formátumba mentés megőrzi a diagram összes testreszabását, és a fájlt készen áll a megosztásra vagy további szerkesztésre.

## Gyakori felhasználási esetek testreszabott szórt diagramokhoz
- **Financial dashboards** – részvényár és volumen ábrázolása.  
- **Scientific research** – kísérleti mérések megjelenítése hibajelölőkkel.  
- **Project management** – tervezett és tényleges erőfeszítés összehasonlítása feladatok szerint.  

## Teljesítmény tippek
- A `Presentation` objektum (`pres.dispose()`) felszabadítása a mentés után a natív erőforrások felszabadításához.  
- Nagy adathalmazok esetén először töltse fel a munkafüzetet, majd kössön sorozatot, hogy elkerülje a többszörös UI frissítéseket.  
- Több sorozat hozzáadásakor használja újra ugyanazt az `IChartDataWorkbook` példányt.

## Gyakran Ismételt Kérdések

### Hogyan változtathatom meg a jelölők színét?
Használja a `series.getMarker().getFillFormat().setFillColor(Color)`-t, ahol a `Color` a `java.awt.Color` példánya (pl. `Color.RED`).

### Hozzáadhatok több mint két sorozatot egy szórt diagramhoz?
Természetesen. Ismételje meg a `chart.getChartData().getSeries().add(...)` hívást minden további sorozathoz, és ennek megfelelően töltse fel az adatpontokat.

### Lehetséges egyedi jelmagyarázatot beállítani minden sorozathoz?
Igen. Sorozat létrehozása után hívja a `series.getLegend().setText("Your Legend Text")`-t az alapértelmezett név felülírásához.

### Hogyan exportálhatom a diagramot képként PPTX helyett?
Hívja a `chart.getImage().save("chart.png", ImageFormat.Png)`-t a diagram konfigurálása után. Ez egy önálló PNG fájlt eredményez.

### Mit tegyek, ha animálni kell a szórt pontokat?
Az Aspose.Slides támogatja az animációs effektusokat. Használja a `chart.getTimeline().getMainSequence().addEffect(...)`-t, hogy belépő vagy hangsúlyozó animációkat adjon a diagramhoz vagy egyes sorozatokhoz.

---

**Utolsó frissítés:** 2026-02-24  
**Tesztelve:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}