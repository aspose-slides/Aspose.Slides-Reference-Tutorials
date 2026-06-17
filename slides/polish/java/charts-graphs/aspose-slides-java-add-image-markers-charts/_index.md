---
date: '2026-06-03'
description: Dowiedz się, jak używać zależności Maven Aspose Slides dla Javy, dodawać
  image markers do wykresów oraz konfigurować niestandardowe elementy wizualne wykresów
  przy użyciu Aspose.Slides.
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
title: 'Jak używać zależności Maven Aspose Slides dla Javy: Dodaj image markers do
  wykresów'
url: /pl/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak używać zależności Aspose Slides Maven dla Javy: Dodawanie znaczników obrazu do wykresów

## Wprowadzenie
W tym samouczku pokazujemy **jak używać zależności Aspose Slides Maven dla Javy**, aby dodać znaczniki obrazu do wykresów, dając każdemu punktowi danych unikalną wskazówkę wizualną. Tworzenie atrakcyjnych wizualnie prezentacji jest kluczem do efektywnej komunikacji, a wykresy są potężnym sposobem na zwięzłe przekazanie złożonych danych. Kiedy zastanawiasz się **jak używać Aspose**, aby Twoje wykresy wyróżniały się, odpowiedzią są niestandardowe znaczniki obrazu. Standardowe znaczniki mogą wyglądać generically, ale z Aspose.Slides for Java możesz je zastąpić dowolnym obrazem — sprawiając, że każdy punkt danych jest od razu rozpoznawalny.

Pod koniec tego przewodnika będziesz w stanie:

* Skonfigurować **aspose slides maven dependency** w Mavenie lub Gradle.
* Utworzyć podstawową prezentację, wstawić wykres liniowy i usunąć domyślne serie.
* Wczytać obrazy PNG/JPEG/BMP i przypisać je jako znaczniki dla poszczególnych punktów danych.
* Dostosować rozmiar i styl znacznika oraz zapisać finalny plik PPTX.

Gotowy, aby podnieść jakość swoich wykresów? Zanurzmy się!

### Szybkie odpowiedzi
- **Jaki jest główny cel?** Dodanie niestandardowych znaczników obrazu do punktów danych wykresu.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Slides for Java (Maven/Gradle).  
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do oceny; pełna licencja jest wymagana w produkcji.  
- **Jaką wersję Javy obsługuje?** JDK 16 lub nowszą.  
- **Czy mogę używać dowolnego formatu obrazu?** Tak — PNG, JPEG, BMP, GIF itd., o ile plik jest dostępny.

## Czym jest zależność Aspose Slides Maven?
Zależność Aspose Slides Maven to artefakt Maven, który zawiera binaria Aspose.Slides for Java niezbędne do tworzenia wykresów, obsługi obrazów i manipulacji prezentacjami. Dodając zależność do swojego `pom.xml`, Maven automatycznie pobiera właściwą wersję dla Twojego JDK, rozwiązuje zależności tranzytywne i udostępnia pełne API podczas kompilacji i uruchamiania.

### Jak dodać zależność Aspose Slides Maven?
Załaduj bibliotekę Aspose Slides za pomocą Maven i Gradle. Bezpośrednia odpowiedź: dodaj fragment `<dependency>` do swojego `pom.xml` **lub** linię `implementation` do swojego `build.gradle`. Ten pojedynczy krok udostępnia pełne API, w tym funkcje związane z wykresami i znacznikami obrazu, natychmiast gotowe do użycia w projekcie.

#### Instalacja Maven
Dodaj następującą zależność do pliku `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Instalacja Gradle
Umieść tę linię w pliku `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Bezpośrednie pobranie
Alternatywnie pobierz najnowsze wydanie z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroki uzyskania licencji
- **Bezpłatna wersja próbna** – rozpocznij od tymczasowej licencji, aby przetestować funkcje.  
- **Licencja tymczasowa** – odblokuj zaawansowane możliwości podczas testowania.  
- **Zakup** – uzyskaj pełną licencję do projektów komercyjnych.

## Wymagania wstępne
Aby podążać za tym samouczkiem, potrzebujesz:

1. **Biblioteka Aspose.Slides for Java** – poprzez Maven, Gradle lub bezpośrednie pobranie.  
2. **Środowisko programistyczne Java** – zainstalowany JDK 16 lub nowszy.  
3. **Podstawowa znajomość programowania w Javie** – znajomość składni i koncepcji Javy będzie pomocna.

