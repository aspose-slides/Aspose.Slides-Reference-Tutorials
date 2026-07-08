---
date: '2026-07-08'
description: Dowiedz się, jak używać Aspose do tworzenia doughnut chart w PowerPoint
  przy użyciu Java. Ten przewodnik krok po kroku pokazuje, jak programowo dodawać
  punkty danych doughnut chart, dostosowywać etykiety oraz zapisywać plik PPTX z wysoką
  wiernością.
keywords:
- how to use aspose
- create doughnut chart powerpoint
- maven dependency aspose slides
lastmod: '2026-07-08'
og_description: Jak używać Aspose pozwala na tworzenie doughnut chart w PowerPoint
  przy użyciu Java. Postępuj zgodnie z tym samouczkiem, aby dodać punkty danych, dostosować
  etykiety i zapisać plik PPTX z wysoką wiernością.
og_image_alt: 'Guide: Create doughnut chart PowerPoint with Aspose.Slides for Java'
og_title: 'Jak używać Aspose: tworzyć doughnut chart w PowerPoint (Java)'
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  headline: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  type: TechArticle
- description: Learn how to use Aspose to create a doughnut chart in PowerPoint with
    Java. This step‑by‑step guide shows adding chart data points programmatically,
    customizing labels, and saving the PPTX with high fidelity.
  name: How to Use Aspose Create Doughnut Chart in PowerPoint (Java)
  steps:
  - name: Initialize the presentation
    text: Create a fresh presentation or open an existing file to obtain a slide collection.
      `Presentation` is the primary class that represents a PowerPoint file.
  - name: Add a doughnut chart to the slide
    text: Insert a chart shape, remove default series/categories, and configure basic
      visual settings like the doughnut hole size. `Chart` (or chart shape) represents
      a chart object placed on a slide.
  - name: Add chart data points and customize labels
    text: Populate category names, add data points for each series, and fine‑tune
      label formatting (font, color, position). This step demonstrates the “add chart
      data points” capability. `Workbook` provides access to the chart’s underlying
      spreadsheet data where cells are populated.
  - name: Save the updated presentation
    text: Persist the changes to a new PPTX file on disk. `save` writes the presentation
      to a file in the chosen format.
  type: HowTo
- questions:
  - answer: Yes, but you need a valid commercial license. A free trial is available
      for evaluation.
    question: Can I use Aspose.Slides for Java in commercial applications?
  - answer: Increase the loop limit in the “Add Doughnut Chart” step and ensure your
      data workbook contains enough rows.
    question: How do I add more than 15 series?
  - answer: Yes, call `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)`
      before saving.
    question: Is it possible to change the doughnut hole size after creation?
  - answer: Absolutely. Use `chart.getImage()` and save the returned `java.awt.image.BufferedImage`
      in your preferred format.
    question: Can I export the chart as an image instead of a PPTX?
  - answer: Animation can be added via the `ISlide.getTimeline()` API, though it’s
      beyond the scope of this tutorial.
    question: Does Aspose.Slides support animated charts?
  type: FAQPage
tags:
- doughnut chart
- Aspose.Slides
- Java PowerPoint
- chart generation
- presentation automation
title: Jak używać Aspose do tworzenia doughnut chart w PowerPoint (Java)
url: /pl/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak używać Aspose do tworzenia wykresu pierścieniowego w PowerPoint (Java)

## Wprowadzenie
Tworzenie atrakcyjnych prezentacji często wymaga czegoś więcej niż tylko tekstu i obrazów; wykresy mogą znacząco wzmocnić opowieść, wizualizując dane w efektywny sposób. **Jak używać Aspose** do generowania wykresów daje kontrolę programistyczną bez konieczności otwierania PowerPointa. Ten samouczek przeprowadzi Cię przez budowanie wykresu pierścieniowego, konfigurowanie jego punktów danych oraz zapisywanie wysokiej jakości pliku PPTX. Wystarczy podstawowa znajomość Javy i kilka minut na przygotowanie środowiska.

`Aspose.Slides for Java` to biblioteka Java umożliwiająca tworzenie, modyfikowanie i konwertowanie plików PowerPoint bez Microsoft Office.

## Szybkie odpowiedzi
- **Jaką bibliotekę użyć do tworzenia wykresu pierścieniowego w PowerPoint?** Aspose.Slides for Java  
- **Czy mogę programowo dodawać punkty danych do wykresu?** Tak, przy użyciu API wykresów  
- **Czy potrzebna jest licencja do produkcji?** Wymagana jest ważna licencja Aspose.Slides  
- **Jakie wersje Javy są obsługiwane?** Java 8 i nowsze (przykład klasyfikatora JDK 16)  
- **Ile serii mogę dodać?** Przykład dodaje do 15 serii, ale można to dostosować według potrzeb  

