---
"date": "2025-04-17"
"description": "Dowiedz się, jak tworzyć dynamiczne wykresy punktowe za pomocą Aspose.Slides dla Java. Ulepsz swoje prezentacje dzięki konfigurowalnym funkcjom wykresów."
"title": "Tworzenie i dostosowywanie wykresów punktowych w języku Java za pomocą Aspose.Slides"
"url": "/pl/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie i dostosowywanie wykresów punktowych w języku Java za pomocą Aspose.Slides

Ulepsz swoje prezentacje, dodając dynamiczne wykresy punktowe za pomocą Java z Aspose.Slides. Ten kompleksowy samouczek przeprowadzi Cię przez proces konfigurowania katalogów, inicjowania prezentacji, tworzenia wykresów punktowych, zarządzania danymi wykresu, dostosowywania typów serii i znaczników oraz zapisywania swojej pracy — wszystko z łatwością.

**Czego się nauczysz:**
- Konfigurowanie katalogu do przechowywania plików prezentacji
- Inicjowanie i manipulowanie prezentacjami za pomocą Aspose.Slides
- Tworzenie wykresów punktowych na slajdach
- Zarządzanie danymi i dodawanie ich do serii wykresów
- Dostosowywanie typów i znaczników serii wykresów
- Zapisywanie prezentacji ze zmianami

Zacznijmy od upewnienia się, czy spełniasz niezbędne wymagania wstępne.

## Wymagania wstępne

Aby skorzystać z tego samouczka, upewnij się, że posiadasz:
- **Aspose.Slides dla Java**: Wymagana jest wersja 25.4 lub nowsza.
- **Zestaw narzędzi programistycznych Java (JDK)**:Wymagany jest JDK 8 lub nowszy.
- Podstawowa znajomość programowania w Javie i znajomość narzędzi do budowania Maven lub Gradle.

## Konfigurowanie Aspose.Slides dla Java

Zanim zaczniesz kodować, zintegruj Aspose.Slides ze swoim projektem, korzystając z jednej z następujących metod:

### Maven
Uwzględnij tę zależność w swoim `pom.xml` plik:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Dodaj tę linię do swojego `build.gradle` plik:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatywnie, pobierz najnowszą wersję Aspose.Slides dla Java ze strony [Wydania Aspose](https://releases.aspose.com/slides/java/).

#### Nabycie licencji
- **Bezpłatna wersja próbna**: Rozpocznij od 30-dniowego bezpłatnego okresu próbnego, aby poznać funkcje.
- **Licencja tymczasowa**:Uzyskaj tymczasową licencję na rozszerzone testy.
- **Zakup**:Kup licencję, aby uzyskać pełny dostęp i wsparcie.

Teraz zainicjuj Aspose.Slides w swojej aplikacji Java, dodając niezbędne importy, jak pokazano poniżej.

## Przewodnik wdrażania

### Konfiguracja katalogu
Najpierw upewnij się, że nasz katalog istnieje do przechowywania plików prezentacji. Ten krok zapobiega błędom podczas zapisywania pliku.

#### Utwórz katalog, jeśli nie istnieje
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Utwórz katalog
    new File(dataDir).mkdirs();
}
```
Ten fragment kodu sprawdza określony katalog i tworzy go, jeśli nie istnieje. Używa `File.exists()` w celu sprawdzenia obecności i `File.mkdirs()` aby tworzyć katalogi.

### Inicjalizacja prezentacji

Następnie zainicjuj obiekt prezentacji, do którego chcesz dodać wykres punktowy.

#### Zainicjuj swoją prezentację
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Tutaj, `new Presentation()` tworzy pustą prezentację. Uzyskujemy dostęp do pierwszego slajdu, aby pracować z nim bezpośrednio.

### Tworzenie wykresu
Następnym krokiem jest utworzenie wykresu punktowego na naszym zainicjowanym slajdzie.

#### Dodaj wykres punktowy do slajdu
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Ten fragment kodu dodaje wykres punktowy z gładkimi liniami do pierwszego slajdu. Parametry definiują pozycję i rozmiar wykresu.

### Zarządzanie danymi wykresu
Teraz możemy zarządzać danymi na wykresie poprzez wyczyszczenie istniejących serii i dodanie nowych.

#### Zarządzaj serią wykresów
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Dodawanie nowej serii do wykresu
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Ta sekcja usuwa istniejące dane i dodaje dwie nowe serie do naszego wykresu punktowego.

### Dodawanie punktów danych dla serii rozrzutu
Aby zwizualizować nasze dane, dodajemy punkty do każdej serii na wykresie punktowym.

#### Dodaj punkty danych
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Używamy `addDataPointForScatterSeries()` aby dodać punkty danych do naszej pierwszej serii. Parametry definiują wartości X i Y.

### Typ serii i modyfikacja znacznika
Dostosuj wygląd wykresu, zmieniając rodzaj i styl znaczników w każdej serii.

#### Dostosuj serię
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modyfikacja drugiej serii
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Te zmiany dostosowują typ serii do używania linii prostych i znaczników. Ustawiamy również rozmiar znacznika i symbol dla rozróżnienia wizualnego.

### Zapisywanie prezentacji
Na koniec zapisz prezentację ze wszystkimi wprowadzonymi modyfikacjami.

#### Zapisz swoją prezentację
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Używać `SaveFormat.Pptx` aby określić format PowerPoint do zapisania pliku. Ten krok jest kluczowy dla zachowania wszystkich zmian.

## Zastosowania praktyczne
Oto kilka przykładów zastosowań w świecie rzeczywistym:
1. **Analiza finansowa**:Użyj wykresów punktowych, aby wyświetlić trendy giełdowe na przestrzeni czasu.
2. **Badania naukowe**:Przedstaw punkty danych eksperymentalnych do analizy.
3. **Zarządzanie projektami**:Wizualizacja alokacji zasobów i wskaźników postępu.

Zintegrowanie Aspose.Slides z systemem umożliwia automatyzację generowania raportów, co przekłada się na zwiększenie produktywności i dokładności.

## Rozważania dotyczące wydajności
Aby uzyskać optymalną wydajność:
- Zarządzaj wykorzystaniem pamięci poprzez usuwanie prezentacji po ich zapisaniu.
- Używaj wydajnych struktur danych w przypadku dużych zbiorów danych.
- Minimalizuj operacje intensywnie wykorzystujące zasoby w pętlach.

Najlepsze praktyki gwarantują płynną realizację nawet w przypadku skomplikowanych manipulacji wykresami.

## Wniosek
W tym samouczku nauczyłeś się konfigurować katalogi, inicjować prezentacje Aspose.Slides, tworzyć i dostosowywać wykresy punktowe, zarządzać danymi serii, modyfikować znaczniki i zapisywać swoją pracę. Aby lepiej poznać możliwości Aspose.Slides, rozważ zanurzenie się w bardziej zaawansowanych funkcjach, takich jak animacja i przejścia slajdów.

**Następne kroki**:Eksperymentuj z różnymi typami wykresów lub zintegruj te techniki w większym projekcie Java.

## Często zadawane pytania

### Jak zmienić kolor znaczników?
Aby zmienić kolor znacznika, użyj `series.getMarker().getFillFormat().setFillColor(ColorObject)`, Gdzie `ColorObject` to jest Twój pożądany kolor.

### Czy mogę dodać do wykresu punktowego więcej niż dwie serie?
Tak, możesz dodać tyle serii, ile potrzebujesz, powtarzając proces dodawania nowych serii i punktów danych.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}