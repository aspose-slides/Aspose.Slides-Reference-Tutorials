---
date: '2026-06-03'
description: Dowiedz się, jak tworzyć wykresy w prezentacjach .NET i dodawać wykres
  do slajdu przy użyciu Aspose.Slides for Java. Postępuj zgodnie z tym przewodnikiem
  krok po kroku dotyczącym wizualizacji danych.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Tworzenie wykresów w .NET przy użyciu Aspose.Slides for Java
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów w .NET przy użyciu Aspose.Slides for Java

## Wprowadzenie
Tworzenie atrakcyjnych prezentacji często wymaga integracji wizualnych reprezentacji danych, takich jak wykresy, aby zwiększyć zrozumienie i zaangażowanie odbiorców. **If you want to create charts in .NET**, Aspose.Slides for Java zapewnia potężne, językowo‑agnostyczne API, które działa płynnie wewnątrz aplikacji .NET. W tym samouczku nauczysz się, jak zainicjować prezentację, dodać różnorodne typy wykresów, zarządzać skoroszytem danych wykresu oraz formatować dane serii — w tym obsługę wartości ujemnych. Po zakończeniu będziesz w stanie programowo generować wykresy w plikach prezentacji i dodawać wykres do slajdu za pomocą kilku linii kodu.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Tworzenie wykresów w prezentacjach .NET przy użyciu Aspose.Slides for Java.  
- **Jakiej wersji biblioteki wymaga?** Aspose.Slides for Java 25.4 lub nowsza.  
- **Czy potrzebuję licencji?** Darmowa wersja próbna działa w środowisku deweloperskim; licencja komercyjna jest wymagana w produkcji.  
- **Czy mogę używać Maven lub Gradle?** Tak — oba systemy budowania są obsługiwane.  
- **Jakie typy wykresów są dostępne?** Kolumnowy grupowany, liniowy, kołowy, słupkowy, obszarowy i inne.

## Jak tworzyć wykresy w prezentacjach .NET przy użyciu Aspose.Slides for Java?
`Presentation` klasa reprezentuje plik PowerPoint i udostępnia metody do manipulacji jego slajdami. Załaduj nowy obiekt `Presentation`, wywołaj `slides.addEmptySlide()` aby uzyskać slajd, a następnie użyj `slide.getShapes().addChart()` aby wstawić wybrany typ wykresu w określonych współrzędnych. Po dodaniu wykresu, wypełnij jego skoroszyt danych seriami i kategoriami, zastosuj formatowanie (np. kolory dla wartości ujemnych) i na końcu zapisz prezentację do pliku .pptx. Ten przepływ pozwala **create charts in .NET** przy użyciu zwięzłego zestawu wywołań API.

## Czym jest Aspose.Slides for Java?
Aspose.Slides for Java to wieloplatformowe API, które umożliwia programistom tworzenie, modyfikowanie i renderowanie plików PowerPoint bez Microsoft Office. Obsługuje **50+ input and output formats** i może przetwarzać prezentacje z tysiącami slajdów, utrzymując zużycie pamięci poniżej 200 MB.

## Dlaczego używać Aspose.Slides for Java w projekcie .NET?
Aspose.Slides for Java działa na Java Virtual Machine i może być wywoływany z .NET poprzez natywną nakładkę, dając programistom .NET dostęp do dojrzałego silnika wykresów, wysokowydajnego przetwarzania dużych zestawów danych oraz pełnej kompatybilności z istniejącym kodem Java bez konieczności przepisywania logiki.

## Wymagania wstępne
Zanim przejdziesz do tworzenia wykresów przy użyciu Aspose.Slides for Java, przedstawmy, czego potrzebujesz:

### Wymagane biblioteki i wersje
- **Aspose.Slides for Java**: Wersja 25.4 lub nowsza.

### Wymagania dotyczące konfiguracji środowiska
- Środowisko programistyczne obsługujące aplikacje .NET.  
- Podstawowa znajomość koncepcji programowania w języku Java.

### Wymagania wiedzy
- Znajomość tworzenia prezentacji w kontekście aplikacji .NET.  
- Zrozumienie zależności Java i ich zarządzania (Maven/Gradle).

## Konfiguracja Aspose.Slides for Java
Aby rozpocząć korzystanie z Aspose.Slides, musisz dodać go jako zależność w swoim projekcie. Oto jak to zrobić:

### Maven
Fragment zależności Maven dodaje Aspose.Slides for Java do Twojego projektu.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Umieść tę linię w pliku `build.gradle`, aby pobrać bibliotekę z Maven Central.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Alternatywnie możesz pobrać najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroki uzyskania licencji
- **Free Trial**: Rozpocznij od tymczasowej licencji, aby przetestować funkcje.  
- **Purchase**: Kup licencję do nieograniczonego użycia w produkcji.

#### Podstawowa inicjalizacja i konfiguracja
Inicjalizacja `Slides` wymaga ustawienia licencji i utworzenia instancji `Presentation`.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Ta konfiguracja zapewnia skuteczne zarządzanie zasobami.

## Przewodnik implementacji
Przeprowadzimy Cię krok po kroku przez implementację funkcji.

