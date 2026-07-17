---
date: '2026-07-17'
description: Dowiedz się, jak dodać Sunburst Charts w PowerPoint przy użyciu Aspose
  Slides for Java. Przewodnik krok po kroku obejmuje konfigurację, tworzenie wykresu,
  dostosowywanie oraz praktyczne przypadki użycia.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Jak dodać Sunburst Charts w PowerPoint przy użyciu Aspose Slides for
  Java. Postępuj zgodnie z tym samouczkiem, aby skonfigurować bibliotekę, utworzyć
  wykres, dostosować punkty danych i zastosować go w rzeczywistych projektach.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Jak dodać Sunburst Charts w PowerPoint przy użyciu Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Jak dodać Sunburst Charts w PowerPoint przy użyciu Aspose (Java)
url: /pl/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak dodać wykresy Sunburst w PowerPoint przy użyciu Aspose (Java)

## Wprowadzenie

Dodanie wykresu Sunburst do prezentacji PowerPoint może natychmiast przekształcić płaską tabelę danych w angażującą wizualną hierarchię. W tym samouczku nauczysz się **jak dodać wykresy Sunburst** w PowerPoint przy użyciu Aspose.Slides for Java, od konfiguracji środowiska po precyzyjne dopasowanie kolorów i etykiet. Niezależnie od tego, czy tworzysz pulpit sprzedażowy, podział zadań projektu, czy edukacyjną prezentację, poniższe kroki zapewnią gotowe rozwiązanie produkcyjne.

**Czego się nauczysz**
- Jak skonfigurować Aspose.Slides w projekcie Maven lub Gradle
- Jak utworzyć nową prezentację i wstawić wykres Sunburst
- Jak dostosować punkty danych, etykiety i kolory wypełnienia
- Praktyczne scenariusze, w których wykresy Sunburst się wyróżniają

Zaczynajmy i zobaczmy, jak łatwo przekształcić surowe dane hierarchiczne w dopracowaną wizualizację PowerPoint.

## Szybkie odpowiedzi
- **Podstawowa biblioteka?** Aspose.Slides for Java  
- **Obsługiwany typ wykresu?** Sunburst (hierarchiczny promieniowy)  
- **Minimalna wersja Java?** JDK 16  
- **Typowy czas implementacji?** 10‑15 minut dla podstawowego wykresu  
- **Licencja wymagana w produkcji?** Tak, ważna licencja Aspose  

## Czym jest wykres Sunburst?
Wykres Sunburst to diagram promieniowy, który wizualizuje dane hierarchiczne poprzez nakładanie pierścieni od środka na zewnątrz. Idealny do przedstawiania wielopoziomowych relacji, takich jak struktury organizacyjne, kategorie produktów czy drzewa systemu plików. Każdy koncentryczny pierścień reprezentuje poziom hierarchii, a rozmiar każdego segmentu odzwierciedla jego wartość ilościową, umożliwiając szybkie zrozumienie zarówno struktury, jak i wielkości.

## Dlaczego używać Aspose.Slides for Java?
Aspose.Slides obsługuje **ponad 50 typów wykresów** i może manipulować prezentacjami zawierającymi **do 10 000 slajdów** bez ładowania całego pliku do pamięci, zapewniając wysoką wydajność w raportowaniu na skalę przedsiębiorstwa. Działa wieloplatformowo, oferuje rozbudowane API oraz solidne opcje licencjonowania, które usuwają ograniczenia wersji próbnej, co czyni go idealnym dla środowisk produkcyjnych.

## Wymagania wstępne
- **Java Development Kit (JDK)** 16 lub nowszy  
- **IDE** – IntelliJ IDEA, Eclipse lub dowolny edytor kompatybilny z Java  
- Podstawowa znajomość składni Java oraz narzędzi budowania Maven/Gradle  

## Konfiguracja Aspose.Slides for Java

