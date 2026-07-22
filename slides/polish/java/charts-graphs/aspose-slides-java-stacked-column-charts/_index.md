---
date: '2026-07-22'
description: Poznaj Aspose Slides Maven Dependency, aby utworzyć skumulowany wykres
  słupkowy w Javie, dodać etykiety danych, zmienić format liczb na osi pionowej oraz
  wyeksportować wynik jako plik PPTX.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency umożliwia tworzenie skumulowanego wykresu
  słupkowego w Javie, dostosowywanie etykiet danych, regulację formatu osi pionowej
  oraz zapis jako PPTX - wszystko przy użyciu concise, production‑ready code.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Skumulowany wykres słupkowy w Javie'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Skumulowany wykres słupkowy w Javie'
url: /pl/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven Dependency: Wykres słupkowy skumulowany w Javie

## Wprowadzenie

Podnieś jakość swoich prezentacji, wprowadzając wnikliwe wizualizacje danych dzięki mocy **Aspose.Slides for Java**. W tym przewodniku **utworzysz wykres słupkowy skumulowany**, który będzie wyglądał profesjonalnie, niezależnie od tego, czy przygotowujesz raporty biznesowe, czy prezentujesz statystyki projektowe. Po zakończeniu tego samouczka będziesz w stanie:

- Skonfiguruj środowisko przy użyciu **Aspose Slides Maven dependency**
- Utwórz prezentację od podstaw
- **Dodaj wykres słupkowy skumulowany procentowo** i dostosuj jego wygląd
- **Formatuj etykiety danych wykresu** oraz **zmień format liczb na osi pionowej**
- **Zapisz prezentację jako PPTX** przy użyciu jednej linii kodu

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Dodaj zależność Maven/Gradle `aspose-slides` (zobacz „Aspose Slides Maven Dependency” poniżej).  
- **Który typ wykresu tworzy widok skumulowany?** Użyj `ChartType.PercentsStackedColumn` dla wykresu słupkowego skumulowanego procentowo.  
- **Jak mogę zmienić format liczb osi?** Wywołaj `IAxis.setNumberFormat()` i ustaw `setNumberFormatLinkedToSource(false)`.  
- **Czy mogę dostosować etykiety danych?** Tak – przeiteruj każdy `IChartDataPoint` i przypisz własny `ITextFrame`.  
- **Jak zapisać plik?** Wywołaj `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Czym jest wykres słupkowy skumulowany?
Wykres słupkowy skumulowany wizualizuje wiele serii danych ułożonych pionowo w każdej kolumnie kategorii, a wariant **procentowo‑skumulowany** normalizuje każdą kolumnę do 100 %, co ułatwia porównywanie proporcji. Ten format pozwala widzom szybko ocenić, jak każdy składnik przyczynia się do całości w różnych kategoriach, czyniąc trendy i względne rozmiary natychmiastowo czytelnymi.

## Dlaczego używać Aspose.Slides for Java?
Aspose.Slides for Java umożliwia generowanie, edytowanie i konwertowanie plików PowerPoint **bez potrzeby posiadania Microsoft Office** oraz obsługuje **ponad 50 formatów wyjściowych** na Windows, Linux i macOS. Biblioteka działa w pełni na JRE, co pozwala na automatyzację po stronie serwera i raportowanie o wysokiej przepustowości. Zapewnia także precyzyjną kontrolę nad obiektami wykresów, układami slajdów i właściwościami dokumentu, co czyni ją idealną do generowania prezentacji na poziomie przedsiębiorstwa.

## Wymagania wstępne
- **Java Development Kit (JDK):** 8 lub wyższy  
- **IDE:** IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Javą  
- **Narzędzie budowania:** Maven lub Gradle (opcjonalnie, ale zalecane)  
- **Podstawowa znajomość Javy** – powinieneś być zaznajomiony z klasami i metodami  

## Konfiguracja Aspose.Slides dla Javy
Aby rozpocząć, dodaj bibliotekę Aspose.Slides do swojego projektu.

### Aspose Slides Maven Dependency
Dodaj poniższy fragment do swojego `pom.xml` (to jest **aspose slides maven dependency**, której potrzebujesz):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternatywa Gradle
Jeśli wolisz Gradle, umieść tę linię w `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Alternatywnie, pobierz najnowszy plik JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
Możesz rozpocząć od bezpłatnej wersji próbnej, aby zapoznać się z funkcjami Aspose.Slides. Aby usunąć ograniczenia wersji ewaluacyjnej, rozważ uzyskanie licencji tymczasowej lub zakupionej.

