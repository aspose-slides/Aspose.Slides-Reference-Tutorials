---
date: '2026-02-12'
description: Dowiedz się, jak tworzyć wykresy i zarządzać nimi przy użyciu Aspose.Slides
  for Java. Ten samouczek pokazuje, jak stworzyć wykres słupkowy grupowany, obsługiwać
  serie danych oraz dostosowywać wizualizację.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Jak stworzyć wykres w Javie przy użyciu Aspose.Slides: Kompletny przewodnik'
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć wykres w Javie z Aspose.Slides

## Jak tworzyć wykres w Javie: Wprowadzenie
Tworzenie dynamicznych prezentacji często wymaga wizualizacji danych za pomocą wykresów. Dzięki **Aspose.Slides for Java** możesz bez wysiłku **tworzyć obiekty wykresu**, zwiększyć przejrzystość i wywrzeć większy wpływ na swoją publiczność. Ten samouczek przeprowadzi Cię przez konfigurację biblioteki, dodanie **skupionego wykresu kolumnowego**, zarządzanie seriami oraz warunkowe odwracanie ujemnych punktów danych.

**Czego się nauczysz**
- Jak skonfigurować Aspose.Slides for Java.
- Kroki do **tworzenia skupionego wykresu kolumnowego** w Twojej prezentacji.
- Techniki zarządzania seriami wykresu i punktami danych.
- Metody warunkowego odwracania ujemnych punktów danych w celu lepszej wizualizacji.
- Jak bezpiecznie zapisać prezentację.

### Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.Slides for Java.
- **Jaki typ wykresu jest pokazany?** Skupiony wykres kolumnowy.
- **Czy mogę odwrócić ujemne wartości?** Tak, używając `invertIfNegative`.
- **Jakiej wersji Javy wymaga?** JDK 16 lub nowszej.
- **Czy potrzebna jest licencja do produkcji?** Tak, ważna licencja Aspose.

## Co to jest skupiony wykres kolumnowy?
Skupiony wykres kolumnowy wyświetla wiele serii danych obok siebie dla każdej kategorii, co ułatwia porównywanie wartości pomiędzy grupami. Jest idealny do raportów finansowych, pulpitów sprzedaży i wszelkich sytuacji, w których trzeba zestawić ze sobą kilka wskaźników.

## Dlaczego warto używać Aspose.Slides do tworzenia wykresów?
- **Pełna kontrola** nad wyglądem wykresu bez polegania na interfejsie PowerPoint.
- **Programowe generowanie** umożliwia automatyzację przepływów raportowania.
- **Wsparcie wieloplatformowe** zapewnia, że Twój kod działa na każdym systemie zgodnym z Javą.
- **Bogate API** do szczegółowej personalizacji (kolory, etykiety danych, odwracanie itp.).

## Wymagania wstępne
1. **Wymagane biblioteki**
   - Aspose.Slides for Java (version 25.4 or later).

2. **Środowisko**
   - JDK 16 or newer.
   - Maven or Gradle for dependency management.

3. **Wiedza**
   - Podstawowa programowanie w Javie.
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

### Pozyskiwanie licencji
- **Bezpłatna wersja próbna:** Przeglądaj funkcje bez licencji.
- **Licencja tymczasowa:** Używaj podczas oceny.
- **Pełna licencja:** Zakup do wdrożeń produkcyjnych.

### Podstawowa inicjalizacja
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Przewodnik krok po kroku

### Krok 1: Utwórz prezentację i dodaj skupiony wykres kolumnowy
W tym kroku **tworzymy obiekty wykresu** i umieszczamy **skupiony wykres kolumnowy** na pierwszym slajdzie.

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
Teraz usuniemy wszystkie domyślne serie, dodamy nową i wypełnimy ją zarówno dodatnimi, jak i ujemnymi wartościami.

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
Domyślnie Aspose.Slides nie odwraca ujemnych wartości. Włączymy odwracanie tylko dla tych punktów, które tego wymagają.

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

### Typowe pułapki i wskazówki
- **Zapomniałeś zwolnić obiekt `Presentation`?** Zawsze wywołuj `dispose()` w bloku `finally`, aby zwolnić zasoby natywne.
- **Ujemne wartości nie są odwrócone?** Upewnij się, że wywołujesz `invertIfNegative(true)` **po** dodaniu punktu danych.
- **Problemy z rozmiarem wykresu:** Współrzędne (X, Y) i wymiary (szerokość, wysokość) są w punktach; dostosuj je do układu slajdu.

## Najczęściej zadawane pytania

**Q: Czy mogę tworzyć inne typy wykresów przy użyciu tego samego podejścia?**  
A: Tak, po prostu zamień `ChartType.ClusteredColumn` na dowolną inną wartość wyliczenia `ChartType` (np. `Line`, `Pie`).

**Q: Czy potrzebna jest licencja do wersji deweloperskich?**  
A: Licencja tymczasowa lub ewaluacyjna jest wymagana do pełnego dostępu do funkcji; w przeciwnym razie biblioteka działa w trybie próbnym z ograniczeniami znaków wodnych.

**Q: Jak wyeksportować prezentację do PDF po dodaniu wykresów?**  
A: Użyj `pres.save("output.pdf", SaveFormat.Pdf);` po zakończeniu manipulacji wykresem.

**Q: Czy można stylizować poszczególne kolumny (kolor, obramowanie)?**  
A: Tak, każdy `IChartDataPoint` udostępnia opcje formatowania, takie jak `getFillFormat().setFillType(FillType.Solid)` oraz `getLineFormat()`.

**Q: Co zrobić, jeśli muszę zaktualizować dane wykresu po zapisaniu prezentacji?**  
A: Wczytaj ponownie prezentację za pomocą `new Presentation("file.pptx")`, zmodyfikuj dane wykresu i ponownie zapisz.

**Ostatnia aktualizacja:** 2026-02-12  
**Testowano z:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}