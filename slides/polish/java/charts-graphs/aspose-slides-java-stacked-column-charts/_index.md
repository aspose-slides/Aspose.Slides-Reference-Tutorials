---
date: '2026-02-22'
description: Dowiedz się, jak stworzyć wykres słupkowy skumulowany w Javie przy użyciu
  Aspose.Slides. Ten samouczek obejmuje zależność Maven Aspose Slides, dodawanie wykresu
  skumulowanego procentowo, formatowanie etykiet danych wykresu oraz zapisywanie prezentacji
  jako PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Jak stworzyć wykres słupkowy skumulowany w Javie z Aspose.Slides – Kompletny
  przewodnik
url: /pl/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

.

We must keep code block placeholders unchanged.

Also bullet lists.

Translate sentences.

Let's produce final content.

Be careful with bullet list items that contain code snippets like `aspose-slides` etc. Keep code unchanged.

Also translate "Quick Answers" etc.

Let's start.

Will produce final markdown.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak stworzyć wykres słupkowy skumulowany w Javie z Aspose.Slides – Kompletny przewodnik

## Wstęp

Podnieś jakość swoich prezentacji, wprowadzając wnikliwe wizualizacje danych dzięki mocy Aspose.Slides dla Javy. W tym przewodniku **stworzysz wykres słupkowy skumulowany** w slajdach, które będą wyglądały profesjonalnie, niezależnie od tego, czy przygotowujesz raporty biznesowe, czy prezentujesz statystyki projektowe. Po zakończeniu tego tutorialu będziesz w stanie:

- Skonfigurować środowisko z zależnością Maven Aspose Slides
- Utworzyć prezentację od podstaw
- **Dodać wykres skumulowany procentowo** i dostosować jego wygląd
- **Sformatować etykiety danych wykresu** oraz **zmienić format pionowej osi**
- **Zapisać prezentację jako PPTX** jedną linią kodu

Przejdźmy krok po kroku, abyś od razu mógł tworzyć atrakcyjne prezentacje.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Zależność Maven/Gradle `aspose-slides` (zobacz „aspose slides maven dependency” poniżej)  
- **Jakiego typu wykres jest używany?** `ChartType.PercentsStackedColumn` dla wykresu słupkowego skumulowanego procentowo  
- **Jak zmienić format liczbowy osi?** Użyj `IAxis.setNumberFormat()` i wyłącz powiązanie z źródłem  
- **Czy mogę dostosować etykiety danych?** Tak – iteruj po obiektach `IChartDataPoint` i ustaw własny `ITextFrame`  
- **Jak zapisać plik?** Wywołaj `presentation.save("output.pptx", SaveFormat.Pptx)`

## Co to jest wykres słupkowy skumulowany?
Wykres słupkowy skumulowany wizualizuje wiele serii danych ułożonych jedna na drugiej w pionowych słupkach. Gdy używasz wariantu **skumulowanego procentowo**, każdy słupek zawsze sumuje się do 100 %, co ułatwia porównywanie proporcjonalnych wkładów w różnych kategoriach.

## Dlaczego warto używać Aspose.Slides dla Javy?
Aspose.Slides udostępnia czysto‑Java API, które działa na każdej platformie bez konieczności instalacji Microsoft Office. Oferuje precyzyjną kontrolę nad obiektami wykresów, obsługuje szeroką gamę formatów i pozwala generować prezentacje programowo — idealne do automatyzacji raportowania lub generowania dokumentów po stronie serwera.

## Wymagania wstępne
- **Java Development Kit (JDK):** 8 lub wyższy  
- **IDE:** IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Javą  
- **Narzędzie budowania:** Maven lub Gradle (opcjonalnie, ale zalecane)  
- **Podstawowa znajomość Javy** – powinieneś czuć się komfortowo z klasami i metodami  

## Konfiguracja Aspose.Slides dla Javy
Aby rozpocząć, dodaj bibliotekę Aspose.Slides do swojego projektu.

