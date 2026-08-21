---
date: '2026-08-21'
description: Dowiedz się, jak utworzyć wykres pudełkowy w Javie przy użyciu Aspose.Slides,
  dodać wykres do slajdu i wygenerować wykres pudełkowy z wąsami w PowerPoint. Idealny
  dla programistów Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Dowiedz się, jak utworzyć wykres pudełkowy w Javie przy użyciu Aspose.Slides,
  dodać wykres do slajdu i wygenerować wykres pudełkowy z wąsami w PowerPoint. Idealny
  dla programistów Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Jak utworzyć wykres pudełkowy w Javie przy użyciu Aspose.Slides dla PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Jak utworzyć wykres pudełkowy w Javie przy użyciu Aspose.Slides dla PowerPoint
url: /pl/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak utworzyć wykres pudełkowy w Javie z Aspose.Slides dla PowerPoint

W tym przewodniku **utworzysz wykres pudełkowy w Javie** przy użyciu Aspose.Slides, a następnie osadzisz wykres bezpośrednio na slajdzie PowerPoint. Generowanie wykresów pudełkowo‑wąsowych programowo pozwala przekształcić surowe dane statystyczne w przejrzyste wizualizacje bez opuszczania kodu Java. Jeśli potrzebujesz automatyzować raportowanie w PowerPoint, Aspose.Slides for Java zapewnia niezawodne, wysokowydajne API.

## Czego się nauczysz

- Konfiguracja środowiska dla Aspose.Slides for Java
- Kroki do **dodania wykresu do slajdu** i wygenerowania wykresu pudełkowo‑wąsowego w PowerPoint przy użyciu Javy
- Najlepsze praktyki optymalizacji wydajności przy pracy z Aspose.Slides
- Praktyczne zastosowania wykresów pudełkowo‑wąsowych

## Szybkie odpowiedzi
- **Jaką bibliotekę używać do tworzenia wykresu pudełkowego w Javie?** Aspose.Slides for Java.  
- **Jaki typ wykresu jest używany?** `ChartType.BoxAndWhisker`.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa do oceny; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę dodać wiele serii?** Tak – powtórz blok tworzenia serii dla każdego zestawu danych.  
- **Jaki jest format końcowego pliku?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Czym jest wykres pudełkowy i dlaczego używać go w Javie?

Wykres pudełkowo‑wąsowy (często nazywany *box plot*) wizualizuje rozkład danych — medianę, kwartyle i wartości odstające — w zwartej formie. W Javie generowanie takiego wykresu programowo pozwala osadzić wnioski statystyczne bezpośrednio w prezentacjach PowerPoint, eliminując ręczne tworzenie wykresów. Jest to szczególnie przydatne przy porównywaniu rozkładów w wielu kategoriach, np. wyników testów w klasach czy sprzedaży w regionach. Dzięki generowaniu wykresu w Javie możesz zintegrować go z automatycznymi pipeline’ami raportowania, zapewniając, że najnowsze dane zawsze znajdują odzwierciedlenie w prezentacjach.

## Dlaczego dodawać wykres do slajdu przy użyciu Aspose.Slides?

Aspose.Slides abstrahuje szczegóły niskopoziomowego OpenXML, oferując płynne API do tworzenia, stylizacji i eksportu wykresów. Dzięki temu możesz automatyzować generowanie raportów, zapewniać spójną identyfikację wizualną i integrować wykresy z większymi przepływami pracy w Javie. Biblioteka obsługuje także opcje stylizacji, takie jak kolory, czcionki i markery, co pozwala dopasować wykres do wizerunku korporacyjnego. Dodatkowo radzi sobie z takimi złożonymi zadaniami jak powiązanie danych i odświeżanie wykresu bez konieczności posiadania Microsoft Office.

## Jak w Javie dodać wykres do slajdu przy użyciu Aspose.Slides?

Załaduj lub utwórz obiekt `Presentation`, wstaw wykres typu `BoxAndWhisker`, podaj dane i zapisz plik — wszystko w kilku linijkach Javy. API zajmuje się układem, skalowaniem i renderowaniem, więc nie musisz samodzielnie manipulować XML. Możesz także programowo ustawiać tytuły wykresów i etykiety osi, aby zapewnić kontekst widzom.

