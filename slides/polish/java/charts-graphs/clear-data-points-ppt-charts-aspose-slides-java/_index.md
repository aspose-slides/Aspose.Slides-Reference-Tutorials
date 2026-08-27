---
date: '2026-08-27'
description: Dowiedz się, jak wyczyścić chart data points w PowerPoint przy użyciu
  Aspose.Slides for Java. Ten step‑by‑step tutorial pokazuje, jak programowo wyczyścić
  chart values, best practices oraz efficient series handling.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: Dowiedz się, jak wyczyścić chart data points w PowerPoint przy użyciu
  Aspose.Slides for Java. Postępuj zgodnie ze step‑by‑step instructions, aby programowo
  zresetować charts efficiently.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: Jak wyczyścić chart data points w PowerPoint przy użyciu Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'Jak wyczyścić data points w PowerPoint charts przy użyciu Aspose.Slides for
  Java: kompleksowy przewodnik'
url: /pl/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak wyczyścić punkty danych w wykresach PowerPoint przy użyciu Aspose.Slides for Java

## Wprowadzenie

W wielu przepływach raportowania musisz **zresetować wykres** bez ponownego tworzenia jego układu. Niezależnie od tego, czy odświeżasz pulpit nawigacyjny, udostępniasz szablon, czy automatyzujesz nocne raporty, znajomość **sposobu czyszczenia punktów danych wykresu** oszczędza czas i zmniejsza liczbę błędów. Ten samouczek pokazuje, jak używać **Aspose.Slides for Java**, aby programowo wyczyścić konkretne punkty lub całą serię, zachowując niezmieniony wygląd wizualny.

**Co się nauczysz**
- Jak Aspose.Slides umożliwia manipulację wykresami PowerPoint z poziomu Java.  
- Instrukcje krok po kroku dotyczące czyszczenia punktów danych wykresu w serii.  
- Wskazówki najlepszych praktyk dotyczące wydajności i licencjonowania.

## Szybkie odpowiedzi
- **Jakiej biblioteki wymaga?** Aspose.Slides for Java (v25.4+).  
- **Która metoda faktycznie czyści punkt danych?** Ustawienie wartości komórek X i Y na `null`.  
- **Czy potrzebna jest licencja do produkcji?** Tak – licencja komercyjna usuwa ograniczenia wersji próbnej.  
- **Czy Java 16 jest obsługiwana?** Absolutnie; biblioteka działa z JDK 16 i nowszymi.  
- **Czy mogę celować tylko w jedną serię?** Tak – iteruj wybraną serię, którą chcesz wyczyścić.

## Czym jest Aspose.Slides for Java?

Aspose.Slides for Java to w pełni funkcjonalne API, które umożliwia tworzenie, edytowanie i konwersję plików PowerPoint bez Microsoft Office. Obsługuje ponad 70 typów wykresów, ponad 150 formatów plików i może przetwarzać prezentacje do 500 MB bez wczytywania całego pliku do pamięci.

## Dlaczego wyczyścić punkty danych wykresu?

Czyszczenie punktów danych wykresu pozwala zachować istniejący układ wykresu — taki jak kolory, legendy, ustawienia osi i znaczniki — jednocześnie zastępując podstawowe wartości liczbowe. Takie podejście jest przydatne, gdy musisz odświeżyć wykres nowymi danymi, udostępnić szablon z pustymi miejscami, lub generować dynamiczne pulpity nawigacyjne, które często się zmieniają, bez konieczności przebudowywania projektu wizualnego.

- Odświeżanie wykresu nowym zestawem danych przy zachowaniu kolorów, legend i ustawień osi.  
- Udostępnianie szablonu zawierającego puste wykresy gotowe do wprowadzenia danych przez użytkownika.  
- Tworzenie dynamicznych pulpitów nawigacyjnych, w których dane zmieniają się często.

## Jak wyczyścić punkty danych wykresu w PowerPoint przy użyciu Aspose.Slides for Java

Załaduj swoją prezentację, zlokalizuj wykres i ustaw komórki X i Y każdego punktu danych na `null`. Ta operacja usuwa wartości liczbowe, ale pozostawia serie, znaczniki i formatowanie nienaruszone. Cały proces zazwyczaj kończy się w mniej niż sekundę dla standardowego pliku PPTX z 10 slajdami.

### Bezpośrednia odpowiedź
Aby wyczyścić punkty danych wykresu, otwórz plik PPTX za pomocą `new Presentation("input.pptx")`, pobierz docelowy obiekt `IChart`, przeiteruj żądaną `IChartSeries` i wywołaj `dataPoint.getXValue().setValue(null)` oraz `dataPoint.getYValue().setValue(null)` dla każdego punktu. Na koniec zapisz prezentację przy użyciu `pres.save("output.pptx", SaveFormat.Pptx)`. To podejście programowo usuwa dane, zachowując projekt wizualny wykresu.

