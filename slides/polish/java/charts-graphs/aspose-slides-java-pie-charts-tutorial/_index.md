---
date: '2026-02-19'
description: Dowiedz się, jak tworzyć wykres kołowy w Javie przy użyciu Aspose.Slides
  oraz dostosowywać kolory wykresu kołowego, dodawać serie wykresu, pracować z arkuszem
  danych wykresu i ustawiać kąt obrotu.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Jak dostosować kolory wykresu kołowego w Javie przy użyciu Aspose.Slides –
  Kompletny przewodnik
url: /pl/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresów kołowych przy użyciu Aspose.Slides for Java: Kompletny samouczek

## Wprowadzenie
Tworzenie dynamicznych i atrakcyjnych wizualnie prezentacji jest kluczowe dla przekazywania istotnych informacji. Dzięki Aspose.Slides for Java możesz płynnie integrować złożone wykresy, takie jak wykresy kołowe, w swoich slajdach, **customize pie chart colors**, i z łatwością ulepszać wizualizację danych. Ten obszerny przewodnik poprowadzi Cię krok po kroku przez proces tworzenia i dostosowywania wykresu kołowego przy użyciu Aspose.Slides Java, rozwiązując typowe wyzwania prezentacyjne z łatwością.

**Co się nauczysz:**
- Inicjalizacja prezentacji i dodawanie slajdów.
- Tworzenie i konfigurowanie wykresu kołowego na slajdzie.
- Ustawianie tytułów wykresu, etykiet danych oraz **customize pie chart colors**.
- Optymalizacja wydajności i efektywne zarządzanie zasobami.
- Integracja Aspose.Slides w projektach Java przy użyciu Maven lub Gradle.

Zacznijmy od upewnienia się, że masz wszystkie niezbędne narzędzia i wiedzę, aby móc podążać za instrukcją!

## Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do rozpoczęcia prezentacji?** `Presentation` z `com.aspose.slides`.
- **Która metoda dodaje wykres kołowy do slajdu?** `addChart(ChartType.Pie, …)`.
- **Jak włączyć różne kolory dla każdego kawałka?** Ustaw `setColorVaried(true)` na grupie serii.
- **Czy można obrócić wykres kołowy?** Tak, użyj `setRotationAngle(double)` na obiekcie wykresu.
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Licencja Aspose.Slides jest wymagana przy wdrożeniach komercyjnych.

## Co oznacza „customize pie chart colors”?
Customizing pie chart colors oznacza przypisywanie odrębnych kolorów wypełnienia do każdego kawałka koła, co poprawia czytelność i wpływ wizualny. W Aspose.Slides osiągasz to, włączając różne kolory, a następnie ustawiając stałe kolory wypełnienia dla poszczególnych punktów danych.

## Dlaczego używać Aspose.Slides for Java do tworzenia wykresów kołowych?
- **Pełna kontrola** nad wyglądem wykresu bez konieczności posiadania Microsoft Office.
- **Cross‑platform** kompatybilność – działa na Windows, Linux i macOS.
- **Bogate API** do wiązania danych, stylizacji i eksportu do PPTX, PDF lub obrazów.
- **Elastyczność licencji** – rozpocznij od darmowej wersji próbnej i zaktualizuj, gdy potrzebujesz pełnego zestawu funkcji.

## Wymagania wstępne
Przed przystąpieniem do tego samouczka upewnij się, że masz gotowe następujące elementy:

### Wymagane biblioteki, wersje i zależności
- **Aspose.Slides for Java**: wersja 25.4 lub nowsza.
- **Java Development Kit (JDK)**: wersja 16 lub wyższa.

### Wymagania dotyczące konfiguracji środowiska
- Środowisko programistyczne z zainstalowanym i skonfigurowanym Javą.
- Zintegrowane środowisko programistyczne (IDE) takie jak IntelliJ IDEA, Eclipse lub NetBeans.

### Wymagania wiedzy
- Podstawowa znajomość programowania w Javie.
- Znajomość Maven lub Gradle do zarządzania zależnościami.

