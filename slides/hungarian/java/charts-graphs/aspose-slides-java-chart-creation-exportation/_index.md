---
date: '2026-02-09'
description: Tanulja meg, hogyan hozhat létre diagramot és exportálhatja azt Excelbe
  az Aspose.Slides for Java segítségével. Sajátítsa el az adatvizualizációt, az üzleti
  jelentés diák készítését és a munkafüzet generálását.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Hogyan készítsünk diagramot az Aspose.Slides Java-val
url: /hu/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagram létrehozása Aspose.Slides for Java használatával

**Mesterszintű adatvizualizációs technikák Aspose.Slides for Java segítségével**

A mai adat‑vezérelt környezetben a *diagram létrehozása* programozott módon olyan készség, amely a nyers számokat lebilincselő vizuális történetekké alakítja. Akár üzleti jelentés prezentációt, akár interaktív analitikai irányítópultot építesz, az Aspose.Slides for Java lehetővé teszi, hogy a kódból közvetlenül generálj, testre szabj és exportálj diagramokat. Ebben az útmutatóban megtanulod, hogyan hozhatsz létre diagramobjektumokat, exportálhatod a diagram adatait Excelbe, és hogyan kapcsolhatod a diagramokat külső munkafüzetekhez a zökkenőmentes adatkezelés érdekében.

## Gyors válaszok
- **Milyen könyvtár szükséges?** Aspose.Slides for Java (v25.4+).  
- **Exportálhatom a diagram adatait Excelbe?** Yes – use `readWorkbookStream()` and write the bytes to an *.xlsx* file.  
- **Melyik Java verzió szükséges?** JDK 16 or higher.  
- **Szükségem van licencre?** A free trial works for evaluation; a permanent license is required for production.  
- **Milyen diagramtípust mutat be?** A Pie chart, but the same approach works for Bar, Line, and other chart types.

## Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy tisztán Java API, amely lehetővé teszi a fejlesztők számára, hogy PowerPoint prezentációkat hozzanak létre, szerkesszenek és konvertáljanak Microsoft Office nélkül. Támogatja a diagramtípusok teljes skáláját, az adatkapcsolást és az exportálási lehetőségeket, így ideális a **data visualization java** projektekhez.

## Miért használjuk az Aspose.Slides-t diagram létrehozásához és diagram exportálásához Excelbe?
- **Nincs Office telepítés** – bármely szerveren vagy felhő környezetben működik.  
- **Gazdag diagramkönyvtár** – tucatnyi diagramtípus és teljes stílusvezérlés.  
- **Közvetlen Excel export** – külső munkafüzet generálása az utólagos elemzéshez.  
- **Teljesítmény‑orientált** – alacsony memóriahasználat és gyors feldolgozás nagy prezentációk esetén.

## Előfeltételek
Mielőtt belemerülnénk, győződj meg róla, hogy a következőkkel rendelkezel:

### Szükséges könyvtárak és verziók
- **Aspose.Slides for Java** version 25.4 or later

### Környezet beállítási követelmények
- Java Development Kit (JDK) 16 or higher  
- Egy IDE, például IntelliJ IDEA vagy Eclipse (vagy bármely kedvelt szövegszerkesztő)

### Tudás előfeltételek
- Basic Java programming skills  
- Familiarity with Maven or Gradle build tools

## Az Aspose.Slides for Java beállítása
Add a könyvtárat a projektedhez a kedvenc építőeszközöd segítségével.

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

Alternatívaként letöltheted a legújabb verziót közvetlenül [download the latest version directly](https://releases.aspose.com/slides/java/).

### Licenc megszerzésének lépései
Aspose.Slides offers a free trial license to explore its full capabilities. You can also apply for a temporary license or purchase one for extended use. Follow these steps:

1. Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get your license.  
2. For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).  
3. Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).

Miután megvan a licencfájl, inicializáld azt a Java alkalmazásodban:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Lépés‑ről‑lépésre útmutató

### Diagram létrehozása – Prezentáció betöltése
Egy meglévő PowerPoint fájl betöltése az első lépés, mielőtt diagramokat adnál hozzá vagy módosítanád őket.

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

