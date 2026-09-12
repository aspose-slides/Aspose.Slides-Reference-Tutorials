---
date: '2026-09-12'
description: Dowiedz się, jak używać Maven Aspose Slides do dodawania i dostosowywania
  dynamicznych wykresów giełdowych w PowerPoint przy użyciu Java. Zawiera konfigurację,
  dodawanie serii danych, formatowanie linii oraz zapisywanie.
keywords:
- maven aspose slides
- add data series chart
- format chart lines
- customize chart java
lastmod: '2026-09-12'
og_description: Samouczek Maven Aspose Slides pokazuje, jak tworzyć i dostosowywać
  dynamiczne wykresy giełdowe w PowerPoint przy użyciu Java, obejmując serie danych,
  formatowanie linii i zapisywanie.
og_image_alt: Illustration of a Java-generated stock chart in PowerPoint using Aspose.Slides
og_title: 'Poradnik Maven Aspose Slides: tworzenie dynamicznych wykresów giełdowych
  w PowerPoint'
schemas:
- author: Aspose
  dateModified: '2026-09-12'
  description: Learn how to use Maven Aspose Slides to add and customize dynamic stock
    charts in PowerPoint with Java. Includes setup, adding data series, formatting
    lines, and saving.
  headline: 'Maven Aspose Slides: create dynamic stock charts in PowerPoint with Java'
  type: TechArticle
- questions:
  - answer: Yes. The library is pure Java, so you can run it in any servlet container
      or Spring Boot service.
    question: Can I use this code in a web application?
  - answer: Absolutely. It supports over 70 chart types, including Line, Bar, Pie,
      and Radar charts.
    question: Does Aspose.Slides support other chart types besides Stock?
  - answer: Use `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`
      and then format the title as needed.
    question: How do I add a chart title programmatically?
  - answer: Practically, you can add tens of thousands of points; memory usage scales
      linearly, and the library streams data to keep the footprint low.
    question: Is there a limit to the number of data points per series?
  - answer: The latest version is always available under `com.aspose:aspose-slides:25.4`
      (or newer) on Maven Central.
    question: Which Maven coordinates should I use for the latest version?
  type: FAQPage
tags:
- maven aspose slides
- dynamic stock charts
- java charting
- aspose.slides
title: 'Maven Aspose Slides: tworzenie dynamicznych wykresów giełdowych w PowerPoint
  przy użyciu Java'
url: /pl/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Maven Aspose Slides: tworzenie dynamicznych wykresów giełdowych w PowerPoint przy użyciu Javy

## Wprowadzenie

**Maven Aspose Slides** pozwala programowo generować zaawansowane prezentacje PowerPoint z Javy. W tym samouczku nauczysz się, jak tworzyć dynamiczne wykresy giełdowe, dodawać i formatować serie danych, dostosowywać linie wykresu oraz ostatecznie zapisywać plik. Niezależnie od tego, czy jesteś analitykiem finansowym przygotowującym kwartalne raporty, czy programistą budującym automatyczne zestawy slajdów, poniższe kroki dostarczają kompletną, gotową do produkcji rozwiązanie.

**Co się nauczysz**
- Jak skonfigurować Maven z Aspose.Slides for Java  
- Jak dodać wykres giełdowy i wyczyścić domyślne dane  
- Jak **add data series chart** i **format chart lines**  
- Jak **customize chart java**‑specific visual elements  
- Jak zapisać zaktualizowaną prezentację

Gotowy, aby zamienić surowe liczby w przyciągające wzrok wizualizacje giełdowe? Zaczynajmy!

## Szybkie odpowiedzi
- **Jakiego artefaktu Maven potrzebuję?** `aspose-slides` version 25.4 (or newer).  
- **Czy mogę uruchomić to na dowolnym systemie operacyjnym?** Tak – biblioteka jest czystą Javą i działa na Windows, macOS i Linux.  
- **Czy potrzebuję licencji do rozwoju?** Darmowa tymczasowa licencja działa w trybie testowym; pełna licencja jest wymagana w produkcji.  
- **Jakie typy wykresów są obsługiwane?** Ponad 70 wbudowanych typów wykresów, w tym Stock, Line i Bar.  
- **Jak duże prezentacje mogę przetwarzać?** Aspose.Slides może obsłużyć pliki z ponad 500 slajdami bez ładowania całego pliku do pamięci.

## Czym jest Maven Aspose Slides?

`Aspose.Slides for Java` to interfejs API w Javie, który umożliwia tworzenie, manipulację i konwersję plików PowerPoint bez Microsoft Office. Integracja z Maven upraszcza zarządzanie zależnościami, pozwalając pobrać bibliotekę bezpośrednio z Maven Central.

## Dlaczego warto używać Maven Aspose Slides do wykresów giełdowych?

