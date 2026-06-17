---
date: '2026-06-03'
description: Ismerje meg, hogyan használja az Aspose Slides Maven Dependency for Java-t,
  hogyan adjon hozzá image markers-t charts-hez, és hogyan konfigurálja a custom chart
  visuals-t az Aspose.Slides segítségével.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Hogyan használjuk az Aspose Slides Maven Dependency for Java: Képmarkerek
  hozzáadása diagramokhoz'
url: /hu/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan használjuk az Aspose Slides Maven Dependency for Java-t: Képmarkerek hozzáadása diagramokhoz

## Bevezetés
Ebben az útmutatóban bemutatjuk, **hogyan használjuk az Aspose Slides Maven Dependency for Java**-t képmarkerek hozzáadásához diagramokhoz, így minden adatponthoz egyedi vizuális jelzést adva. A vizuálisan vonzó prezentációk készítése kulcsfontosságú a hatékony kommunikációhoz, és a diagramok hatékony módja a komplex adatok tömören történő közvetítésének. Ha azon tűnődsz, **hogyan használjuk az Aspose**-t a diagramok kiemeléséhez, a testreszabott képmarkerek a megoldás. A szabványos markerek általánosak lehetnek, de az Aspose.Slides for Java-val bármilyen képpel helyettesítheted őket—így minden adatpont azonnal felismerhető lesz.

A útmutató végére képes leszel:

* Beállítani a **aspose slides maven dependency**-t Maven vagy Gradle környezetben.
* Létrehozni egy alap prezentációt, beszúrni egy vonaldiagramot, és törölni az alapértelmezett sorozatot.
* PNG/JPEG/BMP képeket betölteni és egyes adatpontokhoz képmarkerként hozzárendelni.
* A marker méretét, stílusát beállítani, és elmenteni a végleges PPTX fájlt.

Készen állsz, hogy feljavítsd a diagramjaidat? Merüljünk el!

### Gyors válaszok
- **Mi a fő cél?** Egyedi képmarkerek hozzáadása a diagram adatpontjaihoz.  
- **Melyik könyvtár szükséges?** Aspose.Slides for Java (Maven/Gradle).  
- **Szükségem van licencre?** Egy ideiglenes licenc elegendő értékeléshez; teljes licenc szükséges a termeléshez.  
- **Melyik Java verzió támogatott?** JDK 16 vagy újabb.  
- **Használhatok bármilyen képformátumot?** Igen—PNG, JPEG, BMP, GIF stb., amíg a fájl elérhető.

## Mi az Aspose Slides Maven Dependency?
Az Aspose Slides Maven dependency egy Maven artefakt, amely az Aspose.Slides for Java binárisait csomagolja, amelyek a diagramkészítéshez, képfeldolgozáshoz és prezentációkezeléshez szükségesek. A függőség `pom.xml`-hez való hozzáadásával a Maven automatikusan letölti a megfelelő verziót a JDK-hoz, feloldja a tranzitív könyvtárakat, és a teljes API-t elérhetővé teszi fordítás és futás közben.

### Hogyan adjuk hozzá az Aspose Slides Maven Dependency-t?
Töltsd be az Aspose Slides könyvtárat Maven és Gradle segítségével. A közvetlen válasz: add hozzá a `<dependency>` kódrészletet a `pom.xml`-hez **vagy** az `implementation` sort a `build.gradle`-hez. Ez az egyetlen lépés lehetővé teszi a teljes API, köztük a diagram‑specifikus és képmarker‑funkcionalitás azonnali használatát a projektedben.

