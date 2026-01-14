---
date: '2026-01-14'
description: Dowiedz się, jak utworzyć wykres słupkowy grupowany w języku Java przy
  użyciu Aspose.Slides. Przewodnik krok po kroku obejmujący pustą prezentację, dodawanie
  wykresu do prezentacji oraz zarządzanie seriami.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: Jak stworzyć wykres kolumnowy grupowany w Javie z Aspose.Slides
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie tworzenia wykresów w Javie z Aspose.Slides

## Jak tworzyć i zarządzać wykresami przy użyciu Aspose.Slides dla Javy

### Wprowadzenie
Tworzenie dynamicznych prezentacji często wymaga wizualizacji danych za pomocą wykresów. Dzięki **Aspose.Slides for Java** możesz bez wysiłku **utworzyć wykres kolumnowy grupowany** i zarządzać różnymi typami wykresów, zwiększając zarówno przejrzystość, jak i oddziaływanie. Ten samouczek poprowadzi Cię przez tworzenie pustej prezentacji, dodawanie wykresu kolumnowego grupowanego, zarządzanie seriami oraz dostosowywanie odwracania punktów danych — wszystko przy użyciu Aspose.Slides for Java.

**Czego się nauczysz:**
- Jak skonfigurować Aspose.Slides for Java.
- Krok po kroku **utworzyć pustą prezentację** i dodać wykres do prezentacji.
- Techniki efektywnego zarządzania seriami wykresu i punktami danych.
- Metody warunkowego odwracania ujemnych punktów danych w celu lepszej wizualizacji.
- Jak bezpiecznie zapisać prezentację.

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do rozpoczęcia?** `Presentation` z `com.aspose.slides`.
- **Który typ wykresu tworzy wykres kolumnowy grupowany?** `ChartType.ClusteredColumn`.
- **Jak dodać wykres do slajdu?** Użyj `addChart()` w kolekcji kształtów slajdu.
- **Czy można odwrócić ujemne wartości?** Tak, za pomocą `invertIfNegative(true)` na punkcie danych.
- **Jakiej wersji wymaga się?** Aspose.Slides for Java 25.4 lub nowszej.

## Co to jest wykres kolumnowy grupowany?
Wykres kolumnowy grupowany wyświetla wiele serii danych obok siebie dla każdej kategorii, co czyni go idealnym do porównywania wartości w różnych grupach. Aspose.Slides umożliwia generowanie tego wykresu programowo, bez otwierania PowerPointa.

## Dlaczego warto używać Aspose.Slides for Java do dodawania wykresu do prezentacji?
- **Pełna kontrola** nad danymi wykresu, wyglądem i układem.
- **Brak wymogu instalacji Office** na serwerze.
- **Obsługa wszystkich głównych typów wykresów**, w tym wykresów kolumnowych grupowanych.
- **Łatwa integracja** z projektami Maven/Gradle.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

1. **Wymagane biblioteki:**
   - Aspose.Slides for Java (wersja 25.4 lub nowsza).

2. **Wymagania dotyczące środowiska:**
   - Kompatybilna wersja JDK (np. JDK 16).
   - Zainstalowany Maven lub Gradle, jeśli preferujesz zarządzanie zależnościami.

3. **Wymagania wiedzy:**
   - Podstawowa znajomość programowania w Javie.
   - Znajomość obsługi zależności w środowisku programistycznym.

## Konfiguracja Aspose.Slides for Java
Aby rozpocząć korzystanie z Aspose.Slides, wykonaj następujące kroki:

**Instalacja Maven:**  
Dodaj następującą zależność do pliku `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Instalacja Gradle:**  
Dodaj następującą linię do pliku `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Bezpośrednie pobranie:**  
Alternatywnie pobierz najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
- **Bezpłatna wersja próbna:** Możesz rozpocząć od wersji próbnej, aby wypróbować funkcje.  
- **Licencja tymczasowa:** Uzyskaj tymczasową licencję, aby mieć pełny dostęp w okresie oceny.  
- **Zakup:** Rozważ zakup, jeśli uznasz, że spełnia Twoje długoterminowe potrzeby.

