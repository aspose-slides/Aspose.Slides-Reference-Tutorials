---
"date": "2025-04-17"
"description": "Dowiedz się, jak tworzyć i konfigurować dynamiczne prezentacje z wykresami w Javie przy użyciu Aspose.Slides. Opanuj dodawanie, dostosowywanie i zapisywanie prezentacji w sposób efektywny."
"title": "Tworzenie prezentacji Java z wykresami przy użyciu Aspose.Slides dla Java"
"url": "/pl/java/charts-graphs/create-java-presentations-charts-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć i skonfigurować prezentację z wykresem przy użyciu Aspose.Slides dla Java

## Wstęp

Tworzenie dynamicznych prezentacji, które skutecznie przekazują dane, jest niezbędne w dzisiejszym dynamicznym środowisku biznesowym. Niezależnie od tego, czy przygotowujesz raport finansowy, czy prezentujesz metryki projektu, dodawanie wykresów może znacznie zwiększyć wpływ Twojej prezentacji. Ten samouczek przeprowadzi Cię przez proces tworzenia i konfigurowania prezentacji z trójwymiarowym wykresem kolumnowym przy użyciu Aspose.Slides for Java, potężnej biblioteki zaprojektowanej do obsługi prezentacji programowo.

**Czego się nauczysz:**
- Jak utworzyć nową prezentację
- Dodawaj i konfiguruj wykresy na slajdach
- Dostosuj dane i wygląd wykresu
- Skutecznie zapisuj swoją prezentację

Gotowy, aby opanować tworzenie wizualnie atrakcyjnych prezentacji w Javie? Zaczynajmy!

## Wymagania wstępne

Zanim przejdziesz do samouczka, upewnij się, że spełniłeś poniższe wymagania wstępne:

- **Biblioteki i zależności**: Aspose.Slides dla Java musi być zainstalowany.
- **Konfiguracja środowiska**:Praca w środowisku Java (zalecane JDK 16 lub nowsze).
- **Baza wiedzy**:Znajomość podstawowych koncepcji programowania w języku Java będzie dodatkowym atutem.

## Konfigurowanie Aspose.Slides dla Java

### Instalacja

Aby zintegrować Aspose.Slides ze swoim projektem, wykonaj następujące kroki:

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

**Bezpośrednie pobieranie**:Alternatywnie, pobierz najnowszą wersję z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

### Nabycie licencji
- **Bezpłatna wersja próbna**:Rozpocznij od bezpłatnego okresu próbnego, aby poznać funkcje.
- **Licencja tymczasowa**:Uzyskaj tymczasową licencję na rozszerzone testy.
- **Zakup**:Nabyj pełną licencję do użytku komercyjnego.

Po zainstalowaniu zainicjuj bibliotekę w środowisku Java, tworząc jej wystąpienie `Presentation` klasa. To tworzy podstawę do dodawania wykresów i innych elementów do prezentacji.

## Przewodnik wdrażania

### Tworzenie i konfiguracja prezentacji z wykresem

#### Przegląd
Tworzenie prezentacji od podstaw jest proste dzięki Aspose.Slides. W tej sekcji dodamy wykres kolumnowy 3D do pierwszego slajdu naszej prezentacji.

**Kroki:**

1. **Zainicjuj obiekt prezentacji**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Zainicjuj nowy obiekt prezentacji
           Presentation presentation = new Presentation();
           
           // Uzyskaj dostęp do pierwszego slajdu prezentacji
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Dodaj wykres kolumnowy 3D do slajdu w pozycji (0,0)
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

2. **Wyjaśnij parametry**:
   - `ChartType.StackedColumn3D`: Określa typ wykresu.
   - Pozycja i rozmiar `(0, 0, 500, 500)`:Określa miejsce, w którym wykres pojawi się na slajdzie.

### Konfigurowanie danych wykresu

#### Przegląd
Aby nadać wykresowi sens, skonfiguruj jego serie danych i kategorie. Ta sekcja pokazuje, jak dodawać określone punkty danych do wykresu.

**Kroki:**

1. **Dostęp do skoroszytu danych Chart's**

   ```java
   public static void configureChartData(IChart chart) {
       // Ustaw indeks arkusza kalkulacyjnego zawierającego dane wykresu
       int defaultWorksheetIndex = 0;
       
       // Uzyskaj dostęp do skoroszytu danych wykresu
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Dodaj dwie serie z nazwami
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Dodaj trzy kategorie
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Ustaw właściwości Rotation3D dla wykresu

#### Przegląd
Popraw atrakcyjność wizualną swojego wykresu dzięki właściwościom obrotu 3D. Ta personalizacja pozwala dostosować perspektywę i głębię.

**Kroki:**

1. **Konfiguruj obroty 3D**

   ```java
   public static void setRotation3D(IChart chart) {
       // Włącz osie kątowe i skonfiguruj obroty w kierunkach X, Y oraz procent głębokości
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Wyjaśnij parametry**:
   - `setRightAngleAxes(true)`: Zapewnia prostopadłość osi.
   - Wartości obrotu: dostosowuje kąt i głębokość widoku 3D.

### Wypełnij dane serii na wykresie

#### Przegląd
Wypełnienie wykresu punktami danych jest kluczowe dla analizy. Tutaj dodamy określone wartości do serii w naszym wykresie.

**Kroki:**

1. **Dodaj punkty danych**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Uzyskaj dostęp do drugiej serii wykresów
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Dodaj punkty danych dla serii słupków o określonych wartościach
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

### Dostosuj nakładanie się serii na wykresie

#### Przegląd
Dopracowanie wyglądu wykresu może poprawić czytelność. Ta sekcja opisuje, jak dostosować właściwość nakładania się, aby uzyskać lepszą wizualizację danych.

**Kroki:**

1. **Ustaw nakładanie się serii**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Pobierz drugą serię z wykresu i ustaw jej nakładanie na 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Zapisz prezentację

#### Przegląd
Po skonfigurowaniu prezentacji zapisz ją na dysku w żądanym formacie. Ten krok zapewnia, że wszystkie zmiany zostaną zachowane.

**Kroki:**

1. **Zapisz prezentację**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Zapisz zmodyfikowaną prezentację do pliku
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Wniosek

Nauczyłeś się już, jak tworzyć i konfigurować prezentacje z wykresami przy użyciu Aspose.Slides for Java. Ten przewodnik obejmuje inicjowanie prezentacji, dodawanie wykresu kolumnowego 3D, konfigurowanie serii danych i kategorii, ustawianie właściwości obrotu, wypełnianie danych serii, dostosowywanie nakładania się serii i zapisywanie ostatecznej prezentacji.

Aby uzyskać bardziej zaawansowane funkcje i opcje dostosowywania, zapoznaj się z [Aspose.Slides dla dokumentacji Java](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}