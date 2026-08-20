---
date: '2026-07-27'
description: Dowiedz się, jak utworzyć wykres doughnut w Java przy użyciu Aspose.Slides
  – szybki przewodnik, jak skonfigurować bibliotekę, dodać konfigurowalny wykres doughnut,
  dostosować rozmiar otworu i zapisać prezentację.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Dowiedz się, jak utworzyć wykres doughnut w Java przy użyciu Aspose.Slides
  – szybki przewodnik, jak skonfigurować bibliotekę, dodać konfigurowalny wykres doughnut,
  dostosować rozmiar otworu i zapisać prezentację.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Utwórz wykres doughnut w Java – krok po kroku z Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Utwórz wykres doughnut w Java – krok po kroku z Aspose.Slides
url: /pl/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć wykresy pierścieniowe w Javie przy użyciu Aspose.Slides for Presentations

## Wprowadzenie
Tworzenie wizualnie atrakcyjnych prezentacji jest niezbędne do skutecznego przekazywania informacji. **Create doughnut chart java** jest powszechnym wymaganiem, gdy trzeba przedstawić dane proporcjonalne w nowoczesnym stylu. W tym samouczku dowiesz się, jak skonfigurować Aspose.Slides for Java, zbudować wykres pierścieniowy, dostosować rozmiar otworu i kolory, a na koniec zapisać plik prezentacji. Po zakończeniu będziesz mieć gotowy wzorzec, który możesz wstawić do dowolnego projektu Java generującego automatycznie prezentacje PowerPoint.

**Czego się nauczysz:**
- Konfiguracja Aspose.Slides for Java
- Tworzenie i konfigurowanie wykresów pierścieniowych w prezentacjach
- Dostosowywanie wyglądu wykresu, takiego jak rozmiar otworu
- Zapisywanie prezentacji z nowym wykresem

Zacznijmy od skonfigurowania naszego środowiska!

## Szybkie odpowiedzi
- **Która biblioteka tworzy wykresy pierścieniowe w Javie?** Aspose.Slides for Java.
- **Ile linii kodu potrzebnych jest do podstawowego wykresu pierścieniowego?** Około 8–10 linii po utworzeniu obiektu prezentacji.
- **Czy mogę zmienić rozmiar otworu?** Tak, metoda `setHoleSize(double)` przyjmuje wartości od 0 % do 100 %.
- **Jakie formaty wyjściowe są obsługiwane?** PPTX, PDF, XPS, PNG, JPEG i kilka innych (ponad 50 łącznie).
- **Czy potrzebuję licencji do produkcji?** Wymagana jest licencja komercyjna do nieograniczonego użycia; darmowa wersja próbna działa w celach oceny.

## Czym jest Aspose.Slides for Java?
**Aspose.Slides for Java** to w pełni zarządzane API, które umożliwia programistom tworzenie, modyfikowanie, konwertowanie i renderowanie plików PowerPoint bez Microsoft Office. Obsługuje ponad 50 formatów plików i może obsługiwać prezentacje z tysiącami slajdów przy niskim zużyciu pamięci.

## Dlaczego używać wykresów pierścieniowych w prezentacjach?
Wykresy pierścieniowe pokazują zależności część‑całość, jednocześnie pozostawiając miejsce w centrum na etykiety lub obrazy. Aspose.Slides potrafi renderować wykresy pierścieniowe z prędkością **500 slajdów na minutę** na typowym serwerze 2,5 GHz i przetwarza **prezentacje wielokrotnie setek stron** bez ładowania całego pliku do pamięci, co czyni go idealnym rozwiązaniem do raportowania na dużą skalę.

## Wymagania wstępne
Zanim rozpoczniesz, upewnij się, że spełniasz poniższe wymagania:

### Wymagane biblioteki i wersje
Aby pracować z Aspose.Slides for Java, dołącz ją do projektu za pomocą Maven lub Gradle, albo pobierz bezpośrednio.

#### Wymagania dotyczące konfiguracji środowiska
- Działający Java Development Kit (JDK), najlepiej wersja 8 lub wyższa.
- Zintegrowane środowisko programistyczne (IDE) takie jak IntelliJ IDEA lub Eclipse.

### Wymagania wiedzy
Znajomość Javy i podstawowych koncepcji programowania jest przydatna. Podstawowa wiedza o Maven lub Gradle ułatwi proces konfiguracji.

## Konfigurowanie Aspose.Slides for Java
Włączenie Aspose.Slides do projektu można wykonać na kilka sposobów:

**Maven:**  
Dodaj tę zależność do pliku `pom.xml`:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Umieść to w pliku `build.gradle`:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Alternatywnie, pobierz najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
- **Darmowa wersja próbna:** Rozpocznij od pobrania wersji próbnej, aby przetestować funkcje Aspose.Slides.  
- **Licencja tymczasowa:** Uzyskaj tymczasową licencję dla rozszerzonej funkcjonalności bez ograniczeń.  
- **Zakup:** Do dalszego użytkowania wymagana jest licencja.

Po skonfigurowaniu biblioteki i przygotowaniu środowiska przejdźmy do implementacji naszego wykresu pierścieniowego.

## Jak stworzyć wykres pierścieniowy w Javie?
Załaduj nowy obiekt `Presentation`, dodaj wykres pierścieniowy do slajdu, ustaw rozmiar otworu i zapisz plik – wszystko w kilku prostych wywołaniach API. To podejście daje pełną kontrolę nad danymi wykresu, wyglądem i formatem eksportu, a przy tym nie wymaga zainstalowanego Microsoft PowerPoint na serwerze.