## Konfiguracja Aspose.Slides for Java
Aby rozpocząć korzystanie z Aspose.Slides w projektach Java, musisz dodać bibliotekę jako zależność. Oto jak możesz to zrobić przy użyciu różnych narzędzi budowania:

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
Umieść następujące w pliku `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
Jeśli wolisz nie używać narzędzia budującego, pobierz najnowsze wydanie z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Kroki uzyskania licencji
- **Free Trial**: Rozpocznij od darmowej wersji próbnej, aby wypróbować funkcje Aspose.Slides.  
- **Temporary License**: Uzyskaj tymczasową licencję na rozszerzone użycie bez ograniczeń.  
- **Purchase**: Rozważ zakup, jeśli potrzebujesz długoterminowego dostępu.

**Basic Initialization and Setup**  
Aby rozpocząć korzystanie z Aspose.Slides, zainicjalizuj projekt, tworząc nowy obiekt prezentacji:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Przewodnik implementacji
Teraz rozbijmy proces dodawania i dostosowywania wykresu kołowego na przystępne kroki.

### Inicjalizacja prezentacji i slajdu
Rozpocznij od utworzenia nowej prezentacji i uzyskania dostępu do pierwszego slajdu. To będzie twoje płótno do tworzenia wykresów:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Dodaj wykres kołowy do slajdu
Wstaw wykres kołowy w określonej pozycji z domyślnym zestawem danych:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Ustaw tytuł wykresu
Dostosuj wykres, ustawiając i wyśrodkowując tytuł:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Skonfiguruj etykiety danych dla serii
Upewnij się, że etykiety danych wyświetlają wartości dla przejrzystości:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Przygotuj arkusz danych wykresu
Skonfiguruj arkusz danych wykresu, usuwając istniejące serie i kategorie:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Dodaj kategorie do wykresu
Zdefiniuj kategorie dla wykresu kołowego:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Dodaj serię i wypełnij punkty danych
Utwórz serię i wypełnij ją punktami danych – to miejsce, w którym **add chart series**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Dostosuj kolory serii i obramowania
Zwiększ atrakcyjność wizualną, ustawiając kolory i dostosowując obramowania – to bezpośrednio **customizes pie chart colors**:
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

### Skonfiguruj niestandardowe etykiety danych
Dopracuj etykiety dla każdego punktu danych:
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
Zakończ wykres kołowy, **set rotation angle** i zapisz plik:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Typowe problemy i rozwiązania
| Issue | Cause | Fix |
|-------|-------|-----|
| **Slices all appear the same color** | nie wywołano `setColorVaried(true)` | Upewnij się, że włączyłeś różne kolory w grupie serii. |
| **Data labels not showing** | flaga `showValue` wyłączona | Wywołaj `setShowValue(true)` na odpowiednim formacie etykiety. |
| **Rotation has no effect** | używana starsza wersja Aspose.Slides | Zaktualizuj do wersji 25.4 lub nowszej. |
| **License exception at runtime** | brakujący lub nieprawidłowy plik licencji | Załaduj licencję przy użyciu `License license = new License(); license.setLicense("Aspose.Slides.lic");` przed utworzeniem obiektu `Presentation`. |

## Najczęściej zadawane pytania

**Q: How do I obtain an Aspose.Slides license for Java?**  
A: Możesz poprosić o darmową wersję próbną na stronie Aspose, a następnie zakupić stałą licencję. Załaduj ją w czasie wykonywania, jak pokazano w tabeli Typowe problemy i rozwiązania.

**Q: Can I use this code with older JDK versions?**  
A: API wymaga JDK 16 lub wyższego; starsze wersje nie są obsługiwane.

**Q: Is it possible to export the chart as an image instead of PPTX?**  
A: Tak, wywołaj `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` po renderowaniu.

**Q: What if I need to add more than one series to a pie chart?**  
A: Wykresy kołowe zazwyczaj wyświetlają jedną serię; dla wielu serii rozważ wykres pierścieniowy (doughnut).

**Q: Does the library work on Linux servers?**  
A: Absolutnie – Aspose.Slides for Java jest niezależny od platformy i działa na każdym systemie operacyjnym z kompatybilnym JDK.

---

**Last Updated:** 2026-02-19  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}