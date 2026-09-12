---
date: '2026-09-12'
description: Ismerje meg, hogyan használhatja a Maven Aspose Slides-t a dynamic stock
  charts hozzáadásához és testreszabásához PowerPointban Java-val. Tartalmazza a beállítást,
  az adat sorozatok hozzáadását, a vonalak formázását és a mentést.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: A Maven Aspose Slides oktatóanyag bemutatja, hogyan hozhat létre és
  testreszabhat dynamic stock charts-t PowerPointban Java használatával, bemutatva
  az adat sorozatokat, a vonalak formázását és a mentést.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Maven Aspose Slides útmutató: dinamikus stock charts létrehozása PowerPointban'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: dinamikus stock charts létrehozása PowerPointban Java-val'
url: /hu/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: dinamikus részvénydiagramok létrehozása PowerPointban Java-val

## Bevezetés

**Maven Aspose Slides** lehetővé teszi, hogy programozott módon generálj kifinomult PowerPoint‑prezentációkat Java‑ból. Ebben az útmutatóban megtanulod, hogyan hozz létre dinamikus részvénydiagramokat, hogyan adj hozzá és formázz adat sorozatokat, hogyan testre szabj diagramvonalakat, és végül hogyan mentsd el a fájlt. Akár pénzügyi elemző vagy, aki negyedéves jelentéseket készít, akár fejlesztő, aki automatizált diakészleteket épít, az alábbi lépések egy teljes, termelésre kész megoldást nyújtanak.

**Mit fogsz megtanulni**
- Hogyan állítsd be a Maven‑t az Aspose.Slides for Java‑val  
- Hogyan adj hozzá egy részvénydiagramot és töröld az alapértelmezett adatokat  
- Hogyan **adj hozzá adat sorozat diagramot** és **formázd a diagramvonalakat**  
- Hogyan **testre szabj Java‑specifikus diagram vizuális elemeket**  
- Hogyan mentsd el a frissített prezentációt

Készen állsz, hogy a nyers számokat szemrevaló részvényábrákká alakítsd? Kezdjünk bele!

## Gyors válaszok
- **Mely Maven‑artifactre van szükségem?** `aspose-slides` verzió 25.4 (vagy újabb).  
- **Futtatható ez bármely operációs rendszeren?** Igen – a könyvtár tiszta Java, és működik Windows, macOS és Linux rendszereken.  
- **Szükségem van licencre fejlesztéshez?** Egy ingyenes ideiglenes licenc teszteléshez működik; a termeléshez teljes licenc szükséges.  
- **Milyen diagramtípusok támogatottak?** Több mint 70 beépített diagramtípus, beleértve a részvény, vonal és oszlop diagramokat.  
- **Mekkora prezentációt tudok feldolgozni?** Az Aspose.Slides 500+ diát tartalmazó fájlokat is képes kezelni anélkül, hogy a teljes fájlt a memóriába töltené.

## Mi az a Maven Aspose Slides?

`Aspose.Slides for Java` egy Java API, amely lehetővé teszi PowerPoint‑fájlok létrehozását, manipulálását és konvertálását a Microsoft Office nélkül. A Maven integráció egyszerűsíti a függőségkezelést, lehetővé téve a könyvtár közvetlen letöltését a Maven Central‑ból.

## Miért használjuk a Maven Aspose Slides‑t részvénydiagramokhoz?

Az Aspose.Slides **70+ diagramtípust** támogat, és több száz oldalas prezentációkat képes egy másodpercnél kevesebb idő alatt renderelni tipikus szerverhardveren. A **high‑low line** és **up/down bar** funkciók pontos irányítást biztosítanak a pénzügyi vizualizációk felett, jóval a PowerPoint felhasználói felületénél.

## Előfeltételek

- **Java Development Kit (JDK)** – 11-es vagy újabb verzió.  
- **IDE** – IntelliJ IDEA, Eclipse vagy bármely kedvelt szerkesztő.  
- **Aspose.Slides for Java** – 25.4-es verzió (a legújabb a megírás időpontjában).  

### Az Aspose.Slides for Java beállítása

