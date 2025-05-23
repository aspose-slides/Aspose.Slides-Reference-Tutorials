---
"date": "2025-04-17"
"description": "Dowiedz się, jak tworzyć i dostosowywać wykresy kołowe za pomocą Aspose.Slides dla Java. Ten samouczek obejmuje wszystko, od konfiguracji po zaawansowaną personalizację."
"title": "Tworzenie wykresów kołowych w Javie za pomocą Aspose.Slides&#58; Kompleksowy przewodnik"
"url": "/pl/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów kołowych za pomocą Aspose.Slides dla Java: kompletny samouczek

## Wstęp
Tworzenie dynamicznych i wizualnie atrakcyjnych prezentacji jest kluczowe dla dostarczania informacji o dużym wpływie. Dzięki Aspose.Slides for Java możesz bezproblemowo integrować złożone wykresy, takie jak wykresy kołowe, ze swoimi slajdami, bez wysiłku ulepszając wizualizację danych. Ten kompleksowy przewodnik przeprowadzi Cię przez proces tworzenia i dostosowywania wykresu kołowego za pomocą Aspose.Slides Java, rozwiązując typowe problemy z prezentacjami z łatwością.

**Czego się nauczysz:**
- Inicjowanie prezentacji i dodawanie slajdów.
- Tworzenie i konfigurowanie wykresu kołowego na slajdzie.
- Ustawianie tytułów wykresów, etykiet danych i kolorów.
- Optymalizacja wydajności i efektywne zarządzanie zasobami.
- Integracja Aspose.Slides z projektami Java przy użyciu Maven lub Gradle.

Zacznijmy od upewnienia się, że posiadasz wszystkie niezbędne narzędzia i wiedzę, aby móc nad tym pracować!

## Wymagania wstępne
Zanim przejdziesz do tego samouczka, upewnij się, że masz przygotowaną następującą konfigurację:

### Wymagane biblioteki, wersje i zależności
- **Aspose.Slides dla Java**: Upewnij się, że masz wersję 25.4 lub nowszą.
- **Zestaw narzędzi programistycznych Java (JDK)**: Wymagana jest wersja 16 lub nowsza.

### Wymagania dotyczące konfiguracji środowiska
- Środowisko programistyczne z zainstalowaną i skonfigurowaną Javą.
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA, Eclipse lub NetBeans.

### Wymagania wstępne dotyczące wiedzy
- Podstawowa znajomość programowania w Javie.
- Znajomość Maven lub Gradle do zarządzania zależnościami.

## Konfigurowanie Aspose.Slides dla Java
Aby zacząć używać Aspose.Slides w swoich projektach Java, musisz dodać bibliotekę jako zależność. Oto, jak możesz to zrobić za pomocą różnych narzędzi do kompilacji:

**Maven**
Dodaj ten fragment do swojego `pom.xml` plik:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Włącz do swojego `build.gradle` plik:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Bezpośrednie pobieranie**
Jeśli wolisz nie używać narzędzia do kompilacji, pobierz najnowszą wersję z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

### Etapy uzyskania licencji
- **Bezpłatna wersja próbna**: Rozpocznij od bezpłatnego okresu próbnego, aby poznać funkcje Aspose.Slides.
- **Licencja tymczasowa**:Uzyskaj tymczasową licencję na dłuższe użytkowanie bez ograniczeń.
- **Zakup**:Rozważ zakup, jeśli potrzebujesz dostępu długoterminowego.

**Podstawowa inicjalizacja i konfiguracja**
Aby rozpocząć korzystanie z Aspose.Slides, zainicjuj projekt, tworząc nowy obiekt prezentacji:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Przewodnik wdrażania
Teraz omówimy proces dodawania i dostosowywania wykresu kołowego na łatwiejsze do wykonania kroki.

### Zainicjuj prezentację i slajd
Zacznij od skonfigurowania nowej prezentacji i uzyskania dostępu do pierwszego slajdu. To jest Twoje płótno do tworzenia wykresów:
```java
import com.aspose.slides.*;

// Utwórz nową instancję prezentacji.
Presentation presentation = new Presentation();
// Otwórz pierwszy slajd prezentacji.
islide slides = presentation.getSlides().get_Item(0);
```

### Dodaj wykres kołowy do slajdu
Wstaw wykres kołowy w określonym miejscu z domyślnym zestawem danych:
```java
import com.aspose.slides.*;

// Dodaj wykres kołowy w pozycji (100, 100) i rozmiarze (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Ustaw tytuł wykresu
Dostosuj swój wykres, ustawiając i centrując tytuł:
```java
import com.aspose.slides.*;

// Dodaj tytuł do wykresu kołowego.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurowanie etykiet danych dla serii
Upewnij się, że etykiety danych wyświetlają wartości, aby zapewnić ich przejrzystość:
```java
import com.aspose.slides.*;

// Pokaż wartości danych dla pierwszej serii.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Przygotuj arkusz danych wykresu
Skonfiguruj arkusz danych wykresu, czyszcząc istniejące serie i kategorie:
```java
import com.aspose.slides.*;

// Przygotuj arkusz danych wykresu.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Dodaj kategorie do wykresu
Zdefiniuj kategorie dla swojego wykresu kołowego:
```java
import com.aspose.slides.*;

// Dodaj nowe kategorie.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Dodaj serie i wypełnij punkty danych
Utwórz serię i wypełnij ją punktami danych:
```java
import com.aspose.slides.*;

// Dodaj nową serię i ustaw jej nazwę.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Dostosuj kolory i obramowania serii
Popraw atrakcyjność wizualną, ustawiając kolory i dostosowując obramowania:
```java
import com.aspose.slides.*;

// Ustaw różne kolory dla sektorów serii.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Powtórz tę czynność dla innych punktów danych, używając innych kolorów i stylów.
```

### Konfigurowanie niestandardowych etykiet danych
Dopasuj etykiety dla każdego punktu danych:
```java
import com.aspose.slides.*;

// Skonfiguruj etykiety niestandardowe.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Włącz linie pomocnicze dla etykiet.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Ustaw kąt obrotu i zapisz prezentację
Zakończ wykres kołowy, ustawiając kąt obrotu i zapisując prezentację:
```java
import com.aspose.slides.*;

// Ustaw kąt obrotu.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Zapisz prezentację do pliku.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Wniosek
W tym samouczku nauczyłeś się, jak tworzyć i dostosowywać wykresy kołowe za pomocą Aspose.Slides for Java. Wykonując te kroki, możesz ulepszyć swoje prezentacje za pomocą atrakcyjnych wizualnie wizualizacji danych. Jeśli masz jakieś pytania lub potrzebujesz dalszej pomocy, skontaktuj się z nami.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}