---
date: '2026-07-17'
description: Dowiedz się, jak dodać wykres do PowerPoint, tworząc wykres Pie of Pie
  przy użyciu Aspose.Slides for Java. Zawiera konfigurację, kod, dostosowywanie i
  zapisywanie jako PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Dodaj wykres do PowerPoint przy użyciu Aspose.Slides for Java. Ten
  przewodnik pokazuje, jak w kilka minut stworzyć, dostosować i zapisać wykres Pie
  of Pie jako PPTX.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Dodaj wykres do PowerPoint – Utwórz wykres Pie of Pie w Javie
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Dodaj wykres do PowerPoint – Utwórz wykres Pie of Pie w Javie przy użyciu Aspose.Slides
url: /pl/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dodaj wykres do PowerPoint – Utwórz wykres Pie of Pie w Javie z Aspose.Slides

## Wykresy i diagramy

### Wprowadzenie

W nowoczesnych prezentacjach opartych na danych, **dodawanie wykresu do PowerPoint** jest często najszybszym sposobem przekształcenia surowych liczb w wizualny wgląd. Zwykły wykres kołowy sprawdza się przy kilku kategoriach, ale gdy kilka fragmentów jest bardzo małych, stają się nieczytelne. Wykres *Pie of Pie* rozwiązuje ten problem, wyodrębniając te małe fragmenty do drugiego koła, utrzymując główny wykres przejrzystym, a szczegóły dostępne.

W tym samouczku nauczysz się, jak **dodawać wykres do PowerPoint** tworząc wykres Pie of Pie przy użyciu Aspose.Slides for Java. Przejdziemy przez konfigurację środowiska, tworzenie wykresu, dostosowywanie etykiet, regulację pozycji podziału oraz ostateczne zapisanie prezentacji jako plik PPTX. Po zakończeniu będziesz gotowy wstawić zaawansowane wykresy do dowolnego zestawu slajdów.

## Szybkie odpowiedzi

W Aspose.Slides, `Presentation` reprezentuje plik PPTX, `ChartType.PieOfPie` wybiera wykres Pie of Pie, `setShowValue(true)` wyświetla wartości na etykietach, a `save` zapisuje plik.

- **Jaka jest podstawowa klasa do manipulacji PowerPoint?** `Presentation` – reprezentuje cały plik PPTX w pamięci.  
- **Który typ wykresu tworzy drugie koło dla małych fragmentów?** `ChartType.PieOfPie`.  
- **Jak wyświetlić wartości na każdym fragmencie?** Ustaw `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Czy możesz zapisać plik bezpośrednio jako PPTX?** Tak – wywołaj `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Czy potrzebna jest licencja do rozwoju?** Darmowa 30‑dniowa wersja próbna działa do testów; stała licencja usuwa znaki wodne wersji ewaluacyjnej.

## Czym jest wykres Pie of Pie?

Wykres **Pie of Pie** to dwupoziomowa wizualizacja kołowa, która izoluje jedną lub więcej małych fragmentów w osobnym, połączonym kole, ułatwiając ich odczyt. Aspose.Slides obsługuje ten typ wykresu od razu, umożliwiając kontrolę rozmiaru podziału, pozycji i formatowania etykiet.

## Dlaczego dodawać wykres do PowerPoint przy użyciu Aspose.Slides?

Aspose.Slides może generować, edytować i renderować pliki PowerPoint bez zainstalowanego Microsoft Office. Obsługuje **ponad 50 formatów wejściowych i wyjściowych**, przetwarza prezentacje z **do 500 slajdami** w mniej niż sekundę na typowym sprzęcie serwerowym oraz zapewnia **pełną kontrolę API** nad stylizacją wykresów, etykietami danych i układem — idealne do zautomatyzowanych potoków raportowania.

## Wymagania wstępne

- **Java Development Kit (JDK) 16+** zainstalowany.  
- IDE, takie jak **IntelliJ IDEA**, **Eclipse** lub **NetBeans**.  
- Maven lub Gradle do zarządzania zależnościami (zobacz sekcje poniżej).  
- Podstawowa znajomość Javy oraz doświadczenie w budowaniu projektów.

## Konfiguracja Aspose.Slides dla Javy

### Informacje o instalacji

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Bezpośrednie pobranie:** Możesz pobrać najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Kroki uzyskania licencji

- **Free Trial:** Rozpocznij od 30‑dniowej wersji próbnej, aby wypróbować wszystkie funkcje.  
- **Temporary License:** Poproś o tymczasowy klucz do przedłużonej oceny.  
- **Purchase:** Uzyskaj stałą licencję do użytku produkcyjnego, aby usunąć znaki wodne wersji ewaluacyjnej.

### Podstawowa inicjalizacja i konfiguracja

`Presentation` jest głównym obiektem do tworzenia plików PowerPoint, a `Chart` reprezentuje kształt wykresu na slajdzie.

```java
Presentation presentation = new Presentation();
```  

Tworzy to pustą prezentację gotową na slajdy i wykresy.

## Przewodnik implementacji

### Jak dodać wykres do PowerPoint przy użyciu Aspose.Slides for Java?

