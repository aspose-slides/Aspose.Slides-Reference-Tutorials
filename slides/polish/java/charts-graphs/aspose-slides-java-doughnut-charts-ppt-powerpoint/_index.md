---
date: '2026-02-17'
description: Dowiedz się, jak tworzyć wykres pierścieniowy w PowerPoint przy użyciu
  Aspose.Slides for Java i programowo dodawać punkty danych wykresu. Postępuj według
  prostych kroków i przykładów kodu.
keywords:
- Aspose.Slides for Java
- dynamic doughnut charts PowerPoint
- Java PowerPoint chart creation
title: Utwórz wykres pierścieniowy w PowerPoint przy użyciu Aspose.Slides for Java
url: /pl/java/charts-graphs/aspose-slides-java-doughnut-charts-ppt-powerpoint/
weight: 1
---

 markdown formatting.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie wykresu pierścieniowego w PowerPoint przy użyciu Aspose.Slides for Java

## Wprowadzenie
Tworzenie atrakcyjnych prezentacji często wymaga czegoś więcej niż tylko tekstu i obrazów; wykresy mogą znacząco wzmocnić opowieść, wizualizując dane w efektywny sposób. Jednak wielu programistów ma trudności z integracją dynamicznych funkcji wykresów w plikach PowerPoint programowo. Ten samouczek pokazuje, jak **tworzyć wykres pierścieniowy w PowerPoint** przy użyciu Aspose.Slides for Java — potężnego narzędzia łączącego elastyczność i łatwość użycia.

**Czego się nauczysz:**
- Jak zainicjalizować prezentację przy użyciu Aspose.Slides for Java
- Przewodnik krok po kroku dodawania wykresu pierścieniowego do slajdów
- Konfigurowanie punktów danych i dostosowywanie właściwości etykiet
- Zapisywanie zmodyfikowanej prezentacji z wysoką wiernością

Zanim zaczniemy, upewnij się, że znasz podstawowe koncepcje programowania w Javie.

## Szybkie odpowiedzi
- **Jaką bibliotekę używać do tworzenia wykresu pierścieniowego w PowerPoint?** Aspose.Slides for Java
- **Czy mogę programowo dodawać punkty danych wykresu?** Tak, przy użyciu API wykresu
- **Czy potrzebna jest licencja do użytku produkcyjnego?** Wymagana jest ważna licencja Aspose.Slides
- **Jakie wersje Javy są obsługiwane?** Java 8 i nowsze (pokazany klasyfikator JDK 16)
- **Ile serii mogę dodać?** Przykład dodaje do 15 serii, ale możesz dostosować liczbę według potrzeb

## Co to jest wykres pierścieniowy w PowerPoint?
Wykres pierścieniowy to odmiana wykresu kołowego z pustym środkiem, umożliwiająca wyświetlanie wielu serii danych w kompaktowy, atrakcyjny wizualnie sposób. Idealny do prezentacji relacji części‑całość przy zachowaniu czystego projektu.

## Dlaczego używać Aspose.Slides for Java do tworzenia wykresów pierścieniowych?
- **Pełna kontrola** nad wyglądem wykresu, danymi i układem bez otwierania PowerPointa
- **Brak COM interop** – działa na każdej platformie obsługującej Javę
- **Wysoka wydajność** przy generowaniu dużych zestawów slajdów lub integracji z usługami webowymi
- **Bogata personalizacja** taka jak eksplozja, rozmiar otworu, kąty segmentów i formatowanie etykiet

## Wymagania wstępne
- Podstawowa znajomość programowania w Javie.
- IDE, takie jak IntelliJ IDEA lub Eclipse.
- Maven lub Gradle do zarządzania zależnościami.
- Ważna licencja Aspose.Slides for Java (dostępna wersja próbna).

## Konfiguracja Aspose.Slides for Java
Wybierz menedżer zależności pasujący do Twojego projektu.

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

