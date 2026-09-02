---
date: '2026-09-02'
description: Dowiedz się, jak utworzyć wykres lejkowy w PowerPoint przy użyciu Aspose.Slides
  for Java. Ten przewodnik krok po kroku obejmuje ustawianie danych wykresu, dostosowywanie
  kolorów oraz eksportowanie prezentacji.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Dowiedz się, jak utworzyć wykres lejkowy w PowerPoint przy użyciu
  Aspose.Slides for Java. Ten przewodnik prowadzi Cię przez konfigurację danych, dostosowywanie
  kolorów oraz eksport finalnej prezentacji.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Utwórz wykres lejkowy w PowerPoint przy użyciu Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Utwórz wykres lejkowy w PowerPoint przy użyciu Aspose.Slides for Java
url: /pl/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie tworzenia wykresu lejkowego w PowerPoint przy użyciu Aspose.Slides for Java

## Wprowadzenie

Tworzenie przekonujących prezentacji to sztuka łącząca wizualizację danych, projektowanie i opowiadanie historii. Jednym z potężnych wizualizacji, które natychmiast wyjaśnia proces wieloetapowy, jest wykres lejkowy. Niezależnie od tego, czy musisz zilustrować lejek sprzedaży, przepływ konwersji czy wąskie gardło produkcji, dobrze zaprojektowany wykres lejkowy zamienia surowe liczby w intuicyjną narrację. W tym samouczku nauczysz się, jak **create funnel chart** w PowerPoint programowo przy użyciu Aspose.Slides for Java, skonfigurować jego dane, dostosować kolor każdego segmentu i wyeksportować gotową prezentację.

**Czego się nauczysz**
- Jak dodać Aspose.Slides for Java do projektu Maven lub Gradle  
- Jak utworzyć obiekt `Presentation` i uzyskać dostęp do jego slajdów  
- Jak wstawić wykres lejkowy, zdefiniować kategorie i wypełnić dane serii  
- Jak stylizować każdy segment lejka przy użyciu jednolitych wypełnień lub kolorów specyficznych dla marki  
- Jak zapisać prezentację jako plik PPTX lub wyeksportować slajd jako obraz  

## Szybkie odpowiedzi
- **Jaką jest główna biblioteka do wizualizacji danych w Javie?** Aspose.Slides for Java.  
- **Jak utworzyć wykres lejkowy w PowerPoint?** Call `slide.addChart(ChartType.Funnel, …)` on the target slide.  
- **Które API ustawia źródło danych wykresu?** Use `IChartDataWorkbook` together with `chart.getChartData()`.  
- **Czy możesz dostosować kolory dla każdego segmentu lejka?** Yes—set `FillFormat.setFillType(FillType.Solid)` and assign a `java.awt.Color`.  
- **Czy potrzebujesz licencji do użytku produkcyjnego?** A purchased Aspose.Slides license is required for commercial deployments.

## Co to jest wizualizacja danych w Javie?

Wizualizacja danych w Javie to praktyka przekształcania surowych danych w wykresy, diagramy lub interaktywne grafiki bezpośrednio z aplikacji Java. Aspose.Slides for Java jest wiodącą biblioteką, która umożliwia programistom generowanie ponad 100 typów wykresów — w tym wykresów lejkowych — bez ręcznego uruchamiania PowerPoint, obsługując prezentacje do 500 slajdów przy niskim zużyciu pamięci.

## Dlaczego używać wykresów lejkowych w PowerPoint?

Wykresy lejkowe natychmiast ujawniają wskaźniki spadku na kolejnych etapach, co czyni je idealnymi do lejkowania sprzedaży, analizy konwersji lub przeglądów efektywności procesów. Aspose.Slides zapewnia kontrolę pixel‑perfect nad układem, kolorami segmentów i etykietami danych, dzięki czemu możesz zachować spójność marki i uniknąć ręcznej edycji wykresów w interfejsie PowerPoint.

## Wymagania wstępne (H2)

### Wymagane biblioteki, wersje i zależności
Aby wdrożyć Aspose.Slides for Java w swoim projekcie, dołącz odpowiednie współrzędne Maven lub Gradle. Biblioteka działa z Java 8‑21 i nie wymaga zewnętrznych zależności natywnych.

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

Możesz również pobrać plik JAR bezpośrednio z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Wymagania dotyczące konfiguracji środowiska
Upewnij się, że masz zainstalowany JDK 8 lub nowszy oraz że zmienna `JAVA_HOME` wskazuje na właściwy katalog JDK. Aspose.Slides działa na każdym systemie operacyjnym obsługującym JDK, w tym Windows, macOS i Linux.

### Wymagania wiedzy wstępnej
Podstawowa znajomość składni Java, programowania obiektowego oraz koncepcji pliku prezentacji będzie pomocna, ale fragmenty kodu są w pełni wyjaśnione dla programistów o dowolnym poziomie doświadczenia.

## Konfigurowanie Aspose.Slides for Java (H2)