### Podstawowa inicjalizacja
Poniżej znajduje się minimalny kod potrzebny do utworzenia nowej instancji prezentacji:

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Przewodnik implementacji
Teraz podzielimy każdą funkcję na przystępne kroki.

### Tworzenie prezentacji z wykresem kolumnowym grupowanym
#### Przegląd
Ten fragment pokazuje, jak **utworzyć pustą prezentację**, dodać **wykres kolumnowy grupowany** i umieścić go na pierwszym slajdzie.

**Kroki:**
1. **Zainicjalizuj obiekt Presentation** – utwórz nowy `Presentation`.
2. **Dodaj wykres kolumnowy grupowany** – wywołaj `addChart()` z odpowiednim typem i wymiarami.

**Przykład kodu:**
```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Zarządzanie seriami wykresu
#### Przegląd
Dowiedz się, jak wyczyścić domyślne serie, dodać nową serię i wypełnić ją zarówno dodatnimi, jak i ujemnymi wartościami.

**Kroki:**
1. **Wyczyść istniejące serie** – usuń wszelkie wstępnie wypełnione dane.
2. **Dodaj nową serię** – użyj komórki skoroszytu jako nazwy serii.
3. **Wstaw punkty danych** – dodaj wartości, w tym ujemne, aby później pokazać odwracanie.

**Przykład kodu:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Odwracanie punktów danych serii w zależności od warunków
#### Przegląd
Domyślnie Aspose.Slides może odwracać ujemne wartości. Możesz kontrolować to zachowanie globalnie i dla poszczególnych punktów danych.

**Kroki:**
1. **Ustaw globalne odwracanie** – wyłącz automatyczne odwracanie dla całej serii.
2. **Zastosuj warunkowe odwracanie** – włącz odwracanie tylko dla konkretnych ujemnych punktów.

**Przykład kodu:**
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| Wykres jest pusty | Upewnij się, że indeks slajdu (`0`) istnieje i wymiary wykresu mieszczą się w granicach slajdu. |
| Ujemne wartości nie są odwracane | Sprawdź, czy `invertIfNegative(false)` jest ustawione dla serii oraz `invertIfNegative(true)` dla konkretnego punktu danych. |
| Wyjątek licencyjny | Zastosuj ważną licencję Aspose przed utworzeniem obiektu `Presentation`. |

## Najczęściej zadawane pytania

**P: Czy mogę dodać inne typy wykresów oprócz kolumnowego grupowanego?**  
O: Tak, Aspose.Slides obsługuje wykresy liniowe, kołowe, słupkowe, obszarowe i wiele innych typów.

**P: Czy potrzebna jest licencja do programowania?**  
O: Bezpłatna wersja próbna wystarczy do oceny, ale licencja komercyjna jest wymagana w środowisku produkcyjnym.

**P: Jak wyeksportować wykres jako obraz?**  
O: Użyj `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` po renderowaniu.

**P: Czy można stylizować wykres (kolory, czcionki)?**  
O: Oczywiście. Każdy `IChartSeries` i `IChartDataPoint` udostępnia właściwości stylizacji.

**P: Co zrobić, jeśli chcę dodać wykres do istniejącego pliku PPTX?**  
O: Załaduj plik przy pomocy `new Presentation("existing.pptx")`, a następnie dodaj wykres do wybranego slajdu.

## Zakończenie
W tym samouczku nauczyłeś się, jak **utworzyć wykres kolumnowy grupowany** w Javie, zarządzać seriami oraz warunkowo odwracać ujemne punkty danych przy użyciu Aspose.Slides. Dzięki tym technikom możesz programowo budować atrakcyjne prezentacje oparte na danych.

**Kolejne kroki:**
- Eksperymentuj z innymi typami wykresów oferowanymi przez Aspose.Slides for Java.  
- Zagłęb się w zaawansowane opcje stylizacji, takie jak niestandardowe kolory, etykiety danych i formatowanie osi.  
- Zintegruj generowanie wykresów z procesami raportowania lub analizą danych.

---

**Ostatnia aktualizacja:** 2026-01-14  
**Testowano z:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}