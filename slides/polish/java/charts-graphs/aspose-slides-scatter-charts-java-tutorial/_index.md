---
date: '2026-02-24'
description: Dowiedz się, jak dostosować wykres punktowy przy użyciu Aspose.Slides
  for Java. Ten przewodnik krok po kroku przeprowadzi Cię przez tworzenie, stylizowanie
  i zapisywanie dynamicznych wykresów punktowych w Twoich prezentacjach.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Dostosuj wykres rozrzutu Aspose w Javie
url: /pl/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dostosuj wykres punktowy Aspose w Javie

W tym samouczku nauczysz się, jak **dostosować wykres punktowy Aspose** przy użyciu potężnej biblioteki Aspose.Slides for Java. Przejdziemy przez konfigurację projektu, tworzenie wykresu punktowego, dostosowywanie typów serii i znaczników oraz ostateczne zapisanie prezentacji. Po zakończeniu będziesz w stanie programowo generować profesjonalnie wyglądające wykresy punktowe i dopasowywać każdy szczegół wizualny do swojej marki lub potrzeb raportowych.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Slides for Java (v25.4+).  
- **Która wersja Javy jest obsługiwana?** JDK 8 lub wyższa.  
- **Czy mogę zmienić kształty znaczników?** Tak – użyj `MarkerStyleType`, aby wybrać gwiazdy, koła itp.  
- **Jak zapisać plik?** Wywołaj `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Czy wymagana jest licencja?** Darmowa wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji.

## Co to jest „customize scatter chart aspose”?
Dostosowywanie wykresu punktowego przy użyciu Aspose oznacza programowe definiowanie danych wykresu, jego wyglądu i zachowania — wszystkiego od współrzędnych punktów po symbole znaczników — bez ręcznego otwierania PowerPointa. Takie podejście jest idealne dla automatycznego raportowania, prezentacji opartych na danych lub każdego scenariusza, w którym potrzebne są powtarzalne, wysokiej jakości wizualizacje.

## Dlaczego dostosowywać wykresy punktowe przy użyciu Aspose.Slides?
- **Pełna kontrola** – modyfikuj typy serii, style znaczników, kolory i więcej za pomocą kodu Java.  
- **Automatyzacja** – generuj dziesiątki wykresów w locie dla pulpitów nawigacyjnych lub raportów wsadowych.  
- **Wieloplatformowość** – działa na każdym systemie operacyjnym obsługującym Javę, bez konieczności instalacji Office.  
- **Wydajność** – lekki interfejs API, który efektywnie obsługuje duże zestawy danych.

## Prerequisites

Aby podążać za instrukcją, upewnij się, że masz:

- **Aspose.Slides for Java** (v25.4 lub nowszy).  
- **Java Development Kit (JDK)** 8 + zainstalowany.  
- Maven lub Gradle do zarządzania zależnościami (lub możesz pobrać plik JAR ręcznie).  
- Podstawową znajomość Javy oraz zaznajomienie się z wybranym narzędziem budowania.

## Setting Up Aspose.Slides for Java

Zintegruj bibliotekę z projektem, używając jednej z poniższych metod.

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

Or grab the latest release from [Aspose Releases](https://releases.aspose.com/slides/java/).

#### License Acquisition
- **Free Trial** – 30‑dniowa wersja próbna.  
- **Temporary License** – wydłuczony okres testowy.  
- **Full License** – użycie produkcyjne z wsparciem premium.

## Przewodnik krok po kroku po dostosowaniu wykresu punktowego Aspose

### 1️⃣ Przygotuj folder na pliki prezentacji
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Dlaczego to ważne:* Upewnienie się, że folder wyjściowy istnieje, zapobiega `FileNotFoundException` przy późniejszym zapisywaniu pliku PPTX.

### 2️⃣ Utwórz nową prezentację i pobierz pierwszy slajd
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Nowa `Presentation` zapewnia czyste płótno; pierwszy slajd to miejsce, w którym umieścimy wykres.

### 3️⃣ Dodaj wykres punktowy z wygładzonymi liniami
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` tworzy wykres punktowy z wygładzonymi liniami, idealny do wizualizacji trendów.

### 4️⃣ Wyczyść domyślne serie i dodaj własne
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
Usunięcie domyślnej serii daje pełną kontrolę nad wyświetlanymi danymi.

### 5️⃣ Wypełnij pierwszą serię punktami danych
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` przyjmuje komórkę wartości X i komórkę wartości Y, budując wykres punktowy punkt po punkcie.

### 6️⃣ Dostosuj typ serii i wygląd znaczników
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
Tutaj **dostosowujemy wykres punktowy Aspose**, przełączając na proste linie, powiększając znaczniki i wybierając odrębne symbole (gwiazda vs. koło) dla lepszej przejrzystości wizualnej.

### 7️⃣ Zapisz prezentację
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Zapisanie jako `Pptx` zachowuje wszystkie dostosowania wykresu i przygotowuje plik do udostępniania lub dalszej edycji.

## Typowe przypadki użycia dostosowanych wykresów punktowych
- **Financial dashboards** – wykreśl cenę akcji względem wolumenu.  
- **Scientific research** – wyświetl pomiary eksperymentalne z znacznikami błędów.  
- **Project management** – porównaj planowany vs. rzeczywisty nakład pracy w zadaniach.  

## Wskazówki dotyczące wydajności
- Zwolnij obiekt `Presentation` (`pres.dispose()`) po zapisaniu, aby zwolnić zasoby natywne.  
- Dla dużych zestawów danych najpierw wypełnij skoroszyt, a następnie powiąż serię, aby uniknąć wielokrotnych odświeżeń UI.  
- Używaj jednego egzemplarza `IChartDataWorkbook` przy dodawaniu wielu serii.

## Najczęściej zadawane pytania

### Jak zmienić kolor znaczników?
Użyj `series.getMarker().getFillFormat().setFillColor(Color)`, gdzie `Color` jest instancją `java.awt.Color` (np. `Color.RED`).

### Czy mogę dodać więcej niż dwie serie do wykresu punktowego?
Oczywiście. Powtórz wywołanie `chart.getChartData().getSeries().add(...)` dla każdej dodatkowej serii i odpowiednio wypełnij jej punkty danych.

### Czy można ustawić niestandardową legendę dla każdej serii?
Tak. Po utworzeniu serii wywołaj `series.getLegend().setText("Your Legend Text")`, aby nadpisać domyślną nazwę.

### Jak mogę wyeksportować wykres jako obraz zamiast PPTX?
Wywołaj `chart.getImage().save("chart.png", ImageFormat.Png)` po skonfigurowaniu wykresu. Uzyskasz samodzielny plik PNG.

### Co zrobić, jeśli potrzebuję animować punkty wykresu punktowego?
Aspose.Slides obsługuje efekty animacji. Użyj `chart.getTimeline().getMainSequence().addEffect(...)`, aby dodać animacje wejścia lub podkreślenia do wykresu lub poszczególnych serii.

**Ostatnia aktualizacja:** 2026-02-24  
**Testowano z:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}