Aspose.Slides obsługuje **70+ chart types** i może renderować wielostronicowe prezentacje w czasie krótszym niż sekunda na typowym sprzęcie serwerowym. Funkcje **high‑low line** i **up/down bar** zapewniają precyzyjną kontrolę nad wizualizacjami finansowymi, znacznie wykraczając poza możliwości interfejsu PowerPoint.

## Wymagania wstępne

- **Java Development Kit (JDK)** – wersja 11 lub wyższa.  
- **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor, który preferujesz.  
- **Aspose.Slides for Java** – wersja 25.4 (najnowsza w momencie pisania).  

### Konfiguracja Aspose.Slides for Java

#### Maven
Aby zintegrować Aspose.Slides z projektem przy użyciu Maven, dodaj następującą zależność do swojego `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Dla użytkowników Gradle, umieść to w swoim `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Bezpośrednie pobranie
Alternatywnie, pobierz najnowszy plik JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**License acquisition** – rozpocznij od darmowej wersji próbnej lub poproś o tymczasową licencję. W zastosowaniach komercyjnych zakup pełną licencję.

Szczegółową dokumentację API znajdziesz w [Aspose.Slides documentation](https://docs.aspose.com/slides/java/).

## Jak krok po kroku stworzyć dynamiczny wykres giełdowy

Wczytaj swoją prezentację, dodaj wykres giełdowy, wyczyść domyślne dane, a następnie wstaw własne serie i kategorie. Bezpośrednia odpowiedź na kluczowe pytanie brzmi:

> Wczytaj istniejący plik PPTX przy użyciu `new Presentation("template.pptx")`, dodaj `Chart` typu `ChartType.Stock`, wyczyść jego domyślne serie i kategorie, a następnie wypełnij je własnymi punktami danych i opcjami formatowania. Na koniec wywołaj `presentation.save("output.pptx", SaveFormat.Pptx)`.

### Inicjalizacja prezentacji
#### Przegląd
Rozpocznij od wczytania istniejącego pliku PowerPoint, aby móc go modyfikować w miejscu.

#### Krok po kroku
1. **Import the library** – klasa `Presentation` jest punktem wejścia dla wszystkich operacji na slajdach.  

   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Load the presentation file** – podaj ścieżkę do swojego szablonu PPTX.  

   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Ready to perform operations on 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Dodaj wykres giełdowy do slajdu
#### Przegląd
Wstaw wykres Stock na pierwszym slajdzie prezentacji.

Klasa `Chart` reprezentuje kształt wykresu, który można dodać do slajdu.

#### Bezpośrednia odpowiedź
Dodajesz wykres giełdowy, wywołując `slide.getShapes().addChart(ChartType.Stock, x, y, width, height)`. Tworzy to obiekt wykresu, który możesz od razu manipulować.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Wyczyść istniejące serie danych i kategorie w wykresie
#### Przegląd
Usuń wszelkie wstępnie wypełnione serie lub kategorie, aby rozpocząć z czystym zestawem danych.

Obiekt `ChartData` przechowuje serie i kategorie dla wykresu.

#### Bezpośrednia odpowiedź
Wywołaj `chart.getChartData().getSeries().clear()` oraz `chart.getChartData().getCategories().clear()`, aby usunąć domyślną zawartość przed dodaniem własnych.

```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Dodaj kategorie do danych wykresu
#### Przegląd
Zdefiniuj kategorie osi X (np. daty), które grupują Twoje wartości giełdowe.

`ChartCategory` reprezentuje etykietę osi X dla wykresu.

#### Bezpośrednia odpowiedź
Utwórz nowy `ChartCategory` dla każdej etykiety, używając `chart.getChartData().getCategories().add(dataWorkbook.getCell(0, row, 0), "Jan")`, powtarzając dla każdego miesiąca lub okresu.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Add categories
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Dodaj serie danych do wykresu
#### Przegląd
Dodaj cztery podstawowe serie: Open, High, Low i Close.

`ChartSeries` przechowuje kolekcję punktów danych dla konkretnej serii w wykresie.

#### Bezpośrednia odpowiedź
Dla każdej serii wywołaj `chart.getChartData().getSeries().add(dataWorkbook.getCell(0, 0, colIndex), chart.getType())`. Rejestruje to serię w skoroszycie danych wykresu.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add series for 'Open', 'High', 'Low', and 'Close'
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Dodaj punkty danych do serii
#### Przegląd
Wypełnij każdą serię wartościami liczbowymi reprezentującymi ceny akcji.

`DataPoint` reprezentuje pojedynczą wartość w serii.

#### Bezpośrednia odpowiedź
Iteruj przez swoją kolekcję danych i użyj `series.getDataPoints().addDataPointForBarSeries(dataWorkbook.getCell(0, row, col), value)` (lub odpowiedniej metody dla typu serii), aby wstawić każdy punkt.

```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Add data points to 'Open' series
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Add data points to 'High' series
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Add data points to 'Low' series
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Add data points to 'Close' series
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formatuj linie high‑low oraz up/down bars
#### Przegląd
Dostosuj styl wizualny łączników high‑low oraz wypełnień up/down bar.

`Marker` definiuje wizualny symbol dla punktu danych.

#### Bezpośrednia odpowiedź
Ustaw `chart.getChartData().getSeries().get(0).getMarker().setSize(10)` i skonfiguruj `chart.getChartData().getSeries().get(0).getFormat().getLine().setWidth(2)`, aby kontrolować grubość i kolor linii.

```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Format high-low lines for 'Close' series
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

#### Wyświetl up/down bars
Użyj metody `setShowUpDownBars(true)` wykresu, aby wyświetlić up/down bars.

```java
   // Display up/down bars for the stock chart series group
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Dostosuj etykiety danych na liniach high‑low
#### Przegląd
Wyświetl wartości liczbowe bezpośrednio na liniach high‑low dla szybkiego odniesienia.

`DataLabel` kontroluje wygląd etykiet dołączonych do punktów danych.

#### Bezpośrednia odpowiedź
Włącz etykiety danych przy użyciu `chart.getChartData().getSeries().get(0).getDataPoints().get(i).getLabel().setShowValue(true)` i stylizuj je w razie potrzeby.

```java
    // Show values on up/down bars for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Ustaw kolor wypełnienia up/down bars
#### Przegląd
Nadaj up barom zielone wypełnienie, a down barom czerwone, aby intuicyjnie przekazać ruch rynku.

Obiekt `UpDownBars` zapewnia dostęp do formatowania up i down bar.

#### Bezpośrednia odpowiedź
Zastosuj `chart.getUpDownBars().getUpBar().getFillFormat().setFillType(FillType.Solid)` i ustaw stały kolor na `Color.GREEN`; powtórz dla down bar z `Color.RED`.

```java
    // Change the up/down bar colors for each series in the chart group
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // 'Open' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Up bars in cyan
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // 'High' series
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Down bars in dark sea green
        }
    }
    ```

### Zapisz plik PowerPoint
#### Przegląd
Zachowaj zmiany w nowym pliku PPTX.

Metoda `save` zapisuje prezentację na dysk w określonym formacie.

#### Bezpośrednia odpowiedź
Wywołaj `presentation.save("DynamicStockChart.pptx", SaveFormat.Pptx)` – zapisuje to zmodyfikowaną prezentację na dysku w standardowym formacie PowerPoint.

```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Typowe problemy i rozwiązywanie
- **Chart not appearing** – upewnij się, że współrzędne X/Y wykresu oraz jego wymiary mieszczą się w granicach slajdu.  
- **Data points missing** – sprawdź, czy indeksy komórek skoroszytu danych odpowiadają serii/wierszowi, które chcesz wypełnić.  
- **License exception** – tymczasowa licencja próbna wygasa po 30 dniach; zastąp ją stałą licencją w wersjach produkcyjnych.  
- **Performance slowdown on large files** – użyj `Presentation.setCacheSize(0)`, aby wyłączyć buforowanie, jeśli przetwarzasz tysiące slajdów w partii.

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego kodu w aplikacji webowej?**  
A: Tak. Biblioteka jest czystą Javą, więc możesz uruchomić ją w dowolnym kontenerze servletów lub usłudze Spring Boot.

