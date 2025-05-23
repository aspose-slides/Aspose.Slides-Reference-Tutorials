---
"date": "2025-04-17"
"description": "Dowiedz się, jak tworzyć oszałamiające wykresy pierścieniowe w Javie za pomocą Aspose.Slides. Ten kompleksowy przewodnik obejmuje inicjalizację, konfigurację danych i zapisywanie prezentacji."
"title": "Tworzenie wykresów pierścieniowych w Javie przy użyciu Aspose.Slides&#58; Kompleksowy przewodnik"
"url": "/pl/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów pierścieniowych w Javie przy użyciu Aspose.Slides: przewodnik krok po kroku

## Wstęp

dzisiejszym środowisku opartym na danych skuteczna wizualizacja informacji jest kluczem do zwiększenia zrozumienia i zaangażowania. Podczas gdy tworzenie profesjonalnych wykresów programowo może wydawać się trudne, szczególnie w Javie, ten przewodnik przeprowadzi Cię przez korzystanie z Aspose.Slides dla Javy, aby bez wysiłku tworzyć wykresy pierścieniowe.

Dzięki wykonywaniu tych kroków programiści zdobędą praktyczne doświadczenie w manipulowaniu slajdami prezentacji i płynnym integrowaniu wizualizacji danych.

**Najważniejsze wnioski:**
- Zainicjuj obiekt Presentation przy użyciu Aspose.Slides Java.
- Konfiguruj dane wykresu i zarządzaj istniejącymi seriami lub kategoriami.
- Dodawaj i dostosowuj serie i kategorie do swoich wykresów.
- Formatuj i wyświetlaj punkty danych w sposób efektywny.
- Łatwe zapisywanie prezentacji w różnych formatach.

Zanim rozpoczniesz wdrażanie, upewnij się, że masz wszystko, co jest potrzebne do rozpoczęcia.

## Wymagania wstępne

Aby skorzystać z tego samouczka, upewnij się, że posiadasz:

- **Wymagane biblioteki:**
  - Aspose.Slides dla Java w wersji 25.4 lub nowszej.
  
- **Konfiguracja środowiska:**
  - W systemie zainstalowany jest JDK 16 lub nowszy.
  - Środowisko IDE, takie jak IntelliJ IDEA, Eclipse lub NetBeans.

- **Wymagania wstępne dotyczące wiedzy:**
  - Podstawowa znajomość koncepcji programowania w Javie.
  - Znajomość zarządzania zależnościami w projektach Maven lub Gradle.

## Konfigurowanie Aspose.Slides dla Java

Aby zintegrować Aspose.Slides ze swoim projektem, wykonaj następujące kroki w zależności od narzędzia do kompilacji:

**Konfiguracja Maven:**
Dodaj następującą zależność do swojego `pom.xml` plik:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Konfiguracja Gradle:**
Włącz do swojego `build.gradle` plik:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Bezpośrednie pobieranie:**
Alternatywnie możesz pobrać najnowszą wersję bezpośrednio z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji

Aby używać Aspose.Slides bez ograniczeń oceny:
- **Bezpłatna wersja próbna:** Zacznij od licencji tymczasowej, aby poznać pełen zakres funkcji.
- **Licencja tymczasowa:** Uzyskaj jeden za pośrednictwem [Strona internetowa Aspose](https://purchase.aspose.com/temporary-license/).
- **Zakup:** Rozważ zakup do stałego użytku.

Zastosuj licencję w swojej aplikacji Java za pomocą:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Przewodnik wdrażania

### Inicjalizacja prezentacji i wykresu

#### Przegląd
Zacznij od zainicjowania obiektu prezentacji i dodania wykresu pierścieniowego do pierwszego slajdu.

**Krok 1: Zainicjuj prezentację**
Załaduj istniejący plik PPTX lub utwórz nowy:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Krok 2: Dodaj wykres pierścieniowy**
Utwórz wykres na pierwszym slajdzie w określonych współrzędnych:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurowanie skoroszytu danych wykresu i czyszczenie istniejących serii/kategorii

#### Przegląd
Skonfiguruj skoroszyt danych wykresu i usuń wszelkie istniejące serie lub kategorie.

**Krok 1: Dostęp do skoroszytu danych wykresu**
Pobierz skoroszyt powiązany z wykresem:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Krok 2: Wyczyść istniejące serie i kategorie**
Upewnij się, że nie ma żadnych resztkowych punktów danych:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Dodawanie serii do wykresu

#### Przegląd
Możesz wypełnić swój wykres wieloma seriami, dostosowując wygląd i zachowanie każdej z nich.

**Krok 1: Dodaj serię iteracyjnie**
Pętla przez indeksy w celu dodania serii:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Dostosuj serię
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Dodawanie kategorii i punktów danych do wykresu

#### Przegląd
Konfiguruj kategorie i dodawaj punkty danych ze specjalnym formatowaniem etykiet.

**Krok 1: Dodaj kategorie**
Przejrzyj indeksy dla każdej kategorii:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Krok 2: Dodaj punkty danych do każdej serii**
Przejdź przez każdą serię dla bieżącej kategorii:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Ustawienia formatu punktu danych
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Formatowanie etykiet dla ostatniej serii
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Dostosuj opcje wyświetlania
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Dostosuj położenie etykiety
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Zapisywanie prezentacji

#### Przegląd
Po skonfigurowaniu wykresu zapisz prezentację w określonym katalogu.

**Krok 1: Zapisz prezentację**
Użyj `save` metoda zapisu zmian:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Wniosek

Teraz wiesz, jak tworzyć i dostosowywać wykresy pierścieniowe w Javie przy użyciu Aspose.Slides. Te kroki stanowią podstawę do integrowania zaawansowanych wizualizacji danych w prezentacjach.

**Następne kroki:**
- Eksperymentuj z różnymi typami wykresów dostępnymi w Aspose.Slides.
- Odkryj dodatkowe opcje dostosowywania, takie jak kolory, czcionki i style, aby sprostać potrzebom Twojej marki.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}