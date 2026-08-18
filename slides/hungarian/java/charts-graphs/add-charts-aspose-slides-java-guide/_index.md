---
date: '2026-06-03'
description: Ismerje meg, hogyan adhat hozzá diagramokat az aspose slides maven függőséggel,
  konfigurálhatja az adatcímkéket, és dinamikus diagramokat generálhat Java prezentációkban.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven függőség: Diagramok hozzáadása és konfigurálása prezentációkban
  az Aspose.Slides for Java használatával'
url: /hu/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Diagramok hozzáadása és konfigurálása prezentációkban az Aspose.Slides for Java használatával

## Bevezetés
A **aspose slides maven dependency** lehetővé teszi a Java fejlesztők számára, hogy programozottan hozzanak létre, módosítsanak és gazdagítsanak PowerPoint fájlokat anélkül, hogy valaha megnyitnák a PowerPointot. Sok üzleti és tudományos helyzetben a diagramok kézi beszúrása időigényes és hibára hajlamos. Ez a tutorial lépésről‑lépésre bemutatja, hogyan adjon hozzá egy Buborékdiagramot, kössön adatcímkéket munkalap cellákhoz, és mentse az eredményt – mindezt az aspose slides maven dependency tiszta, újrahasználható módon kihasználva.

**What You'll Learn**
- Hogyan adjunk diagramokat az aspose slides maven dependency segítségével
- Java projekt beállítása Maven vagy Gradle használatával
- Létező prezentáció betöltése és Buborékdiagram beszúrása
- Adatcímkék konfigurálása cellahivatkozásokkal (diagram adatcímkék hozzáadása)
- A frissített fájl mentése későbbi terjesztéshez
- Valós példák, mint a dinamikus diagramgenerálás és prezentációs diagram munkafolyamatok létrehozása

## Gyors válaszok
- **Mely Maven artefakt ad diagramképességet?** `com.aspose:aspose-slides:25.4` (vagy legújabb)  
- **Köthetek adatcímkéket Excel‑stílusú cellákhoz?** Igen – használja a `ChartDataLabel`‑t a `setDataLabelFormat`‑mal és cellahivatkozásokkal.  
- **Szükséges licenc a termeléshez?** Egy teljes licenc eltávolítja a kiértékelési vízjelet és feloldja az összes funkciót.  
- **Működik ez Java 11+ környezetben?** Teljesen; a könyvtár kompatibilis a Java 8‑tól a Java 21‑ig.  
- **Hány diagramtípus támogatott?** Több mint 70 különböző diagramtípus, beleértve a Buborék, Radar és Stock diagramokat.

## Mi az aspose slides maven dependency?
A **aspose slides maven dependency** egy Maven‑kompatibilis csomag, amely teljes körű API‑t biztosít PowerPoint (PPTX, PPT, ODP) fájlok Java‑ban történő létrehozásához és szerkesztéséhez. A `pom.xml`‑be vagy a `build.gradle`‑be való beillesztésével több mint 70 diagramtípushoz, 150+ diaelrendezéshez, valamint alakzatok, animációk és metaadatok manipulálásához férhet hozzá Office telepítése nélkül.

## Miért használjuk az aspose slides maven dependency‑t diagram automatizáláshoz?
Az Aspose.Slides több ezer diából álló prezentációkat másodpercek alatt dolgoz fel standard szerverkörnyezetben, támogat **70+ diagramtípust**, és akár **10 000 diát** is megjeleníthet anélkül, hogy a teljes fájlt memóriába töltené. Ezek a kvantifikált képességek ideálissá teszik vállalati szintű dinamikus diagramgeneráláshoz, ahol a teljesítmény és a skálázhatóság elengedhetetlen.

## Előfeltételek
- **Java Development Kit (JDK)** 8 vagy újabb (Java 11+ ajánlott).  
- **Maven** 3.6+ **or** **Gradle** 6+.  
- **Aspose.Slides for Java** library (the aspose slides maven dependency, version 25.4 or later).  
- Alapvető ismeretek a Java gyűjteményekkel és fájl I/O‑val.  
- Egy kiértékelési vagy teljes licencfájl (`license.json`), ha a kódot a próbaidőszak után szeretné futtatni.