#### Maven
Az Aspose.Slides Maven‑al történő integrálásához add hozzá a következő függőséget a `pom.xml`‑hez:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Gradle felhasználók számára, helyezd ezt a `build.gradle`‑ba:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Direct download
Alternatívaként töltsd le a legújabb JAR‑t a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

**Licenc beszerzése** – kezd egy ingyenes próbaverzióval vagy kérj ideiglenes licencet. Kereskedelmi felhasználáshoz vásárolj teljes licencet.

Részletes API‑referenciáért lásd a [Aspose.Slides dokumentációt](https://docs.aspose.com/slides/java/).

## Hogyan hozzunk létre dinamikus részvénydiagramot lépésről lépésre

Töltsd be a prezentációt, adj hozzá egy részvénydiagramot, töröld az alapértelmezett adatokat, majd injektáld a saját sorozataidat és kategóriáidat. A központi kérdés közvetlen válasza:

> Tölts be egy meglévő PPTX‑et a `new Presentation("template.pptx")`‑vel, adj hozzá egy `Chart`‑ot `ChartType.Stock` típusúként, töröld az alapértelmezett sorozatokat és kategóriákat, majd töltsd fel saját adatpontjaiddal és formázási beállításokkal. Végül hívd meg a `presentation.save("output.pptx", SaveFormat.Pptx)`‑t.

### Prezentáció inicializálása
#### Áttekintés
Kezdd egy meglévő PowerPoint‑fájl betöltésével, hogy helyben módosíthasd.

#### Lépésről‑lépésre
1. **Importáld a könyvtárat** – a `Presentation` osztály a belépési pont minden diaművelethez.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Töltsd be a prezentációfájlt** – add meg a sablon PPTX elérési útját.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Részvénydiagram hozzáadása a diára
#### Áttekintés
Helyezz be egy Stock diagramot a prezentáció első diájára.

A `Chart` osztály egy diagram alakzatot képvisel, amely a diára adható.

#### Közvetlen válasz
A részvénydiagramot a `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)` hívással adod hozzá. Ez létrehoz egy diagram objektumot, amelyet azonnal manipulálhatsz.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### A diagram meglévő adat sorozatainak és kategóriáinak törlése
#### Áttekintés
Távolíts el minden előre feltöltött sorozatot vagy kategóriát, hogy tiszta adatkészlettel kezdj.

A `ChartData` objektum tárolja a diagram sorozatait és kategóriáit.

#### Közvetlen válasz
Hívd meg a `chart.getChartData().getSeries().clear()` és a `chart.getChartData().getCategories().clear()` metódusokat, hogy töröld az alapértelmezett tartalmat, mielőtt a saját adataidat hozzáadnád.

   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Kategóriák hozzáadása a diagram adataihoz
#### Áttekintés
Határozd meg az X‑tengely kategóriákat (pl. dátumok), amelyek csoportosítják a részvényértékeket.

A `ChartCategory` egy X‑tengely címkét képvisel a diagramon.

#### Közvetlen válasz
Hozz létre egy új `ChartCategory`‑t minden címkéhez a `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")` használatával, ismételve minden hónapra vagy időszakra.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Adatsorozatok hozzáadása a diagramhoz
#### Áttekintés
Add hozzá a négy alapvető sorozatot: Open, High, Low és Close.

A `ChartSeries` egy adott sorozathoz tartozó adatpontok gyűjteményét tárolja a diagramon.

#### Közvetlen válasz
Minden sorozathoz hívd meg a `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())` metódust. Ez regisztrálja a sorozatot a diagram adatkönyvtárában.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Adatpontok hozzáadása a sorozathoz
#### Áttekintés
Töltsd fel minden sorozatot a részvényárakat reprezentáló numerikus értékekkel.

A `DataPoint` egy sorozat egyetlen értékét jelenti.

#### Közvetlen válasz
Iterálj a adatgyűjteményeden, és használd a `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (vagy a sorozattípusnak megfelelő metódust) minden pont beszúrásához.

   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### A high‑low vonalak és up/down sávok formázása
#### Áttekintés
Állítsd be a high‑low összekötők és az up/down sávok kitöltésének vizuális stílusát.

A `Marker` meghatározza egy adatpont vizuális szimbólumát.

#### Közvetlen válasz
Állítsd be a `chart.getChartData().getSeries().get(0).getMarker().setSize(10)`‑t, és konfiguráld a `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)`‑t a vonal vastagságának és színének szabályozásához.

   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Up/down sávok megjelenítése
Használd a diagram `setShowUpDownBars(true)` metódusát az up/down sávok láthatóvá tételéhez.

   ```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Adatcímkék testreszabása a high‑low vonalakon
