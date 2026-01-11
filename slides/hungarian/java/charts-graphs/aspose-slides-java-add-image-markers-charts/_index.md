---
date: '2026-01-11'
description: Tanulja meg, hogyan használja az Aspose Slides for Java-t, adjon hozzá
  képjelölőket a diagramokhoz, és konfigurálja az Aspose Slides Maven függőséget egyedi
  diagramábrákhoz.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Hogyan használjuk az Aspose Slides Java-t: Képmarkerek hozzáadása diagramokhoz'
url: /hu/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan használjuk az Aspose Slides Java-t: Képmarkerek hozzáadása diagramokhoz

## Introduction
A vizuálisan vonzó prezentációk létrehozása kulcsfontosságú a hatékony kommunikációhoz, és a diagramok erőteljes eszközök a komplex adatok tömören történő közvetítésére. Amikor azon tűnődsz, **hogyan használjuk az Aspose**-t, hogy diagramjaid kitűnjenek, a testreszabott képmarkerek a megoldás. A szabványos markerek általánosak lehetnek, de az Aspose.Slides for Java-val bármilyen képpel helyettesítheted őket – így minden adatpont azonnal felismerhető.

Ebben az útmutatóban végigvezetünk a teljes folyamaton, hogyan adhatunk képmarkereket egy vonaldiagramhoz, a **Aspose Slides Maven dependency** beállításától a képek betöltéséig és azok adatpontokra alkalmazásáig. A végére magabiztosan fogod tudni, **hogyan adjunk hozzá markereket**, hogyan **adjunk képeket a diagram** sorozataihoz, és kapsz egy azonnal futtatható kódmintát.

**What You'll Learn**
- Hogyan állítsuk be az Aspose.Slides for Java-t (beleértve a Maven/Gradle-t)
- Alapvető prezentáció és diagram létrehozása
- Képmarkerek hozzáadása a diagram adatpontjaihoz
- A marker méretének és stílusának beállítása az optimális megjelenítéshez

Készen állsz a diagramjaid fejlesztésére? Merüljünk el a követelményekben, mielőtt elkezdenénk!

### Quick Answers
- **Mi a fő cél?** Egyedi képmarkerek hozzáadása a diagram adatpontjaihoz.  
- **Melyik könyvtár szükséges?** Aspose.Slides for Java (Maven/Gradle).  
- **Szükségem van licencre?** Ideiglenes licenc elegendő értékeléshez; teljes licenc szükséges a termeléshez.  
- **Melyik Java verzió támogatott?** JDK 16 vagy újabb.  
- **Használhatok bármilyen képfájlt?** Igen – PNG, JPEG, BMP stb., amíg a fájl elérhető.

### Prerequisites
To follow this tutorial, you'll need:
1. **Aspose.Slides for Java Library** – obtain via Maven, Gradle, or direct download.  
2. **Java Development Environment** – JDK 16 or newer installed.  
3. **Basic Java Programming Knowledge** – familiarity with Java syntax and concepts will be helpful.

## What is the Aspose Slides Maven Dependency?
A Maven függőség a megfelelő binárisokat húzza le a Java verziódhoz. A `pom.xml`-hez való hozzáadása biztosítja, hogy a könyvtár fordítási és futási időben is elérhető legyen.

### Maven Installation
Add the following dependency to your `pom.xml` file:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Installation
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Alternatív megoldásként töltsd le a legújabb kiadást a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Free Trial** – kezd egy ideiglenes licenccel a funkciók felfedezéséhez.  
- **Temporary License** – fejlett képességek feloldása tesztelés közben.  
- **Purchase** – teljes licenc beszerzése kereskedelmi projektekhez.

## Basic Initialization and Setup
Először hozz létre egy `Presentation` objektumot. Ez az objektum képviseli a teljes PowerPoint fájlt, és tartalmazni fogja a diagramunkat.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Implementation Guide
Below is a step‑by‑step walkthrough of adding image markers to a chart. Each code block is accompanied by an explanation so you understand **why** each line matters.

### Step 1: Create a New Presentation with a Chart
Egy vonaldiagramot adunk hozzá alapértelmezett markerekkel az első diára.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Step 2: Access and Configure Chart Data
Töröljük az esetleges alapértelmezett sorozatokat, és hozzáadjuk a saját sorozatainkat, előkészítve a munkalapot az egyedi adatpontokhoz.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Step 3: Add Image Markers to Chart Data Points  
Itt bemutatjuk, **hogyan adjunk hozzá markereket** képek segítségével. Cseréld ki a helyőrző útvonalakat a képek tényleges helyére.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Step 4: Configure Marker Size and Save the Presentation  
A marker stílusát a jobb láthatóság érdekében állítjuk be, majd elmentjük a végleges PPTX fájlt.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Common Issues and Troubleshooting
- **FileNotFoundException** – Ellenőrizd, hogy a kép útvonalak (`YOUR_DOCUMENT_DIRECTORY/...`) helyesek-e, és a fájlok léteznek.  
- **LicenseException** – Győződj meg róla, hogy érvényes Aspose licencet állítottál be, mielőtt bármilyen API-t hívnál termelésben.  
- **Marker Not Visible** – Növeld a `setMarkerSize` értékét, vagy használj nagyobb felbontású képeket a tisztább megjelenítéshez.

## Frequently Asked Questions

**Q: Can I use PNG images instead of JPEG for markers?**  
A: Igen, bármely, az Aspose.Slides által támogatott képformátum (PNG, JPEG, BMP, GIF) használható markerként.

**Q: Do I need a license for the Maven/Gradle packages?**  
A: Ideiglenes licenc elegendő fejlesztéshez és teszteléshez; teljes licenc szükséges a kereskedelmi terjesztéshez.

**Q: Is it possible to add different images to each data point in the same series?**  
A: Teljesen lehetséges. Az `AddImageMarkers` példában két képet váltogatunk, de betölthetsz egyedi képet minden egyes ponthoz is.

**Q: How does the `aspose slides maven dependency` affect project size?**  
A: A Maven csomag csak a kiválasztott JDK verzióhoz szükséges binárisokat tartalmazza, így a lábnyoma mérsékelt. Használhatod a **no‑dependencies** verziót is, ha a méret kritikus.

**Q: What Java versions are supported?**  
A: Az Aspose.Slides for Java támogatja a JDK 8-tól a JDK 21-ig terjedő verziókat. A példában JDK 16 van használva, de a klasszifikátort ennek megfelelően módosíthatod.

## Conclusion
A következő útmutató segítségével most már tudod, **hogyan használjuk az Aspose**-t a diagramok testreszabásához egyedi képmarkerekkel, hogyan konfiguráld a **Aspose Slides Maven dependency**-t, és hogyan **adjunk képeket a diagram** sorozataihoz egy kifinomult, professzionális megjelenés érdekében. Kísérletezz különböző ikonokkal, méretekkel és diagramtípusokkal, hogy olyan prezentációkat hozz létre, amelyek valóban kiemelkednek.

---

**Last Updated:** 2026-01-11  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}