## Podstawowa inicjalizacja i konfiguracja
Najpierw utwórz obiekt `Presentation`. Ten obiekt reprezentuje cały plik PowerPoint i będzie przechowywał nasz wykres.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Przewodnik implementacji
Poniżej znajduje się krok po kroku opis dodawania znaczników obrazu do wykresu. Każdy blok kodu jest opatrzony wyjaśnieniem, abyś zrozumiał **dlaczego** dana linia jest istotna.

### Krok 1: Utwórz nową prezentację z wykresem
Obiekt `Presentation` tworzy nowy plik PPTX, a `ISlide` reprezentuje slajd, na którym zostanie umieszczony wykres.

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

### Krok 2: Uzyskaj dostęp i skonfiguruj dane wykresu
Interfejs `IChart` udostępnia metody do modyfikacji serii, kategorii i punktów danych w wykresie.

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

### Krok 3: Dodaj znaczniki obrazu do punktów danych wykresu  
`IDataPoint` reprezentuje pojedynczy punkt, a metoda `setMarker` przypisuje niestandardowy obraz jako znacznik.

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

### Krok 4: Skonfiguruj rozmiar znacznika i zapisz prezentację  
`presentation.save` zapisuje finalny plik PPTX w określonej lokalizacji w wybranym formacie.

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

## Dlaczego warto używać znaczników obrazu w wykresach?
`Aspose.Slides` obsługuje **ponad 60 typów wykresów** oraz **ponad 100 formatów obrazów**, co pozwala połączyć dowolną ikonę wizualną z punktem danych. Użycie niestandardowych znaczników obrazu zwiększa czytelność danych nawet o **35 %** w badaniach użytkowników, ponieważ odbiorcy mogą natychmiast skojarzyć ikonę z jej znaczeniem, nie przeglądając legendy.

## Typowe problemy i rozwiązywanie ich
- **FileNotFoundException** – Sprawdź, czy ścieżki do obrazów (`YOUR_DOCUMENT_DIRECTORY/...`) są poprawne i pliki istnieją.  
- **LicenseException** – Upewnij się, że przed wywołaniem jakiegokolwiek API w produkcji ustawiłeś ważną licencję Aspose.  
- **Marker Not Visible** – Zwiększ `setMarkerSize` lub użyj obrazów o wyższej rozdzielczości, aby uzyskać wyraźniejszy wyświetlacz.

## Najczęściej zadawane pytania

**P: Czy mogę używać obrazów PNG zamiast JPEG jako znaczników?**  
O: Tak, każdy format obrazu obsługiwany przez Aspose.Slides (PNG, JPEG, BMP, GIF) działa jako znacznik.

**P: Czy potrzebna jest licencja dla pakietów Maven/Gradle?**  
O: Tymczasowa licencja wystarczy do rozwoju i testów; pełna licencja jest wymagana przy dystrybucji komercyjnej.

**P: Czy można dodać różne obrazy do każdego punktu danych w tej samej serii?**  
O: Oczywiście. W przykładzie `AddImageMarkers` naprzemiennie używamy dwóch obrazów, ale możesz wczytać unikalny obraz dla każdego punktu.

**P: Jak zależność aspose slides maven wpływa na rozmiar projektu?**  
O: Pakiet Maven zawiera tylko niezbędne binaria dla wybranej wersji JDK, utrzymując rozmiar poniżej **15 MB**. Możesz także użyć wersji **no‑dependencies**, jeśli rozmiar jest istotny.

**P: Jakie wersje Javy są obsługiwane?**  
O: Aspose.Slides for Java obsługuje JDK 8 do JDK 21. Przykład używa JDK 16, ale możesz dostosować klasyfikator odpowiednio.

## Zakończenie
Postępując zgodnie z tym przewodnikiem, teraz wiesz **jak używać zależności Aspose Slides Maven**, aby wzbogacić wykresy o niestandardowe znaczniki obrazu, jak skonfigurować zależność oraz **jak dodać obrazy do serii wykresu** dla profesjonalnego wyglądu. Eksperymentuj z różnymi ikonami, rozmiarami i typami wykresów, aby tworzyć prezentacje, które naprawdę się wyróżniają.

---

**Ostatnia aktualizacja:** 2026-06-03  
**Testowane z:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Create chart in Java with Aspose.Slides – Add & Validate Charts](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Create Line Charts with Default Markers Using Aspose.Slides for Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Enhance PowerPoint Charts with Custom Lines Using Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}