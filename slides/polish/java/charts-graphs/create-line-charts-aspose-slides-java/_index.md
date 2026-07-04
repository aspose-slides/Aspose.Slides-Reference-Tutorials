---
date: '2026-03-23'
description: Dowiedz się, jak używać Aspose.Slides for Java do tworzenia wykresów
  liniowych z markerami, dodawania drugiej serii i obsługi pustych danych w prezentacjach
  PowerPoint.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Jak korzystać z Aspose.Slides for Java: Tworzenie wykresów liniowych z domyślnymi
  znacznikami'
url: /pl/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów liniowych z domyślnymi znacznikami przy użyciu Aspose.Slides for Java

## Wprowadzenie
Jeśli zastanawiasz się **jak używać Aspose**, aby zautomatyzować tworzenie PowerPoint, trafiłeś we właściwe miejsce. W tym samouczku przeprowadzimy Cię przez budowanie **wykresu liniowego ze znacznikami**, dodawanie drugiej serii i obsługę pustych danych — wszystko przy użyciu Aspose.Slides for Java. Po zakończeniu będziesz mieć gotowy do uruchomienia fragment kodu, który generuje profesjonalnie wyglądający wykres bez ręcznego otwierania PowerPointa.

### Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Slides for Java (zalecana najnowsza wersja)  
- **Czy mogę dodać drugą serię?** Tak – API pozwala łatwo dodawać wiele serii.  
- **Jak obsługiwane są puste punkty danych?** Użyj `null` w wartości komórki; wykres pominie ten punkt.  
- **Czy potrzebuję Maven?** Maven lub Gradle działają; zobacz sekcję *aspose slides maven* poniżej.  
- **Czy wymagana jest licencja?** Darmowa wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji.

## Jak używać Aspose.Slides for Java do tworzenia wykresów liniowych
Tworzenie wykresów programowo oszczędza godziny ręcznego formatowania i zapewnia spójność w całych prezentacjach. Niezależnie od tego, czy budujesz funkcję **create powerpoint chart** w narzędziu raportującym, czy generujesz zestawy slajdów w locie, Aspose.Slides daje pełną kontrolę z poziomu kodu Java.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że środowisko programistyczne jest gotowe:

1. **Biblioteki i zależności**
   - Biblioteka Aspose.Slides for Java (zalecana wersja 25.4) – obejmuje scenariusz *aspose slides maven*.
   - Java Development Kit (JDK) wersja 16 lub wyższa.
2. **Konfiguracja środowiska**
   - IDE z obsługą Maven lub Gradle.
   - Ważny plik licencji Aspose, jeśli planujesz uruchamiać kod poza wersją próbną.
3. **Wymagania wiedzy**
   - Podstawowa programowanie w Javie.
   - Znajomość plików budowania Maven lub Gradle.

