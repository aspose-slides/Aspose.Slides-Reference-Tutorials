---
date: '2026-03-20'
description: Dowiedz się, jak dodać wykres do prezentacji w Javie przy użyciu Aspose.Slides
  i szybko generować pliki wykresów w prezentacji.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Jak dodać wykres do prezentacji Java przy użyciu Aspose.Slides
url: /pl/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak dodać wykres do prezentacji przy użyciu Aspose.Slides for Java

## Wprowadzenie

Tworzenie dynamicznych prezentacji, które skutecznie przekazują dane, jest niezbędne w dzisiejszym szybkim środowisku biznesowym. Niezależnie od tego, czy przygotowujesz raport finansowy, prezentację marketingową, czy aktualizację statusu projektu, **znajomość sposobu dodawania wykresu** do slajdów może znacząco zwiększyć zaangażowanie odbiorców. W tym samouczku nauczysz się krok po kroku, jak dodać trójwymiarowy wykres słupkowy skumulowany, skonfigurować jego dane i zapisać ostateczny plik — wszystko przy użyciu Aspose.Slides for Java.

### Szybkie odpowiedzi
- **Jaka jest podstawowa biblioteka?** Aspose.Slides for Java  
- **Jaki typ wykresu jest demonstrowany?** 3D Stacked Column  
- **Czy mogę programowo generować pliki wykresów w prezentacji?** Tak, przy użyciu metod API pokazanych poniżej  
- **Jaką wersję Javy zaleca się?** JDK 16 lub nowszą  
- **Czy potrzebna jest licencja do produkcji?** Ważna licencja Aspose.Slides jest wymagana do użytku komercyjnego  

## Co to jest „jak dodać wykres” w Aspose.Slides?

Aspose.Slides for Java udostępnia bogaty zestaw obiektów, które pozwalają tworzyć, edytować i eksportować pliki PowerPoint bez Microsoft Office. Dodanie wykresu jest tak proste, jak stworzenie obiektu `Presentation`, wstawienie kształtu wykresu i przekazanie danych poprzez wbudowany skoroszyt.

## Dlaczego dodawać wykres do prezentacji Java?

- **Wizualny wpływ:** Wykresy zamieniają surowe liczby w natychmiast zrozumiałe wizualizacje.  
- **Automatyzacja:** Generuj raporty w locie — idealne do zaplanowanych podsumowań e‑mailowych lub pulpitów nawigacyjnych.  
- **Spójność:** Używaj tego samego stylu i identyfikacji wizualnej we wszystkich generowanych prezentacjach.  
- **Przenośność:** Eksportuj do PPTX, PDF lub obrazów jednym wywołaniem metody.  

## Wymagania wstępne

- **Biblioteki i zależności:** Aspose.Slides for Java musi być zainstalowane.  
- **Konfiguracja środowiska:** Pracuj w środowisku Java (zalecany JDK 16 lub nowszy).  
- **Podstawa wiedzy:** Znajomość podstawowych koncepcji programowania w Javie będzie pomocna.  

## Konfiguracja Aspose.Slides dla Java

### Instalacja

Aby zintegrować Aspose.Slides z projektem, postępuj zgodnie z jedną z poniższych opcji.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**: Alternatywnie, pobierz najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
- **Free Trial:** Rozpocznij od bezpłatnej wersji próbnej, aby przetestować funkcje.  
- **Temporary License:** Uzyskaj tymczasową licencję do rozszerzonego testowania.  
- **Purchase:** Nabyj pełną licencję do użytku komercyjnego.  

Po instalacji możesz utworzyć instancję klasy `Presentation`, która jest punktem wejścia dla wszystkich operacji związanych z wykresami.

## Przewodnik implementacji

### Jak dodać wykres do prezentacji z trójwymiarowym wykresem słupkowym skumulowanym

#### Overview
Tworzenie prezentacji od podstaw jest proste przy użyciu Aspose.Slides. W tej sekcji dodamy trójwymiarowy wykres słupkowy skumulowany do pierwszego slajdu naszej prezentacji.

**Steps:**

