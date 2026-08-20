---
date: '2026-08-16'
description: Dowiedz się, jak dodać doughnut charts w Java przy użyciu Aspose.Slides.
  Ten przewodnik krok po kroku obejmuje konfigurację zależności Maven, konfigurację
  wykresu, kolory, etykiety oraz zapisywanie pliku PPTX.
keywords:
- how to add doughnut
- java create chart pptx
- maven aspose slides dependency
- customize doughnut chart colors
lastmod: '2026-08-16'
og_description: Jak dodać doughnut charts w Java przy użyciu Aspose.Slides. Postępuj
  zgodnie z tym przewodnikiem, aby skonfigurować Maven, dostosować kolory, etykiety
  i generować pliki PPTX.
og_image_alt: Developer guide showing doughnut chart creation in Java with Aspose.Slides
og_title: Jak dodać doughnut chart w Java przy użyciu Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-08-16'
  description: Learn how to add doughnut charts in Java using Aspose.Slides. This
    step‑by‑step guide covers Maven dependency setup, chart configuration, colors,
    labels and saving the PPTX.
  headline: How to add doughnut chart in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Yes, instantiate `new Presentation()` to start from a blank slide deck,
      then add a chart as shown above.
    question: Can I generate a doughnut chart without a pre‑existing PPTX file?
  - answer: Absolutely. After creating the chart, call `pres.save("output.pdf", SaveFormat.Pdf);`
      to get a PDF version of the slide.
    question: Does Aspose.Slides support exporting to PDF?
  - answer: Use `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`
      where `value` ranges from 0 to 100.
    question: How do I change the doughnut hole size?
  - answer: Yes, move the label‑formatting block outside the `if (i == ...)` condition
      and apply it to each `dataPoint`.
    question: Is it possible to add data labels to all series, not just the last one?
  - answer: Aspose.Slides 25.4 supports JDK 16 and newer. Earlier JDKs require the
      appropriate classifier in the Maven dependency.
    question: What versions of Java are supported?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PPTX
- data visualization
title: Jak dodać doughnut chart w Java przy użyciu Aspose.Slides
url: /pl/java/charts-graphs/create-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak dodać wykres pierścieniowy w Javie z Aspose.Slides

## Wprowadzenie

Tworzenie **wykresu pierścieniowego** programowo może zamienić surowe liczby w przyciągającą uwagę wizualizację, która od razu opowiada historię. W Javie **Aspose.Slides** upraszcza ten proces, umożliwiając generowanie gotowych do prezentacji wykresów bez konieczności otwierania PowerPointa. W tym samouczku nauczysz się **jak dodać wykresy pierścieniowe** do pliku PPTX krok po kroku — od skonfigurowania zależności Maven Aspose Slides po dostosowanie serii, kategorii, kolorów i etykiet, a na końcu zapisanie prezentacji.

Po zakończeniu tego przewodnika będziesz w stanie osadzać dynamiczne wykresy pierścieniowe w dowolnym pliku PPTX, idealne do raportów, pulpitów nawigacyjnych lub automatycznych zestawów slajdów.

### Szybkie odpowiedzi
- **Jakiej biblioteki użyto?** Aspose.Slides for Java  
- **Główne zadanie?** Dodanie wykresu pierścieniowego w pliku PPTX  
- **Jak dodać bibliotekę?** Użyj zależności Maven Aspose Slides (lub Gradle)  
- **Minimalna wersja Javy?** JDK 16 lub wyższa  
- **Czy mogę dostosować kolory i etykiety?** Tak, API zapewnia pełną kontrolę formatowania  

## Czym jest wykres pierścieniowy i dlaczego go używać?

Wykres pierścieniowy jest wariacją wykresu kołowego z pustym środkiem, co pozwala na wyświetlanie wielu serii danych jako koncentrycznych pierścieni. **Wizualizuje części‑całości w kilku kategoriach, jednocześnie zachowując miejsce na dodatkowe informacje w środku.** Dzięki temu jest idealny do porównywania sprzedaży według regionów w wielu kwartałach, przydziałów budżetu pomiędzy działami lub dowolnego scenariusza, w którym trzeba przedstawić hierarchiczne dane proporcjonalne.