**Explanation:**  
- `Presentation` a PowerPoint fájlt képviseli.  
- Mindig hívd meg a `dispose()`-t a natív erőforrások felszabadításához.

### Diagram létrehozása – Kördiagram hozzáadása a diára
Most egy kördiagramot fogunk beszúrni, amely tökéletes a arányos adatok megjelenítésére.

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

**Explanation:**  
- `addChart` a diagramot az első diára helyezi be.  
- A paraméterek határozzák meg a diagram típusát, X/Y pozícióját és méretét.

### Diagram exportálása Excelbe – Diagram adatok exportálása
A diagram adatok exportálása lehetővé teszi az elemzők számára, hogy az Excelben dolgozzanak a számokkal, mélyebb betekintést nyújtva.

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

**Explanation:**  
- `readWorkbookStream()` a diagram alapjául szolgáló Excel munkafüzetet byte tömbként nyeri ki.  
- A byte tömböt a `externalWorkbook1.xlsx` fájlba írja, így egy azonnal használható Excel fájlt kapsz.

### Diagram létrehozása – Külső munkafüzet beállítása dinamikus adatokhoz
A diagram külső munkafüzethez való kapcsolása lehetővé teszi, hogy a diagramot egyszerűen az Excel fájl szerkesztésével frissítsd.

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

**Explanation:**  
- `setExternalWorkbook` a diagramot a megadott Excel fájlhoz köti, élő adatfrissítést biztosítva a dia újraépítése nélkül.

## Gyakorlati alkalmazások
Aspose.Slides offers versatile solutions for various real‑world scenarios:

1. **Üzleti jelentés diák:** Negyedéves teljesítménydiagramok automatikus generálása az adatcsatornáidból.  
2. **Akademiai prezentációk:** Kutatási adatokat alakíts át tiszta vizualizációkká manuális diagramkészítés nélkül.  
3. **Pénzügyi elemzés:** Exportáld a diagram adatait Excelbe, hogy az auditorok ellenőrizhessék a számokat.  
4. **Marketing analitika:** Vizualizáld a kampány mutatókat, és oszd meg a szerkeszthető munkafüzeteket az érintettekkel.

## Gyakori problémák és hibaelhárítás
- **`FileNotFoundException`** – Ellenőrizd, hogy a `dataDir` érvényes mappára mutat-e, és hogy a kimeneti útvonal írható‑e.  
- **Memory leaks** – Mindig hívd meg a `pres.dispose()`-t egy `finally` blokkban a natív erőforrások felszabadításához.  
- **Chart not appearing** – Győződj meg arról, hogy a diák indexe (`get_Item(0)`) egy valóban létező diára mutat.

## Gyakran ismételt kérdések

**Q: Használhatok más diagramtípust (pl. oszlop, vonal) ugyanazzal a kóddal?**  
A: Igen. Cseréld le a `ChartType.Pie`-t bármely más `ChartType` enum értékre, például `ChartType.Bar` vagy `ChartType.Line`.

**Q: Lehetséges frissíteni a külső munkafüzetet a diagram létrehozása után?**  
A: Természetesen. Módosítsd közvetlenül az Excel fájlt; a kapcsolt diagram a következő megnyitáskor tükrözi a változásokat.

**Q: Szükségem van külön licencre az Excel export funkcióhoz?**  
A: Nem. Az Excel export funkció a standard Aspose.Slides for Java licenc része.

**Q: Mely Java verziók támogatottak?**  
A: Az Aspose.Slides for Java támogatja a JDK 16‑ot és újabbakat; a korábbi verziók működhetnek, de nincsenek hivatalosan tesztelve.

**Q: Hogyan ágyazhatom be a generált Excel munkafüzetet a PPTX fájlba?**  
A: Használd a `chart.getChartData().setExternalWorkbook(null)`-t a munkafüzet beágyazásához, vagy tartsd meg a külső hivatkozást a dinamikus frissítésekhez.

---

**Utoljára frissítve:** 2026-02-09  
**Tesztelve ezzel:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}