Jeśli wolisz pobrać plik bezpośrednio, odwiedź stronę [wydania Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji
Możesz rozpocząć od wersji próbnej, aby poznać możliwości Aspose.Slides. W celu dłuższego użytkowania zakup licencję lub poproś o tymczasową na stronie [strony Aspose](https://purchase.aspose.com/temporary-license/). Postępuj zgodnie z instrukcjami, aby skonfigurować środowisko i zainicjalizować Aspose.Slides w aplikacji.

## Jak stworzyć wykres pierścieniowy w PowerPoint przy użyciu Aspose.Slides for Java
Poniżej znajduje się kompletny przewodnik krok po kroku. Każdy blok kodu jest wyjaśniony tuż przed jego użyciem, abyś dokładnie wiedział, co się dzieje.

### Krok 1: Inicjalizacja prezentacji
Najpierw załaduj istniejący plik PPTX lub utwórz nowy. To przygotowuje kolekcję slajdów do dalszych modyfikacji.

```java
import com.aspose.slides.*;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "/testc.pptx");
ISlide slide = pres.getSlides().get_Item(0);

// Verify successful loading by saving the initial presentation
pres.save(dataDir + "/initialized_chart.pptx", SaveFormat.Pptx);
```

### Krok 2: Dodanie wykresu pierścieniowego do slajdu
Dodajemy kształt wykresu, usuwamy domyślne serie/kategorie i ustawiamy podstawowe właściwości wizualne.

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

### Krok 3: Dodanie punktów danych wykresu i dostosowanie etykiet
Tutaj wypełniamy kategorie, dodajemy punkty danych dla każdej serii i precyzyjnie dopasowujemy wygląd etykiet. To miejsce, w którym wchodzi w grę słowo kluczowe **add chart data points**.

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

### Krok 4: Zapisz zaktualizowaną prezentację
Na koniec zapisujemy zmiany do nowego pliku PPTX.

```java
import com.aspose.slides.*;

pres.save(dataDir + "/chart.pptx", SaveFormat.Pptx);
```

## Praktyczne zastosowania
Wykresy pierścieniowe mogą być używane w różnych scenariuszach:
- **Raporty finansowe:** Wizualizacja podziału budżetu lub wydatków.
- **Analiza rynku:** Pokazanie udziału rynkowego poszczególnych konkurentów.
- **Wyniki ankiet:** Prezentacja danych kategorycznych w skondensowanej formie.
- **Generowanie pulpitów nawigacyjnych:** Połączenie z zapytaniami bazodanowymi w celu tworzenia slajdów aktualizowanych na żywo.

## Rozważania dotyczące wydajności
- **Zwalnianie zasobów**: Wywołaj `pres.dispose()` po zakończeniu, aby zwolnić pamięć natywną.
- **Ogranicz liczbę wykresów**: Dodawanie setek wykresów może zwiększyć zużycie pamięci; w razie potrzeby przetwarzaj partiami.
- **Używaj strumieniowania**: Dla bardzo dużych zestawów danych wypełniaj skoroszyt bezpośrednio ze strumieni zamiast z tablic w pamięci.

## Common Issues and Solutions
| Problem | Przyczyna | Rozwiązanie |
|-------|-------|-----|
| **Wykres jest pusty** | Komórki danych nie zostały poprawnie wypełnione | Sprawdź, czy `workBook.getCell(...)` odwołuje się do prawidłowych indeksów wiersza/kolumny. |
| **Etykiety nakładają się** | Zbyt wiele kategorii w ograniczonej przestrzeni | Zwiększ `DoughnutHoleSize` lub dostosuj `FirstSliceAngle`. |
| **OutOfMemoryError** | Duże prezentacje bez zwalniania zasobów | Wywołaj `pres.dispose()` po zapisaniu i rozważ zwiększenie rozmiaru sterty JVM. |

## Najczęściej zadawane pytania

**Q: Czy mogę używać Aspose.Slides for Java w aplikacjach komercyjnych?**  
A: Tak, ale potrzebna jest ważna licencja komercyjna. Dostępna jest wersja próbna do oceny.

**Q: Jak dodać więcej niż 15 serii?**  
A: Zwiększ limit pętli w kroku „Add Doughnut Chart” i upewnij się, że Twój skoroszyt danych zawiera wystarczającą liczbę wierszy.

**Q: Czy można zmienić rozmiar otworu wykresu pierścieniowego po jego utworzeniu?**  
A: Tak, wywołaj `series.getParentSeriesGroup().setDoughnutHoleSize((byte)desiredSize)` w dowolnym momencie przed zapisem.

**Q: Czy mogę wyeksportować wykres jako obraz zamiast PPTX?**  
A: Oczywiście. Użyj `chart.getImage()` i zapisz zwrócony `java.awt.image.BufferedImage` w wybranym formacie.

**Q: Czy Aspose.Slides obsługuje animowane wykresy?**  
A: Animacje można dodać za pomocą API `ISlide.getTimeline()`, choć wykracza to poza zakres tego samouczka.

## Zakończenie
Masz teraz kompletną, gotową do produkcji metodę **tworzenia wykresu pierścieniowego w PowerPoint** przy użyciu Aspose.Slides for Java, w tym **dodawanie punktów danych wykresu**, personalizację etykiet oraz uwzględnienie kwestii wydajności. Eksperymentuj z różnymi kolorami, źródłami danych i typami wykresów, aby Twoje prezentacje naprawdę się wyróżniały.

---

**Last Updated:** 2026-02-17  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}