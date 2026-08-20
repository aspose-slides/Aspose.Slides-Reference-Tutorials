---
date: '2026-07-27'
description: Jak dostosować wykres przy użyciu Aspose.Slides for Java. Dowiedz się,
  jak tworzyć wykresy w PowerPoint, stylizować serię punktową i efektywnie zapisywać
  prezentacje.
keywords:
- how to customize chart
- java create powerpoint chart
- Aspose.Slides scatter chart
lastmod: '2026-07-27'
og_description: Jak dostosować wykres za pomocą Aspose.Slides for Java. Ten przewodnik
  pokazuje, jak tworzyć wykresy w PowerPoint, stylizować punkty wykresu punktowego
  i eksportować prezentacje.
og_image_alt: 'Guide: Customize scatter chart in Java using Aspose.Slides'
og_title: 'Jak dostosować wykres: wykres punktowy Aspose w Javie'
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to customize chart using Aspose.Slides for Java. Learn to create
    PowerPoint chart, style scatter series, and save presentations efficiently.
  headline: 'How to Customize Chart: Scatter Chart Aspose in Java'
  type: TechArticle
- questions:
  - answer: Use `series.getMarker().getFillFormat().setFillColor(Color)` where `Color`
      is a `java.awt.Color` instance such as `Color.RED`.
    question: How do I change the color of the markers?
  - answer: Yes. Call `chart.getChartData().getSeries().add(...)` for each additional
      series and populate its points accordingly.
    question: Can I add more than two series to a scatter chart?
  - answer: Absolutely. After creating a series, invoke `series.getLegend().setText("Your
      Legend Text")` to override the default name.
    question: Is it possible to set a custom legend for each series?
  - answer: Call `chart.getImage().save("chart.png", ImageFormat.Png)` after configuring
      the chart. This produces a standalone PNG file.
    question: How can I export the chart as an image instead of a PPTX?
  - answer: Aspose.Slides supports animation effects. Use `chart.getTimeline().getMainSequence().addEffect(...)`
      to add entrance or emphasis animations to the chart or individual series.
    question: What if I need to animate the scatter points?
  type: FAQPage
tags:
- customize chart
- Aspose.Slides
- Java charting
title: 'Jak dostosować wykres: wykres punktowy Aspose w Javie'
url: /pl/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dostosuj wykres rozrzutu Aspose w Javie

W tym samouczku odkryjesz **jak dostosować wykres** — konkretnie wykres rozrzutu — używając potężnej biblioteki Aspose.Slides for Java. Przejdziemy przez konfigurację projektu, tworzenie wykresu rozrzutu, dostosowywanie typów serii i znaczników oraz ostateczne zapisywanie prezentacji. Po zakończeniu będziesz w stanie generować profesjonalnie wyglądające wykresy rozrzutu programowo i dopasować każdy szczegół wizualny do swojej marki lub potrzeb raportowych.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Slides for Java (v25.4+).  
- **Która wersja Javy jest obsługiwana?** JDK 8 lub wyższa.  
- **Czy mogę zmienić kształty znaczników?** Tak – użyj `MarkerStyleType`, aby wybrać gwiazdy, okręgi itp.  
- **Jak zapisać plik?** Wywołaj `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Czy wymagana jest licencja?** Darmowa wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji.

## Jak dostosować wykres w Javie przy użyciu Aspose.Slides?
`Presentation` jest klasą Aspose.Slides, która reprezentuje cały plik PowerPoint w pamięci. Załaduj nowy `Presentation`, dodaj wykres rozrzutu na pierwszym slajdzie, skonfiguruj serie i style znaczników, a następnie wywołaj `save`. Ten prosty przepływ tworzy w pełni stylizowany wykres w zaledwie kilku linijkach kodu Java, gotowy do wstawienia w dowolną prezentację PowerPoint.

## Co to jest „dostosowanie wykresu rozrzutu Aspose”?
Dostosowywanie wykresu rozrzutu przy użyciu Aspose oznacza programowe definiowanie danych wykresu, jego wyglądu i zachowania — wszystkiego od współrzędnych punktów po symbole znaczników — bez ręcznego otwierania PowerPointa. Takie podejście jest idealne do automatycznego raportowania, prezentacji opartych na danych lub wszelkich scenariuszy, w których potrzebne są powtarzalne, wysokiej jakości wizualizacje.

## Dlaczego dostosowywać wykresy rozrzutu przy użyciu Aspose.Slides?
Aspose.Slides zapewnia programistom pełną kontrolę programową nad wyglądem wykresu, umożliwiając automatyczne tworzenie wysokiej jakości wizualizacji, płynną integrację z pipeline'ami raportowania oraz możliwość dostosowania każdego elementu wizualnego bez ręcznego otwierania PowerPointa, co oszczędza czas i zapewnia spójność w całych prezentacjach.

- **Pełna kontrola** – modyfikuj typy serii, style znaczników, kolory i inne za pomocą kodu Java.  
- **Automatyzacja** – generuj dziesiątki wykresów w locie dla pulpitów nawigacyjnych lub raportów wsadowych.  
- **Cross‑platform** – działa na każdym systemie operacyjnym obsługującym Javę, bez wymogu instalacji Office.  
- **Wydajność** – lekki interfejs API, który przetwarza **150+ typów wykresów** i obsługuje prezentacje wielostronicowe bez ładowania całego pliku do pamięci.

## Wymagania wstępne

Aby podążać za instrukcją, upewnij się, że masz:

- **Aspose.Slides for Java** (v25.4 lub później).  
- **Java Development Kit (JDK)** 8 + zainstalowany.  
- Maven lub Gradle do zarządzania zależnościami (lub możesz pobrać JAR ręcznie).  
- Podstawową znajomość Javy i zaznajomienie się z wybranym narzędziem budowania.

## Konfiguracja Aspose.Slides dla Javy

Zintegruj bibliotekę z projektem, używając jednej z poniższych metod.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Lub pobierz najnowsze wydanie z [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Uzyskanie licencji
- **Free Trial** – 30‑dniowa wersja próbna.  
- **Temporary License** – wydłuczony okres testowy.  
- **Full License** – użycie produkcyjne z wsparciem premium.

## Przewodnik krok po kroku do dostosowania wykresu rozrzutu Aspose

### 1️⃣ Przygotuj folder na pliki prezentacji
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```  
*Dlaczego to ważne:* Upewnienie się, że folder wyjściowy istnieje, zapobiega `FileNotFoundException` przy późniejszym zapisywaniu pliku PPTX.

