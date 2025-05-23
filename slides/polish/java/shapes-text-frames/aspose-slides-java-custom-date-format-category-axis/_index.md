---
"date": "2025-04-17"
"description": "Dowiedz się, jak dostosować formaty dat dla osi kategorii za pomocą Aspose.Slides dla Java. Ulepsz swoje wykresy za pomocą niestandardowej prezentacji danych, idealnej do raportów rocznych i nie tylko."
"title": "Jak ustawić niestandardowy format daty na osi kategorii w Aspose.Slides Java | Przewodnik po wizualizacji danych"
"url": "/pl/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak ustawić niestandardowy format daty na osi kategorii w Aspose.Slides Java | Przewodnik po wizualizacji danych

W dzisiejszym świecie opartym na danych, jasne przedstawianie informacji jest kluczowe dla podejmowania skutecznych decyzji. Podczas tworzenia wykresów przy użyciu Aspose.Slides dla Java, dostosowywanie formatu daty na osi kategorii może znacznie poprawić zarówno zrozumienie, jak i jakość prezentacji. Ten przewodnik przeprowadzi Cię przez ustawianie niestandardowego formatu daty w Aspose.Slides, aby poprawić atrakcyjność wizualną slajdów i przejrzystość danych.

**Czego się nauczysz:**
- Konfigurowanie Aspose.Slides dla Java
- Implementacja niestandardowych formatów dat na osi kategorii
- Konwersja dat kalendarza gregoriańskiego do formatu daty automatyzacji OLE
- Praktyczne zastosowania tych funkcji w scenariuszach z życia wziętych

Przyjrzyjmy się bliżej, jak możesz to osiągnąć z łatwością!

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że spełniłeś następujące wymagania wstępne:

### Wymagane biblioteki i wersje:
- **Aspose.Slides dla Java**: Potrzebna będzie wersja 25.4 lub nowsza.

### Wymagania dotyczące konfiguracji środowiska:
- Środowisko programistyczne umożliwiające uruchamianie kodu Java (np. IntelliJ IDEA, Eclipse lub NetBeans).
- Maven lub Gradle skonfigurowane w projekcie do zarządzania zależnościami.

### Wymagania wstępne dotyczące wiedzy:
- Podstawowa znajomość programowania w Javie.
- Znajomość sposobów wykorzystywania elementów wykresów w prezentacjach.

## Konfigurowanie Aspose.Slides dla Java

Aby pracować z Aspose.Slides dla Java, uwzględnij go jako zależność w swoim projekcie. Poniżej znajdują się instrukcje instalacji:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Stopień:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatywnie możesz [pobierz najnowszą wersję](https://releases.aspose.com/slides/java/) bezpośrednio z oficjalnej strony Aspose.

### Nabycie licencji:
- **Bezpłatna wersja próbna**:Rozpocznij od bezpłatnego okresu próbnego, aby poznać funkcje.
- **Licencja tymczasowa**:Poproś o tymczasową licencję na potrzeby rozszerzonego testowania.
- **Zakup**: Do długotrwałego użytkowania rozważ zakup subskrypcji. Odwiedź [Zakup Aspose](https://purchase.aspose.com/buy) Więcej szczegółów.

### Podstawowa inicjalizacja:

Oto jak możesz zainicjować Aspose.Slides w swoim projekcie:
```java
import com.aspose.slides.Presentation;
// Utwórz obiekt Prezentacja reprezentujący plik prezentacji
Presentation pres = new Presentation();
```

Przejdźmy teraz do sedna tego poradnika!

## Przewodnik wdrażania

### Ustawianie formatu daty dla osi kategorii

Ta funkcja umożliwia dostosowanie sposobu wyświetlania dat na osi kategorii wykresu. Poniżej znajduje się szczegółowy przewodnik:

#### 1. Utwórz nową prezentację i wykres
Zacznij od utworzenia instancji `Presentation` i dodanie nowego wykresu warstwowego.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // Zainicjuj prezentację
        Presentation pres = new Presentation();
        
        try {
            // Dodaj wykres obszarowy do pierwszego slajdu w określonym miejscu i rozmiarze
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // Dostęp do skoroszytu danych wykresu w celu manipulowania danymi wykresu
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // Wyczyść wszystkie istniejące dane na wykresie

            // Usuń wszelkie istniejące wcześniej kategorie i serie
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // Dodaj daty do osi kategorii za pomocą przekonwertowanych dat automatyzacji OLE
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // Utwórz nową serię i dodaj do niej punkty danych
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // Ustaw typ osi kategorii na Data i skonfiguruj jej format liczbowy
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // Formatuj daty tylko jako rok

            // Zapisz prezentację w określonym katalogu
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Data bazowa dla konwersji automatyzacji OLE
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // Konwertuj na datę automatyzacji OLE
        return String.valueOf(oaDate);
    }
}
```

#### 2. Konwersja daty kalendarza gregoriańskiego do formatu daty automatyzacji OLE

Aspose.Slides wymaga dat w formacie OLE Automation, który jest standardowym formatem daty w programie Excel. Oto jak przekonwertować plik Java `GregorianCalendar` daty:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 15 stycznia 2021 r.
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Data bazowa programu Excel dla automatyzacji OLE
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### Wskazówki dotyczące rozwiązywania problemów:
- Upewnij się, że data bazowa konwersji (`30 Dec 1899`) jest poprawnie parsowany.
- Sprawdź, czy Twoje środowisko Java obsługuje niezbędne biblioteki i klasy.
- Jeśli pojawią się problemy, sprawdź, czy są dostępne aktualizacje lub poprawki dla Aspose.Slides.

### Zastosowania praktyczne

Dostosowywanie formatów dat może być szczególnie przydatne w następujących sytuacjach:
- **Sprawozdania roczne:** Przejrzyste wyświetlanie rocznych trendów danych.
- **Wykresy finansowe:** Dokładne przedstawianie okresów obrachunkowych.
- **Harmonogram projektu:** Podkreślenie konkretnych ram czasowych lub kamieni milowych.

Dzięki temu przewodnikowi będziesz w stanie wzbogacić swoje prezentacje o precyzyjne i atrakcyjne wizualnie formaty dat, korzystając z Aspose.Slides for Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}