### Aspose Slides Maven Dependency
Dodaj poniższy fragment do pliku `pom.xml` (to jest **aspose slides maven dependency**, której potrzebujesz):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Alternatywa Gradle
Jeśli wolisz Gradle, umieść tę linię w pliku `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Alternatywnie pobierz najnowszy JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
Możesz rozpocząć od wersji próbnej, aby zapoznać się z funkcjami Aspose.Slides. Aby usunąć ograniczenia wersji ewaluacyjnej, rozważ uzyskanie tymczasowej lub zakupionej licencji.

- **Wersja próbna:** Dostęp do ograniczonych funkcji bez natychmiastowych kosztów.  
- **Licencja tymczasowa:** Zamów poprzez [stronę Aspose](https://purchase.aspose.com/temporary-license/).  
- **Zakup:** Odwiedź stronę zakupu, aby uzyskać pełny dostęp.

### Podstawowa inicjalizacja
Oto minimalny fragment kodu pokazujący, jak utworzyć obiekt `Presentation`:

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
**Przegląd:**  
Najpierw utworzymy pustą prezentację i sprawdzimy, czy slajd został utworzony.

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

#### Krok 2: Zapis prezentacji
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Dodawanie wykresu słupkowego skumulowanego procentowo do slajdu
**Przegląd:**  
Teraz umieścimy **wykres skumulowany procentowo** na pierwszym slajdzie.

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

#### Krok 2: Dodanie wykresu do slajdu
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Dostosowanie formatu liczbowego osi wykresu
**Przegląd:**  
Aby zwiększyć czytelność, **zmienimy format pionowej osi** na wyświetlanie procentów.

#### Krok 1: Dodanie i dostęp do wykresu
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

#### Krok 2: Ustawienie własnego formatu liczbowego
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Dodawanie serii i punktów danych do wykresu
**Przegląd:**  
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

#### Krok 2: Dodanie serii danych
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatowanie koloru wypełnienia serii
**Przegląd:**  
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

#### Krok 2: Ustawienie kolorów wypełnienia
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatowanie etykiet danych
**Przegląd:**  
Teraz **sformatujemy etykiety danych wykresu**, aby wyświetlały własny tekst.

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

#### Krok 2: Dostosowanie etykiet danych
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
- **Wykres jest pusty:** Upewnij się, że dodałeś przynajmniej jedną serię danych i punkt danych przed zapisem.  
- **Liczby na osi nie wyświetlają procentów:** Pamiętaj, aby ustawić `verticalAxis.setNumberFormatLinkedToSource(false)`; w przeciwnym razie własny format zostanie zignorowany.  
- **Komunikat o wersji ewaluacyjnej licencji:** Zastosuj prawidłowy plik licencji przed utworzeniem obiektu `Presentation`, aby usunąć baner ewaluacji.

## Najczęściej zadawane pytania

**P: Czy mogę używać tego kodu z Javą 11 lub nowszą?**  
O: Tak. Biblioteka obsługuje JDK 8+, wystarczy użyć odpowiedniego klasyfikatora (np. `jdk16` dla JDK 16 i wyżej).

**P: Jak wyeksportować wykres jako obraz zamiast PPTX?**  
O: Użyj `chart.getImage().save("chart.png", ImageFormat.Png);` po dodaniu wykresu do slajdu.

**P: Czy można dodać legendę do wykresu słupkowego skumulowanego?**  
O: Oczywiście. Wywołaj `chart.getChartTitle().addTextFrameForOverriding("My Chart");` i skonfiguruj `chart.getLegend()` według potrzeb.

**P: Co zrobić, jeśli muszę zaktualizować dane po wygenerowaniu prezentacji?**  
O: Możesz zmodyfikować komórki `ChartDataWorkbook`, a następnie wywołać `chart.refresh();`, aby odzwierciedlić zmiany.

**P: Czy Aspose.Slides działa na serwerach Linux?**  
O: Tak. Biblioteka jest czystą Javą i działa na każdym systemie operacyjnym z kompatybilnym JRE.

## Zakończenie
Korzystając z tego przewodnika, nauczyłeś się **tworzyć wykresy słupkowe skumulowane** w prezentacjach przy użyciu Aspose.Slides dla Javy – od konfiguracji środowiska po precyzyjne stylowanie wizualne. Eksperymentuj z różnymi zestawami danych, kolorami i formatami etykiet, aby Twoje raporty naprawdę się wyróżniały.

---

**Ostatnia aktualizacja:** 2026-02-22  
**Testowano z:** Aspose.Slides 25.4 (klasyfikator jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}