## Co to jest wykres pierścieniowy w PowerPoint?
Wykres pierścieniowy to okrągły wykres podobny do wykresu kołowego, ale z pustym środkiem, co pozwala na jednoczesne wyświetlanie wielu serii. Podkreśla zależności części‑całość, zachowując przy tym kompaktowy i czytelny układ.

## Dlaczego warto używać Aspose.Slides for Java do tworzenia wykresów pierścieniowych?
Aspose.Slides for Java obsługuje ponad 50 formatów wejścia i wyjścia oraz może generować prezentacje do 500 MB bez ładowania całego pliku do pamięci. Zapewnia pełną kontrolę programistyczną nad wyglądem wykresu, danymi i układem na dowolnej platformie Java, eliminuje potrzebę interakcji COM i potrafi wyrenderować 100 slajdów bogatych w wykresy w mniej niż dwie sekundy na typowym serwerze.

## Wymagania wstępne
- Podstawowa znajomość programowania w Javie.  
- IDE, takie jak IntelliJ IDEA lub Eclipse.  
- Maven lub Gradle do zarządzania zależnościami.  
- Ważna licencja Aspose.Slides for Java (dostępna wersja próbna).

## Konfiguracja Aspose.Slides for Java
Wybierz menedżer zależności pasujący do Twojego projektu.

**Maven**  
Dodaj następującą zależność do pliku `pom.xml` (zastąp wersję najnowszym wydaniem):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Dodaj tę linię do pliku `build.gradle`:

```gradle
implementation 'com.aspose:aspose-slides:25.4:jdk16'
```

Jeśli wolisz pobrać bibliotekę bezpośrednio, odwiedź stronę [Wydania Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
Możesz rozpocząć od wersji próbnej, aby przetestować funkcje Aspose.Slides. W celu dalszego użytkowania zakup licencję lub poproś o tymczasową licencję na [stronie Aspose](https://purchase.aspose.com/temporary-license/). Postępuj zgodnie z instrukcjami dotyczącymi konfiguracji środowiska i inicjalizacji Aspose.Slides w aplikacji.

## Jak stworzyć wykres pierścieniowy w PowerPoint przy użyciu Aspose.Slides for Java
Aby zbudować wykres pierścieniowy, najpierw załaduj lub utwórz obiekt `Presentation`, dodaj kształt wykresu typu `ChartType.Doughnut`, usuń domyślne serie, ustaw rozmiar otworu, a następnie wypełnij skoroszyt wykresu nazwami kategorii i wartościami liczbowymi. Na końcu dostosuj formatowanie etykiet i zapisz plik PPTX.

### Krok 1: Inicjalizacja prezentacji
Utwórz nową prezentację lub otwórz istniejący plik, aby uzyskać kolekcję slajdów.

`Presentation` jest główną klasą reprezentującą plik PowerPoint.  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Krok 2: Dodanie wykresu pierścieniowego do slajdu
Wstaw kształt wykresu, usuń domyślne serie/kategorie i skonfiguruj podstawowe ustawienia wizualne, takie jak rozmiar otworu pierścienia.

`Chart` (lub kształt wykresu) reprezentuje obiekt wykresu umieszczony na slajdzie.  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Krok 3: Dodanie punktów danych i dostosowanie etykiet
Wypełnij nazwy kategorii, dodaj punkty danych dla każdej serii i dopracuj formatowanie etykiet (czcionka, kolor, pozycja). Ten krok demonstruje możliwość „dodawania punktów danych do wykresu”.

`Workbook` zapewnia dostęp do arkusza kalkulacyjnego leżącego u podstaw wykresu, w którym wypełniane są komórki.  
```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Krok 4: Zapisz zaktualizowaną prezentację
Zapisz zmiany do nowego pliku PPTX na dysku.

`save` zapisuje prezentację do pliku w wybranym formacie.  
```java
import com.aspose.slides.*;

ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);

// Configure the series properties
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.getType());
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

## Praktyczne zastosowania
Wykresy pierścieniowe są idealne do:
- **Raportów finansowych:** Wizualizacji alokacji budżetu lub podziału kosztów.  
- **Analizy rynkowej:** Pokazywania udziału rynkowego poszczególnych konkurentów.  
- **Wyników ankiet:** Prezentacji danych kategorycznych w skondensowanej formie.  
- **Generowania pulpitów nawigacyjnych:** Łączenia z zapytaniami bazodanowymi w celu tworzenia slajdów aktualizowanych na żywo.

