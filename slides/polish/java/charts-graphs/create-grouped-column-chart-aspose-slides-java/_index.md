---
date: '2026-09-17'
description: Dowiedz się, jak dodać wykres słupkowy grupowany do prezentacji PowerPoint,
  dostosować wykres w PowerPoint oraz wstawić wykres serii danych przy użyciu Aspose.Slides
  for Java.
keywords:
- add clustered column chart
- add chart to powerpoint
- save presentation as pptx
- java create powerpoint presentation
lastmod: '2026-09-17'
og_description: Dowiedz się, jak dodać wykres słupkowy grupowany do prezentacji PowerPoint
  przy użyciu Aspose.Slides for Java, w tym kroki wstawiania serii danych, dostosowywania
  grupowania i zapisywania pliku jako PPTX.
og_image_alt: Guide showing clustered column chart creation in PowerPoint with Aspose.Slides
  Java
og_title: Dodaj wykres słupkowy grupowany do PowerPoint przy użyciu Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to add clustered column chart to a PowerPoint presentation,
    customize PowerPoint chart, and insert data series chart using Aspose.Slides for
    Java.
  headline: How to add clustered column chart in PowerPoint using Aspose.Slides for
    Java
  type: TechArticle
- questions:
  - answer: '`Presentation` from `com.aspose.slides`.'
    question: "Add chart to slide** and configure it as a clustered column chart.
      \ \n- **Create grouped column chart** by defining grouping levels for categories.
      \ \n- **Insert data series chart** so your data is displayed correctly.  \n-
      Save the finished presentation as a PPTX file.\n\n## Quick answers\n- **What
      is the primary class?"
  - answer: '`ChartType.ClusteredColumn`.'
    question: Which chart type is used?
  - answer: A free trial works, but a license removes evaluation limits.
    question: Do I need a license for testing?
  - answer: JDK 16 or newer (the example uses JDK 16).
    question: What Java version is supported?
  - answer: Add the Maven/Gradle dependency, compile, and run the `main` method.
    question: How to run the sample?
  type: FAQPage
tags:
- add clustered column chart
- aspose.slides
- java powerpoint automation
- chart generation
title: Jak dodać wykres słupkowy grupowany w programie PowerPoint przy użyciu Aspose.Slides
  for Java
url: /pl/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak dodać wykres słupkowy grupowany w PowerPoint przy użyciu Aspose.Slides for Java

## Wprowadzenie

Kiedy potrzebujesz **add clustered column chart** w prezentacji PowerPoint, wyraźna wizualizacja może przekształcić surowe liczby w natychmiast zrozumiałą historię. Robienie tego ręcznie w PowerPoint może być czasochłonne, szczególnie gdy musisz programowo generować wiele slajdów. **Aspose.Slides for Java** usuwa tarcia – pozwala tworzyć, dostosowywać wykresy PowerPoint i wstawiać wykresy serii danych za pomocą kilku linii kodu.

W tym samouczku nauczysz się:
- Zainicjalizować nową prezentację PowerPoint przy użyciu Aspose.Slides for Java.  
- **Add chart to slide** i skonfigurować go jako wykres słupkowy grupowany.  
- **Create grouped column chart** poprzez definiowanie poziomów grupowania dla kategorii.  
- **Insert data series chart** aby dane były wyświetlane prawidłowo.  
- Zapisz gotową prezentację jako plik PPTX.

## Szybkie odpowiedzi
- **What is the primary class?** `Presentation` z `com.aspose.slides`.  
- **Which chart type is used?** `ChartType.ClusteredColumn`.  
- **Do I need a license for testing?** Dostępna jest darmowa wersja próbna, ale licencja usuwa ograniczenia ewaluacyjne.  
- **What Java version is supported?** JDK 16 lub nowszy (przykład używa JDK 16).  
- **How to run the sample?** Dodaj zależność Maven/Gradle, skompiluj i uruchom metodę `main`.

## Co to jest „add clustered column chart”?

Wykres słupkowy grupowany wyświetla wiele serii danych obok siebie dla każdej kategorii, umożliwiając porównanie wartości pomiędzy grupami w jednej wizualizacji. Jest idealny do prezentacji wyników kwartalnych sprzedaży, wyników ankiet lub dowolnego scenariusza, w którym trzeba zestawić kilka zestawów danych w tej samej kategorii.

## Dlaczego używać Aspose.Slides do dodania wykresu słupkowego grupowanego?

Możesz automatycznie generować dziesiątki slajdów, dostosowywać każdy element wizualny i uruchamiać kod na dowolnym systemie operacyjnym obsługującym Javę — bez konieczności instalacji Microsoft Office. Aspose.Slides obsługuje **ponad 50 typów wykresów** i może przetwarzać prezentacje zawierające **do 500 slajdów** bez wczytywania całego pliku do pamięci, co czyni go odpowiednim dla dużych przepływów raportowania.

## Wymagania wstępne

- Biblioteka **Aspose.Slides for Java** (zalecana najnowsza wersja).  
- JDK 16 lub nowszy.  
- Narzędzie budujące Maven lub Gradle (lub możesz dodać plik JAR ręcznie).  
- IDE lub edytor tekstu do uruchamiania kodu Java.

## Konfiguracja Aspose.Slides for Java

