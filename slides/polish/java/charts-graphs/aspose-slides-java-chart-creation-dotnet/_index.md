---
date: '2026-01-14'
description: Dowiedz się, jak dodać wykres słupkowy grupowany i umieścić wykres na
  slajdzie w prezentacjach .NET przy użyciu Aspose.Slides for Java. Postępuj zgodnie
  z tym przewodnikiem krok po kroku, zawierającym pełne przykłady kodu.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Dodaj wykres słupkowy grupowany do .NET Slides Aspose.Slides Java
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów w prezentacjach .NET przy użyciu Aspose.Slides for Java
## Wprowadzenie
Tworzenie atrakcyjnych prezentacji często wymaga integracji wizualnych reprezentacji danych, takich jak wykresy, aby zwiększyć zrozumienie i zaangażowanie odbiorców. Jeśli jesteś programistą, który chce dodać dynamiczne, konfigurowalne wykresy do swoich prezentacji .NET przy użyciu Aspose.Slides for Java, ten samouczek jest właśnie dla Ciebie. Przyjrzymy się, jak inicjalizować prezentacje, dodawać różne typy wykresów, zarządzać danymi wykresu i skutecznie formatować dane serii.

**Co się nauczysz:**
- Jak skonfigurować i używać Aspose.Slides for Java w środowisku .NET.
- Inicjalizacja nowej prezentacji przy użyciu Aspose.Slides.
- Dodawanie i dostosowywanie wykresów na slajdach.
- Zarządzanie skoroszytem danych wykresu.
- Formatowanie danych serii, w szczególności obsługa wartości ujemnych.

Przejście do sekcji wymagań wstępnych zapewni, że będziesz gotowy, aby śledzić instrukcje bez problemów.

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Dodanie wykresu kolumnowego grupowanego do slajdu .NET.
- **Jakiej biblioteki wymaga projekt?** Aspose.Slides for Java (v25.4+).
- **Czy mogę używać jej w projekcie .NET?** Tak – biblioteka Java działa poprzez most Java‑to‑.NET.
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w fazie rozwoju; licencja komercyjna jest wymagana w produkcji.
- **Jak długo trwa implementacja?** Około 10‑15 minut dla podstawowego wykresu.

## Co to jest wykres kolumnowy grupowany?
Wykres kolumnowy grupowany wyświetla wiele serii danych obok siebie dla każdej kategorii, co ułatwia porównywanie wartości pomiędzy grupami. Ten rodzaj wizualizacji jest idealny dla pulpitów biznesowych, raportów wydajności i wszelkich scenariuszy, w których trzeba zestawić ze sobą kilka miar.

## Dlaczego dodać wykres do slajdu przy użyciu Aspose.Slides for Java?
Użycie Aspose.Slides pozwala generować, modyfikować i zapisywać prezentacje bez konieczności posiadania zainstalowanego Microsoft PowerPoint. Oferuje pełną kontrolę nad typami wykresów, danymi i stylizacją, co oznacza, że możesz automatyzować generowanie raportów bezpośrednio z aplikacji .NET.

## Wymagania wstępne
Zanim przejdziesz do tworzenia wykresów przy użyciu Aspose.Slides for Java, określmy, co jest potrzebne:

### Wymagane biblioteki i wersje
- **Aspose.Slides for Java**: wersja 25.4 lub nowsza.

### Wymagania dotyczące konfiguracji środowiska
- Środowisko programistyczne obsługujące aplikacje .NET.
- Podstawowa znajomość koncepcji programowania w języku Java.

### Wymagania dotyczące wiedzy
- Znajomość tworzenia prezentacji w kontekście aplikacji .NET.
- Rozumienie zależności Java i ich zarządzania (Maven/Gradle).

## Konfiguracja Aspose.Slides for Java
Aby rozpocząć korzystanie z Aspose.Slides, musisz dodać go jako zależność w swoim projekcie. Oto jak to zrobić:

### Maven
Dodaj następującą zależność do pliku `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Umieść to w pliku `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Alternatywnie możesz pobrać najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroki uzyskania licencji
- **Free Trial**: Rozpocznij od tymczasowej licencji, aby przetestować funkcje.
- **Purchase**: Rozważ zakup licencji przy intensywnym użytkowaniu.