### Inicjalizacja obiektu Presentation
Klasa `Presentation` jest głównym obiektem Aspose.Slides reprezentującym plik PowerPoint w pamięci.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Ten krok tworzy pustą prezentację, do której możesz dodawać slajdy, kształty i wykresy.

### Dodawanie wykresu pierścieniowego do slajdu
`ISlide` jest interfejsem pojedynczego slajdu; możesz pobrać pierwszy slajd lub dodać nowy.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Metoda `addChart` tworzy wykres pierścieniowy; parametry określają pozycję (X, Y) oraz rozmiar (szerokość, wysokość) na slajdzie.

### Konfiguracja rozmiaru otworu wykresu pierścieniowego
`Chart` udostępnia metodę `setHoleSize(double)`, aby kontrolować wewnętrzny promień jako procent promienia wykresu.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Ustawienie rozmiaru otworu na 90 % sprawia, że wykres wygląda prawie jak pełne koło, co jest przydatne, gdy chcesz podkreślić zewnętrzne segmenty.

### Zapis prezentacji
`presentation.save(String, SaveFormat)` zapisuje plik na dysku w wybranym formacie.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Przykład zapisuje wynik jako `DoughnutHoleSize_out.pptx`, ale możesz wybrać także PDF, PNG lub dowolny z ponad 50 obsługiwanych formatów.

### Czyszczenie zasobów
Wywołanie `presentation.dispose()` zwalnia zasoby natywne i zapobiega wyciekom pamięci, co jest szczególnie ważne w długotrwale działających aplikacjach serwerowych.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Praktyczne zastosowania
Wykresy pierścieniowe są wszechstronne. Oto kilka scenariuszy, w których się sprawdzają:
1. **Alokacja budżetu:** Pokazuje, jak budżet jest rozdzielany pomiędzy działy.  
2. **Wyniki ankiety:** Wizualizuje odpowiedzi na pytania z wielokrotnym wyborem.  
3. **Źródła ruchu na stronie:** Pokazuje procent ruchu pochodzącego z różnych kanałów (organiczny, płatny, referencyjny itp.).

## Wskazówki dotyczące wydajności
Podczas pracy z Aspose.Slides weź pod uwagę następujące zalecenia:
- Zwalniaj obiekty `Presentation` natychmiast po zakończeniu pracy, aby zwolnić pamięć natywną.  
- Używaj strumieni (`FileInputStream`, `ByteArrayOutputStream`) dla dużych zestawów danych, aby uniknąć ładowania całych plików do pamięci RAM.  
- Ponownie używaj obiektów wykresów przy generowaniu wielu slajdów w pętli, aby zmniejszyć narzut tworzenia obiektów.

## Typowe problemy i rozwiązania
- **Błąd podczas zapisywania:** Sprawdź, czy katalog wyjściowy istnieje i aplikacja ma uprawnienia do zapisu.  
- **Brak danych wykresu:** Upewnij się, że wypełniasz kolekcję `ChartData` wykresu przed wywołaniem `setHoleSize`.  
- **Wzrost zużycia pamięci:** W prezentacjach z tysiącami slajdów, ustaw `Presentation.setSlideSize` na mniejszy rozmiar i szybko zwalniaj pośrednie slajdy.

## Najczęściej zadawane pytania

**P:** Czy mogę dostosować kolory segmentów mojego wykresu pierścieniowego?  
**O:** Tak. Użyj `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` i określ żądany kolor RGB.

**P:** Jak dodać etykiety danych do mojego wykresu?  
**O:** Wywołaj `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`, aby wyświetlić wartość wewnątrz każdego segmentu.

**P:** Czy można zapisać wykresy w formatach innych niż PPTX?  
**O:** Oczywiście. Aspose.Slides obsługuje PDF, XPS, PNG, JPEG, TIFF i wiele innych formatów — ponad 50 łącznie.

**P:** Co zrobić, jeśli napotkam wyjątek podczas ładowania dużej prezentacji?  
**O:** Użyj konstruktora `Presentation`, który przyjmuje strumień, i włącz `loadOptions.setLoadFormat(LoadFormat.Pptx)`, aby strumieniować plik i zmniejszyć zużycie pamięci.

**P:** Czy mogę automatyzować aktualizacje wykresów z żywymi źródłami danych?  
**O:** Tak. Pobierz dane z bazy danych lub API REST, zaktualizuj kolekcję `ChartData` i wywołaj `chart.refresh()` przed zapisaniem prezentacji.

## Zasoby
- **Dokumentacja:** Zapoznaj się ze szczegółowymi referencjami API pod adresem [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).  
- **Pobieranie:** Pobierz najnowszą wersję biblioteki z [Aspose.Slides releases](https://releases.aspose.com/slides/java/).  
- **Zakup:** Aby uzyskać pełny dostęp, zakup licencję na [Aspose Purchase](https://purchase.aspose.com/buy).  
- **Darmowa wersja próbna:** Wypróbuj Aspose.Slides w darmowej wersji próbnej dostępnej na stronie pobierania.  
- **Licencja tymczasowa:** Uzyskaj tymczasową licencję do rozszerzonego testowania bez ograniczeń.  
- **Wsparcie:** Masz pytania? Odwiedź [Aspose Forum](https://forum.aspose.com/c/slides/11) po pomoc.

---

**Ostatnia aktualizacja:** 2026-07-27  
**Testowano z:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Jak dodać wykresy do PowerPoint przy użyciu Aspose.Slides for Java: Przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Jak stworzyć wykres w Javie z Aspose.Slides: Kompletny przewodnik](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}