### 2️⃣ Utwórz nową prezentację i pobierz pierwszy slajd
`Presentation` reprezentuje dokument PowerPoint i zapewnia dostęp do slajdów oraz kształtów. Klasa `Presentation` reprezentuje cały plik PowerPoint w pamięci.  
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### 3️⃣ Dodaj wykres rozrzutu z wygładzonymi liniami
`ChartType.ScatterWithSmoothLines` tworzy wykres rozrzutu, w którym punkty są połączone wygładzonymi liniami.  
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### 4️⃣ Wyczyść domyślne serie i dodaj własne
`IChartSeries` reprezentuje serię danych w wykresie.  
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### 5️⃣ Wypełnij pierwszą serię punktami danych
`addDataPointForScatterSeries` dodaje pojedynczy punkt X‑Y do serii rozrzutu.  
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### 6️⃣ Dostosuj typ serii i wygląd znaczników
`Marker` kontroluje wizualny symbol używany dla każdego punktu danych w serii wykresu.  
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### 7️⃣ Zapisz prezentację
`save` zapisuje prezentację do pliku w określonym formacie.  
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Typowe przypadki użycia dostosowanych wykresów rozrzutu
- **Dashboardy finansowe** – wykreśl cenę akcji względem wolumenu.  
- **Badania naukowe** – wyświetl pomiary eksperymentalne z znacznikami błędów.  
- **Zarządzanie projektami** – porównaj planowany vs. rzeczywisty nakład pracy w zadaniach.

## Wskazówki dotyczące wydajności
- Wywołaj `pres.dispose()` po zapisaniu, aby zwolnić pamięć natywną.  
- Dla dużych zestawów danych najpierw wypełnij skoroszyt, a następnie powiąż serie, aby uniknąć wielokrotnych odświeżeń UI.  
- Ponownie używaj jednej instancji `IChartDataWorkbook` przy dodawaniu wielu serii, aby utrzymać niskie zużycie pamięci.

## Najczęściej zadawane pytania

**Q: Jak zmienić kolor znaczników?**  
A: Użyj `series.getMarker().getFillFormat().setFillColor(Color)`, gdzie `Color` jest instancją `java.awt.Color`, np. `Color.RED`.

**Q: Czy mogę dodać więcej niż dwie serie do wykresu rozrzutu?**  
A: Tak. Wywołaj `chart.getChartData().getSeries().add(...)` dla każdej dodatkowej serii i wypełnij jej punkty odpowiednio.

**Q: Czy można ustawić własną legendę dla każdej serii?**  
A: Oczywiście. Po utworzeniu serii wywołaj `series.getLegend().setText("Your Legend Text")`, aby nadpisać domyślną nazwę.

**Q: Jak wyeksportować wykres jako obraz zamiast PPTX?**  
A: Wywołaj `chart.getImage().save("chart.png", ImageFormat.Png)` po skonfigurowaniu wykresu. To utworzy samodzielny plik PNG.

**Q: Co zrobić, jeśli potrzebuję animować punkty rozrzutu?**  
A: Aspose.Slides obsługuje efekty animacji. Użyj `chart.getTimeline().getMainSequence().addEffect(...)`, aby dodać animacje wejścia lub podkreślenia do wykresu lub poszczególnych serii.

---

**Ostatnia aktualizacja:** 2026-07-27  
**Testowano z:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Tworzenie i dostosowywanie wykresów PowerPoint w Javie przy użyciu Aspose.Slides](/slides/java/charts-graphs/java-aspose-slides-powerpoint-charts-automation/)
- [Jak stworzyć wykres bąbelkowy w PowerPoint przy użyciu Aspose.Slides for Java (samouczek)](/slides/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/)
- [Tworzenie i dostosowywanie wykresów z liniami trendu w Aspose.Slides for Java](/slides/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}