Dodaj bibliotekę do swojego projektu, używając jednego z poniższych skryptów budujących.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatywnie możesz bezpośrednio pobrać najnowsze wydanie z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji

Przed wdrożeniem do produkcji uzyskaj licencję:
- **Free trial** – przetestuj wszystkie funkcje bez zakupu.  
- **Temporary license** – oceń rozszerzone możliwości przez krótki okres.  
- **Full license** – odblokuj nieograniczone użycie. Uzyskaj ją ze [strony zakupu Aspose](https://purchase.aspose.com/buy).

## Jak dodać wykres słupkowy grupowany w PowerPoint przy użyciu Aspose.Slides for Java?

Załaduj nową `Presentation`, dodaj slajd, wstaw `Chart` typu `ChartType.ClusteredColumn`, wypełnij jego wewnętrzny skoroszyt kategoriami i seriami, a następnie zapisz plik jako PPTX. Ta sekwencja tworzy w pełni funkcjonalny wykres słupkowy grupowany przy użyciu kilku wywołań API.

### Inicjalizacja prezentacji

`Presentation` jest klasą reprezentującą plik PowerPoint w pamięci, umożliwiającą programowe dodawanie slajdów, kształtów i wykresów.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Dodaj wykres do slajdu

`ChartType.ClusteredColumn` mówi Aspose.Slides, aby renderował wykres słupkowy grupowany.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Przygotuj skoroszyt danych wykresu

Wykres przechowuje swoje dane w wewnętrznym skoroszycie. Czyszczenie go daje czystą bazę dla własnych danych.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Dodaj kategorie z poziomami grupowania

Grupowanie kategorii tworzy efekt wykresu słupkowego grupowanego. Każda kategoria może należeć do logicznej grupy, która pojawia się w etykietach osi.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Dodaj serie danych do wykresu

Obiekty `Series` reprezentują poszczególne słupki w wykresie. Dodanie wielu serii skutkuje słupkami obok siebie dla każdej kategorii.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Zapisz prezentację z wykresem

Zapisanie `Presentation` tworzy standardowy plik PPTX, który może być otwarty w dowolnym przeglądarce PowerPoint.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktyczne zastosowania

- **Business reports** – porównaj kwartalne przychody w różnych regionach.  
- **Academic research** – pokaż wyniki eksperymentów pogrupowane według warunków testowych.  
- **Project management** – wizualizuj wskaźniki ukończenia zadań dla wielu zespołów na jednym slajdzie.

## Rozważania dotyczące wydajności

- **Memory management** – zwalniaj duże skoroszyty po użyciu.  
- **Batch operations** – unikaj aktualizacji wykresu w wewnątrz ciasnych pętli; najpierw zbierz dane, a potem zastosuj je.  
- **Built‑in optimizations** – Aspose.Slides udostępnia metody takie jak `Presentation.optimize()` dla dużych plików, zmniejszając zużycie pamięci nawet o **30 %**.

## Częste pułapki i wskazówki

- **Pitfall:** Zapomnienie o wyczyszczeniu istniejących serii/kategorii może prowadzić do duplikacji danych.  
  **Tip:** Zawsze wywołuj `clear()` przed wypełnieniem nowymi danymi.  
- **Pitfall:** Użycie niewłaściwego adresu komórki (np. `"c2"` zamiast `"C2"`).  
  **Tip:** Odwołania do komórek nie rozróżniają wielkości liter, ale zachowaj spójność dla czytelności.  
- **Tip:** Użyj `setGroupingItem`, aby stworzyć znaczące etykiety grup; pojawiają się automatycznie w legendzie wykresu.

## Najczęściej zadawane pytania

**Q1: How can I add multiple series to my chart?**  
A1: Wywołuj `ch.getChartData().getSeries().add()` wielokrotnie, podając unikalną nazwę i punkty danych dla każdej serii.

**Q2: What are some common issues with Aspose.Slides charts?**  
A2: Problemy często wynikają z niepasujących zakresów danych lub brakujących komórek skoroszytu. Zweryfikuj, czy każda kategoria i punkt danych ma odpowiadającą komórkę.

**Q3: Can I use Aspose.Slides with other programming languages?**  
A3: Tak, Aspose udostępnia równoważne biblioteki dla .NET, C++, Pythona i innych.

**Q4: How do I update an existing chart in a presentation?**  
A4: Załaduj prezentację, zlokalizuj wykres poprzez `slide.getShapes().get_Item(index)`, a następnie zmodyfikuj jego serie lub formatowanie w razie potrzeby.

**Q5: Are there limitations on chart types with Aspose.Slides?**  
A5: Biblioteka obsługuje ponad **50 typów wykresów** i stale dodaje nowe; zawsze sprawdzaj najnowszą dokumentację, aby uzyskać najbardziej aktualną listę.

## Zasoby

- **Documentation:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Download:** [Latest Releases](https://releases.aspose.com/slides/java/)  
- **Purchase:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free trial:** [Start Your Free Trial](https://releases.aspose.com/slides/java/)  
- **Temporary license:** [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-09-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose

## Powiązane samouczki

- [Przewodnik tworzenia wykresów w Javie z Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)
- [Jak dodać wykres do PowerPoint przy użyciu Aspose.Slides for Java: przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Dodaj animację do wykresu PowerPoint przy użyciu Aspose.Slides for Java – przewodnik krok po kroku](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}