### Definicje
- `Presentation` to obiekt najwyższego poziomu Aspose.Slides, który reprezentuje plik PowerPoint w pamięci.  
- `IChart` to interfejs zapewniający dostęp do serii, osi i formatowania kształtu wykresu.  
- `IChartSeries` reprezentuje pojedynczą serię w wykresie i zawiera kolekcję obiektów `IDataPoint`.  
- `IDataPoint` przechowuje poszczególne wartości X i Y dla punktu na wykresie.

### Implementacja krok po kroku

1. **Załaduj prezentację** – utwórz instancję `Presentation` wskazującą na plik źródłowy.  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **Uzyskaj dostęp do slajdu i wykresu** – pobierz slajd (zwykle indeks 0) i rzutuj pierwszy kształt na `IChart`.  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **Iteruj przez docelową serię** – wybierz serię, którą chcesz wyczyścić (np. `chart.getChartData().getSeries().get_Item(0)`) i przeiteruj jej punkty danych, ustawiając zarówno wartości komórek X, jak i Y na `null`.  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **Zapisz zmodyfikowaną prezentację** – zapisz zmiany do nowego pliku lub nadpisz oryginał.  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## Konfiguracja Aspose.Slides for Java

### Instalacja Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### Instalacja Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### Bezpośrednie pobranie

Ewentualnie pobierz najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji

Aby używać Aspose.Slides poza ograniczeniami wersji próbnej:
- Uzyskaj licencję **bezpłatnej wersji próbnej**.  
- Złóż wniosek o **licencję tymczasową** do oceny.  
- Kup **licencję komercyjną** do użytku produkcyjnego.

#### Podstawowa inicjalizacja i konfiguracja

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## Praktyczne zastosowania

Czyszczenie punktów danych wykresu jest przydatne w wielu rzeczywistych scenariuszach:

1. **Potoki odświeżania danych** – zastąp przestarzałe liczby nowymi analizami bez przebudowy układu wykresu.  
2. **Dystrybucja szablonów** – udostępnij szablony PowerPoint zawierające puste wykresy gotowe do wprowadzenia danych przez użytkownika.  
3. **Dynamiczne pulpity nawigacyjne** – generuj nocne prezentacje pobierające dane z API, najpierw czyszcząc stare wartości.  
4. **Zautomatyzowane zadania raportowania** – zintegrować logikę czyszczenia w potokach CI/CD do automatycznego generowania raportów.

## Rozważania dotyczące wydajności

- **Zwalnianie obiektów**: Wywołaj `pres.dispose()` po zapisaniu, aby zwolnić zasoby natywne.  
- **Przetwarzanie wsadowe**: Ponownie używaj jednej instancji `License` w wielu plikach, aby zminimalizować narzut.  
- **Dostosowanie JVM**: Zwiększ rozmiar sterty (`-Xmx2g` lub większy) przy obsłudze prezentacji większych niż 200 MB.  
- **Tryb oszczędny pamięci**: Aspose.Slides może strumieniować duże pliki PPTX, umożliwiając przetwarzanie do 10 000 slajdów bez pełnego ładowania do pamięci.

## Najczęściej zadawane pytania

**Q: Czy potrzebuję licencji do wersji deweloperskich?**  
A: Licencja wersji próbnej jest wystarczająca do rozwoju i testów. Licencja komercyjna jest wymagana w środowiskach produkcyjnych.

**Q: Czy Aspose.Slides for Java obsługuje funkcje PowerPoint 2016/2019?**  
A: Tak, biblioteka w pełni obsługuje nowoczesne funkcje PPTX, w tym zaawansowane typy wykresów i SmartArt.

**Q: Czy mogę wyczyścić punkty danych w wykresie używającym drugiej osi?**  
A: Oczywiście – wystarczy odwołać się do serii należącej do drugiej osi i ustawić jej punkty danych na `null`, jak opisano powyżej.

**Q: Czy można wyczyścić tylko wartości Y, zachowując etykiety X?**  
A: Tak. Wywołaj `dataPoint.getYValue().setValue(null)` i pozostaw komórkę X niezmienioną.

**Q: Jak mogę zautomatyzować to dla wielu prezentacji?**  
A: Umieść kod czyszczenia w pętli, która iteruje po katalogu plików PPTX, stosując tę samą logikę do każdego pliku.

## Zasoby

- [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/)
- [Pobierz Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Kup licencję](https://purchase.aspose.com/buy)
- [Wersja próbna](https://releases.aspose.com/slides/java/)
- [Wniosek o licencję tymczasową](https://purchase.aspose.com/temporary-license/)
- [Forum społeczności Aspose](https://forum.aspose.com/c/slides/11)

Z tymi zasobami jesteś gotowy, aby rozpocząć czyszczenie punktów danych wykresu w swoich aplikacjach Java. Szczęśliwego kodowania!

---

**Ostatnia aktualizacja:** 2026-08-27  
**Testowano z:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose

## Powiązane samouczki

- [Jak edytować dane wykresu PowerPoint przy użyciu Aspose.Slides for Java: Kompletny przewodnik](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Jak dodać wykres do PowerPoint przy użyciu Aspose.Slides for Java: Przewodnik krok po kroku](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Wyczyść konkretne punkty danych serii wykresu w Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}