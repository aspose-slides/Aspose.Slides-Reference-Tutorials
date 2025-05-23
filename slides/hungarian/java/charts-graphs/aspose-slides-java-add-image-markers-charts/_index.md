---
"date": "2025-04-17"
"description": "Tanuld meg, hogyan teheted egyedi képjelölők hozzáadásával még élvezetesebbé diagramjaidat az Aspose.Slides Java verziójában. Növeld a vizuálisan megkülönböztető prezentációkkal a felhasználói élményt."
"title": "Aspose.Slides Java mesterképzés – Képjelölők hozzáadása diagramokhoz"
"url": "/hu/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose.Slides Java elsajátítása: Képjelölők hozzáadása diagramokhoz

## Bevezetés
vizuálisan vonzó prezentációk készítése kulcsfontosságú a hatékony kommunikációhoz, és a diagramok hatékony eszközök az összetett adatok tömör és tömör közvetítéséhez. A hagyományos diagramjelölők néha nem elég jól kiemelik az adatokat. Az Aspose.Slides Java verziójával egyéni képek hozzáadásával jelölőként javíthatod diagramjaidat, így azok még vonzóbbak és informatívabbak lesznek.

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan integrálhatsz képjelölőket a diagramjaidba az Aspose.Slides Java könyvtár segítségével. Ezen technikák elsajátításával olyan prezentációkat hozhatsz létre, amelyek egyedi vizuális elemeikkel vonzzák a figyelmet.

**Amit tanulni fogsz:**
- Az Aspose.Slides beállítása Java-hoz
- Alapvető prezentáció és diagram létrehozása
- Képjelölők hozzáadása a diagram adatpontjaihoz
- Jelölőbeállítások konfigurálása az optimális megjelenítés érdekében

Készen állsz, hogy magasabb szintre emeld a listáidat? Mielőtt belekezdenénk, nézzük meg az előfeltételeket!

### Előfeltételek
bemutató követéséhez a következőkre lesz szükséged:
1. **Aspose.Slides Java könyvtárhoz**Maven vagy Gradle függőségeken keresztül, vagy közvetlenül az Aspose oldalról letöltve szerezhető be.
2. **Java fejlesztői környezet**Győződjön meg arról, hogy a JDK 16 telepítve van a gépén.
3. **Alapvető Java programozási ismeretek**Előnyt jelent a Java szintaxisának és fogalmainak ismerete.

## Az Aspose.Slides beállítása Java-hoz
Mielőtt belemerülnénk a kódba, állítsuk be a fejlesztői környezetünket a szükséges könyvtárakkal.

### Maven telepítés
Adja hozzá a következő függőséget a `pom.xml` fájl:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle telepítése
Vedd bele ezt a `build.gradle` fájl:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Vagy töltse le a legújabb kiadást innen: [Aspose.Slides Java kiadásokhoz](https://releases.aspose.com/slides/java/).

#### Licencbeszerzés lépései
- **Ingyenes próbaverzió**Kezdje egy ideiglenes licenccel az Aspose.Slides funkcióinak felfedezéséhez.
- **Ideiglenes engedély**: Ideiglenes licenc beszerzésével hozzáférhet a speciális funkciókhoz.
- **Vásárlás**Hosszú távú használat esetén érdemes teljes licencet vásárolni.

### Alapvető inicializálás és beállítás
Inicializálja a `Presentation` objektum a diák létrehozásának megkezdéséhez:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Ide kerül a diák és diagramok hozzáadásához szükséges kód.
    }
}
```

## Megvalósítási útmutató
Most pedig bontsuk le a képjelölők hozzáadásának folyamatát a diagramsorozathoz.

### Új bemutató létrehozása diagrammal
Először is szükségünk van egy diára, ahová beilleszthetjük a diagramunkat:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // A Presentation objektum inicializálása
        Presentation presentation = new Presentation();

        // Szerezd meg az első diát a gyűjteményből
        ISlide slide = presentation.getSlides().get_Item(0);

        // Alapértelmezett vonaldiagram hozzáadása jelölőkkel a diához
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Diagramadatok elérése és konfigurálása
Ezután a diagram adatlapját fogjuk használni a sorozatok kezeléséhez:

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

        // Töröld a meglévő sorozatot, és adj hozzá egy újat
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Képjelölők hozzáadása diagram adatpontjaihoz
Most pedig jön az izgalmas rész – képek hozzáadása jelölőként:

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

        // Képek betöltése és hozzáadása jelölőkként
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Adatpontok hozzáadása képekkel jelölőként
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

### Diagramsorozat-jelölő konfigurálása és a prezentáció mentése
Végül állítsuk be a marker méretét a jobb láthatóság érdekében, és mentsük el a prezentációnkat:

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

        // Képek betöltése és hozzáadása jelölőkként (példa helyőrző útvonalak használatával)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Következtetés
Az útmutató követésével megtanultad, hogyan javíthatod a diagramjaidat az Aspose.Slides Java-ban egyéni képjelölők hozzáadásával. Ez a megközelítés jelentősen növelheti a prezentációid lebilincselőségét és érthetőségét.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}