#### Áttekintés
Jeleníts meg numerikus értékeket közvetlenül a high‑low vonalakon a gyors hivatkozás érdekében.

A `DataLabel` szabályozza az adatpontokhoz csatolt címkék megjelenését.

#### Közvetlen válasz
Engedélyezd az adatcímkéket a `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` használatával, és formázd őket igény szerint.

   ```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Az up/down sávok kitöltőszínének beállítása
#### Áttekintés
Adj az up sávoknak zöld, a down sávoknak piros kitöltést, hogy intuitív módon jelezd a piaci mozgást.

Az `UpDownBars` objektum hozzáférést biztosít az up és down sávok formázásához.

#### Közvetlen válasz
Alkalmazd a `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)`‑t, és állítsd a szilárd színt `Color.GREEN`‑ra; ismételd meg a down sáv esetén `Color.RED`‑del.

   ```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### PowerPoint fájl mentése
#### Áttekintés
Mentsd el a módosításokat egy új PPTX fájlba.

A `save` metódus a prezentációt a megadott formátumban a lemezre írja.

#### Közvetlen válasz
Hívd meg a `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)`‑t – ez a módosított prezentációt a standard PowerPoint formátumban írja a lemezre.

   ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Gyakori problémák és hibaelhárítás

- **A diagram nem jelenik meg** – győződj meg róla, hogy a diagram X/Y koordinátái és méretei a dia határain belül vannak.  
- **Az adatpontok hiányoznak** – ellenőrizd, hogy az adatkönyvtár cellaindexei megegyeznek a kitölteni kívánt sorozat/sorral.  
- **Licenc kivétel** – az ideiglenes próbaverzió 30 nap után lejár; cseréld le egy állandó licencre a termelési buildekhez.  
- **Teljesítménycsökkenés nagy fájloknál** – használd a `Presentation.setCacheSize(0)`‑t a gyorsítótár letiltásához, ha ezrek diáját dolgozod fel egy kötegben.

## Gyakran ismételt kérdések

**K: Használhatom ezt a kódot webalkalmazásban?**  
A: Igen. A könyvtár tiszta Java, ezért bármely servlet konténerben vagy Spring Boot szolgáltatásban futtatható.

**K: Támogatja az Aspose.Slides más diagramtípusokat is a Stock‑on kívül?**  
A: Természetesen. Több mint 70 diagramtípust támogat, beleértve a vonal, oszlop, kör és radar diagramokat.

**K: Hogyan adhatok hozzá diagramcímkét programozottan?**  
A: Használd a `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`‑t, majd formázd a címet igény szerint.

**K: Van korlát a sorozatonkénti adatpontok számában?**  
A: Gyakorlatilag tízezreket adhatsz hozzá, a memóriahasználat lineárisan nő, és a könyvtár adatfolyamot használ a lábnyom alacsonyan tartásához.

**K: Mely Maven koordinátákat használjam a legújabb verzióhoz?**  
A: A legújabb verzió mindig elérhető a `com.aspose:aspose-slides:25.4` (vagy újabb) alatt a Maven Central‑on.

---

**Last Updated:** 2026-09-12  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Kapcsolódó útmutatók

- [aspose slides maven függőség: Diagramok hozzáadása és konfigurálása prezentációkban az Aspose.Slides for Java használatával](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [PowerPoint diagram létrehozása Java‑val – Prezentációk mentése diagramokkal az Aspose.Slides használatával](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [PowerPoint diagramok formázása Aspose Slides Java segítségével](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}