#### Podstawowa inicjalizacja i konfiguracja
Oto jak zainicjalizować Aspose.Slides w kodzie:
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
**Przegląd:**  
Utworzenie instancji prezentacji przygotowuje scenę dla wszystkich kolejnych operacji. Ta sekcja pokazuje, jak rozpocząć od zera przy użyciu Aspose.Slides.

#### Krok 1: Importuj niezbędne pakiety
```java
import com.aspose.slides.Presentation;
```

#### Krok 2: Utwórz nowy obiekt Presentation
Oto jak to zrobić:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Zapewnia to prawidłowe zwolnienie obiektu prezentacji po użyciu, zapobiegając wyciekom pamięci.*

### Dodawanie wykresu do slajdu
**Przegląd:**  
Dodanie wykresu do slajdu może uczynić wizualizację danych bardziej efektywną i angażującą.

#### Krok 1: Importuj niezbędne pakiety
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Krok 2: Zainicjalizuj prezentację i dodaj wykres
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
**Przegląd:**  
Efektywne zarządzanie skoroszytem danych wykresu pozwala płynnie manipulować seriami i kategoriami.

#### Krok 1: Importuj niezbędne pakiety
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Krok 2: Uzyskaj dostęp i wyczyść skoroszyt danych
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
*Wyczyszczenie skoroszytu jest kluczowe, aby rozpocząć z czystym stanem przy dodawaniu nowych serii i kategorii.*

### Dodawanie serii i kategorii do wykresu
**Przegląd:**  
Ta sekcja pokazuje, jak dodać istotne punkty danych poprzez zarządzanie seriami i kategoriami.

#### Krok 1: Dodaj serie i kategorie
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
*Dodanie serii i kategorii umożliwia bardziej uporządkowaną prezentację danych.*

### Wypełnianie danych serii i formatowanie
**Przegląd:**  
Wypełnij wykres punktami danych i sformatuj wygląd, aby zwiększyć czytelność, szczególnie przy wartościach ujemnych.

#### Krok 1: Wypełnij dane serii
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
*Ta sekcja demonstruje, jak wypełnić dane i zastosować formatowanie kolorów dla lepszej wizualizacji.*

## Typowe problemy i rozwiązania
- **Memory leaks:** Zawsze wywołuj `dispose()` na obiekcie `Presentation` w bloku `finally`.
- **Incorrect chart type:** Upewnij się, że używasz `ChartType.ClusteredColumn`, gdy potrzebny jest wykres kolumnowy grupowany; inne typy wygenerują inne wyniki wizualne.
- **Negative value colors not applied:** Sprawdź, czy wartość `IDataPoint` jest poprawnie rzutowana na `Number` przed porównaniem.

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Slides for Java w czystym projekcie .NET bez Java?**  
A: Tak. Biblioteka działa poprzez most Java‑to‑.NET, umożliwiając wywoływanie interfejsów API Java z języków .NET.

**Q: Czy wersja próbna obsługuje tworzenie wykresów?**  
A: Wersja próbna zawiera pełną funkcjonalność wykresów, ale wygenerowane pliki zawierają mały znak wodny oceny.

**Q: Które wersje .NET są kompatybilne?**  
A: Każda wersja .NET, która może współpracować z Java 16+, w tym .NET Framework 4.6+, .NET Core 3.1+ oraz .NET 5/6/7.

**Q: Jak radzić sobie z dużymi prezentacjami zawierającymi wiele wykresów?**  
A: W miarę możliwości ponownie używaj tej samej instancji `IChartDataWorkbook` i niezwłocznie zwalniaj każdy `Presentation`, aby zwolnić pamięć.

**Q: Czy można wyeksportować wykres jako obraz?**  
A: Tak. Użyj metod `chart.getImage()` lub `chart.exportChartImage()`, aby uzyskać reprezentacje PNG/JPEG.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-01-14  
**Testowano z:** Aspose.Slides for Java 25.4  
**Autor:** Aspose  

---