- **Bezpłatna wersja próbna:** Dostęp do ograniczonych funkcji bez natychmiastowych kosztów.  
- **Licencja tymczasowa:** Zamów poprzez [stronę Aspose](https://purchase.aspose.com/temporary-license/).  
- **Zakup:** Odwiedź stronę zakupu, aby uzyskać pełny dostęp.

### Podstawowa inicjalizacja
`Presentation` jest podstawową klasą Aspose.Slides reprezentującą plik PowerPoint w pamięci. Poniższy minimalny fragment kodu pokazuje, jak utworzyć obiekt `Presentation`:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Przewodnik implementacji

### Tworzenie prezentacji i dodawanie slajdu
**Overview:**  
Najpierw utworzymy pustą prezentację i sprawdzimy, czy slajd istnieje.

#### Krok 1: Inicjalizacja obiektu Presentation
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Krok 2: Zapisz prezentację
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Dodawanie wykresu słupkowego skumulowanego procentowo do slajdu
**Overview:**  
Teraz umieścimy **wykres skumulowany procentowo** na pierwszym slajdzie.

`ChartType.PercentsStackedColumn` określa typ wykresu słupkowego skumulowanego procentowo.

#### Krok 1: Inicjalizacja i dostęp do slajdu
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Krok 2: Dodaj wykres do slajdu
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Dostosowywanie formatu liczb osi wykresu
**Overview:**  
Dla lepszej czytelności **zmienimy format osi pionowej**, aby wyświetlała procenty.

`IAxis` jest interfejsem reprezentującym oś wykresu, umożliwiającym dostosowanie formatu i skalowania.

#### Krok 1: Dodaj i uzyskaj dostęp do wykresu
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Krok 2: Ustaw własny format liczby
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Dodawanie serii i punktów danych do wykresu
**Overview:**  
Wypełnimy wykres przykładowymi seriami danych.

#### Krok 1: Inicjalizacja prezentacji i wykresu
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Krok 2: Dodaj serie danych
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatowanie koloru wypełnienia serii
**Overview:**  
Nadaj każdej serii odrębny kolor, aby wykres był łatwiejszy do odczytania.

#### Krok 1: Inicjalizacja i dostęp do wykresu
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Krok 2: Ustaw kolory wypełnienia
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatowanie etykiet danych
**Overview:**  
Teraz **sformatujemy etykiety danych wykresu**, aby wyświetlały własny tekst.

`IChartDataPoint` reprezentuje pojedynczy punkt danych w serii wykresu, a `ITextFrame` przechowuje tekst etykiety.

#### Krok 1: Dostęp do serii wykresu i punktów danych
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Krok 2: Dostosuj etykiety danych
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Typowe problemy i rozwiązania
- **Wykres jest pusty:** Upewnij się, że dodałeś co najmniej jedną serię danych i punkt danych przed zapisaniem.  
- **Liczby na osi nie wyświetlają procentów:** Pamiętaj, aby ustawić `verticalAxis.setNumberFormatLinkedToSource(false)`; w przeciwnym razie własny format zostanie zignorowany.  
- **Komunikat o wersji ewaluacyjnej licencji:** Zastosuj prawidłowy plik licencji przed utworzeniem obiektu `Presentation`, aby usunąć baner ewaluacji.

## Najczęściej zadawane pytania

**Q: Czy mogę używać tego kodu z Java 11 lub nowszą?**  
A: Tak. Biblioteka obsługuje JDK 8+; wystarczy użyć odpowiedniego klasyfikatora (np. `jdk16` dla JDK 16 lub nowszego).

**Q: Jak wyeksportować wykres jako obraz zamiast PPTX?**  
A: Użyj `chart.getImage().save("chart.png", ImageFormat.Png);` po dodaniu wykresu do slajdu.

**Q: Czy można dodać legendę do wykresu słupkowego skumulowanego?**  
A: Oczywiście. Wywołaj `chart.getChartTitle().addTextFrameForOverriding("My Chart");` i skonfiguruj `chart.getLegend()` według potrzeb.

**Q: Co zrobić, jeśli muszę zaktualizować dane po wygenerowaniu prezentacji?**  
A: Możesz zmodyfikować komórki `ChartDataWorkbook`, a następnie wywołać `chart.refresh();`, aby odzwierciedlić zmiany.

**Q: Czy Aspose.Slides działa na serwerach Linux?**  
A: Tak. Biblioteka jest czystą Javą i działa na każdym systemie operacyjnym z kompatybilnym JRE.

## Zakończenie
Postępując zgodnie z tym przewodnikiem, nauczyłeś się **tworzyć wykres słupkowy skumulowany** w Javie przy użyciu **Aspose Slides Maven dependency**, od konfiguracji środowiska po precyzyjne stylowanie wizualne. Eksperymentuj z różnymi zestawami danych, kolorami i formatami etykiet, aby Twoje raporty naprawdę się wyróżniały.

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak utworzyć wykres słupkowy grupowany w Javie z Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Jak ustawić formaty liczb w punktach danych wykresu przy użyciu Aspose.Slides for Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Jak dodać i skonfigurować wykresy w prezentacjach przy użyciu Aspose.Slides for Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}