## Konfiguracja Aspose.Slides for Java
### Maven
Dodaj następującą zależność do pliku `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Umieść to w pliku `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Bezpośrednie pobranie
Alternatywnie możesz pobrać najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Kroki uzyskania licencji:**
- Aby uzyskać darmową wersję próbną, odwiedź [stronę wersji próbnej](https://releases.aspose.com/slides/java/).
- Aby uzyskać tymczasową licencję, przejdź do [strony tymczasowej licencji](https://purchase.aspose.com/temporary-license/).
- Kup pełną licencję przez ich [portal zakupowy](https://purchase.aspose.com/buy).

**Podstawowa inicjalizacja:**
Oto jak możesz zainicjalizować Aspose.Slides w aplikacji Java:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

Teraz przejdźmy do tworzenia wykresów!

## Przewodnik implementacji
### Funkcja 1: Tworzenie wykresu z domyślnymi znacznikami
Ta sekcja pokazuje, jak stworzyć **wykres liniowy ze znacznikami**, co jest idealne do podkreślania pojedynczych punktów danych na linii trendu.

#### Dodawanie wykresu liniowego
Aby dodać wykres liniowy ze znacznikami:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Czyszczenie serii i kategorii
Aby rozpocząć od nowa:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Funkcja 2: Dodawanie serii i kategorii
Dodawanie serii i kategorii jest kluczowe dla wypełnienia wykresów znaczącymi danymi.

#### Tworzenie nowej serii
Aby dodać nową serię o nazwie "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Wypełnianie kategorii i punktów danych
Aby dodać kategorie i odpowiadające im punkty danych:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Funkcja 3: Dodawanie drugiej serii i wypełnianie punktów danych
Dodanie dodatkowych serii zapewnia większą głębię analizy wizualnej.

#### Tworzenie i wypełnianie drugiej serii
Aby dodać "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Funkcja 4: Konfiguracja legendy wykresu
Konfiguracja legendy zwiększa czytelność wykresu, szczególnie gdy **dodajesz drugą serię**.

#### Dostosowywanie ustawień legendy
Aby skonfigurować:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Funkcja 5: Zapis prezentacji
Gdy wykres jest gotowy, będziesz chciał **utworzyć pliki wykresu PowerPoint**, które można udostępniać lub dalej edytować.

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Praktyczne zastosowania
1. **Raportowanie biznesowe:** Użyj wykresu liniowego ze znacznikami, aby zilustrować trendy finansowe w kolejnych kwartałach.  
2. **Analiza danych:** Zwizualizuj dane eksperymentalne, gdzie każdy znacznik podkreśla punkt pomiarowy.  
3. **Materiały edukacyjne:** Stwórz slajdy wykładowe pokazujące zmiany krok po kroku w procesie.  
4. **Zarządzanie projektami:** Śledź kamienie milowe na osi czasu przy użyciu wyraźnych znaczników dla kluczowych dat.  
5. **Prezentacje marketingowe:** Pokaż skoki wydajności kampanii przy użyciu wyraźnych symboli znaczników.

## Typowe problemy i rozwiązania
- **Puste punkty danych powodują błędy:** Przekaż `null` jako wartość komórki (jak pokazano) – Aspose po prostu pominie ten punkt.  
- **Wykres pojawia się bez znaczników:** Upewnij się, że używasz `ChartType.LineWithMarkers` zamiast `ChartType.Line`.  
- **Legenda zachodzi na dane:** Ustaw `chart.getLegend().setOverlay(false)`, aby legenda była oddzielona.  

## Najczęściej zadawane pytania

**P:** Czy mogę użyć tego podejścia do generowania wykresów w usłudze sieciowej?  
**O:** Zdecydowanie. Biblioteka działa w każdym środowisku Java, w tym w aplikacjach po stronie serwera.

**P:** Czy potrzebuję licencji do wersji deweloperskich?  
**O:** Darmowa wersja próbna działa w fazie rozwoju i testowania. Licencja komercyjna jest wymagana w produkcji.

**P:** Jak Aspose radzi sobie z dużymi zestawami danych?  
**O:** API strumieniuje dane efektywnie; jednak zachowaj rozsądną liczbę punktów danych, aby uniknąć dużych rozmiarów plików.

**P:** Czy istnieje wsparcie dla innych typów wykresów?  
**O:** Tak – Aspose.Slides obsługuje wykresy słupkowe, kołowe, punktowe i wiele innych.

**P:** Czy mogę dostosować kształty i kolory znaczników?  
**O:** Możesz modyfikować format znacznika za pomocą właściwości `Marker` dla każdego punktu danych.

## Podsumowanie
Teraz wiesz **jak używać Aspose**, aby stworzyć wykres liniowy z domyślnymi znacznikami, dodać drugą serię, obsłużyć puste dane i zapisać wynik jako plik PowerPoint. Te techniki pozwalają automatyzować generowanie raportów, ulepszyć opowiadanie historii danych i utrzymać spójność prezentacji.

Aby zgłębić temat, przeglądaj [oficjalną dokumentację](https://docs.aspose.com/slides/java/) lub dołącz do forów społecznościowych, takich jak Stack Overflow.

---

**Last Updated:** 2026-03-23  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}