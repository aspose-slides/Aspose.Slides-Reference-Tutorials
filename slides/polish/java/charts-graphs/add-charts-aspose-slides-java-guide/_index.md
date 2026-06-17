---
date: '2026-06-03'
description: Dowiedz się, jak dodać wykresy przy użyciu aspose slides maven dependency,
  skonfigurować etykiety danych i generować dynamiczne wykresy w prezentacjach Java.
keywords:
- aspose slides maven dependency
- how to add charts
- add data labels chart
- dynamic chart generation
- create presentation chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  headline: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  type: TechArticle
- description: Learn how to add charts with the aspose slides maven dependency, configure
    data labels, and generate dynamic charts in Java presentations.
  name: 'aspose slides maven dependency: Add and Configure Charts in Presentations
    Using Aspose.Slides for Java'
  steps:
  - name: Add the aspose slides maven dependency
    text: '**Maven:** xml <dependency> <groupId>com.aspose</groupId> <artifactId>aspose-slides</artifactId>
      <version>25.4</version> <classifier>jdk16</classifier> </dependency> **Gradle:**
      gradle implementation group: ''com.aspose'', name: ''aspose-slides'', version:
      ''25.4'', classifier: ''jdk16'' These snippets pull'
  - name: Load the presentation and insert a Bubble Chart
    text: '**Implementation:** java import com.aspose.slides.Presentation; /* The
      `Presentation` class represents a PowerPoint file and provides access to its
      slides and content. */ String dataDir = "YOUR_DOCUMENT_DIRECTORY"; Presentation
      pres = new Presentation(dataDir + "/chart2.pptx"); try { // Modification'
  - name: Configure the chart’s data series and labels
    text: '**Implementation:** java import com.aspose.slides.IChart; import com.aspose.slides.ISlide;
      import com.aspose.slides.Presentation; import com.aspose.slides.ChartType; /*
      `IChart` is the interface for chart objects, allowing manipulation of series,
      axes, and formatting. */ Presentation pres = new Pres'
  - name: Save the modified presentation
    text: '**Implementation:** java import com.aspose.slides.IChartDataWorkbook; import
      com.aspose.slides.IChartSeriesCollection; /* `IChartDataWorkbook` represents
      the internal workbook that stores chart data and cell references. */ IChartSeriesCollection
      series = chart.getChartData().getSeries(); series.get_'
  type: HowTo
- questions:
  - answer: Yes, the `ChartType` enumeration includes line, bar, pie, radar, stock,
      and more than 70 additional types.
    question: Can I add other chart types besides Bubble?
  - answer: Absolutely; it is fully compatible with OpenJDK 8‑21 and runs on all major
      operating systems.
    question: Does the aspose slides maven dependency work with OpenJDK?
  - answer: Load the Excel workbook with `WorkbookFactory.create(new FileInputStream("data.xlsx"))`,
      then bind the chart’s `ChartDataWorkbook` to the workbook before setting cell
      references.
    question: How do I embed a chart from an existing Excel file?
  - answer: Practically no—Aspose.Slides can handle dozens of charts per slide, limited
      only by available memory.
    question: Is there a limit to the number of charts per slide?
  - answer: PPTX, PPT, ODP, PDF, XPS, HTML, and even image formats such as PNG and
      JPEG are supported.
    question: What format can I export the final presentation to?
  type: FAQPage
title: 'aspose slides maven dependency: Dodaj i skonfiguruj wykresy w prezentacjach
  przy użyciu Aspose.Slides for Java'
url: /pl/java/charts-graphs/add-charts-aspose-slides-java-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# aspose slides maven dependency: Dodaj i skonfiguruj wykresy w prezentacjach przy użyciu Aspose.Slides for Java

## Wprowadzenie
**aspose slides maven dependency** umożliwia programistom Java programowe tworzenie, modyfikowanie i wzbogacanie plików PowerPoint bez konieczności otwierania samego PowerPointa. W wielu scenariuszach biznesowych i akademickich ręczne wstawianie wykresów jest czasochłonne i podatne na błędy. Ten samouczek pokazuje krok po kroku, jak dodać wykres bąbelkowy, powiązać etykiety danych z komórkami arkusza oraz zapisać wynik — wszystko przy użyciu aspose slides maven dependency w czysty, powtarzalny sposób.

**Co się nauczysz**
- Jak dodawać wykresy przy użyciu aspose slides maven dependency
- Konfigurowanie projektu Java przy użyciu Maven lub Gradle
- Ładowanie istniejącej prezentacji i wstawianie wykresu bąbelkowego
- Konfigurowanie etykiet danych przy użyciu odwołań do komórek (dodaj wykres etykiet danych)
- Zapisywanie zaktualizowanego pliku do późniejszej dystrybucji
- Praktyczne przypadki użycia, takie jak dynamiczne generowanie wykresów i tworzenie przepływów pracy wykresów w prezentacjach

## Szybkie odpowiedzi
- **Który artefakt Maven dodaje możliwości wykresów?** `com.aspose:aspose-slides:25.4` (lub najnowszy)  
- **Czy mogę powiązać etykiety danych z komórkami w stylu Excel?** Tak – użyj `ChartDataLabel` z `setDataLabelFormat` i odwołaniami do komórek.  
- **Czy licencja jest wymagana w produkcji?** Pełna licencja usuwa znak wodny wersji próbnej i odblokowuje wszystkie funkcje.  
- **Czy to będzie działać na Java 11+?** Absolutnie; biblioteka jest kompatybilna z Java 8 do Java 21.  
- **Ile typów wykresów jest obsługiwanych?** Ponad 70 różnych typów wykresów, w tym wykresy bąbelkowe, radarowe i giełdowe.

## Czym jest aspose slides maven dependency?
**aspose slides maven dependency** to pakiet kompatybilny z Maven, który udostępnia w pełni funkcjonalne API do tworzenia i edytowania plików PowerPoint (PPTX, PPT, ODP) w Javie. Dodając tę zależność do swojego `pom.xml` lub `build.gradle`, zyskujesz dostęp do ponad 70 typów wykresów, ponad 150 układów slajdów oraz możliwość manipulacji kształtami, animacjami i metadanymi bez zainstalowanego Office.

## Dlaczego warto używać aspose slides maven dependency do automatyzacji wykresów?
Aspose.Slides przetwarza zestawy tysięcy slajdów w mniej niż sekundę na standardowym sprzęcie serwerowym, obsługuje **ponad 70 typów wykresów** i może renderować prezentacje do **10 000 slajdów** bez ładowania całego pliku do pamięci. Te wymierne możliwości czynią go idealnym rozwiązaniem do generowania dynamicznych wykresów w skali przedsiębiorstwa, gdzie wydajność i skalowalność są nie do negocjacji.

## Wymagania wstępne
- **Java Development Kit (JDK)** 8 lub nowszy (zalecany Java 11+).  
- **Maven** 3.6+ **lub** **Gradle** 6+.  
- **Biblioteka Aspose.Slides for Java** (aspose slides maven dependency, wersja 25.4 lub późniejsza).  
- Podstawowa znajomość kolekcji Java i operacji I/O na plikach.  
- Plik licencji ewaluacyjnej lub pełnej (`license.json`), jeśli planujesz uruchamiać kod po okresie próbnym.

## Jak dodać wykres do slajdu przy użyciu Aspose.Slides?
Załaduj docelową prezentację, utwórz nowy kształt wykresu na wybranym slajdzie i określ typ wykresu (bąbelkowy w tym przykładzie). Cała operacja może być wykonana w **trzech zwięzłych linijkach kodu** po odwołaniu do biblioteki, co czyni ją idealną do szybkiego prototypowania i produkcyjnych pipeline'ów.

### Krok 1: Dodaj aspose slides maven dependency
**Maven:**  
```text
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
```  
**Gradle:**  
```text
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
```  
Te fragmenty pobierają pełne API Aspose.Slides — w tym obsługę wykresów — bezpośrednio z Maven Central.

### Krok 2: Załaduj prezentację i wstaw wykres bąbelkowy
**Implementation:**  
```text
```java
import com.aspose.slides.Presentation;

/* The `Presentation` class represents a PowerPoint file and provides access to its slides and content. */
String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/chart2.pptx");
try {
    // Modifications will be done here
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Krok 3: Skonfiguruj serię danych wykresu i etykiety
**Implementation:**  
```text
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

/* `IChart` is the interface for chart objects, allowing manipulation of series, axes, and formatting. */
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(
        ChartType.Bubble, 50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```
```  

### Krok 4: Zapisz zmodyfikowaną prezentację
**Implementation:**  
```text
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeriesCollection;

/* `IChartDataWorkbook` represents the internal workbook that stores chart data and cell references. */
IChartSeriesCollection series = chart.getChartData().getSeries();
series.get_Item(0).getLabels()
    .getDefaultDataLabelFormat()
    .setShowLabelValueFromCell(true);

String lbl0 = "Label 0 cell value";
String lbl1 = "Label 1 cell value";
String lbl2 = "Label 2 cell value";
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
series.get_Item(0).getLabels()
    .get_Item(0).setValueFromCell(wb.getCell(0, "A10", lbl0));
series.get_Item(0).getLabels()
    .get_Item(1).setValueFromCell(wb.getCell(0, "A11", lbl1));
series.get_Item(0).getLabels()
    .get_Item(2).setValueFromCell(wb.getCell(0, "A12", lbl2));
```
```  

## Jak skonfigurować etykiety danych przy użyciu odwołań do komórek?
Etykiety danych mogą być powiązane z zewnętrznymi wartościami komórek, odzwierciedlając funkcję Excel „Link to Cell”. Takie podejście eliminuje sztywno zakodowane wartości i umożliwia **dynamiczne generowanie wykresów**, gdzie zawartość etykiet aktualizuje się automatycznie wraz ze zmianą danych źródłowych. Łącząc każdą etykietę z konkretną komórką skoroszytu, zapewniasz, że każda modyfikacja danych źródłowych jest natychmiast odzwierciedlana w prezentacji, co zmniejsza nakład pracy konserwacyjnej i minimalizuje ryzyko przestarzałych informacji.

### Bezpośrednia odpowiedź
Wywołaj `chart.getSeries().get_Item(0).getDataPoints().get_Item(i).getLabel().setDataLabelFormat(...)` i przekaż `DataLabelFormat`, który odwołuje się do adresu komórki, np. `"Sheet1!A2"`. Aspose.Slides rozwiązuje odwołanie w czasie wykonywania, wstawiając bieżącą wartość komórki do etykiety wykresu.

### Krok po kroku
1. Zidentyfikuj serię, którą chcesz oznaczyć.  
2. Pobierz obiekt `IDataLabel` dla każdego punktu danych.  
3. Użyj `setDataLabelFormat` z `DataLabelFormat` skonfigurowanym dla `CellReference`.  
4. Opcjonalnie dostosuj czcionkę, kolor i opcje wyświetlania.

## Jak zapisać zmodyfikowaną prezentację?
Zapisywanie to jednoczyńska metoda, która zapisuje obiekt `Presentation` w pamięci do ścieżki pliku lub strumienia wyjściowego. Możesz także wybrać format wyjściowy (PPTX, PDF, ODP), przekazując odpowiedni enum `SaveFormat`. Operacja ta przesyła wynik bezpośrednio na dysk, automatycznie zwalniając wszystkie natywne zasoby po zamknięciu lub wyjściu poza zakres instancji `Presentation`, co pomaga utrzymać niskie zużycie pamięci nawet przy dużych zestawach slajdów.

### Bezpośrednia odpowiedź
Wywołaj `presentation.save("output.pptx", SaveFormat.Pptx)`; biblioteka przesyła wynik bezpośrednio na dysk, automatycznie zwalniając wszystkie natywne zasoby po zamknięciu lub wyjściu poza zakres instancji `Presentation`.

## Praktyczne zastosowania
1. **Raporty biznesowe:** Automatyczne generowanie wykresów sprzedaży kwartalnej z zrzutu bazy danych.  
2. **Wykłady akademickie:** Pobieranie aktualnych danych badawczych do slajdów wykładowych na każdą sesję.  
3. **Prezentacje sprzedażowe:** Tworzenie na bieżąco pulpitów wydajności specyficznych dla klienta.  
4. **Zarządzanie projektami:** Wizualizacja harmonogramów w stylu Gantta z dynamicznymi etykietami danych.  
5. **Analiza marketingowa:** Osadzanie KPI kampanii w prezentacjach, które aktualizują się wraz z pojawianiem się nowych metryk.

## Rozważania dotyczące wydajności
- **Zarządzanie pamięcią:** Używaj try‑with‑resources lub jawnego `presentation.dispose()`, aby szybko zwolnić natywną pamięć.  
- **Duże zestawy danych:** Przy obsłudze ponad 10 000 punktów danych, wypełniaj dane wykresu za pomocą `ChartDataWorkbook`, aby uniknąć ładowania całego zestawu danych do obiektów Java.  
- **Bezpieczeństwo wątków:** Każdy wątek powinien pracować z własną instancją `Presentation`; API nie jest bezpieczne wątkowo przy współdzielonych obiektach.  

## Typowe problemy i rozwiązania
- **Problem:** „Nie znaleziono pliku licencji.”  
  **Rozwiązanie:** Umieść `license.json` w classpath i wywołaj `License license = new License(); license.setLicense("license.json");` przed użyciem jakiejkolwiek API.  

- **Problem:** Wykres jest pusty po zapisaniu.  
  **Rozwiązanie:** Upewnij się, że skoroszyt danych wykresu jest zapisany razem z prezentacją (`presentation.getCharts().setDataWorkbook(chartWorkbook);`).  

- **Problem:** Etykiety danych wyświetlają błędy „#REF!”.  
  **Rozwiązanie:** Sprawdź, czy ciąg odwołania do komórki dokładnie odpowiada nazwie arkusza i adresowi oraz czy odwołany skoroszyt jest podłączony do wykresu.  

## Najczęściej zadawane pytania
**P:** Czy mogę dodać inne typy wykresów oprócz bąbelkowego?  
**O:** Tak, wyliczenie `ChartType` zawiera wykresy liniowe, słupkowe, kołowe, radarowe, giełdowe i ponad 70 dodatkowych typów.  

**P:** Czy aspose slides maven dependency działa z OpenJDK?  
**O:** Absolutnie; jest w pełni kompatybilny z OpenJDK 8‑21 i działa na wszystkich głównych systemach operacyjnych.  

**P:** Jak osadzić wykres z istniejącego pliku Excel?  
**O:** Załaduj skoroszyt Excel przy użyciu `WorkbookFactory.create(new FileInputStream("data.xlsx"))`, a następnie powiąż `ChartDataWorkbook` wykresu ze skoroszytem przed ustawieniem odwołań do komórek.  

**P:** Czy istnieje limit liczby wykresów na slajdzie?  
**O:** Praktycznie nie — Aspose.Slides może obsłużyć dziesiątki wykresów na slajdzie, ograniczone jedynie dostępna pamięcią.  

**P:** Do jakich formatów mogę wyeksportować ostateczną prezentację?  
**O:** Obsługiwane są formaty PPTX, PPT, ODP, PDF, XPS, HTML oraz formaty graficzne takie jak PNG i JPEG.  

## Zasoby
- [Wydania Aspose.Slides dla Java](https://releases.aspose.com/slides/java/) – download the latest library binaries.  
- [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/) – comprehensive API reference and guides.  
- [Pobierz Aspose.Slides dla Java](https://releases.aspose.com/slides/java/) – direct download page for the Maven/Gradle packages.  
- [Kup licencję](https://purchase.aspose.com/buy) – obtain a full commercial license.  
- [Bezpłatna wersja próbna](https://releases.aspose.com/slides/java/) – start with a trial to evaluate features.  
- [Licencja tymczasowa](https://purchase.aspose.com/temporary-license/) – request a temporary key for extended evaluation.  
- [Forum wsparcia Aspose](https://forum.aspose.com/c/slides/11) – get help from the community and Aspose engineers.  

## Podsumowanie
Masz teraz kompletny, kompleksowy przewodnik dotyczący używania **aspose slides maven dependency** do dodawania, konfigurowania i zapisywania wykresów w prezentacjach Java. Postępując zgodnie z powyższymi krokami, możesz automatyzować tworzenie wykresów, powiązać etykiety danych z bieżącymi wartościami komórek i generować profesjonalne zestawy slajdów w dużej skali. Eksperymentuj z innymi typami wykresów, odkrywaj API animacji i integruj ten przepływ pracy z pipeline'ami raportowymi, aby uzyskać maksymalny efekt.

---  
**Ostatnia aktualizacja:** 2026-06-03  
**Testowano z:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

```java
import com.aspose.slides.SaveFormat;

String outputDir = "YOUR_OUTPUT_DIRECTORY";
pres.save(outputDir + "/resultchart.pptx", SaveFormat.Pptx);
```

## Powiązane samouczki

- [Jak tworzyć i konfigurować prezentacje przy użyciu Aspose.Slides Java: Przewodnik krok po kroku](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)
- [Tworzenie PPTX w Javie z Aspose.Slides Maven – Przewodnik automatyzacji](/slides/java/batch-processing/aspose-slides-java-automate-presentation-management/)
- [Jak tworzyć wykresy w Javie z Aspose.Slides: Kompletny przewodnik](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}