## Hogyan adjunk diagramot egy diára az Aspose.Slides használatával?
Töltsük be a célprezentációt, hozzunk létre egy új diagram alakzatot a kívánt dián, és adjuk meg a diagram típusát (ebben a példában Buborék). A teljes művelet **három tömör kódsor** segítségével végezhető el, amint a könyvtár hivatkozásra került, így tökéletes gyors prototípusfejlesztéshez és termelési csővezetékekhez.

### 1. lépés: Az aspose slides maven dependency hozzáadása
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Ezek a kódrészletek a teljes Aspose.Slides API‑t – beleértve a diagramtámogatást – közvetlenül a Maven Central‑ról töltik le.

### 2. lépés: A prezentáció betöltése és Buborékdiagram beszúrása
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### 3. lépés: A diagram adat sorozatainak és címkéinek konfigurálása
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### 4. lépés: A módosított prezentáció mentése
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Hogyan konfiguráljuk az adatcímkéket cellahivatkozásokkal?
Az adatcímkék külső cellaértékekhez köthetők, hasonlóan az Excel „Link to Cell” funkciójához. Ez a megközelítés megszünteti a keménykódolt értékeket, és lehetővé teszi a **dinamikus diagramgenerálást**, ahol a címke tartalma automatikusan frissül a mögöttes adatok változásakor. Minden címkét egy adott munkafüzet cellához kapcsolva biztosítható, hogy a forrásadat módosítása azonnal tükröződjön a prezentációban, csökkentve a karbantartási erőfeszítést és a elavult információk kockázatát.

### Közvetlen válasz
Hívja meg a `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` metódust, és adjon meg egy `DataLabelFormat`‑ot, amely cellacímre, például `"Sheet1!A2"` hivatkozik. Az Aspose.Slides futásidőben feloldja a hivatkozást, és a cella aktuális értékét helyezi a diagramcímkébe.

### Lépés‑ről‑lépésre
1. Azonosítsa a címkézni kívánt sorozatot.  
2. Szerezze be az `IDataLabel` objektumot minden adatponthoz.  
3. Használja a `setDataLabelFormat`‑ot a `DataLabelFormat`‑tal, amely `CellReference`‑re van beállítva.  
4. Opcionálisan testreszabhatja a betűtípust, színt és megjelenítési beállításokat.

## Hogyan mentjük a módosított prezentációt?
A mentés egyetlen metódushívás, amely az memóriában lévő `Presentation` objektumot fájlútvonalra vagy kimeneti áramlásra írja. A kimeneti formátum (PPTX, PDF, ODP) a megfelelő `SaveFormat` enum megadásával választható. Ez a művelet közvetlenül a lemezre streameli az eredményt, és a `Presentation` példány bezárásakor vagy hatókörön kívül kerülve automatikusan felszabadítja a natív erőforrásokat, ami nagy prezentációk esetén is alacsony memóriahasználatot biztosít.

### Közvetlen válasz
Hívja meg a `presentation.save("output.pptx", SaveFormat.Pptx)`‑t; a könyvtár közvetlenül a lemezre streameli az eredményt, és a `Presentation` példány bezárásakor vagy hatókörön kívül kerülve automatikusan felszabadítja a natív erőforrásokat.

## Gyakorlati alkalmazások
1. **Üzleti jelentések:** Negyedéves értékesítési diagramok automatikus generálása adatbázis dumpból.  
2. **Akademiai előadások:** Élő kutatási adatok beillesztése előadási diákba minden órához.  
3. **Értékesítési bemutatók:** Ügyfélre szabott teljesítmény‑dashboardok gyors létrehozása.  
4. **Projektmenedzsment:** Gantt‑stílusú ütemtervek megjelenítése dinamikus adatcímkékkel.  
5. **Marketing elemzés:** Kampány KPI‑k beágyazása prezentációkba, amelyek frissülnek az új mérőszámok érkezésekor.

