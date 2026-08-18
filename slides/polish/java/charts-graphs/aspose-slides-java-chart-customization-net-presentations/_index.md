---
date: '2026-06-08'
description: Dowiedz się, jak dodać serię do wykresu i dostosować wykresy słupkowe
  skumulowane w prezentacjach .NET przy użyciu Aspose.Slides for Java.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Dodaj serię do wykresu przy użyciu Aspose.Slides for Java w .NET
url: /pl/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie dostosowywania wykresów w prezentacjach .NET przy użyciu Aspose.Slides dla Java

## Wprowadzenie
W świecie prezentacji opartych na danych wykresy są niezbędnymi narzędziami, które zamieniają surowe liczby w przekonujące historie wizualne. Kiedy potrzebujesz **add series to chart** programowo, szczególnie w plikach prezentacji .NET, zadanie może wydawać się przytłaczające. Na szczęście **Aspose.Slides for Java** oferuje potężne, niezależne od języka API, które upraszcza tworzenie i dostosowywanie wykresów — nawet gdy docelowy format to .NET PPTX. Ten przewodnik przeprowadzi Cię przez dodawanie serii, budowanie wykresu słupkowego skumulowanego oraz precyzyjne dostosowanie elementów wizualnych, takich jak szerokość przerwy, abyś mógł generować dynamiczne, bogate w dane slajdy, które wyglądają profesjonalnie i elegancko.

## Szybkie odpowiedzi
The `Presentation` class represents a PPTX file, and `slide.getShapes().addChart(...)` inserts a chart shape. Use `chart.getChartData().getSeries().add(...)` to add a series, and `setGapWidth()` adjusts spacing.

- **Jaka jest podstawowa klasa do rozpoczęcia prezentacji?** `Presentation` – reprezentuje plik PPTX w pamięci.  
- **Która metoda dodaje wykres do slajdu?** `slide.getShapes().addChart(...)` tworzy obiekt wykresu na slajdzie.  
- **Jak dodać nową serię?** `chart.getChartData().getSeries().add(...)` wstawia nową serię danych.  
- **Czy można zmienić szerokość przerwy między słupkami?** Tak — wywołaj `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` (wartość w procentach).  
- **Czy potrzebna jest licencja do produkcji?** Zdecydowanie — ważna licencja Aspose.Slides for Java odblokowuje wszystkie funkcje i usuwa znaki wodne wersji ewaluacyjnej.

## Co oznacza „add series to chart”?
Dodanie serii do wykresu oznacza wstawienie nowej kolekcji punktów danych, które wykres renderuje jako odrębny element wizualny (np. osobną grupę słupków). Każda seria może mieć własne wartości, kolory i formatowanie, co umożliwia porównanie kilku zestawów danych obok siebie.

## Dlaczego używać Aspose.Slides for Java do modyfikacji prezentacji .NET?
Aspose.Slides for Java pozwala generować lub edytować pliki PPTX w pełni kompatybilne z przeglądarkami PowerPoint w .NET, bez konieczności instalacji Microsoft Office. Używaj Aspose.Slides for Java, gdy potrzebujesz rozwiązania po stronie serwera, wieloplatformowego, które tworzy lub aktualizuje pliki .NET PPTX, obsługuje ponad 50 typów wykresów i przetwarza pliki do 500 MB bez ładowania całego dokumentu do pamięci. Jego API działa w Javie, Kotlinie, Scali lub dowolnym języku JVM, dostarczając taki sam wynik, jakiego oczekują programiści .NET.

## Wymagania wstępne
- Biblioteka **Aspose.Slides for Java** (wersja 25.4 lub nowsza).  
- Maven, Gradle lub ręczne pobranie pliku JAR.  
- Podstawowa znajomość Javy oraz struktury plików PPTX.  

## Konfiguracja Aspose.Slides for Java
### Instalacja Maven
Dodaj następującą zależność do swojego `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalacja Gradle
Include this line in your `build.gradle` file:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Alternatively, grab the latest JAR from the official release page: [wydania Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

**Uzyskanie licencji**  
Rozpocznij od bezpłatnej wersji próbnej, pobierając tymczasową licencję z [tutaj](https://purchase.aspose.com/temporary-license/). Do użytku produkcyjnego zakup pełną licencję, aby odblokować wszystkie funkcje i usunąć znaki wodne wersji ewaluacyjnej.

## Przewodnik krok po kroku
Poniżej każdego kroku znajdziesz zwięzły fragment kodu (niezmieniony względem oryginalnego samouczka) oraz wyjaśnienie, co on robi.

### Krok 1: Utwórz pustą prezentację
`Presentation` jest klasą wejściową, która reprezentuje plik PowerPoint w pamięci.  
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```  
*Zaczynamy od czystego pliku PPTX, który daje nam płótno do dodawania wykresów.*

