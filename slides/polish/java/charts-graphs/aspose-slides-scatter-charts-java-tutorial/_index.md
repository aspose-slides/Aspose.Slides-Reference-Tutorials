---
date: '2026-01-24'
description: Przewodnik krok po kroku, jak stworzyć wykres punktowy w Javie przy użyciu
  Aspose.Slides, dodać punkty danych do wykresu punktowego i pracować z wykresem punktowym
  zawierającym wiele serii.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Tworzenie wykresu punktowego w Javie z Aspose.Slides – Dostosuj i zapisz
url: /pl/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Utwórz wykres punktowy w Javie z Aspose.Slides

W tym samouczku **utworzysz projekty wykresu punktowego w Javie** od podstaw, dodasz punkty danych do wykresu punktowego i nauczysz się pracować z wykresem punktowym z wieloma seriami — wszystko przy użyciu Aspose.Slides for Java. Przejdziemy przez konfigurację katalogu, inicjalizację prezentacji, tworzenie wykresu, zarządzanie danymi, dostosowywanie znaczników oraz ostateczne zapisanie prezentacji.

**Co się nauczysz**
- Konfigurowanie katalogu do przechowywania plików prezentacji  
- Inicjalizowanie i manipulowanie prezentacjami przy użyciu Aspose.Slides  
- Tworzenie wykresu punktowego na slajdzie  
- Dodawanie i zarządzanie punktami danych dla każdej serii  
- Dostosowywanie typów serii, znaczników oraz obsługa wykresu punktowego z wieloma seriami  
- Zapisywanie gotowej prezentacji  

Zacznijmy od wymagań wstępnych.

## Szybkie odpowiedzi
- **Jaka jest podstawowa biblioteka?** Aspose.Slides for Java  
- **Jaka wersja Javy jest wymagana?** JDK 8 lub wyższa (zalecany JDK 16)  
- **Czy mogę dodać więcej niż dwie serie?** Tak – możesz dodać dowolną liczbę serii do wykresu punktowego  
- **Jak zmienić kolory znaczników?** Użyj `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Czy potrzebna jest licencja do produkcji?** Tak, licencja komercyjna usuwa ograniczenia wersji próbnej  

## Wymagania wstępne

Aby podążać za tym samouczkiem, upewnij się, że masz:
- **Aspose.Slides for Java** – wersja 25.4 lub nowsza.  
- **Java Development Kit (JDK)** – JDK 8 lub nowszy.  
- Podstawową znajomość Javy oraz doświadczenie z Maven lub Gradle.  

## Konfiguracja Aspose.Slides for Java

Zintegruj Aspose.Slides z projektem, korzystając z jednej z poniższych metod.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Lub pobierz najnowszy pakiet z [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Pozyskanie licencji
- **Bezpłatna wersja próbna** – 30‑dniowa ocena.  
- **Licencja tymczasowa** – rozszerzone testowanie.  
- **Licencja komercyjna** – pełne użycie produkcyjne.

Teraz przejdźmy do kodu.

## Przewodnik implementacji

### Krok 1: Konfiguracja katalogu
Najpierw upewnij się, że folder wyjściowy istnieje, aby prezentacja mogła zostać zapisana bez błędów.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Krok 2: Inicjalizacja prezentacji
Utwórz nową prezentację i pobierz pierwszy slajd.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Krok 3: Dodaj wykres punktowy
Wstaw wykres punktowy z gładkimi liniami na slajd.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Krok 4: Zarządzanie danymi wykresu (czyszczenie i dodawanie serii)
Wyczyść domyślne serie i dodaj własne serie dla **wykresu punktowego z wieloma seriami**.

```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### Krok 5: Dodaj punkty danych do wykresu punktowego
Wypełnij każdą serię wartościami X‑Y przy użyciu **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Krok 6: Dostosuj typy serii i znaczniki
Dostosuj styl wizualny — przełącz na proste linie ze znacznikami i ustaw odrębne symbole znaczników.

```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### Krok 7: Zapisz prezentację
Zapisz plik na dysku.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktyczne zastosowania
- **Analiza finansowa** – wykreśl ruchy cen akcji przy użyciu wykresu punktowego z wieloma seriami.  
- **Badania naukowe** – wizualizuj pomiary eksperymentalne, używając add data points scatter dla precyzyjnej reprezentacji danych.  
- **Zarządzanie projektami** – pokaż trendy alokacji zasobów w kilku projektach na jednym wykresie punktowym.

## Wskazówki dotyczące wydajności
- Zwolnij obiekt `Presentation` po zapisaniu, aby zwolnić pamięć.  
- Przy dużych zestawach danych wprowadzaj dane do skoroszytu partiami, a nie pojedynczo.  
- Unikaj nadmiernego stylizowania wewnątrzuj style po wstawieniu danych.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Wykres jest pusty** | Sprawdź, czy punkty danych zostały dodane do właściwej serii i czy indeksy skoroszytu są prawidłowe. |
| **Znaczniki nie są widoczne** | Upewnij się, że `series.getMarker().setSize()` ma wartość większą niż 0 oraz że symbol znacznika został określony. |
| **OutOfMemoryError przy dużych wykresach** | Użyj `pres.dispose()` po zapisaniu i rozważ zwiększenie rozmiaru sterty JVM (`-Xmx`). |

## Najczęściej zadawane pytania

### Jak zm gdzie `.Color`.

### Czy mogę dodać dodaniu wszystkich danych.

### Czy Aspose.Slides obsługuje interaktywne podpowiedzi na punktach wykresu?
PowerPoint nie zapew możesz osadzić etykiety danych używając `series.getDataPoints().get_Item(i).getLabel().setText("Twój tekst")`.

### Jak mogę animować serie punktowe?
Użyjć prostą animację pojawiania się.

---

**Ostatnia aktualizacja:** 2026-01-24  
**Testowano z:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}