## Teljesítményfontosságú szempontok
- **Memória kezelés:** Használjon try‑with‑resources vagy explicit `presentation.dispose()`‑t a natív memória gyors felszabadításához.  
- **Nagy adathalmazok:** Több mint 10 000 adatpont kezelésekor töltse fel a diagram adatokat `ChartDataWorkbook`‑on keresztül, hogy elkerülje a teljes adathalmaz Java objektumokba való betöltését.  
- **Szálbiztonság:** Minden szálnak saját `Presentation` példányt kell használnia; az API nem szálbiztos megosztott objektumok esetén.

## Gyakori problémák és megoldások
- **Issue:** “License file not found.”  
  **Solution:** Helyezze a `license.json`‑t az osztályútvonalra, és hívja meg a `License license = new License(); license.setLicense("license.json");`‑t minden API‑használat előtt.  
- **Issue:** Chart appears blank after saving.  
  **Solution:** Győződjön meg arról, hogy a diagram adatkönyvtára a prezentációval együtt van mentve (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  
- **Issue:** Data labels show “#REF!” errors.  
  **Solution:** Ellenőrizze, hogy a cellahivatkozás karakterlánc pontosan egyezik a munkalap nevével és címével, valamint hogy a hivatkozott munkafüzet csatolva van a diagramhoz.  

## Gyakran ismételt kérdések

**Q: Can I add other chart types besides Bubble?**  
A: Igen, a `ChartType` felsorolás tartalmaz line, bar, pie, radar, stock és több mint 70 további típust.

**Q: Does the aspose slides maven dependency work with OpenJDK?**  
A: Teljesen; kompatibilis az OpenJDK 8‑21‑gyel, és minden főbb operációs rendszeren fut.

**Q: How do I embed a chart from an existing Excel file?**  
A: Töltse be az Excel munkafüzetet a `WorkbookFactory.create(new FileInputStream("data.xlsx"))`‑vel, majd a diagram `ChartDataWorkbook`‑ját kössön a munkafüzethez, mielőtt cellahivatkozásokat állítana be.

**Q: Is there a limit to the number of charts per slide?**  
A: Gyakorlatilag nincs – az Aspose.Slides tucatnyi diagramot képes kezelni egy dián, csak a rendelkezésre álló memória korlátozza.

**Q: What format can I export the final presentation to?**  
A: PPTX, PPT, ODP, PDF, XPS, HTML, valamint képfájlformátumok, mint a PNG és JPEG támogatottak.

## Erőforrások
- [Aspose.Slides for Java kiadások](https://releases.aspose.com/slides/java/) – a legújabb könyvtári binárisok letöltése.  
- [Aspose.Slides Dokumentáció](https://reference.aspose.com/slides/java/) – átfogó API‑referencia és útmutatók.  
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/) – közvetlen letöltési oldal a Maven/Gradle csomagokhoz.  
- [Purchase a License](https://purchase.aspose.com/buy) – teljes kereskedelmi licenc beszerzése.  
- [Free Trial](https://releases.aspose.com/slides/java/) – próbaverzió indítása a funkciók kiértékeléséhez.  
- [Temporary License](https://purchase.aspose.com/temporary-license/) – ideiglenes kulcs kérése a meghosszabbított kiértékeléshez.  
- [Aspose Support Forum](https://forum.aspose.com/c/slides/11) – segítség a közösségtől és az Aspose mérnököktől.

## Következtetés
Most már rendelkezik egy teljes, vég‑től‑végig útmutatóval a **aspose slides maven dependency** használatához diagramok hozzáadásához, konfigurálásához és mentéséhez Java‑prezentációkban. A fenti lépések követésével automatizálhatja a diagramkészítést, élő cellaértékekhez kötheti az adatcímkéket, és professzionális szintű prezentációkat generálhat nagy léptékben. Kísérletezzen más diagramtípusokkal, fedezze fel az animációs API‑kat, és integrálja ezt a munkafolyamatot jelentéskészítő csővezetékeibe a maximális hatás érdekében.

---  
**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Kapcsolódó oktatóanyagok

- [Hogyan hozzunk létre és konfiguráljunk prezentációkat az Aspose.Slides Java-val: Lépésről‑lépésre útmutató](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Create PPTX Java with Aspose.Slides Maven – Automation Guide](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [How to Create Chart in Java with Aspose.Slides: A Comprehensive Guide](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}