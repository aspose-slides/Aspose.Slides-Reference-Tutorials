---
date: '2026-06-03'
description: Dowiedz się, jak tworzyć wykres Clustered Column Chart w języku Java
  przy użyciu Aspose.Slides. Ten przewodnik obejmuje Maven dependency, kroki tworzenia
  wykresu oraz obsługę danych.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Tworzenie wykresu Clustered Column Chart w języku Java przy użyciu Aspose.Slides
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Utwórz wykres kolumnowy grupowany w Javie z Aspose.Slides

## Jak tworzyć wykres w Javie: Wprowadzenie
Tworzenie dynamicznych prezentacji często wymaga wizualizacji danych za pomocą wykresów. Dzięki **Aspose.Slides for Java** możesz bez wysiłku **tworzyć wykresy kolumnowe grupowane**, zwiększyć przejrzystość i wywrzeć większy wpływ na swoją publiczność. Ten samouczek przeprowadzi Cię przez konfigurację biblioteki, dodawanie wykresu kolumnowego grupowanego, zarządzanie seriami oraz warunkowe odwracanie ujemnych punktów danych.

**Czego się nauczysz**
- Jak skonfigurować Aspose.Slides for Java.
- Kroki do **utworzenia wykresu kolumnowego grupowanego** w Twojej prezentacji.
- Techniki zarządzania seriami wykresu i punktami danych.
- Metody warunkowego odwracania ujemnych punktów danych w celu lepszej wizualizacji.
- Jak bezpiecznie zapisać prezentację.

## Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.Slides for Java.  
- **Jaki typ wykresu jest demonstrowany?** Wykres kolumnowy grupowany.  
- **Czy mogę odwrócić ujemne wartości?** Tak, używając `invertIfNegative`.  
- **Jaka wersja Javy jest wymagana?** JDK 16 lub nowsza.  
- **Czy licencja jest wymagana w produkcji?** Tak, ważna licencja Aspose.

## Czym jest wykres kolumnowy grupowany?
Wykres kolumnowy grupowany to wizualna reprezentacja, w której wiele serii danych jest umieszczonych obok siebie dla każdej kategorii, umożliwiając szybkie porównanie pomiędzy grupami. Jest idealny do raportów finansowych, pulpitów sprzedaży oraz wszelkich sytuacji, w których trzeba zestawić ze sobą kilka wskaźników jednocześnie.

## Dlaczego warto używać Aspose.Slides do tworzenia wykresów?
Aspose.Slides pozwala generować i w pełni dostosowywać wykresy programowo, eliminując potrzebę ręcznej edycji PowerPointa. Obsługuje **ponad 70 formatów wejściowych i wyjściowych** oraz może przetwarzać prezentacje zawierające **do 10 000 slajdów** bez ładowania całego pliku do pamięci, zapewniając wysoką wydajność przy raportowaniu na dużą skalę.

## Wymagania wstępne
1. **Wymagane biblioteki**  
   - Aspose.Slides for Java (wersja 25.4 lub nowsza).  

2. **Środowisko**  
   - JDK 16 lub nowszy.  
   - Maven lub Gradle do zarządzania zależnościami.  

3. **Wiedza**  
   - Podstawowe programowanie w Javie.  
   - Znajomość narzędzi budowania (Maven/Gradle).  

## Konfiguracja Aspose.Slides dla Javy
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
Dodaj następującą linię do pliku `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Alternatywnie, pobierz najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
- **Bezpłatna wersja próbna:** Przeglądaj funkcje bez licencji.  
- **Licencja tymczasowa:** Użyj podczas oceny.  
- **Pełna licencja:** Zakup do wdrożeń produkcyjnych.

### Podstawowa inicjalizacja
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Jak dodać wykres kolumnowy grupowany do slajdu?
`Presentation` jest podstawową klasą reprezentującą plik PowerPoint. Załaduj nowy `Presentation`, dodaj slajd i wywołaj `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. To pojedyncze wywołanie tworzy w pełni funkcjonalny wykres kolumnowy grupowany umieszczony w określonych współrzędnych. Następnie możesz uzyskać dostęp do obiektu wykresu, aby modyfikować serie, punkty danych i style wizualne.

## Przewodnik krok po kroku
### Krok 1: Utwórz prezentację i dodaj wykres kolumnowy grupowany
`Presentation` reprezentuje dokument PowerPoint i pozwala tworzyć slajdy.  
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

### Krok 2: Zarządzanie seriami wykresu
Teraz wyczyścimy wszystkie domyślne serie, dodamy nową i wypełnimy ją zarówno dodatnimi, jak i ujemnymi wartościami.  
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

### Krok 3: Warunkowe odwracanie ujemnych punktów danych
Metoda `invertIfNegative` umożliwia odwrócenie ujemnych wartości w serii wykresu.  
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

## Częste pułapki i wskazówki
- **Zapomniałeś zwolnić obiekt `Presentation`?** Zawsze wywołuj `dispose()` w bloku `finally`, aby zwolnić zasoby natywne.  
- **Ujemne wartości nie są wyświetlane jako odwrócone?** Upewnij się, że wywołujesz `invertIfNegative(true)` **po** dodaniu punktu danych.  
- **Problemy z rozmiarem wykresu:** Współrzędne (X, Y) oraz wymiary (szerokość, wysokość) są podawane w punktach; dostosuj je do układu slajdu.  

## Najczęściej zadawane pytania

**Q:** Czy mogę tworzyć inne typy wykresów przy użyciu tego samego podejścia?  
A: Tak, po prostu zamień `ChartType.ClusteredColumn` na dowolną inną wartość wyliczenia `ChartType` (np. `Line`, `Pie`).  

**Q:** Czy potrzebna jest licencja dla wersji deweloperskich?  
A: Wymagana jest tymczasowa lub ewaluacyjna licencja, aby uzyskać pełny dostęp do funkcji; w przeciwnym razie biblioteka działa w trybie próbnym z ograniczeniami znaków wodnych.  

**Q:** Jak wyeksportować prezentację do PDF po dodaniu wykresów?  
`SaveFormat.Pdf` określa PDF jako format wyjściowy przy zapisywaniu prezentacji. Użyj `pres.save("output.pdf", SaveFormat.Pdf);` po zakończeniu manipulacji wykresem.  

**Q:** Czy można stylizować pojedyncze kolumny (kolor, obramowanie)?  
`IChartDataPoint` reprezentuje pojedynczy punkt danych w wykresie i umożliwia formatowanie. Każdy `IChartDataPoint` oferuje opcje takie jak `getFillFormat().setFillType(FillType.Solid)` oraz `getLineFormat()`.  

**Q:** Co zrobić, jeśli muszę zaktualizować dane wykresu po zapisaniu prezentacji?  
A: Załaduj ponownie prezentację przy użyciu `new Presentation("file.pptx")`, zmodyfikuj dane wykresu i ponownie zapisz.  

---

**Ostatnia aktualizacja:** 2026-06-03  
**Testowano z:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Powiązane samouczki

- [Jak utworzyć wykres kolumnowy skumulowany w Javie z Aspose.Slides – Kompletny przewodnik](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Jak tworzyć wykresy w Javie z Aspose.Slides – Opanowanie tworzenia wykresów i walidacji](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Tworzenie i formatowanie wykresów w Javie przy użyciu Aspose.Slides: Kompletny przewodnik](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}