## Wymagania wstępne

- **Java Development Kit (JDK)**: JDK 8 lub nowszy.  
- **Biblioteka Aspose.Slides for Java**: Wymagana do manipulacji PowerPoint.  
- **IDE**: IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Javą.

## Konfiguracja Aspose.Slides for Java

Dodaj bibliotekę jako zależność Maven, Gradle lub ręczną.

### Maven

Dodaj następującą zależność w pliku `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

W pliku `build.gradle` umieść:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie

Alternatywnie, pobierz najnowszą wersję ze strony [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Uzyskanie licencji

- **Darmowa wersja próbna** – przetestuj funkcje bez kosztów.  
- **Licencja tymczasowa** – użyj do krótkoterminowej oceny.  
- **Zakup** – odblokuj pełną funkcjonalność dla środowisk produkcyjnych.

Aby zainicjować Aspose.Slides, upewnij się, że plik JAR znajduje się w classpath i ustaw plik licencyjny zgodnie z opisem w dokumentacji.

## Przewodnik implementacji

Poniżej znajduje się instrukcja krok po kroku. Każdy blok jest wyjaśniony przed fragmentem kodu, abyś dokładnie wiedział, co robi.

### Co to jest klasa `Presentation`?

Klasa `Presentation` jest centralnym obiektem w Aspose.Slides, który reprezentuje cały plik PowerPoint w pamięci. Zapewnia dostęp do slajdów, wykresów, kształtów i innych elementów, umożliwiając programowe tworzenie, modyfikowanie i zapisywanie prezentacji. Dzięki tej klasie możesz dodawać nowe slajdy, wstawiać obrazy i manipulować kolejnością slajdów przy użyciu prostych wywołań API.

### Krok 1: utwórz lub otwórz prezentację

Najpierw otwórz istniejący plik PPTX lub rozpocznij nowy:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Wskazówka:** Jeśli plik nie istnieje, Aspose.Slides automatycznie utworzy nową pustą prezentację.

### Krok 2: dodaj wykres pudełkowo‑wąsowy do slajdu

Umieść wykres w wybranym miejscu, określając pozycję i rozmiar (w punktach):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Krok 3: wyczyść istniejące dane

Przed wprowadzeniem nowych danych usuń wszelkie kategorie lub serie zastępcze:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Krok 4: skonfiguruj kategorie

Dodaj kategorie (etykiety osi X), które pojawią się pod każdym pudełkiem:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Uwaga:** Dostosuj tekst etykiet do zakresu danych (np. „Q1”, „Produkt A”).

### Krok 5: utwórz i dostosuj serię

Teraz utwórz serię, ustaw opcje wizualne i wprowadź numeryczne punkty danych:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Możesz zastąpić tablicę `int[] data` wartościami odczytanymi z bazy danych, pliku CSV lub innego źródła.

### Krok 6: zapisz prezentację

Zapisz zmiany do nowego pliku PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Krok 7: zwolnij zasoby

Zawsze zwalniaj obiekt `Presentation`, aby zwolnić zasoby natywne:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Praktyczne zastosowania

Wykresy pudełkowo‑wąsowe są nieocenione w analizie statystycznej i prezentacji danych. Oto kilka scenariuszy, w których błyszczą:

1. **Analiza finansowa** – wizualizacja rozkładu przychodów w różnych regionach.  
2. **Kontrola jakości** – wykrywanie odchyleń w pomiarach produkcyjnych.  
3. **Badania akademickie** – prezentacja zmienności wyników eksperymentalnych.  
4. **Badania rynkowe** – porównanie wyników produktów w różnych grupach demograficznych.

Osadzanie tych wykresów bezpośrednio w prezentacjach PowerPoint pozwala interesariuszom szybko zrozumieć złożone dane.

## Uwagi dotyczące wydajności

Aspose.Slides może obsługiwać prezentacje z **500+ slajdami** oraz wykresy z **100 000+ punktami danych**, utrzymując zużycie pamięci poniżej 200 MB na typowym serwerze. Aby pozostać w tych granicach:

- **Zarządzanie pamięcią** – niezwłocznie zwalniaj obiekty `Presentation`.  
- **Obsługa danych** – wczytuj tylko potrzebne dane; unikaj wprowadzania ogromnych zestawów danych bezpośrednio do skoroszytu wykresu.  
- **Ładowanie leniwe** – przy generowaniu wielu slajdów twórz wykresy tylko dla tych, które będą wyświetlane.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **Wykres jest pusty** | Komórki danych nie są prawidłowo wypełnione | Sprawdź, czy `wb.getCell` odwołuje się do właściwego wiersza/kolumny i czy wartość nie jest `null`. |
| **Punkty odstające nie są wyświetlane** | `setShowOutlierPoints` ustawione na `false` | Upewnij się, że wywołano `series.setShowOutlierPoints(true)`. |
| **Wycieki pamięci** | Obiekt Presentation nie został zwolniony | Zawsze otaczaj użycie blokiem `try/finally` i wywołaj `dispose()`. |
| **Nieprawidłowe kwartyle** | Używanie domyślnej metody `Inclusive` | Przełącz na `Exclusive` za pomocą `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Najczęściej zadawane pytania

