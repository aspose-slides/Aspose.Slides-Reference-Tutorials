---
date: '2026-01-11'
description: Dowiedz się, jak korzystać z Aspose Slides for Java, dodawać znaczniki
  obrazu do wykresów oraz konfigurować zależność Maven Aspose Slides dla niestandardowych
  wizualizacji wykresów.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Jak używać Aspose Slides Java: Dodawanie znaczników obrazu do wykresów'
url: /pl/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak używać Aspose Slides Java: Dodawanie znaczników obrazu do wykresów

## Wprowadzenie
Tworzenie atrakcyjnych wizualnie prezentacji jest kluczem do skutecznej komunikacji, a wykresy są potężnym narzędziem do zwięzłego przekazywania złożonych danych. Gdy zastanawiasz się **jak używać Aspose**, aby Twoje wykresy wyróżniały się, odpowiedzią są niestandardowe znaczniki obrazu. Standardowe znaczniki mogą wyglądać generically, ale dzięki Aspose.Slides for Java możesz zamienić je na dowolny obraz — sprawiając, że każdy punkt danych jest od razu rozpoznawalny.

W tym samouczku przeprowadzimy Cię przez cały proces dodawania znaczników obrazu do wykresu liniowego, od skonfigurowania **Aspose Slides Maven dependency** po wczytanie obrazów i zastosowanie ich do punktów danych. Po zakończeniu będziesz pewny **jak dodać znaczniki**, jak **dodać obrazy do serii wykresu** oraz będziesz mieć gotowy do uruchomienia przykład kodu.

**Czego się nauczysz**
- Jak skonfigurować Aspose.Slides for Java (w tym Maven/Gradle)
- Tworzenie podstawowej prezentacji i wykresu
- Dodawanie znaczników obrazu do punktów danych wykresu
- Konfigurowanie rozmiaru i stylu znacznika dla optymalnej wizualizacji

Gotowy, aby podnieść jakość swoich wykresów? Przejdźmy do wymagań wstępnych, zanim zaczniemy!

### Szybkie odpowiedzi
- **Jaki jest główny cel?** Dodanie niestandardowych znaczników obrazu do punktów danych wykresu.  
- **Jakiej biblioteki potrzebujesz?** Aspose.Slides for Java (Maven/Gradle).  
- **Czy potrzebna jest licencja?** Tymczasowa licencja wystarczy do oceny; pełna licencja jest wymagana w produkcji.  
- **Jaką wersję Javy obsługuje?** JDK 16 lub nowszą.  
- **Czy mogę używać dowolnego formatu obrazu?** Tak — PNG, JPEG, BMP itp., pod warunkiem, że plik jest dostępny.

### Wymagania wstępne
Aby podążać za tym samouczkiem, potrzebujesz:
1. **Aspose.Slides for Java Library** — pobierz przez Maven, Gradle lub bezpośrednio.  
2. **Środowisko programistyczne Java** — zainstalowany JDK 16 lub nowszy.  
3. **Podstawowa znajomość programowania w Javie** — znajomość składni i koncepcji Javy będzie pomocna.

## Co to jest Aspose Slides Maven Dependency?
Zależność Maven pobiera właściwe pliki binarne dla Twojej wersji Javy. Dodanie jej do `pom.xml` zapewnia dostępność biblioteki w czasie kompilacji i uruchomienia.

### Instalacja Maven
Dodaj następującą zależność do pliku `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalacja Gradle
Umieść tę linię w pliku `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Alternatywnie, pobierz najnowsze wydanie z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroki uzyskania licencji
- **Bezpłatna wersja próbna** — rozpocznij od tymczasowej licencji, aby wypróbować funkcje.  
- **Licencja tymczasowa** — odblokowuje zaawansowane możliwości podczas testów.  
- **Zakup** — uzyskaj pełną licencję do projektów komercyjnych.

## Podstawowa inicjalizacja i konfiguracja
Najpierw utwórz obiekt `Presentation`. Obiekt ten reprezentuje cały plik PowerPoint i będzie przechowywał nasz wykres.

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
Poniżej znajduje się krok‑po‑kroku opis dodawania znaczników obrazu do wykresu. Każdy blok kodu jest opatrzony wyjaśnieniem, abyś rozumiał **dlaczego** dana linia jest istotna.

### Krok 1: Utwórz nową prezentację z wykresem
Dodajemy wykres liniowy z domyślnymi znacznikami do pierwszego slajdu.

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
Usuwamy domyślne serie i dodajemy własne, przygotowując arkusz kalkulacyjny do niestandardowych punktów danych.

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
Tutaj demonstrujemy **jak dodać znaczniki** przy użyciu obrazów. Zamień ścieżki zastępcze na rzeczywiste lokalizacje swoich obrazów.

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
Dostosowujemy styl znacznika dla lepszej widoczności i zapisujemy finalny plik PPTX.

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

## Typowe problemy i rozwiązywanie
- **FileNotFoundException** – Sprawdź, czy ścieżki do obrazów (`YOUR_DOCUMENT_DIRECTORY/...`) są poprawne i czy pliki istnieją.  
- **LicenseException** – Upewnij się, że przed wywołaniem jakiegokolwiek API w produkcji ustawiłeś ważną licencję Aspose.  
- **Znacznik niewidoczny** – Zwiększ `setMarkerSize` lub użyj obrazów o wyższej rozdzielczości, aby uzyskać wyraźniejszy efekt.

## Najczęściej zadawane pytania

**P: Czy mogę używać obrazów PNG zamiast JPEG jako znaczników?**  
O: Tak, każdy format obrazu obsługiwany przez Aspose.Slides (PNG, JPEG, BMP, GIF) działa jako znacznik.

**P: Czy potrzebuję licencji na pakiety Maven/Gradle?**  
O: Tymczasowa licencja wystarczy do rozwoju i testów; pełna licencja jest wymagana przy dystrybucji komercyjnej.

**P: Czy można dodać różne obrazy do każdego punktu danych w tej samej serii?**  
O: Oczywiście. W przykładzie `AddImageMarkers` naprzemiennie używamy dwóch obrazów, ale możesz wczytać unikalny obraz dla każdego punktu.

**P: Jak `aspose slides maven dependency` wpływa na rozmiar projektu?**  
O: Pakiet Maven zawiera tylko niezbędne binaria dla wybranej wersji JDK, co utrzymuje rozmiar w rozsądnych granicach. Możesz także użyć wersji **no‑dependencies**, jeśli rozmiar jest krytyczny.

**P: Jakie wersje Javy są obsługiwane?**  
O: Aspose.Slides for Java obsługuje JDK 8‑21. Przykład używa JDK 16, ale możesz dostosować klasyfikator odpowiednio.

## Zakończenie
Postępując zgodnie z tym przewodnikiem, wiesz już **jak używać Aspose**, aby wzbogacić wykresy o niestandardowe znaczniki obrazu, jak skonfigurować **Aspose Slides Maven dependency** oraz jak **dodać obrazy do serii wykresu** dla profesjonalnego wyglądu. Eksperymentuj z różnymi ikonami, rozmiarami i typami wykresów, aby tworzyć prezentacje, które naprawdę się wyróżniają.

---

**Ostatnia aktualizacja:** 2026-01-11  
**Testowane z:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}