### Inicjalizacja prezentacji
**Overview:**  
Utworzenie instancji prezentacji przygotowuje scenę dla wszystkich kolejnych operacji. Ta funkcja pokazuje, jak rozpocząć od zera przy użyciu Aspose.Slides.

#### Krok 1: Importowanie niezbędnych pakietów
`Presentation` i powiązane klasy znajdują się w przestrzeni nazw `com.aspose.slides`.

```java
import com.aspose.slides.Presentation;
```

#### Krok 2: Utworzenie nowego obiektu Presentation
Zainstaluj obiekt `Presentation` i otocz go blokiem try‑with‑resources, aby zapewnić jego zwolnienie.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*To zapewnia, że obiekt prezentacji jest prawidłowo zwalniany po użyciu, zapobiegając wyciekom pamięci.*

### Dodawanie wykresu do slajdu
**Overview:**  
Dodanie wykresu do slajdu może uczynić wizualizację danych bardziej efektywną i angażującą.

#### Krok 1: Importowanie niezbędnych pakietów
Klasa `Chart` reprezentuje kształt wykresu, który może być umieszczony na slajdzie i dostosowany.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Krok 2: Inicjalizacja prezentacji i dodanie wykresu
Utwórz slajd, a następnie wywołaj `addChart` z `ChartType.ClusteredColumn` oraz żądanymi współrzędnymi i rozmiarem.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Tutaj dodajemy wykres kolumnowy grupowany do pierwszego slajdu w określonych współrzędnych i wymiarach.*

### Zarządzanie skoroszytem danych wykresu
**Overview:**  
Efektywne zarządzanie skoroszytem danych wykresu umożliwia płynne manipulowanie seriami i kategoriami.

#### Krok 1: Importowanie niezbędnych pakietów
`IChartDataWorkbook` zapewnia dostęp do podstawowego skoroszytu podobnego do Excel, używanego przez wykresy.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Krok 2: Dostęp i czyszczenie skoroszytu danych
Pobierz skoroszyt z wykresu i wyczyść istniejące dane, aby rozpocząć od nowa.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Czyszczenie skoroszytu jest kluczowe, aby rozpocząć z czystym stanem przy dodawaniu nowych serii i kategorii.*

### Dodawanie serii i kategorii do wykresu
**Overview:**  
Ta funkcja pokazuje, jak dodać istotne punkty danych poprzez zarządzanie seriami i kategoriami.

#### Krok 1: Dodawanie serii i kategorii
Użyj `chart.getChartData().getSeries().add()` oraz `chart.getChartData().getCategories().add()`, aby zdefiniować strukturę.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Dodawanie serii i kategorii umożliwia bardziej uporządkowaną prezentację danych.*

### Wypełnianie danych serii i formatowanie
**Overview:**  
Wypełnij wykres punktami danych i sformatuj wygląd, aby zwiększyć czytelność, szczególnie przy obsłudze wartości ujemnych.

#### Krok 1: Wypełnianie danych serii
Przypisz wartości liczbowe do każdej komórki w skoroszycie i zastosuj czerwone wypełnienie dla liczb ujemnych.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Ta sekcja demonstruje, jak wypełnić dane i zastosować formatowanie kolorów w celu lepszej wizualizacji.*

## Typowe problemy i rozwiązania
- **LicenseNotFoundException** – Upewnij się, że ścieżka do pliku licencji jest poprawna i plik jest dostępny w czasie wykonywania.  
- **NullPointerException on chart data** – Zawsze czyść skoroszyt przed dodaniem nowych serii, aby uniknąć pozostałych danych.  
- **Chart not rendering in .NET** – Sprawdź, czy używasz wersji JAR Aspose.Slides kompatybilnej z .NET oraz czy środowisko Java jest poprawnie skonfigurowane w Twoim projekcie .NET.

## Najczęściej zadawane pytania

**Q: Czy mogę generować wykres w plikach prezentacji bez interfejsu GUI?**  
A: Tak, Aspose.Slides for Java jest w pełni trybem headless i działa na serwerach bez żadnych komponentów graficznych.

**Q: Jakie wersje .NET są obsługiwane?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, i .NET 6 są wszystkie obsługiwane.

**Q: Ile typów wykresów mogę dodać?**  
A: Dostępnych jest ponad 20 typów wykresów, w tym kolumnowy, liniowy, kołowy, obszarowy i radarowy.

**Q: Czy można stylizować poszczególne punkty danych?**  
A: Oczywiście — możesz ustawić kolory wypełnienia, obramowania i markery dla każdego punktu danych za pomocą API `IDataPoint`.

**Q: Czy muszę ręcznie konwertować obiekty Java na typy .NET?**  
A: Nie, nakładka .NET Aspose.Slides for Java automatycznie obsługuje konwersję typów.

---

**Ostatnia aktualizacja:** 2026-06-03  
**Testowano z:** Aspose.Slides for Java 25.4  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak osadzić wykresy w prezentacjach .NET przy użyciu Aspose.Slides dla efektywnej wizualizacji danych](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Jak pobrać typ źródła danych wykresu przy użyciu Aspose.Slides dla .NET – wykresy i grafy](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Mistrzowskie tworzenie i manipulacja seriami wykresów z Aspose.Slides .NET dla efektywnej wizualizacji danych](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}