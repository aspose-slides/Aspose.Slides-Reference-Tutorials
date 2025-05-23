---
"date": "2025-04-17"
"description": "Dowiedz się, jak utworzyć i dostosować wykres kołowy za pomocą Aspose.Slides dla Java. Ten przewodnik obejmuje konfigurację, implementację i praktyczne zastosowania."
"title": "Tworzenie wykresu kołowego w języku Java za pomocą Aspose.Slides&#58; Kompleksowy przewodnik"
"url": "/pl/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresu kołowego w języku Java za pomocą Aspose.Slides: kompleksowy przewodnik

## Wykresy i grafy

### Wstęp

W wizualizacji danych wykresy kołowe są intuicyjnym sposobem przedstawiania proporcji w zestawie danych. Jednak w przypadku złożonych zestawów danych, w których niektóre segmenty są znacznie mniejsze od innych, tradycyjne wykresy kołowe mogą stać się zagracone i trudne do zinterpretowania. Wykresy kołowe rozwiązują ten problem, dzieląc małe wycinki na wykres drugorzędny, co zwiększa czytelność.

tym samouczku nauczysz się, jak tworzyć i manipulować wykresem kołowym za pomocą Aspose.Slides dla Java. Omówisz konfigurację środowiska, tworzenie wykresu, dostosowywanie właściwości, takich jak etykiety danych i pozycje podziału, oraz zapisywanie prezentacji w formacie PPTX. Do końca opanujesz te funkcje dzięki praktycznym aplikacjom i wskazówkom dotyczącym wydajności.

**Czego się nauczysz:**
- Konfigurowanie Aspose.Slides dla Java
- Tworzenie wykresu kołowego
- Dostosowywanie właściwości wykresu, takich jak etykiety danych i konfiguracje podziału
- Zapisywanie prezentacji na dysku

Gotowy, aby zacząć? Najpierw przyjrzyjmy się wymaganiom wstępnym!

## Wymagania wstępne

Zanim utworzysz wykres kołowy, upewnij się, że masz:

### Wymagane biblioteki, wersje i zależności:
- **Aspose.Slides dla Java**:Niezbędny do programowego zarządzania prezentacjami PowerPoint.

### Wymagania dotyczące konfiguracji środowiska:
- Java Development Kit (JDK) zainstalowany na Twoim komputerze. Zalecamy używanie JDK 16 lub nowszego.
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA, Eclipse lub NetBeans.

### Wymagania wstępne dotyczące wiedzy:
- Podstawowa znajomość programowania w Javie
- Znajomość Maven lub Gradle do zarządzania zależnościami

## Konfigurowanie Aspose.Slides dla Java

### Informacje o instalacji:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Stopień:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Bezpośrednie pobieranie**:Najnowszą wersję możesz pobrać ze strony [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

### Etapy uzyskania licencji:
- **Bezpłatna wersja próbna**: Zacznij od 30-dniowego okresu próbnego, aby poznać wszystkie funkcje.
- **Licencja tymczasowa**:Poproś o tymczasową licencję w celu rozszerzonej oceny.
- **Zakup**: Rozważ zakup licencji, jeśli Aspose.Slides spełnia Twoje potrzeby.

### Podstawowa inicjalizacja i konfiguracja

Po skonfigurowaniu biblioteki w projekcie zainicjuj ją, tworząc wystąpienie `Presentation` klasa:

```java
Presentation presentation = new Presentation();
```

To przygotowuje grunt pod dodawanie różnych wykresów do slajdów. Następnie przejdźmy do implementacji naszego wykresu kołowego.

## Przewodnik wdrażania

### Tworzenie wykresu kołowego

#### Przegląd
Zaczniemy od utworzenia instancji `Presentation` i dodaj wykres kołowy na pierwszym slajdzie. Ten wykres będzie skutecznie wizualizować dane poprzez oddzielenie mniejszych segmentów w drugorzędnym wykresie kołowym, zwiększając czytelność.

#### Krok 1: Utwórz instancję klasy Presentation
```java
// Utwórz nową prezentację
ePresentation presentation = new Presentation();
```
Ten kod inicjuje prezentację, do której dodamy nasze wykresy.

#### Krok 2: Dodaj wykres kołowy „Kołowy kołowy” na pierwszym slajdzie
```java
// Dodaj wykres kołowy do pierwszego slajdu na pozycji (50, 50) o rozmiarze (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Tutaj określamy typ wykresu (`PieOfPie`) oraz jego położenie i wymiary na slajdzie.

#### Krok 3: Ustaw etykiety danych, aby wyświetlały wartości dla serii
```java
// Konfigurowanie etykiet danych w celu wyświetlania wartości
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Ten krok zapewnia, że każdy segment wykresu kołowego wyświetla odpowiadającą mu wartość, co pomaga w szybkiej interpretacji danych.

#### Krok 4: Skonfiguruj drugi rozmiar wykresu kołowego i podziel go według procentów
```java
// Ustaw rozmiar dodatkowego wykresu kołowego
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Podziel ciasto procentowo
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Ustaw pozycję podziału
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Konfiguracje te umożliwiają dostosowanie sposobu podziału wykresu i wyświetlania mniejszych segmentów, co zwiększa czytelność wykresu dla odbiorców.

#### Krok 5: Zapisz prezentację na dysku w formacie PPTX
```java
// Zdefiniuj katalog wyjściowy
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Zapisz prezentację\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}