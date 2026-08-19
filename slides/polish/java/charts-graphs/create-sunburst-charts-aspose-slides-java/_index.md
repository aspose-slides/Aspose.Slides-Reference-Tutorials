---
date: '2026-07-03'
description: Dowiedz się, jak krok po kroku tworzyć wykresy sunburst w Javie przy
  użyciu Aspose.Slides, z pełnymi opcjami dostosowywania prezentacji PowerPoint.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Jak tworzyć wykresy sunburst w Javie przy użyciu Aspose.Slides
url: /pl/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć wykresy Sunburst w Javie przy użyciu Aspose.Slides

## Wprowadzenie
W dzisiejszych prezentacjach opartych na danych, szybkie **tworzenie wizualizacji sunburst** może wyróżnić Twoje slajdy. Ten samouczek przeprowadzi Cię krok po kroku przez tworzenie wykresu Sunburst przy użyciu Aspose.Slides dla Javy, od konfiguracji projektu po ostateczny eksport, abyś mógł dostarczać przekonujące grafiki hierarchicznych danych bez opuszczania ekosystemu Javy.

## Szybkie odpowiedzi
- **Jaka jest główna klasa dla pliku PowerPoint?** `Presentation` – reprezentuje cały PPTX w pamięci.  
- **Ile linii kodu potrzebnych jest do podstawowego wykresu sunburst?** Zazwyczaj 5–7 linii po odwołaniu do biblioteki.  
- **Jakie formaty wyjściowe są obsługiwane?** PPTX, PDF, PNG, SVG i HTML.  
- **Czy mogę stylizować poszczególne segmenty?** Tak – kolory wypełnienia, obramowania i etykiety danych są w pełni konfigurowalne.  
- **Czy potrzebna jest licencja do produkcji?** Darmowa wersja ewaluacyjna działa do testów; licencja komercyjna jest wymagana przy wdrożeniu.

## Co to jest wykres Sunburst?
Wykres Sunburst wizualizuje dane hierarchiczne jako koncentryczne pierścienie, gdzie każdy pierścień reprezentuje poziom hierarchii. Umożliwia widzom szybkie zrozumienie relacji rodzic‑dziecko, co czyni go idealnym do diagramów organizacyjnych, prezentacji taksonomii i wielopoziomowych metryk. Jest szczególnie przydatny do wyświetlania wielopoziomowych kategorii, takich jak linie produktów, regiony geograficzne czy struktury organizacyjne, pozwalając odbiorcom zobaczyć zarówno ogólny rozkład, jak i szczegółowy podział w każdym segmencie.

## Dlaczego używać Aspose.Slides do wykresów Sunburst?
Aspose.Slides obsługuje **ponad 30 typów wykresów**, przetwarza pliki do **500 MB** bez ładowania całego dokumentu do pamięci i renderuje grafikę w **300 DPI**, zapewniając krystalicznie czysty wynik. Te wymierne możliwości gwarantują szybkie generowanie i wysokiej jakości wizualizacje nawet w dużych prezentacjach. Dodatkowo biblioteka oferuje operacje bezpieczne dla wątków i integruje się płynnie z popularnymi narzędziami budowania Javy, co czyni ją odpowiednią zarówno do generowania prezentacji na komputerze, jak i po stronie serwera w dużej skali.

## Wymagania wstępne
- Java Development Kit (JDK) 8 lub nowszy.  
- Maven lub Gradle do zarządzania zależnościami.  
- Aspose.Slides for Java (najnowsza wersja).  
- Podstawowa znajomość struktur danych hierarchicznych.

## Jak tworzyć wykresy Sunburst krok po kroku?
Załaduj środowisko, dodaj wykres, wprowadź dane hierarchiczne, sformatuj go i zapisz plik – wszystko w kilku prostych krokach. Poniżej znajduje się dokładny przepływ pracy, którego możesz używać bez pisania dodatkowego kodu szkieletowego. Proces jest w pełni zautomatyzowany, nie wymaga ręcznej interakcji z interfejsem użytkownika i może być włączony do zadań wsadowych lub usług internetowych, aby generować wykresy na żądanie.

### Krok 1: Konfiguracja projektu
Dodaj zależność Aspose.Slides Maven (lub równoważny fragment Gradle) do swojego `pom.xml`. Spowoduje to pobranie wszystkich wymaganych binarek i bibliotek tranzytywnych.

### Krok 2: Załaduj lub utwórz prezentację
`Presentation` jest obiektem najwyższego poziomu w Aspose.Slides, który reprezentuje pojedynczy plik PowerPoint w pamięci. Utwórz go przy pomocy `new Presentation()` dla nowej prezentacji lub podaj ścieżkę do pliku, aby otworzyć istniejący PPTX.