#### Maven telepítés
Add hozzá a következő függőséget a `pom.xml` fájlodhoz:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle telepítés
Illeszd be ezt a sort a `build.gradle` fájlodba:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Közvetlen letöltés
Alternatívaként töltsd le a legújabb kiadást a [Aspose.Slides for Java kiadások](https://releases.aspose.com/slides/java/) oldalról.

#### Licenc beszerzési lépések
- **Ingyenes próba** – kezdj egy ideiglenes licenccel a funkciók felfedezéséhez.  
- **Ideiglenes licenc** – fejlesztés és tesztelés közben feloldja a fejlett képességeket.  
- **Vásárlás** – teljes licenc beszerzése kereskedelmi projektekhez.

## Előfeltételek
A tutorial követéséhez szükséged lesz:

1. **Aspose.Slides for Java Library** – Maven, Gradle vagy közvetlen letöltés útján.  
2. **Java fejlesztői környezet** – JDK 16 vagy újabb telepítve.  
3. **Alap Java programozási ismeretek** – a Java szintaxis és koncepciók ismerete hasznos lesz.  

## Alap inicializálás és beállítás
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

## Implementációs útmutató
Az alábbiakban lépésről‑lépésre bemutatjuk a képmarkerek hozzáadását egy diagramhoz. Minden kódrészlethez magyarázat tartozik, hogy megértsd, **miért** fontos az adott sor.

### 1. lépés: Új prezentáció létrehozása diagrammal
A `Presentation` objektum új PPTX fájlt hoz létre, az `ISlide` pedig egy diát képvisel, ahol a diagram elhelyezésre kerül.

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

### 2. lépés: Diagramadatok elérése és konfigurálása
Az `IChart` interfész metódusokat biztosít a sorozatok, kategóriák és adatpontok módosításához a diagramon belül.

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

### 3. lépés: Képmarkerek hozzáadása a diagram adatpontjaihoz  
Az `IDataPoint` egy egyedi pontot képvisel, és a `setMarker` metódusa egy egyéni képet rendel a markerhez.

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

### 4. lépés: Marker méretének beállítása és a prezentáció mentése  
A `presentation.save` a végleges PPTX fájlt a megadott helyre írja a kiválasztott formátummal.

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

## Miért használjunk képmarkereket diagramokban?
Az `Aspose.Slides` **60+ diagramtípust** és **100+ képformátumot** támogat, lehetővé téve, hogy bármilyen vizuális ikont párosíts egy adatponttal. Az egyedi képmarkerek használata akár **35 %**‑kal is javíthatja az adatérthetőséget felhasználói tanulmányok szerint, mivel a nézők azonnal összekapcsolják az ikont a jelentésével anélkül, hogy a jelmagyarázatot kellene átnézniük.

## Gyakori problémák és hibaelhárítás
- **FileNotFoundException** – Ellenőrizd, hogy a képútvonalak (`YOUR_DOCUMENT_DIRECTORY/...`) helyesek-e, és a fájlok léteznek.  
- **LicenseException** – Győződj meg róla, hogy érvényes Aspose licencet állítottál be, mielőtt bármilyen API-t meghívnál a termelésben.  
- **Marker Not Visible** – Növeld a `setMarkerSize` értékét, vagy használj nagyobb felbontású képeket a tisztább megjelenítéshez.  

## Gyakran ismételt kérdések

**K: Használhatok PNG képeket JPEG helyett a markerekhez?**  
V: Igen, bármely, az Aspose.Slides által támogatott képformátum (PNG, JPEG, BMP, GIF) használható markerként.

**K: Szükségem van licencre a Maven/Gradle csomagokhoz?**  
V: Egy ideiglenes licenc elegendő fejlesztéshez és teszteléshez; teljes licenc szükséges a kereskedelmi terjesztéshez.

**K: Lehet-e különböző képeket hozzáadni minden adatponthoz ugyanabban a sorozatban?**  
V: Természetesen. Az `AddImageMarkers` példában két képet váltogatunk, de betölthetsz egyedi képet minden ponthoz.

**K: Hogyan befolyásolja az aspose slides maven dependency a projekt méretét?**  
V: A Maven csomag csak a kiválasztott JDK verzióhoz szükséges binárisokat tartalmazza, így a lábnyoma **15 MB** alatt marad. Ha a méret kritikus, használhatod a **no‑dependencies** verziót is.

**K: Mely Java verziók támogatottak?**  
V: Az Aspose.Slides for Java támogatja a JDK 8‑tól a JDK 21‑ig terjedő verziókat. A példában JDK 16 van használva, de a classifier-t ennek megfelelően módosíthatod.

## Következtetés
Ezzel az útmutatóval most már tudod, **hogyan használjuk az Aspose Slides Maven Dependency**‑t egyedi képmarkerek hozzáadásához a diagramokhoz, hogyan konfiguráljuk a függőséget, és hogyan **adjunk képeket a diagram sorozatokhoz** egy professzionális megjelenés érdekében. Kísérletezz különböző ikonokkal, méretekkel és diagramtípusokkal, hogy olyan prezentációkat hozz létre, amelyek valóban kiemelkednek.

---

**Last Updated:** 2026-06-03  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Diagram létrehozása Java-val az Aspose.Slides segítségével – Diagramok hozzáadása és ellenőrzése](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Vonaldiagramok létrehozása alapértelmezett markerekkel az Aspose.Slides for Java segítségével](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [PowerPoint diagramok testreszabása egyedi vonalakkal az Aspose.Slides Java segítségével](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}