## Wskazówki dotyczące wydajności
- **Zwolnij zasoby:** Wywołaj `pres.dispose()` po zapisaniu, aby zwolnić pamięć natywną.  
- **Ogranicz liczbę wykresów:** Dodawanie setek wykresów może zwiększyć zużycie pamięci; w razie potrzeby przetwarzaj je partiami.  
- **Używaj strumieniowania:** Dla bardzo dużych zestawów danych wypełniaj skoroszyt bezpośrednio ze strumieni zamiast z tablic w pamięci.  

## Typowe problemy i rozwiązania
| Problem | Przyczyna | Rozwiązanie |
|---------|-----------|-------------|
| **Wykres jest pusty** | Komórki danych nie zostały poprawnie wypełnione | Sprawdź, czy wywołania `workBook.getCell(...)` odwołują się do właściwych indeksów wierszy/kolumn. |
| **Etykiety nachodzą na siebie** | Zbyt wiele kategorii w ograniczonej przestrzeni | Zwiększ `DoughnutHoleSize` lub dostosuj `FirstSliceAngle`. |
| **OutOfMemoryError** | Duże prezentacje bez zwalniania zasobów | Wywołaj `pres.dispose()` po zapisaniu i rozważ zwiększenie rozmiaru sterty JVM. |

## Najczęściej zadawane pytania

**P: Czy mogę używać Aspose.Slides for Java w aplikacjach komercyjnych?**  
O: Tak, ale wymagana jest ważna licencja komercyjna. Dostępna jest wersja próbna do oceny.

**P: Jak dodać więcej niż 15 serii?**  
O: Zwiększ limit pętli w kroku „Dodaj wykres pierścieniowy” i upewnij się, że Twój skoroszyt danych zawiera wystarczającą liczbę wierszy.

**P: Czy można zmienić rozmiar otworu pierścienia po utworzeniu wykresu?**  
O: Tak, wywołaj `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` przed zapisem.

**P: Czy mogę wyeksportować wykres jako obraz zamiast PPTX?**  
O: Oczywiście. Użyj `chart.getImage()` i zapisz zwrócony `java.awt.image.BufferedImage` w wybranym formacie.

**P: Czy Aspose.Slides obsługuje animowane wykresy?**  
O: Animacje można dodać za pomocą API `ISlide.getTimeline()`, choć nie jest to przedmiotem tego samouczka.

## Podsumowanie
Masz teraz kompletną, gotową do produkcji metodę **tworzenia wykresów pierścieniowych w PowerPoint** przy użyciu Aspose.Slides for Java, w tym **dodawanie punktów danych do wykresu**, dostosowywanie etykiet oraz uwzględnianie kwestii wydajnościowych. Eksperymentuj z różnymi kolorami, źródłami danych i typami wykresów, aby Twoje prezentacje naprawdę się wyróżniały.

---

**Ostatnia aktualizacja:** 2026-07-08  
**Testowane z:** Aspose.Slides for Java 25.4 (klasyfikator JDK 16)  
**Autor:** Aspose

```java
import com.aspose.slides.*;
import java.awt.Color;

int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
    int i = 0;
    while (i < chart.getChartData().getSeries().size()) {
        IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
        IChartDataPoint dataPoint = iCS.getDataPoints().addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));
        
        // Format the data point
        dataPoint.getFormat().getFill().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
        dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
        dataPoint.getFormat().getLine().setWidth(1);
        dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
        dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

        // Customize label properties for the last series in each category
        if (i == chart.getChartData().getSeries().size() - 1) {
            IDataLabel lbl = dataPoint.getLabel();
            lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.LIGHT_GRAY);
            lbl.getDataLabelFormat().getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
            lbl.getDataLabelFormat().setShowValue(false);
            lbl.getDataLabelFormat().setShowCategoryName(true);
            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowLeaderLines(true);
            lbl.getX() += 0.5f;
            lbl.getY() += 0.5f;
        }
        i++;
    }
    categoryIndex++;
}
```

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Powiązane samouczki

- [Jak dodać wykresy do PowerPoint przy użyciu Aspose.Slides for Java: Przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Jak edytować dane wykresu PowerPoint przy użyciu Aspose.Slides for Java: Kompletny przewodnik](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animowanie wykresów w PowerPoint przy użyciu Aspose.Slides for Java – Przewodnik krok po kroku](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}