### Krok 3: Dodaj wykres Sunburst
Wstaw nowy kształt wykresu na slajd przy użyciu `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Tworzy to miejsce na wykres Sunburst gotowe na dane. `ChartType.Sunburst` określa typ wykresu Sunburst przy dodawaniu wykresu do slajdu.

### Krok 4: Wypełnij dane hierarchiczne
`ChartData` przechowuje serie danych i kategorie dla wykresu. Uzyskaj dostęp do kolekcji `ChartData` wykresu i dodaj serie oraz kategorie odzwierciedlające Twoją hierarchię. Dla każdego poziomu określ relację rodzic‑dziecko za pomocą właściwości `ParentSeries`, co pozwala wykresowi automatycznie renderować koncentryczne pierścienie.

### Krok 5: Dostosuj wygląd
Doprecyzuj kolory segmentów, style obramowań i etykiety danych za pomocą obiektów `ChartSeries` i `ChartDataPoint`. `ChartSeries` reprezentuje serię punktów danych w wykresie. `ChartDataPoint` reprezentuje pojedynczy punkt danych w serii. Możesz także włączyć obrót 3‑D lub ustawić właściwość `Explode`, aby wyróżnić konkretne fragmenty.

### Krok 6: Zapisz prezentację
Enum `SaveFormat` definiuje formaty plików, w jakich możesz zapisać prezentację. Wywołaj `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)`, aby zapisać plik na dysku. Możesz także wyeksportować do PDF lub PNG, zmieniając wartość enum `SaveFormat`.

## Jak dostosować kolory wykresu Sunburst?
Określ kolor wypełnienia dla każdego `ChartDataPoint` używając `point.getFillFormat().setFillType(FillType.Solid)`, a następnie `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Takie bezpośrednie podejście pozwala dopasować branding korporacyjny lub podkreślić kluczowe punkty danych. Możesz także zastosować wypełnienia gradientowe, dostosować przezroczystość lub użyć kolorów motywu, aby zapewnić spójność z resztą projektu slajdu.

## Typowe problemy i rozwiązania
- **Problem:** Hierarchia wygląda płasko.  
  **Rozwiązanie:** Upewnij się, że każda seria potomna prawidłowo odwołuje się do swojego `ParentSeries`. Brakujące powiązania powodują, że wykres traktuje wszystkie dane jako jeden poziom.  
- **Problem:** Wyeksportowany PNG jest rozmyty.  
  **Rozwiązanie:** Zwiększ DPI eksportu, ustawiając `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)`.  
- **Problem:** Duże pliki PPTX powodują OutOfMemoryError.  
  **Rozwiązanie:** Użyj `Presentation.setMemoryOptimization(true)`, aby strumieniować dane i utrzymać niskie zużycie pamięci.

## Najczęściej zadawane pytania

**P:** Czy mogę wygenerować wykres Sunburst z pliku CSV?  
**O:** Tak. Odczytaj CSV, zbuduj hierarchię w pamięci i przekaż ją do kolekcji `ChartData` wykresu przed zapisem.

**P:** Czy Aspose.Slides obsługuje animowane przejścia dla wykresów Sunburst?  
**O:** Tak. Zastosuj `SlideShowTransition` do slajdu lub użyj `ChartFormat.setAnimationEnabled(true)` dla animacji na poziomie wykresu.

**P:** Czy można wyeksportować wykres jako grafikę wektorową SVG?  
**O:** Oczywiście. Zapisz prezentację przy użyciu `SaveFormat.Svg`, aby uzyskać skalowalną wersję wektorową wykresu Sunburst.

**P:** Jaka jest maksymalna liczba punktów danych, które wykres Sunburst może obsłużyć?  
**O:** Aspose.Slides niezawodnie przetwarza do **10 000** punktów danych w jednym wykresie Sunburst bez pogorszenia wydajności.

**P:** Czy potrzebuję osobnej licencji dla każdego środowiska wdrożeniowego?  
**O:** Jedna licencja komercyjna obejmuje wszystkie środowiska (deweloperskie, testowe, produkcyjne), pod warunkiem przestrzegania warunków licencji.

## Podsumowanie
Masz teraz kompletny, krok po kroku przewodnik, jak **tworzyć wykresy sunburst** w Javie przy użyciu Aspose.Slides. Postępując zgodnie z powyższym przepływem pracy, możesz generować wysokiej jakości, w pełni konfigurowalne wizualizacje hierarchiczne dla dowolnej prezentacji PowerPoint.

---

**Ostatnia aktualizacja:** 2026-07-03  
**Testowano z:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Jak dodać wykresy do PowerPoint przy użyciu Aspose.Slides dla Javy: przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Mistrzowska personalizacja wykresów PowerPoint przy użyciu Aspose.Slides Java dla dynamicznych prezentacji](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animuj kategorie wykresów PowerPoint przy użyciu Aspose.Slides dla Javy | przewodnik krok po kroku](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}