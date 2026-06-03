---
date: '2026-06-03'
description: Tanulja meg, hogyan exportáljon diagramot Excelbe, és hogyan hozzon létre
  diagramot Java-ban az Aspose.Slides for Java segítségével. Szerezzen mesteri tudást
  a data visualization, a business report slides és a workbook generation terén.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Diagram exportálása Excelbe és diagramok létrehozása az Aspose.Slides segítségével
url: /hu/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagram exportálása Excelbe és diagramok létrehozása az Aspose.Slides segítségével

**Mesteri adatvizualizációs technikák az Aspose.Slides for Java-val**

A mai adat‑központú környezetben a *export chart to excel* programozottan egy olyan képesség, amely a nyers számokat lenyűgöző vizuális történetekké alakíthatja. Akár üzleti jelentés diakészletet, akár interaktív analitikai irányítópultot építesz, az Aspose.Slides for Java lehetővé teszi, hogy a kódból közvetlenül generálj, testre szabj és exportálj diagramokat. Ebben az útmutatóban megtanulod, hogyan hozhatsz létre diagramobjektumokat, exportálhatod a diagram adatait Excelbe, és hogyan kapcsolhatod a diagramokat külső munkafüzetekhez a zökkenőmentes adatkezelés érdekében.

## Gyors válaszok
- **Milyen könyvtár szükséges?** Aspose.Slides for Java (v25.4+).  
- **Exportálhatom a diagram adatait Excelbe?** Igen – használd a `readWorkbookStream()` metódust, és írd a bájtokat egy *.xlsx* fájlba.  
- **Melyik Java verzió szükséges?** JDK 16 vagy újabb.  
- **Szükségem van licencre?** Egy ingyenes próba licenc elegendő az értékeléshez; a termeléshez állandó licenc szükséges.  
- **Milyen diagramtípust mutat be?** Egy kördiagram, de ugyanaz a megközelítés működik oszlop, vonal és más diagramtípusok esetén is.

## Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy tisztán Java API, amely lehetővé teszi a fejlesztők számára, hogy PowerPoint prezentációkat hozzanak létre, szerkesszenek és konvertáljanak Microsoft Office nélkül. Átfogó osztálykészletet biztosít a diák manipulálásához, diagramok generálásához és formátumkonverzióhoz, lehetővé téve az automatizált jelentéskészítési megoldásokat. Támogat **50+ diagramtípust**, teljes adatkötést és közvetlen Excel exportot, így ideális a **data visualization java** projektekhez.

## Miért használjuk az Aspose.Slides-et diagram létrehozásához és diagram exportálásához Excelbe?
A diagram exportálása Excelbe gyorsan és megbízhatóan. Az Aspose.Slides megszünteti az Office telepítésének szükségességét, több mint **50 beépített diagramstílust** kínál, és a prezentációkat **akár 300 MB-ot is feldolgozza 30 másodperc alatt** a szokásos szerverhardveren. Ezen felül natív Excel munkafüzet-generálást is kapsz, amely lehetővé teszi a downstream elemzők számára, hogy a nyers számokkal dolgozzanak manuális másolás‑beillesztés nélkül.

## Előfeltételek
Mielőtt belemerülnénk, győződj meg róla, hogy a következőkkel rendelkezel:

### Szükséges könyvtárak és verziók
- **Aspose.Slides for Java** verzió 25.4 vagy újabb (támogatja a JDK 16+ verziót)

### Környezet beállítási követelmények
- Java Development Kit (JDK) 16 vagy újabb  
- Olyan IDE, mint az IntelliJ IDEA vagy az Eclipse (vagy bármely kedvelt szövegszerkesztő)

### Tudás előfeltételek
- Alapvető Java programozási ismeretek  
- Maven vagy Gradle építőeszközök ismerete

## Az Aspose.Slides for Java beállítása
Add hozzá a könyvtárat a projektedhez a kedvenc építő rendszereddel.

**Maven**  
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