Załaduj nowy `Presentation`, dodaj slajd i wstaw `Chart` typu `PieOfPie`. Łańcuch wywołań API jest zwięzły: utwórz wykres, wypełnij dane serii, dostosuj widoczność etykiet, skonfiguruj rozmiar drugiego koła i na końcu zapisz. Cały proces zazwyczaj mieści się w mniej niż 20 liniach kodu, co czyni go idealnym do automatycznego generowania raportów.

### Tworzenie wykresu 'Pie of Pie'

#### Przegląd

Zbudujemy wykres Pie of Pie na pierwszym slajdzie, wyodrębniając najmniejsze fragmenty i oznaczając każdy segment jego wartością.

#### Krok 1: Utwórz instancję klasy Presentation

```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  

Inicjalizuje to kontener dla wszystkich kolejnych slajdów i wykresów.

#### Krok 2: Dodaj wykres 'Pie of Pie' na pierwszym slajdzie

```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  

Tutaj określamy `ChartType.PieOfPie` i definiujemy pozycję wykresu (X, Y) oraz rozmiar (szerokość, wysokość) na płótnie slajdu.

#### Krok 3: Ustaw etykiety danych, aby wyświetlały wartości dla serii

```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  

Włączenie `showValue` powoduje, że każdy fragment wyświetla swoją wartość liczbową, co jest niezbędne do szybkiej interpretacji danych.

#### Krok 4: Skonfiguruj rozmiar drugiego koła i podział procentowy

```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  

Te opcje pozwalają określić, jaka część wykresu jest przydzielona do drugiego koła oraz które fragmenty są przenoszone na podstawie progu procentowego.

#### Krok 5: Zapisz prezentację na dysku w formacie PPTX

```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Wskazówka:** Użyj ścieżki bezwzględnej lub `Paths.get()` z Javy, aby uniknąć separatorów specyficznych dla platformy.

## Typowe problemy i rozwiązania

Klasa `License` ładuje plik licencji, aby usunąć ograniczenia wersji ewaluacyjnej.

- **Brak ostrzeżenia o licencji:** Jeśli widzisz „Evaluation Only” na wykresie, upewnij się, że zastosowano prawidłowy plik licencji za pomocą `License license = new License(); license.setLicense("Aspose.Slides.lic");`.  
- **Nieprawidłowy podział fragmentów:** Sprawdź, czy właściwość `splitBy` jest ustawiona na `SplitBy.Percentage` oraz czy `secondPieSize` ma wartość pomiędzy 0 a 100.  
- **Dane nie wyświetlają się:** Upewnij się, że seria wykresu zawiera co najmniej jeden punkt danych; w przeciwnym razie wykres będzie pusty.

## Najczęściej zadawane pytania

`IChart` reprezentuje obiekt wykresu, który może być dodany do slajdu.

**Q: Czy mogę generować wiele wykresów w jednej prezentacji?**  
A: Tak, utwórz nowy `IChart` dla każdego slajdu lub miejsca; API pozwala na nieograniczoną liczbę obiektów wykresu w pliku.

`SaveFormat.Pdf` określa format wyjściowy PDF przy zapisywaniu.

**Q: Czy Aspose.Slides obsługuje również zapisywanie jako PDF?**  
A: Oczywiście – wywołaj `presentation.save("output.pdf", SaveFormat.Pdf)`, aby wyeksportować ten sam zestaw slajdów do PDF.

`IPortion` reprezentuje pojedynczy fragment wykresu kołowego.

**Q: Jaka jest maksymalna liczba punktów danych, które wykres Pie of Pie może obsłużyć?**  
A: Biblioteka obsługuje do **10 000** punktów danych na serię, ograniczona jedynie dostępnej pamięcią.

**Q: Czy można dostosować kolory poszczególnych fragmentów?**  
A: Tak, uzyskaj dostęp do każdego `IPortion` poprzez `chart.getChartData().getSeries().get_Item(0).getPortions()` i ustaw `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.

**Q: Jak wbudować wygenerowany PPTX w aplikację webową?**  
A: Po zapisaniu pliku, przesyłaj go bezpośrednio do klienta używając `HttpServletResponse` z nagłówkiem `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Podsumowanie

Masz teraz kompletny, gotowy do produkcji przepis na **dodawanie wykresu do PowerPoint** poprzez tworzenie wykresu Pie of Pie przy użyciu Aspose.Slides for Java. Eksperymentuj z różnymi progami podziału, formatami etykiet i schematami kolorów, aby dopasować je do wytycznych marki. Następnie odkryj inne typy wykresów — takie jak wykres słupkowy skumulowany czy radarowy — aby jeszcze bardziej wzbogacić automatyczne zestawy slajdów.

---

**Ostatnia aktualizacja:** 2026-07-17  
**Testowane z:** Aspose.Slides for Java 24.12  
**Autor:** Aspose

## Powiązane samouczki

- [Tworzenie dynamicznego wykresu Java – Samouczki wykresów PowerPoint dla Aspose.Slides](/slides/java/charts-graphs/)
- [Jak dodać wykres kołowy do PowerPoint przy użyciu Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Jak dodać wykresy do PowerPoint przy użyciu Aspose.Slides for Java: Przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}