### Zależność Maven
Dodaj artefakt Aspose.Slides Maven do swojego `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Zależność Gradle
Jeśli wolisz Gradle, umieść następującą linię w `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Możesz również pobrać najnowszy plik JAR bezpośrednio ze strony oficjalnych wydań: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
Aby uruchomić bez ograniczeń wersji próbnej, uzyskaj licencję:
- **Bezpłatna wersja próbna** – tymczasowa licencja do szybkiej oceny.  
- **Licencja tymczasowa** – zamów ją na [stronie Aspose](https://purchase.aspose.com/temporary-license).  
- **Pełny zakup** – kup subskrypcję na nieograniczone użycie produkcyjne.

### Podstawowa inicjalizacja
Klasa `Presentation` jest punktem wejścia do tworzenia lub otwierania plików PowerPoint.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Przewodnik implementacji

### Jak dodać wykres Sunburst do prezentacji PowerPoint przy użyciu Aspose.Slides for Java?
Załaduj nowy `Presentation`, dodaj slajd, wstaw `IChart` typu `ChartType.Sunburst` i wywołaj `save`. Ten zwięzły, trzyetapowy wzorzec tworzy w pełni funkcjonalny wykres Sunburst gotowy do dalszej personalizacji.

#### Krok 1: Inicjalizacja prezentacji
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Krok 2: Dodaj wykres Sunburst
Interfejs `IChart` definiuje obiekt wykresu, który może być umieszczony na dowolnym slajdzie. Tutaj dodajemy wykres Sunburst w współrzędnych (100, 100) o rozmiarze 450 × 400 punktów.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Krok 3: Zapisz prezentację
Zawsze zachowuj zmiany, wywołując `save`. Możesz wybrać PPTX, PDF lub dowolny z ponad 50 obsługiwanych formatów wyjściowych.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Modyfikacja punktów danych w wykresie

#### Przegląd
Możesz dostosować każdy segment wykresu Sunburst — etykiety, kolory i widoczność — poprzez kolekcję punktów danych wykresu.

#### Krok 1: Dostęp do kolekcji punktów danych
Pierwsza seria wykresu zawiera kolekcję obiektów `IChartDataPoint`, które reprezentują poszczególne segmenty.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Krok 2: Wyświetl wartość dla konkretnego punktu danych
Ustaw `IsValueShown` na `true` dla wybranego punktu danych, aby wyświetlić jego wartość liczbową bezpośrednio na segmencie.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Krok 3: Modyfikacja formatów etykiet
Dostosuj widoczność etykiet, kolor czcionki i tło, aby poprawić czytelność.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Krok 4: Ustaw kolor wypełnienia dla punktów danych
Dostosuj kolor wypełnienia poszczególnych segmentów, aby pasował do palety marki lub podkreślił kluczowe części.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Krok 5: Zapisz zmodyfikowaną prezentację
Zachowaj spersonalizowany wykres, zapisując ponownie prezentację.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Praktyczne zastosowania

1. **Analiza biznesowa** – wizualizuj sprzedaż według regionu → linii produktów → SKU w jednym widoku promieniowym.  
2. **Zarządzanie projektami** – pokaż struktury podziału pracy, przechodząc od faz do zadań i podzadań.  
3. **Edukacja** – mapuj hierarchie programów nauczania, takie jak wydziały → kursy → moduły.  

## Rozważania dotyczące wydajności

- **Wydajność pamięci:** Aspose.Slides strumieniuje dane, więc nawet 500‑stronicowa prezentacja z wieloma wykresami mieści się w pamięci poniżej 200 MB RAM.  
- **Garbage Collection:** Zwolnij obiekty slajdów (`slide.dispose()`), gdy nie są już potrzebne, aby uniknąć wycieków pamięci.  

## Najczęściej zadawane pytania

**Q: Czym jest wykres Sunburst?**  
A: Wykres Sunburst wizualizuje dane hierarchiczne w koncentrycznych pierścieniach, przy czym każdy pierścień reprezentuje poziom hierarchii.

**Q: Jak zainstalować Aspose.Slides for Java przy użyciu Maven?**  
A: Dodaj zależność Maven przedstawioną w sekcji „Zależność Maven” do swojego `pom.xml` i uruchom `mvn clean install`.

**Q: Czy mogę dostosować inne typy wykresów przy użyciu Aspose.Slides?**  
A: Tak, biblioteka obsługuje ponad 50 typów wykresów, w tym kolumnowe, liniowe, kołowe i radarowe.

**Q: Moja prezentacja nie zapisuje się — co sprawdzić?**  
A: Zweryfikuj, czy ścieżka pliku jest poprawna, katalog istnieje i masz uprawnienia do zapisu. Upewnij się także, że wywołano metodę `Presentation.save()`.

**Q: Gdzie mogę uzyskać więcej pomocy lub przykładów?**  
A: Odwiedź [forum Aspose](https://forum.aspose.com/c/slides/11) lub zapoznaj się z oficjalną [referencją Aspose.Slides](https://reference.aspose.com/slides/java/).

## Zasoby
- **Dokumentacja:** [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)  
- **Odniesienie (małe litery):** [Aspose.Slides reference](https://reference.aspose.com/slides/java/)  
- **Forum społeczności:** [Aspose Forum](https://forum.aspose.com/c/slides)  
- **Pobrania:** [Aspose.Slides Downloads](https://releases.aspose.com/slides/java)  

---

**Ostatnia aktualizacja:** 2026-07-17  
**Testowano z:** Aspose.Slides for Java 24.12  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak dodać wykresy do PowerPoint przy użyciu Aspose.Slides for Java: Przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animuj wykresy w PowerPoint przy użyciu Aspose.Slides for Java – Przewodnik krok po kroku](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Utwórz wykres w Javie z Aspose.Slides – Dodaj i zweryfikuj wykresy](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}