Alternatívaként [töltsd le a legújabb verziót közvetlenül](https://releases.aspose.com/slides/java/).

### Licenc beszerzési lépések
Az Aspose.Slides ingyenes próba licencet kínál a teljes funkcionalitás felfedezéséhez. Ideiglenes licencet is igényelhetsz, vagy megvásárolhatod a hosszabb távú használathoz. Kövesd az alábbi lépéseket:
1. Látogasd meg az [Aspose vásárlási oldalt](https://purchase.aspose.com/buy), hogy megszerezd a licencet.  
2. Ingyenes próba esetén töltsd le a [Releases](https://releases.aspose.com/slides/java/) oldalról.  
3. Ideiglenes licencet igényelj [itt](https://purchase.aspose.com/temporary-license/).

Miután megvan a licencfájl, inicializáld a Java alkalmazásodban:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Lépésről‑lépésre útmutató

### Hogyan hozzunk létre diagramot – Prezentáció betöltése
Tölts be egy meglévő PowerPoint fájlt, mielőtt diagramokat adnál hozzá vagy módosítanád őket.  
A `Presentation` osztály egy PowerPoint fájlt reprezentál a memóriában, elérhetővé téve a diákat, alakzatokat és diagramobjektumokat.  
Töltsd be a fájlt a `new Presentation("input.pptx")` paranccsal, majd az első diát a `presentation.getSlides().get_Item(0)` segítségével kezeld. Mindig hívd meg a `presentation.dispose()` metódust egy `finally` blokkban a natív erőforrások felszabadításához.

### Hogyan hozzunk létre diagramot – Kördiagram hozzáadása egy diára
Helyezz be egy kördiagramot, amely tökéletes a arányos adatok megjelenítéséhez.  
Az `IChart` interfész a diagramkezelés fő belépési pontja; az `addChart` új diagramot hoz létre a cél dián. Add meg a diagram típusát (`ChartType.Pie`), az X/Y koordinátákat, valamint a szélességet/magasságot. Létrehozás után a `ChartData` objektumon keresztül testre szabhatod a címeket, a jelmagyarázatot és az adat sorozatokat.

### Hogyan exportáljunk diagramot Excelbe – Diagram adatok exportálása
A diagram adatok exportálása lehetővé teszi az elemzők számára, hogy a számokkal Excelben dolgozzanak, mélyebb betekintést nyújtva.  
`readWorkbookStream()` visszaadja a diagram alá tartozó Excel munkafüzetet bájt tömbként. Hívd meg a `chart.getChartData().readWorkbookStream()` metódust a munkafüzet lekéréséhez, és írd ezt a tömböt egy `externalWorkbook1.xlsx` nevű fájlba a szokásos Java I/O használatával. A kapott Excel fájl pontosan a diagram által használt adatokat tartalmazza, készen állva a további elemzésre.

### Hogyan hozzunk létre diagramot – Külső munkafüzet beállítása dinamikus adatokhoz
Kösd össze a diagramot egy külső munkafüzettel, hogy élő adatfrissítéseket érj el a dia újraépítése nélkül.  
`setExternalWorkbook()` a diagramot egy külső Excel fájlhoz köti a dinamikus adatfrissítésekhez. Használd a `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")` metódust a diagram külső fájlhoz való kötéséhez. Amikor az Excel munkafüzetet szerkesztik, a diagram automatikusan tükrözi a változásokat a következő megnyitáskor, támogatva a dinamikus jelentési forgatókönyveket.

## Gyakorlati alkalmazások
Az Aspose.Slides sokoldalú megoldásokat kínál különféle valós életbeli helyzetekhez:
1. **Üzleti jelentés diák:** Negyedéves teljesítménydiagramok automatikus generálása az adatcsatornákból.  
2. **Akademiai prezentációk:** Kutatási adatok átalakítása tiszta vizualizációkká manuális diagramkészítés nélkül.  
3. **Pénzügyi elemzés:** Diagram adatok exportálása Excelbe, hogy az auditorok ellenőrizhessék a számokat, csökkentve a manuális hibákat.  
4. **Marketing analitika:** Kampány mutatók vizualizálása és szerkeszthető munkafüzetek megosztása az érintettekkel az együttműködéses döntéshozatalhoz.  
5. **Automatizált irányítópult generálás:** A diagramkészítő API kombinálása ütemezett feladatokkal, hogy minden reggel naprakész diakészleteket állíts elő.

## Gyakori problémák és hibaelhárítás
- **`FileNotFoundException`** – Ellenőrizd, hogy a `dataDir` egy érvényes mappára mutat, és hogy a kimeneti útvonal írható.  
- **Memóriaszivárgások** – Mindig hívd meg a `presentation.dispose()` metódust egy `finally` blokkban a natív erőforrások felszabadításához.  
- **Diagram nem jelenik meg** – Győződj meg róla, hogy a diák index (`get_Item(0)`) létező diára mutat, és hogy a diagram méretei a dia határain belül vannak.  
- **Az Excel export üres fájlt eredményez** – Ellenőrizd, hogy a diagram valóban tartalmaz adat sorozatokat a `readWorkbookStream()` hívása előtt.

## Gyakran ismételt kérdések

**Q: Használhatok más diagramtípust (pl. oszlop, vonal) ugyanazzal a kóddal?**  
A: Igen. Cseréld le a `ChartType.Pie`-t bármely más `ChartType` enum értékre, például `ChartType.Bar` vagy `ChartType.Line`.

**Q: Lehetséges frissíteni a külső munkafüzetet a diagram létrehozása után?**  
A: Teljesen. Módosítsd közvetlenül az Excel fájlt; a kapcsolt diagram a következő megnyitáskor tükrözi a változásokat.

**Q: Szükségem van külön licencre az Excel export funkcióhoz?**  
A: Nem. Az Excel export képesség a standard Aspose.Slides for Java licencben benne van.

**Q: Mely Java verziók támogatottak?**  
A: Az Aspose.Slides for Java támogatja a JDK 16 és újabb verziókat; korábbi verziók működhetnek, de nincsenek hivatalosan tesztelve.

**Q: Hogyan ágyazhatom be a generált Excel munkafüzetet a PPTX fájlba?**  
A: Használd a `chart.getChartData().setExternalWorkbook(null)` metódust a munkafüzet beágyazásához, vagy tartsd meg a külső hivatkozást a dinamikus frissítésekhez.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Recover Workbook Data from PowerPoint Charts Using Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [How to Update PowerPoint Chart Data Range Using Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}