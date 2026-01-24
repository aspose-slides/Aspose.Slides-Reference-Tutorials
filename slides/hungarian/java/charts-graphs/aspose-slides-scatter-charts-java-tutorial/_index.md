---
date: '2026-01-24'
description: Lépésről lépésre útmutató a szórásdiagram Java-ban történő létrehozásához
  az Aspose.Slides használatával, adatpontok hozzáadása a szóráshoz és több sorozatos
  szórásdiagram kezelése.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Szórásdiagram létrehozása Java-ban az Aspose.Slides használatával – Testreszabás
  és mentés
url: /hu/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Szórt diagram létrehozása Java-val az Aspose.Slides segítségével

Ebben az útmutatóban **create scatter chart java** projekteket hozunk létre a semmiből, hozzáadunk adatpontokat a szórt diagramhoz, és megtanuljuk, hogyan dolgozzunk több sorozatos szórt diagrammal – mindezt az Aspose.Slides for Java használatával. Végigvezetünk a könyvtár beállításán, a prezentáció inicializálásán, a diagram létrehozásán, az adatok kezelésén, a jelölők testreszabásán, és végül a prezentáció mentésén.

**Mit fogsz megtanulni**
- Könyvtár beállítása a prezentáció fájlok tárolásához  
- Prezentációk inicializálása és manipulálása az Aspose.Slides segítségével  
- Szórt diagram létrehozása egy dián  
- Adatpontok hozzáadása és kezelése minden sorozathoz  
- Sorozattípusok, jelölők testreszabása és több sorozatos szórt diagram kezelése  
- A kész prezentáció mentése  

Kezdjük a szükséges előfeltételekkel.

## Gyors válaszok
- **Mi a fő könyvtár?** Aspose.Slides for Java  
- **Melyik Java verzió szükséges?** JDK 8 vagy újabb (JDK 16 ajánlott)  
- **Hozzáadhatok több mint két sorozatot?** Igen – bármennyi sorozatot hozzáadhatsz egy szórt diagramhoz  
- **Hogyan változtathatom meg a jelölő színeit?** Használd a `series.getMarker().getFillFormat().setFillColor(Color)` metódust  
- **Szükséges licenc a termeléshez?** Igen, egy kereskedelmi licenc eltávolítja a kiértékelési korlátokat  

## Előfeltételek

- **Aspose.Slides for Java** – verzió 25.4 vagy újabb.  
- **Java Development Kit (JDK)** – JDK 8 vagy újabb.  
- Alap Java ismeretek és Maven vagy Gradle ismerete.  

## Az Aspose.Slides for Java beállítása

Integrálja az Aspose.Slides-et a projektjébe az alábbi módszerek egyikével.

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

Vagy töltse le a legújabb csomagot a [Aspose Releases](https://releases.aspose.com/slides/java/) oldalról.

#### Licenc beszerzése
- **Ingyenes próba** – 30‑napos értékelés.  
- **Ideiglenes licenc** – Kiterjesztett tesztelés.  
- **Kereskedelmi licenc** – Teljes termelési használat.

Most merüljünk el a kódban.

## Megvalósítási útmutató

### 1. lépés: Könyvtár beállítása
Először győződjön meg arról, hogy a kimeneti mappa létezik, hogy a prezentáció hibamentesen menthető legyen.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### 2. lépés: Prezentáció inicializálása
Hozzon létre egy új prezentációt, és vegye fel az első diát.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3. lépés: Szórt diagram hozzáadása
Helyezzen be egy szórt diagramot sima vonalakkal a diára.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4. lépés: Diagram adatok kezelése (törlés és sorozatok hozzáadása)
Törölje az alapértelmezett sorozatokat, és adja hozzá a saját sorozatainkat a **multiple series scatter chart**-hez.

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

### 5. lépés: Adatpontok hozzáadása a szórt diagramhoz
Töltse fel minden sorozatot X‑Y értékekkel a **add data points scatter** használatával.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6. lépés: Sorozattípusok és jelölők testreszabása
Állítsa be a vizuális stílust – váltson egyenes vonalakra jelölőkkel, és állítson be különböző jelölő szimbólumokat.

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

### 7. lépés: Prezentáció mentése
Mentse a fájlt a lemezre.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Gyakorlati alkalmazások
- **Pénzügyi elemzés** – Részvényármozgások ábrázolása több sorozatos szórt diagrammal.  
- **Tudományos kutatás** – Kísérleti mérések vizualizálása a add data points scatter használatával a pontos adatmegjelenítéshez.  
- **Projektmenedzsment** – Erőforrás-elosztási trendek megjelenítése több projektben egyetlen szórt diagramon.  

## Teljesítmény szempontok
- A `Presentation` objektum eldobása a mentés után a memória felszabadításához.  
- Nagy adathalmazok esetén töltse fel a munkafüzetet kötegben, ne egyenként.  
- Kerülje a túlzott stílus alkalmazását szoros ciklusokban; alkalmazza a stílusokat az adatok beszúrása után.  

## Gyakori problémák és megoldások

| Probléma | Megoldás |
|----------|----------|
| **A diagram üresnek jelenik meg** | Ellenőrizze, hogy az adatpontok a megfelelő sorozathoz lettek-e hozzáadva, és hogy a munkafüzet indexek egyeznek-e. |
| **A jelölők nem láthatók** | Győződjön meg arról, hogy a `series.getMarker().setSize()` értéke nagyobb, mint 0, és hogy a jelölő szimbólum definiálva van. |
| **OutOfMemoryError nagy diagramok esetén** | Használja a `pres.dispose()`-t a mentés után, és fontolja meg a JVM heap méretének növelését (`-Xmx`). |

## Gyakran Ismételt Kérdések

### Hogyan változtathatom meg a jelölők színét?
Használja a `series.getMarker().getFillFormat().setFillColor(Color)`-t, ahol a `Color` a `java.awt.Color` egy példánya.

### Hozzáadhatok több mint két sorozatot egy szórt diagramhoz?
Természetesen. Ismételje meg a sorozat‑létrehozó blokkot (4. lépés) minden további sorozathoz, amelyre szüksége van.

### Lehetséges a diagramot képként exportálni?
Igen. Hívja meg a `chart.exportChartImage("chart.png", ImageFormat.Png)`-t az összes adat hozzáadása után.

### Támogatja az Aspose.Slides az interaktív tooltip-eket a szórt pontokon?
Bár a PowerPoint önmagában nem biztosít futásidejű tooltip-eket, beágyazhat adatcímkéket a `series.getDataPoints().get_Item(i).getLabel().setText("Your text")` használatával.

### Hogyan animálhatom a szórt sorozatot?
Használja a `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)`-t egy egyszerű megjelenő animáció hozzáadásához.

---

**Last Updated:** 2026-01-24  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}