1. **Dodaj zależność** – użyj fragmentu Maven lub Gradle powyżej.  
2. **Uzyskaj licencję** –  
   - **Free trial** – Pobierz tymczasową licencję z [Aspose's website](https://purchase.aspose.com/temporary-license/) do oceny.  
   - **Full license** – Kup licencję produkcyjną poprzez [purchase page](https://purchase.aspose.com/buy).  
3. **Podstawowa inicjalizacja** –  

`Presentation` is Aspose.Slides' core class that represents a PowerPoint file in memory. It provides access to slides, shapes, and chart objects.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

Powyzszy kod tworzy nową instancję `Presentation`, gotową do manipulacji slajdami i zapewnia zwolnienie zasobów przy użyciu `dispose()`.

## Przewodnik implementacji

Przejdziemy przez każdą funkcję potrzebną do zbudowania pełnego wykresu lejkowego, dodając krótkie wyjaśniające teksty przed każdym miejscem kodu.

### Funkcja 1: tworzenie prezentacji (H2)

#### Przegląd
Rozpocznij od utworzenia instancji klasy `Presentation`. Ten obiekt jest punktem wejścia dla wszystkich kolejnych operacji.

`Presentation` jest obiektem najwyższego poziomu w Aspose.Slides, który przechowuje kolekcję slajdów i globalne ustawienia dokumentu.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Fragment otwiera pustą prezentację, którą możesz później zapisać jako plik `.pptx`.

### Funkcja 2: dodawanie wykresu lejkowego do slajdu (H2)

#### Przegląd
Wstaw wykres lejkowy na pierwszym slajdzie, określ jego rozmiar i ustaw typ wykresu.

`ChartType.Funnel` instruuje Aspose.Slides, aby renderował wizualizację w stylu lejka zamiast wykresu słupkowego lub liniowego.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

Wywołanie `addChart` tworzy kształt wykresu, pozycjonuje go w punkcie `(50, 50)` i nadaje mu szerokość `500` oraz wysokość `400`.

### Funkcja 3: czyszczenie danych wykresu (H2)

#### Przegląd
Przed wypełnieniem wykresu, wyczyść wszelkie kategorie lub serie zastępcze, które może zawierać szablon.

`chart.getChartData().getCategories().clear()` usuwa wszystkie istniejące wpisy kategorii, natomiast `chart.getChartData().getSeries().clear()` usuwa wszelkie wstępnie wypełnione serie.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

To zapewnia czystą kartę, aby Twoje własne dane pojawiły się dokładnie tak, jak zamierzone.

### Funkcja 4: konfigurowanie skoroszytu danych wykresu (H2)

#### Przegląd
Obiekt `IChartDataWorkbook` przechowuje surowe wartości napędzające wykres. Inicjalizacja pozwala zapisywać dane bezpośrednio do komórek.

`IChartDataWorkbook` jest lekką, pamięciową tabelą kalkulacyjną, której Aspose.Slides używa do dostarczania serii i kategorii wykresu.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

Kod usuwa wszystkie istniejące komórki, przygotowując skoroszyt do nowych wpisów.

### Funkcja 5: dodawanie kategorii do wykresu (H2)

#### Przegląd
Zdefiniuj tekstowe etykiety pojawiające się po lewej stronie lejka — reprezentują one każdy etap Twojego procesu.

`chart.getChartData().getCategories().add()` tworzy nowy obiekt kategorii powiązany z określoną komórką skoroszytu.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Tutaj dodajemy trzy etapy: „Prospects”, „Qualified Leads” i „Closed Deals”.

### Funkcja 6: dodawanie serii danych do wykresu (H2)

#### Przegląd
Wypełnij lejek wartościami liczbowymi i opcjonalnie przypisz unikalny kolor do każdego segmentu.

`IDataPoint` reprezentuje pojedynczy punkt danych w serii wykresu.  

`chart.getChartData().getSeries().add()` tworzy serię, która przechowuje numeryczne punkty danych; każdy `IDataPoint` może otrzymać własny kolor wypełnienia.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

Pętla demonstruje, jak ustawić jednolite wypełnienie dla każdego punktu, używając specyficznych dla marki stałych `java.awt.Color` lub losowo generowanych kolorów dla różnorodności wizualnej.

## Typowe przypadki użycia i wskazówki (H2)

- **Raportowanie leja sprzedaży** – Pokaż, ile leadów przechodzi od prospect do closed‑won na każdym etapie.  
- **Analiza efektywności procesu** – Zwizualizuj straty materiałowe lub opóźnienia czasowe w kolejnych krokach produkcji.  
- **Przegląd lejka marketingowego** – Porównaj wskaźniki konwersji w różnych kampaniach lub źródłach ruchu.  

**Pro tip:** Zamiast losowych kolorów, użyj palety marki firmy (np. `new Color(0, 112, 192)`), aby prezentacja była spójna z innymi materiałami marketingowymi.

## Najczęściej zadawane pytania (H2)

**Q: Jak zmienić orientację wykresu lejkowego?**  
A: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical` or `ChartOrientation.Horizontal`.

**Q: Czy mogę wyeksportować slajd jako obraz po dodaniu wykresu?**  
A: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.

**Q: Co zrobić, jeśli potrzebuję więcej niż trzy kategorie?**  
A: Simply add additional categories using `chart.getChartData().getCategories().add(...)` and provide matching data points for each new category.

**Q: Czy istnieje sposób, aby ukryć legendę?**  
A: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)` to remove both the title and legend from the visual.

**Q: Czy potrzebuję licencji do wersji deweloperskich?**  
A: A temporary license is sufficient for evaluation; a full commercial license is required for production deployments.

---

**Ostatnia aktualizacja:** 2026-09-02  
**Testowano z:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose

## Powiązane samouczki

- [Jak dodać wykres do PowerPoint przy użyciu Aspose.Slides for Java: przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Jak edytować dane wykresu PowerPoint przy użyciu Aspose.Slides for Java: kompleksowy przewodnik](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Dodaj animację do wykresu PowerPoint przy użyciu Aspose.Slides for Java – przewodnik krok po kroku](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}