---
"date": "2025-04-17"
"description": "Dowiedz się, jak ulepszyć swoje wykresy w Aspose.Slides for Java, dodając niestandardowe znaczniki obrazów. Zwiększ zaangażowanie dzięki wizualnie odrębnym prezentacjom."
"title": "Master Aspose.Slides Java&#58; Dodawanie znaczników obrazu do wykresów"
"url": "/pl/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie Aspose.Slides Java: Dodawanie znaczników obrazu do wykresów

## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji jest kluczem do skutecznej komunikacji, a wykresy są potężnym narzędziem do przekazywania złożonych danych w zwięzły sposób. Standardowe znaczniki wykresów czasami nie wystarczają, aby wyróżnić dane. Dzięki Aspose.Slides for Java możesz ulepszyć swoje wykresy, dodając niestandardowe obrazy jako znaczniki, dzięki czemu będą bardziej angażujące i informacyjne.

W tym samouczku pokażemy, jak zintegrować znaczniki obrazów z wykresami, korzystając z biblioteki Aspose.Slides w Javie. Opanowując te techniki, będziesz w stanie tworzyć prezentacje, które przyciągają uwagę dzięki unikalnym elementom wizualnym.

**Czego się nauczysz:**
- Jak skonfigurować Aspose.Slides dla Java
- Tworzenie podstawowej prezentacji i wykresu
- Dodawanie znaczników obrazu do punktów danych wykresu
- Konfigurowanie ustawień znaczników w celu uzyskania optymalnej wizualizacji

Gotowy, aby podnieść swoje wykresy? Zanurzmy się w wymaganiach wstępnych, zanim zaczniemy!

### Wymagania wstępne
Aby skorzystać z tego samouczka, będziesz potrzebować:
1. **Aspose.Slides dla biblioteki Java**: Można go pobrać za pośrednictwem zależności Maven lub Gradle albo bezpośrednio ze strony Aspose.
2. **Środowisko programistyczne Java**: Upewnij się, że na Twoim komputerze jest zainstalowany JDK 16.
3. **Podstawowa wiedza z zakresu programowania w Javie**:Znajomość składni i pojęć języka Java będzie przydatna.

## Konfigurowanie Aspose.Slides dla Java
Zanim zagłębimy się w kod, skonfigurujmy środowisko programistyczne, zawierające niezbędne biblioteki.

### Instalacja Maven
Dodaj następującą zależność do swojego `pom.xml` plik:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalacja Gradle
Uwzględnij to w swoim `build.gradle` plik:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobieranie
Alternatywnie, pobierz najnowszą wersję z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

#### Etapy uzyskania licencji
- **Bezpłatna wersja próbna**: Zacznij od tymczasowej licencji, aby poznać funkcje Aspose.Slides.
- **Licencja tymczasowa**:Uzyskaj dostęp do zaawansowanych funkcji, uzyskując tymczasową licencję.
- **Zakup**:W przypadku długoterminowego użytkowania należy rozważyć zakup pełnej licencji.

### Podstawowa inicjalizacja i konfiguracja
Zainicjuj `Presentation` obiekt, aby rozpocząć tworzenie slajdów:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Tutaj wpisz kod umożliwiający dodawanie slajdów i wykresów.
    }
}
```

## Przewodnik wdrażania
Teraz przeanalizujemy szczegółowo proces dodawania znaczników graficznych do serii wykresów.

### Utwórz nową prezentację z wykresem
Po pierwsze, potrzebujemy slajdu, do którego możemy dodać nasz wykres:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Zainicjuj obiekt prezentacji
        Presentation presentation = new Presentation();

        // Pobierz pierwszy slajd z kolekcji
        ISlide slide = presentation.getSlides().get_Item(0);

        // Dodaj do slajdu domyślny wykres liniowy ze znacznikami
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Dostęp i konfiguracja danych wykresu
Następnie uzyskamy dostęp do arkusza danych naszego wykresu, aby zarządzać seriami:

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

        // Wyczyść istniejącą serię i dodaj nową
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Dodaj znaczniki obrazu do punktów danych wykresu
A teraz czas na ekscytującą część — dodawanie obrazów jako znaczników:

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

        // Załaduj i dodaj obrazy jako znaczniki
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Dodaj punkty danych z obrazami jako znacznikami
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

### Skonfiguruj znacznik serii wykresów i zapisz prezentację
Na koniec dostosujmy rozmiar znacznika, aby był lepiej widoczny i zapiszmy naszą prezentację:

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

        // Załaduj i dodaj obrazy jako znaczniki (przykład z użyciem ścieżek zastępczych)
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

## Wniosek
Dzięki temu przewodnikowi dowiedziałeś się, jak ulepszyć swoje wykresy w Aspose.Slides for Java, dodając niestandardowe znaczniki obrazów. Takie podejście może znacznie zwiększyć zaangażowanie i przejrzystość Twoich prezentacji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}