## Dlaczego używać Aspose.Slides dla Javy?

Możesz dodać wykres pierścieniowy bez instalowania Microsoft Office, a biblioteka obsługuje **ponad 50 + formatów wejściowych i wyjściowych**, jednocześnie radząc sobie z prezentacjami przekraczającymi 500 slajdów. Aspose.Slides zapewnia **do 3× szybsze renderowanie** w porównaniu z natywną automatyzacją Office na tym samym sprzęcie i działa na systemach Windows, Linux i macOS. Te wymierne korzyści oznaczają, że możesz generować duże zestawy slajdów na serwerach bez interfejsu graficznego z przewidywalną wydajnością.

## Wymagania wstępne

- **Wymagane biblioteki**  
  - Aspose.Slides for Java 25.4 lub nowsza (biblioteka umożliwiająca dodawanie wykresów pierścieniowych).  

- **Środowisko**  
  - JDK 16 lub wyższa zainstalowana na Twoim komputerze.  
  - IDE, takie jak IntelliJ IDEA, Eclipse lub NetBeans.  

- **Wiedza**  
  - Podstawowa składnia Javy i pojęcia obiektowo‑zorientowane.  
  - Znajomość Maven lub Gradle do zarządzania zależnościami.  

## Zależność Maven Aspose Slides

Dodaj następującą zależność Maven do swojego `pom.xml`. To jest **zależność maven aspose slides**, której potrzebujesz, aby pobrać bibliotekę do swojego projektu.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

Jeśli wolisz Gradle, użyj poniższego równoważnego fragmentu.

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Możesz również pobrać plik JAR bezpośrednio z oficjalnej strony wydania:  
[ Aspose.Slides for Java – wydania ](https://releases.aspose.com/slides/java/)

### Uzyskanie licencji

Aby usunąć znak wodny wersji ewaluacyjnej i odblokować pełny zestaw funkcji:

- **Bezpłatna wersja próbna** – rozpocznij od tymczasowej licencji.  
- **Licencja tymczasowa** – zamów ją ze [strony Aspose](https://purchase.aspose.com/temporary-license/).  
- **Licencja komercyjna** – zakup do użytku produkcyjnego.

Zastosuj licencję w swoim kodzie:

```java
License license = new License();
license.setLicense("path/to/license.lic");
```

## Przewodnik implementacji

### Inicjalizacja prezentacji i dodawanie wykresu pierścieniowego

Presentation jest klasą Aspose.Slides reprezentującą prezentację PowerPoint.  
Wczytaj istniejący plik PPTX lub utwórz nowy obiekt `Presentation`, a następnie dodaj wykres pierścieniowy do pierwszego slajdu.

```java
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 50, 50, 500, 400);
```

### Konfigurowanie skoroszytu danych wykresu i czyszczenie istniejących danych

Skoroszyt jest wewnętrznym arkuszem kalkulacyjnym przechowującym dane wykresu.  
Uzyskaj skoroszyt będący podstawą wykresu, a następnie wyczyść wszystkie domyślne serie lub kategorie, aby rozpocząć od czystego stanu.

```java
IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Dodawanie serii do wykresu

Seria reprezentuje zbiór punktów danych wykreślonych na wykresie.  
Możesz dodać maksymalnie 15 serii. Każda seria może być dostosowana — tutaj ustawiamy eksplozję, rozmiar otworu pierścieniowego i kąt pierwszego wycinka.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, i + 1, 0), chart.getType());
    series.getParentSeriesGroup().setExplosion(i * 5);
}
chart.getParentSeriesGroup().setDoughnutHoleSize((byte) 50);
chart.getParentSeriesGroup().setFirstSliceAngle(30);
```

### Dodawanie kategorii i punktów danych

Kategorie są etykietami dla każdego punktu danych wzdłuż osi wykresu.  
Utwórz 15 kategorii i wypełnij każdą serię punktem danych. Ostatnia seria otrzymuje specjalne formatowanie etykiet.

```java
for (int i = 0; i < 15; i++) {
    IChartCategory category = chart.getChartData().getCategories().add(wb.getCell(0, 0, i + 1));
    for (int j = 0; j < 15; j++) {
        IChartDataPoint dp = chart.getChartData().getSeries().get_Item(j).getDataPoints().addDataPointForDoughnutSeries(wb.getCell(0, j + 1, i + 1));
        dp.getValue().setData(wb.getCell(0, j + 1, i + 1).getDoubleValue());
    }
}
```

### Dostosowywanie kolorów i etykiet danych

`FillType.Solid` określa jednolity kolor wypełnienia elementów wykresu.  
Ustaw jednolite wypełnienie dla każdej serii i włącz etykiety danych. Dla ostatniej serii zmieniamy również kolor czcionki etykiety.

```java
for (int i = 0; i < 15; i++) {
    IChartSeries series = chart.getChartData().getSeries().get_Item(i);
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getFill().getSolidFillColor().setColor(Color.fromArgb(255, (i * 15) % 256, (i * 30) % 256));
    series.getDataPoints().forEach(dp -> dp.getLabel().setShowValue(true));
}
IChartSeries lastSeries = chart.getChartData().getSeries().get_Item(14);
lastSeries.getDataPoints().forEach(dp -> dp.getLabel().getFont().setColor(Color.Red));
```

### Zapisywanie prezentacji

`save` zapisuje prezentację do pliku w wybranym formacie.  
Zapisz zaktualizowaną prezentację na dysku w formacie PPTX lub wyeksportuj do PDF, jeśli jest to wymagane.

```java
pres.save("DoughnutChartDemo.pptx", SaveFormat.Pptx);
```

## Częste problemy i rozwiązania

- **Licencja nie znaleziona** – Zweryfikuj, czy ścieżka do `license.lic` jest poprawna i plik jest czytelny.  
- **Wykres jest pusty** – Upewnij się, że wyczyściłeś istniejące serie/kategorie przed dodaniem nowych.  
- **Nieprawidłowe kolory** – Potwierdź, że `FillType.Solid` jest ustawiony zarówno dla wypełnienia, jak i formatu linii.  
- **Wydajność przy wielu seriach** – Ogranicz liczbę serii/kategorii lub ponownie używaj komórek skoroszytu, aby utrzymać zużycie pamięci pod kontrolą.  

## Najczęściej zadawane pytania

**P: Czy mogę wygenerować wykres pierścieniowy bez istniejącego pliku PPTX?**  
O: Tak, utwórz `new Presentation()` aby rozpocząć od pustego zestawu slajdów, a następnie dodaj wykres jak pokazano powyżej.

**P: Czy Aspose.Slides obsługuje eksport do PDF?**  
O: Zdecydowanie. Po utworzeniu wykresu wywołaj `pres.save("output.pdf", SaveFormat.Pdf);`, aby uzyskać wersję PDF slajdu.

**P: Jak zmienić rozmiar otworu pierścieniowego?**  
O: Użyj `chart.getParentSeriesGroup().setDoughnutHoleSize((byte) value);`, gdzie `value` mieści się w przedziale od 0 do 100.

**P: Czy można dodać etykiety danych do wszystkich serii, a nie tylko do ostatniej?**  
O: Tak, przenieś blok formatowania etykiet poza warunek `if (i == ...)` i zastosuj go do każdego `dataPoint`.

**P: Jakie wersje Javy są obsługiwane?**  
O: Aspose.Slides 25.4 obsługuje JDK 16 i nowsze. Starsze wersje JDK wymagają odpowiedniego klasyfikatora w zależności Maven.

---

**Ostatnia aktualizacja:** 2026-08-16  
**Testowano z:** Aspose.Slides for Java 25.4 (klasyfikator jdk16)  
**Autor:** Aspose

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

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

```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Powiązane samouczki

- [Jak dodać wykres do PowerPoint przy użyciu Aspose.Slides dla Javy: przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Jak dostosować kolory wykresu kołowego w Javie z Aspose.Slides – kompletny przewodnik](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Animowanie kategorii wykresu PowerPoint przy użyciu Aspose.Slides dla Javy | przewodnik krok po kroku](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}