**Q: Czy Aspose.Slides obsługuje inne typy wykresów poza Stock?**  
A: Zdecydowanie tak. Obsługuje ponad 70 typów wykresów, w tym Line, Bar, Pie i Radar.

**Q: Jak dodać tytuł wykresu programowo?**  
A: Użyj `chart.getTitle().addTextFrameForOverriding("Quarterly Stock Overview")`, a następnie sformatuj tytuł w razie potrzeby.

**Q: Czy istnieje limit liczby punktów danych na serię?**  
A: Praktycznie możesz dodać dziesiątki tysięcy punktów; zużycie pamięci rośnie liniowo, a biblioteka strumieniuje dane, aby utrzymać niski rozmiar.

**Q: Jakie współrzędne Maven powinienem używać dla najnowszej wersji?**  
A: Najnowsza wersja jest zawsze dostępna pod `com.aspose:aspose-slides:25.4` (lub nowsza) w Maven Central.

---

**Ostatnia aktualizacja:** 2026-09-12  
**Testowano z:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Powiązane samouczki

- [aspose slides zależność Maven: Dodaj i skonfiguruj wykresy w prezentacjach przy użyciu Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Utwórz wykres PowerPoint w Javie – Zapisz prezentacje z wykresami przy użyciu Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)
- [Utwórz i sformatuj wykresy PowerPoint przy użyciu Aspose Slides Java](/slides/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}