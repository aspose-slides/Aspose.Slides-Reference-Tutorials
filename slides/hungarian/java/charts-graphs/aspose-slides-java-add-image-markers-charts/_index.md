---
date: '2026-01-11'
description: Tanulja meg, hogyan használja az Aspose Slides for Java-t, adjon hozzá
  képjelölőket a diagramokhoz, és konfigurálja az Aspose Slides Maven függőséget egyedi
  diagramábrákhoz.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Hogyan használjuk az Aspose Slides Java-t - Képmarkerek hozzáadása diagramokhoz'
url: /hu/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan használjuk az Aspose Slides Java-t: Képmarkerek hozzáadása diagramokhoz

## Bevezetés
A vizuálisan vonzó prezentációk létrehozása kulcsfontosságú a hatékony kommunikációhoz, és a diagramok rendelkezésre álló eszközök komplex adatok tömören közvetítésére. Amikor azon tűnődsz, **hogyan használjuk az Aspose**-t, hogy diagramjaid kitűnjenek, a testreszabott képmarkerek a megoldást. A szabványos markerek általánosak lehetnek, de az Aspose.Slides for Java-val bármilyen képpel helyettesítheti őket – így minden adatpont azonnal felismerhető.

Ebben az útmutatóban végigvezetünk a teljes folyamaton, hogyan adhatunk képmarkereket egy vonaldiagramhoz, a **Aspose Slides Maven dependency** beállításától a képek betöltéséig és azok adatpontokra alkalmazásáig. A végére magabiztosan fogod tudni, **hogyan adjunk hozzá markereket**, hogyan **adjunk képeket a diagram** sorozataihoz, és kapsz egy azonnal futtatható kódmintát.

**Amit meg fogsz tanulni**
- Hogyan állítsuk be az Aspose.Slides for Java-t (beleértve a Maven/Gradle-t)
- Alapvető prezentáció és diagram létrehozása
- Képmarkerek a diagram adatpontjaihoz
- A marker és stílusának beállítása az optimális mérethez

Készen állsz a diagramjaid fejlesztésére? Merüljünk el a követelményekben, nagyon sokat tanulnánk!

### Gyors válaszok
- **Mi a fő cél?** Egyedi képmarkerek szükséges a diagram adatpontjaihoz.
- **Melyik könyvtár szükséges?** Aspose.Slides for Java (Maven/Gradle).
- **Szükségem van licencre?** Ideiglenes licenc értékeléshez; teljes licenc szükséges a termeléshez.
- **Melyik Java verzió támogatott?** JDK16 vagy újabb.
- **Használhatok bármilyen képfájlt?** Igen – PNG, JPEG, BMP stb., amíg a fájl elérhető.

### Előfeltételek
Az oktatóanyag követéséhez a következőkre lesz szüksége:
1. **Aspose.Slides for Java Library** – beszerezhető a Mavenen, a Gradle-en vagy közvetlenül letölthető.
2. **Java fejlesztői környezet** – JDK16 vagy újabb telepítve.
3. **Alapszintű Java programozási ismeretek** – a Java szintaxis és fogalmak ismerete hasznos lesz.

## Mi az Aspose Slides Maven-függősége?
A Maven függőség a megfelelő binárisokat húzza le a Java verziódhoz. A `pom.xml`-hez valós biztosítása, hogy a könyvtár fordítási és futási időben elérhető legyen.

### Maven telepítés
Add hozzá a következő függőséget a `pom.xml` fájlodhoz:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle telepítése
Írd be ezt a sort a `build.gradle` fájlodba:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Alternatív megoldásként töltsd le a legújabb kiadást a [Aspose.Slides for Java]-hoz kiadások](https://releases.aspose.com/slides/java/).

#### Licencbeszerzés lépései
- **Free Trial** – kezd egy ideiglenes licenccel a funkciók felfedezéséhez.
- **Temporary License** – fejlett képességek feloldása tesztelés közben.
- **Vásárlás** – teljes licenc beszerzése kereskedelmi projektekhez.

## Alapvető inicializálás és beállítás
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

## Megvalósítási útmutató
Az alábbiakban lépésről lépésre bemutatjuk a képjelölők diagramhoz való hozzáadását. Minden kódblokkot magyarázat kísér, hogy megértse, **miért** minden sor számít.

### 1. lépés: Hozzon létre egy új prezentációt diagrammal
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

### 2. lépés: A diagramadatok elérése és konfigurálása
Töröljük az előre elkészített sorozatokat, és adjuk hozzá a saját sorozatainkat, a munkalapot az egyedi adatpontokhoz.

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

### 3. lépés: Képjelzők hozzáadása a diagram adatpontjaihoz
Itt bemutatjuk, **hogyan adjunk hozzá markereket** képek segítségével. Cseréld ki a helyőrző útvonalakat a tényleges helyére.

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

### 4. lépés: A jelölő méretének konfigurálása és a prezentáció mentése
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

## Gyakori problémák és hibaelhárítás
- **FileNotFoundException** – Ellenőrizd, hogy a kép útvonalak (`YOUR_DOCUMENT_DIRECTORY/...`) helyesek-e, és a fájlok léteznek.
- **LicenseException** – Gyződj meg róla, hogy érvényes Aspose licencet állítottál be, bármilyen API-t hívnál termelésben.
- **Marker Not Visible** – Növeld a `setMarkerSize` értékét, vagy használj nagyobb felbontású képeket a tisztábbhoz.

## Gyakran Ismételt Kérdések

**K: Használhatok PNG képeket JPEG helyett jelölőként?**
A: Igen, bármilyen, az Aspose.Slides által támogatott képformátum (PNG, JPEG, BMP, GIF) használható markerként.

**K: Szükségem van licencre a Maven/Gradle csomagokhoz?**
A: Ideiglenes licenc fejlesztéshez és teszteléshez; teljes licenc szükséges a kereskedelmi terjesztéshez.

**K: Lehetséges-e különböző képeket hozzáadni ugyanabban a sorozatban lévő adatpontokhoz?**
A: Teljesen lehetséges. Az `AddImageMarkers` példában két képet váltogatunk, de betölthetsz egyedi képet minden egyes ponthoz.

**K: Hogyan befolyásolja az "aspose slides maven dependency" a projekt méretét?**
A: A Maven csomag csak a kiválasztott JDK verzióhoz szükséges binárisokat tartalmazza, így a lábnyoma mérsékelt. Használhatod a **no-dependencies** verziót is, ha a méret kritikus.

**K: Milyen Java-verziók támogatottak?**
A: Az Aspose.Slides for Java támogatja a JDK8-tól a JDK21-ig terjedő verziókat. A példában JDK16 van használva, de a klasszifikátort ennek megfelelően módosíthatja.

## Következtetés
A következő útmutató segítségével most már tudod, **hogyan használjuk az Aspose**-t a diagramok testreszabásához egyedi képmarkerekkel, hogyan konfiguráld a **Aspose Slides Maven dependency**-t, és hogyan **adjunk képeket a diagram** sorozataihoz egy kifinomult, professzionális megjelenés érdekében. Kísérletezz különböző ikonokkal, méretekkel és diagramtípusokkal, hogy olyan prezentációkat hozz létre, amelyek valóban kiemelkednek.

---

**Utolsó frissítés:** 2026-01-11
**Tesztelve:** Aspose.Slides for Java 25.4 (jdk16)
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}