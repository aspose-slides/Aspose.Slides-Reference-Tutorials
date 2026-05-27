---
date: '2026-03-07'
description: Dowiedz się, jak tworzyć wykres pierścieniowy w Javie przy użyciu Aspose.Slides.
  Ten przewodnik krok po kroku obejmuje konfigurację zależności Maven Aspose Slides,
  konfigurację wykresu oraz zapisywanie prezentacji.
keywords:
- create doughnut charts Java
- Aspose.Slides Java guide
- Java data visualization
title: Tworzenie wykresu pierścieniowego w Javie z przewodnikiem Aspose.Slides
url: /pl/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresu pierścieniowego w Javie – przewodnik Aspose.Slides

## Wprowadzenie

Tworzenie **doughnut chart** programowo może zamienić surowe liczby w przyciągającą wzrok wizualizację, która od razu opowiada historię. W Javie **Aspose.Slides** upraszcza ten proces, umożliwiając generowanie wykresów gotowych do prezentacji bez konieczności otwierania PowerPointa. W tym samouczku nauczysz się, jak **create doughnut chart java** krok po kroku — od skonfigurowania zależności Maven Aspose Slides, przez dostosowanie serii, kategorii, aż po zapisanie prezentacji.

Po zakończeniu tego przewodnika będziesz mógł osadzać dynamiczne wykresy pierścieniowe w dowolnym pliku PPTX, idealne do raportów, pulpitów nawigacyjnych lub automatycznych zestawów slajdów.

### Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.Slides for Java  
- **Główne zadanie?** Utworzyć wykres pierścieniowy w Javie w pliku PPTX  
- **Jak dodać bibliotekę?** Użyj zależności Maven Aspose Slides (lub Gradle)  
- **Minimalna wersja Javy?** JDK 16 lub wyższa  
- **Czy mogę dostosować kolory i etykiety?** Tak, API zapewnia pełną kontrolę formatowania  

## Co to jest wykres pierścieniowy i dlaczego go używać?

Wykres pierścieniowy to wariant wykresu kołowego z pustym środkiem, co pozwala wyświetlać wiele serii danych w koncentrycznych pierścieniach. Dzięki temu idealnie nadaje się do porównywania części całości w kilku kategoriach — np. sprzedaży według regionu w kolejnych kwartałach lub alokacji budżetu w różnych działach.

## Dlaczego używać Aspose.Slides dla Javy?

- **Brak wymogu instalacji Office** – generuj pliki PPTX na dowolnym serwerze.  
- **Bogate API** – pełna kontrola nad typami wykresów, punktami danych i stylizacją.  
- **Wysoka wydajność** – zoptymalizowane pod kątem dużych prezentacji.  
- **Wieloplatformowość** – działa na Windows, Linux i macOS.

## Wymagania wstępne

- **Wymagane biblioteki:**  
  - Aspose.Slides for Java w wersji 25.4 lub nowszej.  

- **Konfiguracja środowiska:**  
  - JDK 16 lub wyższa.  
  - Ulubione IDE (IntelliJ IDEA, Eclipse, NetBeans itp.).  

- **Wymagania wiedzy:**  
  - Podstawy programowania w Javie.  
  - Znajomość Maven lub Gradle do zarządzania zależnościami.

## Zależność Maven Aspose Slides

Dodaj następującą zależność Maven do swojego `pom.xml`. To jest **maven aspose slides dependency**, której potrzebujesz, aby pobrać bibliotekę do projektu.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Jeśli wolisz Gradle, użyj poniższego odpowiedniego fragmentu.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Możesz także pobrać plik JAR bezpośrednio ze strony wydania:  
[ Aspose.Slides for Java releases ](https://releases.aspose.com/slides/java/)

### Uzyskiwanie licencji

Aby usunąć znak wodny wersji ewaluacyjnej i odblokować pełny zestaw funkcji:

- **Bezpłatna wersja próbna** – rozpocznij od tymczasowej licencji.  
- **Licencja tymczasowa** – zamów ją na [stronie Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licencja komercyjna** – zakup do użytku produkcyjnego.

Zastosuj licencję w swoim kodzie:

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Przewodnik implementacji

### Inicjalizacja prezentacji i dodawanie wykresu pierścieniowego

Najpierw utwórz lub załaduj prezentację i dodaj wykres pierścieniowy do pierwszego slajdu.

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurowanie skoroszytu danych wykresu i czyszczenie istniejących danych

Następnie uzyskaj skoroszyt, który zasila wykres, i wyczyść wszelkie domyślne serie lub kategorie.

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Dodawanie serii do wykresu

Teraz dodamy do 15 serii. Każda seria może być dostosowana — tutaj ustawiamy eksplozję, rozmiar otworu pierścieniowego i kąt pierwszego wycinka.

```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Customize the series
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Dodawanie kategorii i punktów danych

Utworzymy 15 kategorii i wypełnimy każdą serię punktami danych. Ostatnia seria otrzymuje specjalne formatowanie etykiet.

```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Data point format settings
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Label formatting for the last series
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

        // Adjust display options
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Adjust label position
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Zapisywanie prezentacji

Na koniec zapisz zaktualizowaną prezentację na dysku.

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Typowe problemy i rozwiązania

- **Licencja nie znaleziona** – sprawdź, czy ścieżka do `license.lic` jest prawidłowa i plik jest czytelny.  
- **Wykres jest pusty** – upewnij się, że wyczyściłeś istniejące serie/kategorie przed dodaniem nowych.  
- **Nieprawidłowe kolory** – sprawdź, czy `FillType.Solid` jest ustawiony zarówno dla wypełnienia, jak i formatu linii.  
- **Wydajność przy wielu seriach** – ogranicz liczbę serii/kategorii lub ponownie użyj komórek skoroszytu.

## Najczęściej zadawane pytania

**Q: Czy mogę wygenerować wykres pierścieniowy bez istniejącego pliku PPTX?**  
A: Tak, utwórz `new Presentation()` aby rozpocząć od pustego zestawu slajdów.

**Q: Czy Aspose.Slides obsługuje eksport do PDF?**  
A: Absolutnie. Po utworzeniu wykresu wywołaj `pres.save("output.pdf", SaveFormat.Pdf);`.

**Q: Jak zmienić rozmiar otworu pierścieniowego?**  
A: Użyj `series.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`, gdzie wartość wynosi od 0‑100.

**Q: Czy można dodać etykiety danych do wszystkich serii, a nie tylko do ostatniej?**  
A: Tak, przenieś blok formatowania etykiet poza warunek `if (i == ...)` i zastosuj go do każdego `dataPoint`.

**Q: Jakie wersje Javy są wspierane?**  
A: Aspose.Slides 25.4 wspiera JDK 16 i nowsze. Starsze wersje JDK wymagają odpowiedniego klasyfikatora.

---

**Ostatnia aktualizacja:** 2026-03-07  
**Testowano z:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}