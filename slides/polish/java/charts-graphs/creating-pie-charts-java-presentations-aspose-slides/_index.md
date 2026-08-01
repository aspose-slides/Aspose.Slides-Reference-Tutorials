---
date: '2026-08-01'
description: Dowiedz się, jak używać licencji Aspose Slides do tworzenia i dostosowywania
  pie charts w prezentacjach Java. Postępuj zgodnie z instrukcjami krok po kroku,
  aby skonfigurować dane wykresu i efektywnie dodawać slajdy z wykresami.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Dowiedz się, jak używać licencji Aspose Slides do tworzenia i dostosowywania
  pie charts w prezentacjach Java. Postępuj zgodnie z instrukcjami krok po kroku,
  aby skonfigurować dane wykresu i efektywnie dodawać slajdy z wykresami.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Tworzenie pie charts w Java z licencją Aspose Slides
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Tworzenie pie charts w Java z licencją Aspose Slides
url: /pl/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć wykresy kołowe w prezentacjach Java przy użyciu Aspose.Slides

## Wprowadzenie

Jeśli potrzebujesz tworzyć profesjonalnie wyglądające prezentacje, **licencja Aspose Slides** daje Ci możliwość generowania i stylizacji wykresów programowo. W tym przewodniku nauczysz się, jak stworzyć wykres kołowy, skonfigurować jego dane i osadzić go w zestawie slajdów Java — bez korzystania z Microsoft PowerPoint. Przejdziemy przez konfigurację, przepływ kodu oraz wskazówki najlepszych praktyk, abyś w kilka minut mógł dostarczyć dopracowane raporty wizualne.

**Czego się nauczysz:**
- Konfiguracja Aspose.Slides dla Java z ważną licencją
- Kroki tworzenia i dostosowywania wykresu kołowego
- Jak skonfigurować dane wykresu kołowego i dodać slajdy z wykresami
- Typowe pułapki i triki wydajnościowe

Zacznijmy od potwierdzenia, że Twoje środowisko jest gotowe.

## Szybkie odpowiedzi
- **Co umożliwia licencja Aspose Slides?** Pełna funkcjonalność tworzenia wykresów, eksport do PDF/HTML oraz usuwanie znaków wodnych.
- **Która wersja Java jest wymagana?** JDK 16 lub nowsza.
- **Czy potrzebuję Maven czy Gradle?** Oba działają; biblioteka jest dostępna w obu.
- **Ile punktów danych może pomieścić wykres kołowy?** Do 10 000 punktów bez problemów z pamięcią.
- **Czy mogę wyeksportować slajd jako obraz?** Tak – obsługiwane są PNG, JPEG, SVG i inne.

## Wymagania wstępne

Przed rozpoczęciem zweryfikuj, że masz:
- **Required Libraries:** Aspose.Slides for Java (version 25.4 or later) – this version supports the latest file formats and performance optimizations.
- **Environment Setup:** JDK 16+ installed and configured in your IDE or build system.
- **Basic Knowledge:** Familiarity with Java, Maven or Gradle, and object‑oriented programming concepts.

## Konfiguracja Aspose.Slides dla Java

Aby używać Aspose.Slides for Java, dołącz go do swojego projektu. Oto jak dodać zależność przy użyciu najpopularniejszych narzędzi budowania:

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

**Direct Download:** Możesz również pobrać najnowszy plik JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji

