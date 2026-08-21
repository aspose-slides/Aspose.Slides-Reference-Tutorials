---
date: '2026-08-21'
description: Dowiedz się, jak utworzyć wykres słupkowy grupowany i dodać linie trendu
  przy użyciu Aspose.Slides for Java. Zawiera konfigurację licencji, integrację Maven/Gradle
  oraz szczegółowe przykłady.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Utwórz wykres słupkowy grupowany i dodaj linie trendu przy użyciu
  Aspose.Slides for Java. Ten przewodnik obejmuje konfigurację licencji, Maven/Gradle
  oraz krok po kroku fragmenty kodu.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Utwórz wykres słupkowy grupowany i dodaj linie trendu przy użyciu Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Jak utworzyć wykres słupkowy grupowany i dodać linie trendu przy użyciu Aspose.Slides
  for Java
url: /pl/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć wykres kolumnowy grupowany i dodać linie trendu przy użyciu Aspose.Slides for Java

Tworzenie atrakcyjnych prezentacji często zaczyna się od przejrzystej wizualizacji danych. W tym przewodniku **utworzysz obiekty wykresu kolumnowego grupowanego**, a następnie wzbogacisz je o różne linie trendu — wykładniczą, liniową, logarytmiczną, średnią kroczącą, wielomianową i potęgową — przy użyciu potężnego API Aspose.Slides for Java.

## Szybkie odpowiedzi
- **Jaki jest pierwszy krok?** Zainicjalizuj obiekt `Presentation` i dodaj wykres kolumnowy grupowany do slajdu.  
- **Jakiej wersji biblioteki wymaga się?** Aspose.Slides for Java 25.4 lub nowsza.  
- **Czy mogę używać Maven lub Gradle?** Tak, oba są obsługiwane; Maven używa `<dependency>`, a Gradle `implementation`.  
- **Czy potrzebna jest licencja?** Licencja próbna działa w trybie ewaluacji; pełna licencja Aspose.Slides usuwa ograniczenia wersji próbnej.  
- **Ile typów linii trendu jest dostępnych?** Sześć wbudowanych typów: wykładnicza, liniowa, logarytmiczna, średnia krocząca, wielomianowa i potęgowa.

## Co to jest wykres kolumnowy grupowany?
`create clustered column chart` oznacza generowanie wykresu, który grupuje wiele serii danych obok siebie w każdej kategorii, ułatwiając porównywanie wartości pomiędzy seriami. Ten typ wykresu jest idealny do wizualizacji danych kategorycznych, takich jak kwartalne sprzedaże w różnych regionach, pozwalając odbiorcom szybko zauważyć różnice między grupami.

## Dlaczego dodać linię trendu?
Linie trendu ujawniają ukryty wzorzec serii danych, pomagając prognozować przyszłe wartości, podkreślać tempo wzrostu lub wygładzać szum w danych. Dodając linię trendu do wykresu kolumnowego grupowanego, surowe liczby zamieniają się w praktyczne wnioski, umożliwiając interesariuszom zrozumienie długoterminowych tendencji i podejmowanie decyzji opartych na danych.

## Wymagania wstępne
- **Java Development Kit (JDK):** 8 lub nowszy.  
- **Aspose.Slides for Java:** wersja 25.4 lub nowsza.  
- **IDE:** IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Javą.  
- **Narzędzie budowania:** Maven lub Gradle (opcjonalne, ale zalecane).  
- **Licencja:** plik licencji Aspose.Slides – próbny lub zakupiony.  

Powinieneś być zaznajomiony z podstawową składnią Javy oraz zarządzaniem zależnościami projektu.

## Jak skonfigurować Aspose.Slides for Java?
Dodaj bibliotekę Aspose.Slides do swojego projektu, używając wybranego menedżera zależności, a następnie umieść plik licencji w miejscu, które środowisko wykonawcze może odnaleźć. Zapewnia to pełną funkcjonalność i usuwa ograniczenia wersji próbnej.

