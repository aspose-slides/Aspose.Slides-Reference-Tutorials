---
"date": "2025-04-17"
"description": "Naucz się tworzyć profesjonalne prezentacje za pomocą Aspose.Slides for Java. Ten przewodnik obejmuje konfigurację środowiska, dodawanie wykresów kolumnowych i dostosowywanie ich w celu uzyskania przejrzystości."
"title": "Opanuj wykresy kolumnowe w Javie z Aspose.Slides&#58; Kompleksowy przewodnik"
"url": "/pl/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Poznaj wykresy kolumnowe w Javie z Aspose.Slides: kompleksowy przewodnik

## Wstęp

Podnieś poziom swoich prezentacji, włączając wnikliwe wizualizacje danych z mocą Aspose.Slides dla Java. Tworzenie profesjonalnie wyglądających slajdów z wykresami kolumnowymi jest proste, niezależnie od tego, czy przygotowujesz raporty biznesowe, czy prezentujesz statystyki projektu.

W tym samouczku pokażemy, jak używać Aspose.Slides for Java do tworzenia dynamicznych prezentacji i dodawania atrakcyjnych wizualnie wykresów kolumnowych. Do końca tego przewodnika będziesz wyposażony w umiejętności potrzebne do:
- Skonfiguruj swoje środowisko do korzystania z Aspose.Slides
- Utwórz prezentację od podstaw
- Dodawaj i dostosowuj wykresy kolumnowe z procentowym ułożeniem
- Formatuj osie wykresu i etykiety danych, aby zapewnić przejrzystość

Przyjrzyjmy się bliżej tworzeniu prezentacji, które zachwycą Twoją publiczność.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
- **Zestaw narzędzi programistycznych Java (JDK):** Wersja 8 lub nowsza.
- **Środowisko programistyczne:** Dowolne zintegrowane środowisko programistyczne, takie jak IntelliJ IDEA lub Eclipse.
- **Maven/Gradle:** Do zarządzania zależnościami (opcjonalne, ale zalecane).
- **Podstawowa wiedza o Javie:** Znajomość koncepcji programowania w języku Java.

## Konfigurowanie Aspose.Slides dla Java
Aby rozpocząć, musisz uwzględnić bibliotekę Aspose.Slides w swoim projekcie. Oto jak to zrobić:

**Maven:**
Dodaj tę zależność do swojego `pom.xml` plik:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Stopień:**
Uwzględnij to w swoim `build.gradle` plik:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Bezpośrednie pobieranie:**
Alternatywnie, pobierz najnowszy plik JAR z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

### Nabycie licencji
Możesz zacząć od bezpłatnej wersji próbnej, aby poznać funkcje Aspose.Slides. Aby usunąć ograniczenia ewaluacyjne, rozważ uzyskanie tymczasowej lub zakupionej licencji.
- **Bezpłatna wersja próbna:** Uzyskaj dostęp do ograniczonych funkcji bez natychmiastowych kosztów.
- **Licencja tymczasowa:** Zapytaj przez [Strona Aspose'a](https://purchase.aspose.com/temporary-license/).
- **Zakup:** Aby uzyskać pełny dostęp, odwiedź stronę zakupu.

### Podstawowa inicjalizacja
Oto jak zainicjować Aspose.Slides w aplikacji Java:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Utwórz instancję klasy Presentation
        Presentation presentation = new Presentation();
        
        // Wykonaj operacje na obiekcie prezentacji
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Przewodnik wdrażania

### Tworzenie prezentacji i dodawanie slajdu
**Przegląd:**
Zacznij od stworzenia prostej prezentacji ze slajdem początkowym. To podstawa do dalszych udoskonaleń.

#### Krok 1: Zainicjuj obiekt prezentacji
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Utwórz nową instancję prezentacji
        Presentation presentation = new Presentation();
        
        // Odniesienie do pierwszego slajdu (utworzone automatycznie)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Krok 2: Zapisz prezentację
```java
// Zapisz prezentację do pliku
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Dodawanie wykresu kolumnowego procentowego do slajdu
**Przegląd:**
Ulepsz swój slajd, dodając wykres kolumnowy z procentowymi wartościami, który umożliwi łatwe porównywanie danych.

#### Krok 1: Zainicjuj i uzyskaj dostęp do slajdu
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Przejdź do dodania wykresu w następnym kroku
    }
}
```

#### Krok 2: Dodaj wykres do slajdu
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Dostosowywanie formatu numerów osi wykresu
**Przegląd:**
Dostosuj format liczb na osi pionowej wykresu, aby zwiększyć jego czytelność.

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

#### Krok 2: Ustaw niestandardowy format liczb
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Dodawanie serii i punktów danych do wykresu
**Przegląd:**
Uzupełnij wykres seriami danych, aby stał się bardziej informacyjny i atrakcyjny wizualnie.

#### Krok 1: Zainicjuj prezentację i wykres
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

#### Krok 2: Dodaj serię danych
```java
// Wyczyść istniejące serie i dodaj nowe
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// W razie potrzeby dodaj więcej punktów danych
```

### Formatowanie serii Wypełnienie kolorem
**Przegląd:**
Popraw estetykę wykresu poprzez formatowanie koloru wypełnienia każdej serii.

#### Krok 1: Zainicjuj i uzyskaj dostęp do wykresu
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

// Powtórz dla innych serii z innymi kolorami
```

### Formatowanie etykiet danych
**Przegląd:**
Zwiększ czytelność etykiet danych, dostosowując ich format.

#### Krok 1: Dostęp do serii wykresów i punktów danych
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

## Wniosek
Postępując zgodnie z tym przewodnikiem, nauczyłeś się, jak skonfigurować Aspose.Slides dla Java i tworzyć dynamiczne prezentacje z wykresami kolumnowymi ułożonymi w procentach. Dostosuj swoje wykresy dalej, dostosowując kolory i etykiety do swoich potrzeb.

Miłego kodowania!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}