Aspose oferuje bezpłatną wersję próbną, która odblokowuje wszystkie funkcje, ale **ważna licencja Aspose Slides** jest wymagana w środowisku produkcyjnym, aby usunąć znaki wodne wersji ewaluacyjnej i uzyskać korzyści wydajnościowe. Opcje zakupu są wymienione na [purchase page](https://purchase.aspose.com/buy). Po uzyskaniu pliku licencji, załaduj go raz przy uruchamianiu aplikacji:

`License` loads and applies your Aspose.Slides license.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Przewodnik implementacji

### Tworzenie i dodawanie wykresu kołowego do prezentacji

#### Przegląd
Ta sekcja wyjaśnia, jak stworzyć wykres kołowy, skonfigurować jego serię danych i osadzić wykres na slajdzie. Zobaczysz kompletny przepływ od inicjalizacji obiektu prezentacji po zapisanie finalnego pliku.

#### Krok 1: Inicjalizacja prezentacji  
`Presentation` is Aspose.Slides' top‑level object that represents a PowerPoint file in memory. Creating an instance gives you a blank slide deck ready for modification.

```java
demo.Presentation pres = new demo.Presentation();
```  
Ten wiersz tworzy nową prezentację, w której zostaną zastosowane wszystkie kolejne zmiany.

#### Krok 2: Dodanie wykresu kołowego do slajdu  
`Chart` is the class that encapsulates chart objects, including pie charts. Adding a chart to a slide is a single method call that specifies position and size.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` i `yPosition` ustawiają lewy górny róg wykresu.  
- `width` i `height` definiują wizualny rozmiar wykresu na slajdzie.

#### Krok 3: Konfiguracja danych wykresu kołowego  
`ChartData` holds the data series for a chart.  
**Jak skonfigurować dane wykresu kołowego?**  
Użyj kolekcji `ChartData`, aby dodać serię, a następnie wypełnij obiekty `ChartDataPoint` wartościami liczbowymi i nazwami kategorii. Takie podejście pozwala wyświetlić do 10 000 segmentów przy zachowaniu formatowania etykiet. Po ustawieniu danych możesz dostosować kolory, legendy i etykiety danych, aby pasowały do wytycznych stylu korporacyjnego.

Teraz kod, który dodaje dwie kategorie i wyświetla ich etykiety:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
Fragment tworzy serię danych, wstawia dwa punkty i włącza etykiety kategorii na wykresie.

#### Krok 4: Zapis prezentacji  
Na koniec zapisz prezentację w wybranym formacie (PPTX, PDF lub PNG). Metoda `save` respektuje aktywną licencję, zapewniając brak znaków wodnych wersji próbnej.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Typowe problemy i rozwiązania
- **Błąd brakującej licencji:** Upewnij się, że ścieżka do pliku licencji jest prawidłowa i obiekt `License` został zainicjowany przed jakimikolwiek wywołaniami Aspose.Slides.
- **Pusty wykres:** Sprawdź, czy seria `ChartData` zawiera co najmniej jeden `ChartDataPoint`. Pusta seria skutkuje pustym obszarem wykresu.
- **Opóźnienia wydajności przy dużych zestawach danych:** Użyj `presentation.getSlides().removeAt(index)`, aby usunąć nieużywane slajdy i wywołaj `System.gc()` po intensywnym przetwarzaniu.

## Praktyczne zastosowania
1. **Raporty biznesowe:** Wizualizuj udział rynkowy lub dystrybucję przychodów w poszczególnych regionach za pomocą jednego wykresu kołowego.
2. **Prezentacje akademickie:** Przedstaw wyniki ankiet lub eksperymentów w przejrzystym, przystępnym formacie.
3. **Dashboardy projektowe:** Przedstaw odsetek ukończenia zadań lub alokację zasobów natychmiast na slajdzie.

Możesz także połączyć Aspose.Slides z JDBC, aby pobierać dane na żywo z bazy danych, generując aktualne wykresy do cotygodniowych briefów dla kadry zarządzającej.

## Rozważania dotyczące wydajności
Podczas przetwarzania prezentacji zawierających wiele obrazów wysokiej rozdzielczości lub duże zestawy danych:
- Zwalniaj obiekty niezwłocznie, używając `try‑with‑resources` lub wywołań `dispose()`.
- Włącz leniwe ładowanie zasobów slajdów, aby utrzymać niskie zużycie pamięci.
- Podczas przetwarzania wsadowego, w miarę możliwości ponownie używaj jednej instancji `Presentation`, aby zmniejszyć obciążenie JVM.

## Zakończenie
Masz teraz kompletny, gotowy do produkcji proces tworzenia wykresów kołowych w Javie przy użyciu **licencji Aspose Slides**. Eksperymentuj z dodatkowymi typami wykresów — słupkowymi, liniowymi lub pierścieniowymi — aby jeszcze bardziej wzbogacić swoje slajdy. Następnie odkryj możliwości eksportu API, aby automatycznie generować raporty PDF lub obrazy PNG.

## Najczęściej zadawane pytania

**P: Jak dodać wiele wykresów do jednego slajdu?**  
O: Wywołaj `slide.getShapes().addChart()` dla każdego wykresu, podając unikalne współrzędne i wymiary dla każdej instancji.

**P: Jakie są alternatywy dla Aspose.Slides dla Java?**  
O: Apache POI i JFreeChart są popularnymi alternatywami, ale nie oferują tak kompleksowych opcji eksportu i modelu licencjonowania jak Aspose.

**P: Czy mogę konwertować moją prezentację na inne formaty przy użyciu Aspose.Slides?**  
O: Tak — eksportuj do PDF, XPS, HTML, PNG, JPEG, SVG i innych przy użyciu jednego wywołania `save`.

**P: Jak zarządzać licencjonowaniem dla dużego zespołu deweloperskiego?**  
O: Kup licencję enterprise obejmującą wielu deweloperów i serwery; skontaktuj się z działem sprzedaży Aspose w celu uzyskania rabatów ilościowych.

**P: Co zrobić, gdy dane wykresu są często aktualizowane?**  
O: Zintegruj Aspose.Slides ze źródłem danych (np. zapytaniem SQL) i odtwarzaj wykres w czasie rzeczywistym; API obsługuje dynamiczne powiązanie danych.

## Zasoby
- **Dokumentacja:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **Pobieranie:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **Zakup:** [Buy a License](https://purchase.aspose.com/buy)
- **Bezpłatna wersja próbna:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Licencja tymczasowa:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **Wsparcie:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-08-01  
**Tested With:** Aspose.Slides for Java 25.4  
**Author:** Aspose

## Powiązane samouczki

- [Jak dodać i skonfigurować wykresy w prezentacjach przy użyciu Aspose.Slides dla Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Tworzenie i dostosowywanie wykresów w prezentacjach Java przy użyciu Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Jak tworzyć i konfigurować prezentacje z Aspose.Slides Java: przewodnik krok po kroku](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}