---
date: '2026-01-17'
description: Dowiedz się, jak dodać serie do wykresu i dostosować wykresy słupkowe
  skumulowane w prezentacjach .NET przy użyciu Aspose.Slides dla Javy.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Dodaj serię do wykresu za pomocą Aspose.Slides for Java w .NET
url: /pl/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie dostosowywania wykresów w prezentacjach .NET przy użyciu Aspose.Slides for Java

## Wstęp
W świecie prezentacji na wykresach danych są nieodzownymi narzędziami, które zamieniają surowe liczby w przekonujące historie wizualne. Gdy **add series to chart** programowo, szczególnie w pliku prezentacji .NET, zadanie może wydać się przytłaczające. Na szczęście **Aspose.Slides for Java** oferuje, niezależny od języka API, które upraszcza tworzenie i tworzenie wykresów — nawet gdy działa format na .NETPPTX.

W tym samouczku dowiesz się, jak **dodaj serię do wykresu**, jak **jak dodać wykres** typu ułożonego kolumnowo oraz jak szczegółowo dostroić aspekty wizualne, takie jak szerokość przerwy. Po zakończeniu zostaną wygenerowane szczegółowe dane slajdów, które zostaną przedstawione w sposób estetycznie.

**Czego się nauczysz**
- Jak stworzyć pustą prezentację przy użyciu Aspose.Slides
- Jak **dodaj skumulowany wykres kolumnowy** zrób slajdu
- Jak **dodaj serię do wykresu** i odpowiednie kategorie
- Jak wprowadzić punkty danych i dostosować ustawienia wizualne

wirusowe środowisko programistyczne.

## Szybkie odpowiedzi
- **Jakie są podstawowe zajęcia, od których rozpoczyna się prezentacja?** `Prezentacja`
- **Która metoda dodaje wykres do slajdu?** `slide.getShapes().addChart(...)`
- **Jak dodać nową serię?** `chart.getChartData().getSeries().add(...)`
- **Czy możesz zmienić szerokość przerwy między słupkami?** Tak, używając `setGapWidth()` w grupie serii
- **Czy potrzebuję licencji na produkcję?** Tak, wymagana jest ważna licencja Aspose.Slides for Java

## Co to jest „dodaj serię do wykresu”?
Dodanie serii do wykresu oznacza wprowadzenie nowej kolekcji danych, wykres wyjściowy jako element alternatywny (np. nowy słupek, początek lub części koła). Dostępna seria może mieć własny zestaw wartości, produktów i formatowania, co pozwala na porównywalność wielu zestawów danych obok siebie.

## Po co używać Aspose.Slides for Java do modyfikowania prezentacji .NET?
- **Wiele platform**: Napisz kod w Javie raz i celuj w plikach PPTX używanych przez aplikacje .NET.
- **Brak zależności COM lub Office**: Działa na serwerze, w rurociągach CI i kontenerach.
- **Bogate wykresy API**: Obsługuje ponad 50 charakterystycznych wykresów, w tym wykresy ułożone w kolumnie.

## Warunki wstępne
1. Biblioteka **Aspose.Slides for Java** (wersja25.4 lub nowsza).
2. narzędzie budujące Maven lub Gradle, albo ręczne pobranie JAR-a.
3. Podstawowa przyjemność Javy oraz struktury plików PPTX.

## Konfigurowanie Aspose.Slides dla Java
### Instalacja Mavena
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
Dodaj ten wiersz do pliku `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobieranie
Alternatywnie, pobierz najnowszy plik JAR z oficjalnej strony wydania: [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

**Nabycie licencji**
Rozpocznij od bezpłatnego okresu próbnego, pobierając tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/). Do użytku produkcyjnego, kup pełną licencję, aby odblokować wszystkie funkcje.

## Przewodnik implementacji krok po kroku
Poniżej każdego kroku znajdziesz zwięzły fragment kodu (niezmieniony w stosunku do oryginalnego samouczka), a następnie wyjaśnienie jego działania.

### Krok 1: Utwórz pustą prezentację
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

### Krok 2: Dodaj wykres kolumnowy skumulowany do slajdu
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Metoda `addChart` tworzy **add stacked column chart** i umieszcza go w lewym‑górnym rogu slajdu.*

### Krok 3: Dodaj serie do wykresu (cel główny)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Tutaj **add series to chart** – każde wywołanie tworzy nową serię danych, która pojawi się jako oddzielna grupa słupków.*

### Krok 4: Dodaj kategorie do wykresu
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*Kategorie pełnią rolę etykiet osi X, nadając sens każdemu słupkowi.*

### Krok 5: Uzupełnij dane serii
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
*Punkty danych dostarczają każdej serii wartości liczbowych, które wykres wyświetli jako wysokość słupków.*

### Krok 6: Ustaw szerokość przerwy dla grupy serii wykresu
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*Regulacja szerokości przerwy poprawia czytelność, szczególnie przy dużej liczbie kategorii.*

## Typowe przypadki użycia
- **Sprawozdawczość finansowa** – zestawienie wyników kwartalnych w różnych jednostkach biznesowych.
- **Dashboardy projektów** – wyświetlanie procentu zadań w poszczególnych zespołach.
- **Analiza marketingowa** – wizualizacje wyników obok siebie.

## Wskazówki dotyczące wydajności
- **Ponownie użyj obiektu „Prezentacja”** podczas tworzenia wielu wykresów, aby zmniejszyć obciążenie pamięci.
- **Ogranicz liczbę punktów danych** tylko do tych potrzebnych do historii wizualnej.
- **Pozbądź się obiektów** (`presentation.dispose()`) po zapisaniu w wolnych zasobach.

## Często zadawane pytania
**P: Czy mogę dodać inne typy wykresów oprócz skumulowanych kolumn?**
O: Tak, Aspose.Slides obsługuje wykresy liniowe, kołowe, obszarowe i wiele innych typów wykresów.

**P: Czy potrzebuję osobnej licencji na wyjście .NET?**
O: Nie, ta sama licencja Java działa dla wszystkich formatów wyjściowych, w tym plików .NET PPTX.

**P: Jak zmienić paletę kolorów wykresu?**
O: Użyj `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` i ustaw żądany `Color`.

**P: Czy można programowo dodawać etykiety danych?**
O: Oczywiście. Wywołaj `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`, aby wyświetlić wartości.

**P: Co zrobić, jeśli muszę zaktualizować istniejącą prezentację?**
O: Wczytaj plik za pomocą `new Presentation("existing.pptx")`, zmodyfikuj wykres i zapisz go ponownie.

## Wniosek
Masz teraz kompletny przewodnik, jak **dodaj serię do wykresu**, jak stworzyć **stacked Column Chart** oraz jak dopracować jego wygląd w prezentacji .NET przy użyciu Aspose.Slides for Java. Eksperymentuj z typami wykresów, kolorów i źródeł danych, aby utworzyć przekonujące raporty wizualne, które zrobią wrażenie na interesariuszach.

---

**Ostatnia aktualizacja:** 17.01.2026
**Testowano z:** Aspose.Slides dla Java 25.4 (jdk16)
**Autor:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