1. **Initialize Presentation Object**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Explain Parameters**  
   - `ChartType.StackedColumn3D`: Określa typ wykresu.  
   - Pozycja i rozmiar `(0, 0, 500, 500)`: Określa, gdzie wykres pojawia się na slajdzie.

### Konfiguracja danych wykresu

#### Overview
Aby wykres był sensowny, skonfiguruj jego serie danych i kategorie. Ta sekcja pokazuje, jak dodać konkretne punkty danych do wykresu.

**Steps:**

1. **Access Chart's Data Workbook**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Ustaw właściwości Rotation3D dla wykresu

#### Overview
Zwiększ atrakcyjność wizualną wykresu dzięki właściwościom rotacji 3D. Ta personalizacja pozwala dostosować perspektywę i głębokość.

**Steps:**

1. **Configure 3D Rotations**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Explain Parameters**  
   - `setRightAngleAxes(true)`: Zapewnia, że osie są prostopadłe.  
   - Wartości rotacji: Dostosowują kąt i głębokość widoku 3D.

### Wypełnij dane serii w wykresie

#### Overview
Wypełnienie wykresu punktami danych jest kluczowe dla analizy. Tutaj dodamy konkretne wartości do serii w naszym wykresie.

**Steps:**

1. **Add Data Points**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Dostosuj nakładanie się serii w wykresie

#### Overview
Drobne dopasowanie wyglądu wykresu może poprawić czytelność. Ta sekcja opisuje, jak dostosować właściwość nakładania się serii dla lepszej wizualizacji danych.

**Steps:**

1. **Set Series Overlap**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Zapisz prezentację

#### Overview
Po skonfigurowaniu prezentacji zapisz ją na dysku w żądanym formacie. Ten krok zapewnia zachowanie wszystkich zmian.

**Steps:**

1. **Save the Presentation**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|----------|
| **Wykres wygląda płasko** | Rotacja 3D nie jest ustawiona | Wywołaj `setRotation3D` z odpowiednimi wartościami X/Y. |
| **Dane nie wyświetlają się** | Komórki skoroszytu nie są połączone | Upewnij się, że `fact.getCell` odwołuje się do prawidłowych indeksów wiersza/kolumny. |
| **Plik nie został zapisany** | Nieprawidłowa ścieżka lub brak uprawnień | Sprawdź, czy `outputFilePath` jest zapisywalny i folder istnieje. |

## Najczęściej zadawane pytania

**Q: Czy mogę generować pliki wykresów w prezentacji w formatach innych niż PPTX?**  
A: Tak, Aspose.Slides obsługuje formaty PDF, ODP i obrazy poprzez enum `SaveFormat`.

**Q: Czy potrzebuję licencji do uruchamiania kodu w środowisku deweloperskim?**  
A: Tymczasowa lub ewaluacyjna licencja działa w środowisku deweloperskim, ale pełna licencja jest wymagana przy wdrożeniach produkcyjnych.

**Q: Czy można dodać wiele wykresów do tego samego slajdu?**  
A: Oczywiście. Wywołaj `slide.getShapes().addChart` wielokrotnie z różnymi pozycjami lub rozmiarami.

**Q: Jak zmienić paletę kolorów wykresu?**  
A: Użyj `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` i ustaw `SolidFillColor`.

**Q: Czy mogę podłączyć wykres do zewnętrznego źródła danych, takiego jak baza danych?**  
A: Tak. Pobierz dane przy użyciu JDBC, a następnie programowo wypełnij komórki skoroszytu przed zapisem.

## Podsumowanie

Teraz nauczyłeś się **jak dodać wykres** do prezentacji Java, skonfigurować jego dane, dostosować rotację 3D, regulować nakładanie się serii i zapisać ostateczny plik. Ta wiedza pozwala automatyzować generowanie raportów, tworzyć spójną identyfikację wizualną i dostarczać prezentacje oparte na danych bez ręcznej pracy. Aby uzyskać głębsze możliwości dostosowywania — takie jak stylizowanie legend, osi czy stosowanie motywów — zapoznaj się z pełnymi możliwościami w oficjalnej dokumentacji.

Aby uzyskać więcej zaawansowanych funkcji i opcji dostosowywania, odwołaj się do [dokumentacji Aspose.Slides for Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-03-20  
**Testowano z:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose