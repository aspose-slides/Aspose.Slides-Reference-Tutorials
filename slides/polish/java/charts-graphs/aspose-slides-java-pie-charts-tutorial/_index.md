---
date: '2026-07-17'
description: Dowiedz się, jak obrócić pie chart, dostosować kolory pie chart oraz
  wyeksportować slajd do PDF przy użyciu Aspose.Slides for Java – kompletny przewodnik
  po wizualizacji danych.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Obróć pie chart i dostosuj kolory pie chart przy użyciu Aspose.Slides
  for Java. Dowiedz się, jak wyeksportować slajd do PDF i pracować z chart data worksheet.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Obróć pie chart i dostosuj kolory w Javie – przewodnik Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Jak obrócić pie chart i dostosować kolory w Javie z Aspose.Slides
url: /pl/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów kołowych przy użyciu Aspose.Slides dla Javy: Kompletny samouczek

## Wprowadzenie
W tym przewodniku dowiesz się, jak **obrócić wykres kołowy**, dostosować kolor każdego wycinka oraz wyeksportować gotowy slajd do PDF — wszystko przy użyciu Aspose.Slides dla Javy. Niezależnie od tego, czy tworzysz pulpit sprzedażowy, raport finansowy, czy inną prezentację opartą na danych, opanowanie tych technik pozwoli Ci dostarczyć przejrzyste, przyciągające wzrok wizualizacje bez konieczności korzystania z Microsoft Office. Przygotujmy narzędzia i zanurzmy się w temat.

## Szybkie odpowiedzi
- **Jaką klasę używa się do rozpoczęcia nowej prezentacji?** `Presentation` z `com.aspose.slides`.
- **Które wywołanie API dodaje wykres kołowy?** `slide.addChart(ChartType.Pie, …)`.
- **Jak nadać każdej części unikalny kolor?** Wywołaj `series.setColorVaried(true)` i ustaw wypełnienia stałe dla poszczególnych punktów danych.
- **Jaką metodę użyć do obrotu wykresu?** `chart.setRotationAngle(double)` – użyj stopni od 0 do 360.
- **Czy slajd można wyeksportować do PDF?** Tak, wywołaj `presentation.save("output.pdf", SaveFormat.Pdf)`.

## Co oznacza „customize pie chart colors”?
Dostosowanie kolorów wykresu kołowego polega na przypisaniu odrębnych kolorów wypełnienia każdemu wycinkowi koła, co poprawia czytelność i oddziaływanie wizualne. W Aspose.Slides osiąga się to, włączając zróżnicowane kolory, a następnie ustawiając stałe kolory wypełnienia dla poszczególnych punktów danych. Dzięki temu każdy segment danych wyraźnie wyróżnia się w prezentacji.

## Dlaczego warto używać Aspose.Slides dla Javy do tworzenia wykresów kołowych?
Aspose.Slides obsługuje **ponad 150 typów wykresów** i potrafi wyrenderować 300‑stronnicową prezentację w czasie krótszym niż **5 sekund** na typowym serwerze, bez konieczności instalacji Microsoft Office. Biblioteka działa na Windows, Linux i macOS, zapewniając elastyczność wieloplatformową dla każdego projektu wizualizacji danych w Javie.

## Wymagania wstępne
- **Aspose.Slides for Java** ≥ 25.4
- **JDK** 16 lub nowszy
- IDE, takie jak IntelliJ IDEA, Eclipse lub NetBeans
- Podstawowa znajomość Javy oraz Maven lub Gradle

## Konfiguracja Aspose.Slides dla Javy
Dodaj bibliotekę do konfiguracji swojego projektu.

**Maven**  
Dodaj ten fragment do pliku `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Umieść poniższy kod w pliku `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Bezpośrednie pobranie**  
Jeśli wolisz ręczne podejście, pobierz najnowszy plik JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Kroki uzyskania licencji
- **Free Trial** – bezpłatna wersja próbna – przetestuj wszystkie funkcje bez kosztów.  
- **Temporary License** – licencja tymczasowa – wydłuż limit wersji próbnej na krótki okres.  
- **Purchase** – zakup – uzyskaj stałą licencję do użytku produkcyjnego.

**Podstawowa inicjalizacja i konfiguracja**  
Klasa `Presentation` reprezentuje plik PowerPoint w pamięci i udostępnia metody do manipulacji slajdami.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Przewodnik implementacji
Poniżej znajdziesz krok‑po‑kroku opis, który obejmuje wszystko, od tworzenia slajdu po obrót końcowego wykresu kołowego.

### Inicjalizacja prezentacji i slajdu
Utwórz nową instancję `Presentation` i pobierz pierwszy slajd, który posłuży jako płótno wykresu.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Dodaj wykres kołowy do slajdu
`addChart` dodaje kształt wykresu określonego typu do slajdu w podanych współrzędnych.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Ustaw tytuł wykresu
`setTitle` przypisuje tekstowy tytuł wykresowi i pozycjonuje go centralnie.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfiguracja etykiet danych dla serii
`setShowValue(true)` włącza wyświetlanie wartości liczbowych na każdym punkcie danych serii.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Przygotowanie arkusza danych wykresu
`ChartDataWorkbook` przechowuje podstawową tabelę danych, która zasila serie i kategorie wykresu.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Dodaj kategorie do wykresu
`addCategory` tworzy nową etykietę kategorii dla serii danych wykresu.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Dodaj serię i wypełnij punkty danych
`addSeries` tworzy serię danych, a `addDataPointForBarSeries` wstawia wartości liczbowe dla każdej kategorii.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Dostosowanie kolorów i obramowań serii
`setColorVaried(true)` włącza kolory per‑wycinek, a `setFillFormat` przypisuje stałe wypełnienie każdemu punktowi danych.  
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Konfiguracja niestandardowych etykiet danych
`setDataLabelFormat` dostosowuje wygląd etykiety, pozycję i czcionkę, aby uzyskać czytelniejsze adnotacje wykresu.  
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Ustaw kąt obrotu i zapisz prezentację
`setRotationAngle` obraca cały wykres kołowy, a `save` zapisuje prezentację do pliku.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Jak obrócić wykres kołowy?
Wczytaj obiekt wykresu, wywołaj `chart.setRotationAngle(45.0)` (lub dowolną wartość w stopniach), a następnie zapisz prezentację. Obrót wykresu kołowego przesuwa kąt początkowy, co pozwala podkreślić wybrany segment bez zmiany danych. To pojedyncze wywołanie metody działa dla każdej instancji `Chart` w Aspose.Slides. Możesz także połączyć obrót z różnorodnymi kolorami wycinków, aby przyciągnąć uwagę do najważniejszego punktu danych.

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **Slices all appear the same color** | `setColorVaried(true)` not called | Upewnij się, że włączyłeś zróżnicowane kolory w grupie serii. |
| **Data labels not showing** | `showValue` flag disabled | Wywołaj `setShowValue(true)` na formacie etykiety. |
| **Rotation has no effect** | Using an older Aspose.Slides version | Zaktualizuj do wersji 25.4 lub nowszej. |
| **License exception at runtime** | Missing or invalid license file | Załaduj licencję przy pomocy `License license = new License(); license.setLicense("Aspose.Slides.lic");` przed utworzeniem obiektu `Presentation`. |

## Najczęściej zadawane pytania

**Q: Jak uzyskać licencję Aspose.Slides dla Javy?**  
A: Poproś o bezpłatną wersję próbną na stronie Aspose, a następnie zakup stałą licencję. Załaduj ją w czasie wykonywania, jak pokazano w tabeli „Typowe problemy i rozwiązania”.

**Q: Czy mogę używać tego kodu ze starszymi wersjami JDK?**  
A: API wymaga JDK 16 lub wyższego; starsze wersje nie są obsługiwane.

**Q: Czy istnieje możliwość wyeksportowania wykresu jako obrazu zamiast PPTX?**  
A: Tak — po renderowaniu wywołaj `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);`.

**Q: Co zrobić, jeśli potrzebuję więcej niż jednej serii w wykresie kołowym?**  
A: Wykresy kołowe są przeznaczone do jednej serii danych; w przypadku wielu serii rozważ użycie wykresu pierścieniowego (doughnut).

**Q: Czy Aspose.Slides działa na serwerach Linux?**  
A: Absolutnie — Aspose.Slides dla Javy jest niezależny od platformy i działa na każdym systemie operacyjnym z kompatybilnym JDK.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Jak tworzyć wykresy kołowe w prezentacjach Java przy użyciu Aspose.Slides: Kompletny przewodnik](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Mistrzostwo wykresów kołowych w Javie z Aspose.Slides: Kompletny przewodnik](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Obracanie tekstów wykresu w Javie z Aspose.Slides: Kompletny przewodnik](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}