**Q1: Czym jest wykres pudełkowo‑wąsowy?**  
Wykres pudełkowo‑wąsowy, znany również jako wykres pudełkowy, wyświetla rozkład danych na podstawie pięciu statystyk podsumowujących: minimum, pierwszy kwartyl, mediana, trzeci kwartyl i maksimum, plus ewentualne wartości odstające.

**Q2: Czy mogę dostosować wygląd wykresu pudełkowo‑wąsowego?**  
Tak. Aspose.Slides pozwala zmieniać kolory, style linii, kształty markerów oraz dodawać etykiety danych poprzez API formatowania wykresu.

**Q3: Czy można obsłużyć wiele serii w jednym wykresie?**  
Oczywiście. Powtórz blok tworzenia serii dla każdego zestawu danych, który chcesz zwizualizować.

**Q4: Jak rozwiązać problemy z niepoprawnym wyświetlaniem danych?**  
Upewnij się, że dane są prawidłowo zapisane w komórkach skoroszytu oraz że właściwości widoczności, takie jak `setShowMeanLine`, są włączone.

**Q5: Gdzie mogę uzyskać wsparcie w razie problemów?**  
Odwiedź [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) po pomoc społeczności lub zapoznaj się z oficjalną dokumentacją.

**Q6: Czy Aspose.Slides obsługuje inne typy wykresów?**  
Tak, obsługuje ponad 50 typów wykresów — w tym liniowe, słupkowe, kołowe, punktowe, radarowe i lejkowe — więc możesz wybrać najlepszą wizualizację dla swoich danych.

**Q7: Czy mogę generować wykresy w środowisku serwera bez interfejsu graficznego?**  
Biblioteka działa w pełni w scenariuszach po stronie serwera; nie wymaga instalacji Microsoft Office ani interfejsu UI.

## Zasoby

- **Dokumentacja**: Przeglądaj szczegółowe odniesienia API pod adresem [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Pobierz**: Odwiedź stronę wydań Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Zakup**: Kup licencję, aby odblokować pełne funkcje [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Darmowa wersja próbna i licencja tymczasowa**: Rozpocznij od wersji próbnej lub poproś o licencję tymczasową [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Postępując zgodnie z tym przewodnikiem, jesteś gotowy do programowego generowania wnikliwych wykresów pudełkowo‑wąsowych w aplikacjach Java i ich bezpośredniego osadzania w prezentacjach PowerPoint. Powodzenia w kodowaniu!

---

**Last Updated:** 2026-08-21  
**Testowano z:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Autor:** Aspose

## Powiązane samouczki

- [Jak dodać wykres do PowerPoint przy użyciu Aspose.Slides for Java: Przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java tworzenie wykresu PowerPoint przy użyciu Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Dodaj animację do wykresu PowerPoint przy użyciu Aspose.Slides for Java – Przewodnik krok po kroku](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}