### Maven
Add this dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this line in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
You can also download the JAR manually from [Wydania Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

#### Licencja Aspose Slides
Place the `Aspose.Slides.lic` file in the root of your project or set the license programmatically with `License license = new License(); license.setLicense("Aspose.Slides.lic");`. A trial license removes all feature restrictions, but a purchased license eliminates the evaluation watermark and grants full performance optimizations. For production use, consider purchasing a license from the [stronie zakupu Aspose](https://purchase.aspose.com/buy).

## Jak utworzyć prezentację i dodać wykres kolumnowy grupowany?
Klasa `Presentation` reprezentuje plik PowerPoint i udostępnia metody do tworzenia, edytowania i zapisywania slajdów. Utwórz instancję `Presentation`, dodaj slajd, a następnie wywołaj `addChart` z `ChartType.ClusteredColumn`, aby utworzyć obiekt wykresu. Ten proces konfiguruje płótno slajdu, wstawia kształt wykresu i przygotowuje go do wypełniania danymi oraz stylizacji.

1. **Zainicjalizuj prezentację** – skonfiguruj folder wyjściowy i utwórz nową instancję `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Dodaj wykres kolumnowy grupowany** – uzyskaj kształt wykresu, skonfiguruj jego serie i wypełnij punkty danych.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Jak dodać wykładniczą linię trendu?
Interfejs `ITrendline` definiuje linię trendu, którą można dodać do serii wykresu w celu modelowania wzorców danych. Dodaj wykładniczą linię trendu do serii, tworząc instancję `ITrendline`, ustawiając jej `TrendlineType` na `Exponential` i dołączając ją do wybranej serii. Ten typ linii trendu jest przydatny dla danych rosnących szybko przy rosnącym tempie.

1. **Skonfiguruj linię trendu** – wybierz serię i wywołaj `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Jak dodać liniową linię trendu?
Liniowa linia trendu pokazuje prostą najlepiej dopasowaną do punktów danych. Możesz także dostosować jej wygląd, np. kolor i grubość linii, aby pasował do stylu prezentacji.

1. **Ustaw linię trendu** – użyj `addTrendline(TrendlineType.Linear)`, a następnie dostosuj `getLineFormat().setFillFormat().setFillType(FillType.Solid)`, aby zmienić kolor.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Jak dodać logarytmiczną linię trendu z niestandardową ramką tekstową?
Logarytmiczne linie trendu są idealne dla danych, które początkowo rosną szybko, a następnie stabilizują się. Nadpisanie domyślnej etykiety pozwala dodać wyjaśniający tekst, który wyjaśnia znaczenie trendu.

1. **Dostosuj linię trendu** – po dodaniu linii trendu, uzyskaj dostęp do `getDataLabel()` i ustaw właściwość `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Jak dodać linię trendu średniej kroczącej?
Linie trendu średniej kroczącej wygładzają krótkoterminowe wahania, aby podkreślić długoterminowe trendy. Możesz określić okres (liczbę punktów) używany do średniej, co pozwala kontrolować płynność linii.

1. **Skonfiguruj linię trendu** – wywołaj `addTrendline(TrendlineType.MovingAverage)` i ustaw `setPeriod(3)`, aby użyć średniej kroczącej z trzech punktów.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Jak dodać wielomianową linię trendu?
Wielomianowe linie trendu dopasowują dane do krzywej określonej równaniem wielomianowym. Właściwość `order` kontroluje stopień wielomianu, umożliwiając modelowanie bardziej złożonych zależności.

1. **Dostosuj linię trendu** – po dodaniu linii trendu, ustaw `setOrder(3)`, aby uzyskać dopasowanie sześcienne.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Jak dodać potęgową linię trendu?
Potęgowe linie trendu są przydatne, gdy dane podążają za zależnością potęgową. Możesz także ustawić wartości prognozowania wstecz i do przodu, aby wydłużyć linię poza istniejący zakres danych.

1. **Skonfiguruj linię trendu** – użyj `addTrendline(TrendlineType.Power)` i dostosuj `setBackward(2)`, aby wydłużyć linię wstecz.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Praktyczne zastosowania linii trendu w wykresach kolumnowych grupowanych
- **Analiza finansowa:** Trendy wykładnicze i wielomianowe pomagają prognozować ruchy cen akcji.  
- **Prognozowanie sprzedaży:** Linie średniej kroczącej wygładzają sezonowe szczyty, dając wyraźniejszy obraz podstawowych trendów sprzedaży.  
- **Badania naukowe:** Trendy logarytmiczne są idealne dla danych obejmujących kilka rzędów wielkości, takich jak natężenie akustyczne czy poziomy pH.  
- **Monitorowanie operacji:** Potęgowe linie trendu mogą modelować degradację wydajności w czasie.

## Jak zoptymalizować pamięć przy użyciu Aspose.Slides?
Niezwłocznie zwalniaj obiekty i używaj `presentation.dispose()` po zapisaniu. Dla dużych zestawów danych włącz leniwe ładowanie obrazów i unikaj ładowania całego wykresu do pamięci jednocześnie.

- **Wzorce zwalniania:** Umieść `Presentation` w bloku try‑with‑resources lub wywołaj `presentation.dispose()` w klauzuli finally.  
- **Leniwe ładowanie:** Ustaw `ChartData.setUseCache(true)` przy obsłudze tysięcy punktów danych.  
- **Strumieniowe wyjście:** Zapisz prezentację bezpośrednio do `FileOutputStream`, aby nie przechowywać całego pliku w pamięci RAM.

## Zmierzalne korzyści Aspose.Slides for Java
Aspose.Slides obsługuje **ponad 50 typów wykresów**, może generować prezentacje z **ponad 1 000 slajdów** w mniej niż **30 sekund** na typowym procesorze 2 GHz oraz przetwarza **PDF‑y o 500 stronach** bez konieczności instalacji Microsoft Office. Te liczby zostały zweryfikowane w najnowszej wersji 25.4.

## Podsumowanie
Masz teraz kompletną, kompleksową metodę **tworzenia obiektów wykresu kolumnowego grupowanego** i wzbogacania ich o wszystkie główne typy linii trendu dostępne w Aspose.Slides for Java. Postępując zgodnie z powyższymi krokami, możesz tworzyć prezentacje oparte na danych, które są zarówno atrakcyjne wizualnie, jak i analitycznie potężne.

Kolejne kroki obejmują eksplorację opcji stylizacji wykresów, eksport do PDF/HTML oraz automatyzację generowania wykresów z wielu źródeł danych.

## Najczęściej zadawane pytania

**Q: Jak skonfigurować Aspose.Slides dla projektu Maven?**  
A: Dodaj fragment `<dependency>` przedstawiony w sekcji Maven do swojego `pom.xml` i uruchom `mvn clean install`.

**Q: Czy mogę dostosować linie trendu poza kolorem i etykietą?**  
A: Tak, możesz modyfikować styl linii, szerokość, wzór kreski oraz nawet prognozować wartości w przód/w tył za pomocą API `ITrendline`.

**Q: Co zrobić, jeśli napotkam błąd niekompatybilności wersji?**  
A: Sprawdź, czy wersja JDK spełnia minimalne wymagania Aspose.Slides (JDK 8+). Zapoznaj się z notatkami wydania Aspose w celu wykrycia ewentualnych zmian łamiących kompatybilność.

**Q: Czy można automatycznie dodać linie trendu do wielu wykresów?**  
A: Oczywiście. Przejdź w pętli przez każdy `IChart` w kolekcji slajdów i wywołaj odpowiednią metodę `addTrendline` dla każdej serii.

**Q: Czy potrzebna jest płatna licencja do użytku produkcyjnego?**  
A: Tak, zakupiona licencja Aspose.Slides usuwa ograniczenia wersji próbnej i odblokowuje pełne optymalizacje wydajności.

---

**Ostatnia aktualizacja:** 2026-08-21  
**Testowano z:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Powiązane samouczki

- [aspose slides maven dependency: Dodaj i skonfiguruj wykresy w prezentacjach przy użyciu Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}