### Krok 2: Dodaj wykres słupkowy skumulowany do slajdu
`Chart` reprezentuje kształt wykresu na slajdzie. `ChartType.StackedColumn` określa wykres słupkowy skumulowany.  
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Metoda `addChart` tworzy **wykres słupkowy skumulowany** i umieszcza go w lewym górnym rogu slajdu.*

### Krok 3: Dodaj serie do wykresu (główny cel)
`Series` zawiera pojedynczą serię danych w wykresie.  
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```  
*Tutaj **add series to chart** – każde wywołanie tworzy nową serię danych, która pojawi się jako osobna grupa słupków.*

### Krok 4: Dodaj kategorie do wykresu
`Category` definiuje etykietę osi X dla danych wykresu.  
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*Kategorie pełnią rolę etykiet osi X, nadając znaczenie każdemu słupkowi.*

### Krok 5: Wypełnij dane serii
`DataPoint` przechowuje wartość liczbową serii dla określonej kategorii.  
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```  
*Punkty danych dostarczają każdej serii jej wartości liczbowe, które wykres renderuje jako wysokość słupków.*

### Krok 6: Ustaw szerokość przerwy dla grupy serii wykresu
`SeriesGroup` kontroluje właściwości układu dla grupy serii, takie jak szerokość przerwy.  
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*Dostosowanie szerokości przerwy poprawia czytelność, szczególnie gdy występuje wiele kategorii.*

## Typowe przypadki użycia
- **Raportowanie finansowe** – porównaj kwartalne przychody w różnych jednostkach biznesowych.  
- **Pulpity projektowe** – pokaż procenty ukończenia zadań w poszczególnych zespołach.  
- **Analiza marketingowa** – wizualizuj wyniki kampanii obok siebie.  

Scenariusze te korzystają z **przykładu wykresu słupkowego skumulowanego**, ponieważ podkreślają wkład poszczególnych kategorii w sumę.

## Wskazówki dotyczące wydajności
- **Ponowne użycie obiektu `Presentation`** przy tworzeniu wielu wykresów, aby zmniejszyć zużycie pamięci.  
- **Ogranicz liczbę punktów danych** do niezbędnych dla historii wizualnej; Aspose.Slides radzi sobie z 10 000 punktami, ale prędkość renderowania spada po około 5 000.  
- **Zwolnij obiekty** (`presentation.dispose()`) po zapisaniu, aby zwolnić zasoby i uniknąć wycieków pamięci.  

## Najczęściej zadawane pytania
**P: Czy mogę dodać inne typy wykresów oprócz słupkowego skumulowanego?**  
O: Tak, Aspose.Slides obsługuje wykresy liniowe, kołowe, obszarowe, radarowe, bąbelkowe i ponad 50 innych typów, wszystkie dostępne poprzez tę samą metodę `addChart`.

**P: Czy potrzebuję osobnej licencji na wyjście .NET?**  
O: Nie, ta sama licencja Java działa dla wszystkich formatów wyjściowych, w tym plików .NET PPTX.

**P: Jak zmienić paletę kolorów wykresu?**  
O: Użyj `series.getFormat().getFill().setFillType(FillType.Solid)`, a następnie ustaw żądany obiekt `Color` dla każdej serii.

**P: Czy można programowo dodać etykiety danych?**  
O: Zdecydowanie. Wywołaj `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`, aby wyświetlić wartość liczbową na każdym słupku.

**P: Co zrobić, jeśli trzeba zaktualizować istniejącą prezentację?**  
O: Wczytaj plik za pomocą `new Presentation("existing.pptx")`, zmodyfikuj wykres przy użyciu tych samych wywołań API i zapisz go ponownie na dysk.

## Zakończenie
Masz teraz kompletny, kompleksowy przewodnik, jak **add series to chart**, stworzyć **wykres słupkowy skumulowany** i precyzyjnie dopasować jego wygląd w prezentacjach .NET przy użyciu Aspose.Slides for Java. Eksperymentuj z różnymi typami wykresów, kolorami i źródłami danych, aby tworzyć przekonujące raporty wizualne, które zachwycą interesariuszy i wspierają decyzje oparte na danych.

**Ostatnia aktualizacja:** 2026-06-08  
**Testowano z:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak tworzyć wykresy słupkowe skumulowane oparte na procentach w .NET przy użyciu Aspose.Slides](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Mistrzowskie tworzenie i manipulacja seriami wykresów z Aspose.Slides .NET dla efektywnej wizualizacji danych](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Usuwanie konkretnych punktów danych serii wykresu przy użyciu Aspose.Slides .NET](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}