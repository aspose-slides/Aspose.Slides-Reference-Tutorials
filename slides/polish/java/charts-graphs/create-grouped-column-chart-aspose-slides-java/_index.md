---
date: '2026-03-20'
description: Dowiedz się, jak dodać wykres kolumnowy grupowany do prezentacji PowerPoint,
  dostosować wykres PowerPoint oraz wstawić wykres serii danych przy użyciu Aspose.Slides
  for Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Jak dodać wykres słupkowy grupowany w PowerPoint przy użyciu Aspose.Slides
  dla Javy
url: /pl/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak dodać wykres kolumnowy grupowany w PowerPoint przy użyciu Aspose.Slides for Java

## Wprowadzenie

Kiedy potrzebujesz **dodać wykres kolumnowy grupowany** do prezentacji PowerPoint, przejrzysta wizualizacja może zamienić surowe liczby w od razu zrozumiałą historię. Ręczne tworzenie takiego wykresu w PowerPoint może być czasochłonne, szczególnie gdy musisz programowo wygenerować wiele slajdów. **Aspose.Slides for Java** usuwa tę barierę – pozwala tworzyć, dostosowywać wykresy PowerPoint i wstawiać wykresy serii danych za pomocą kilku linijek kodu.

W tym samouczku dowiesz się, jak:
- Zainicjować nową prezentację PowerPoint przy użyciu Aspose.Slides for Java.
- **Dodaj wykres do slajdu** i skonfiguruj go jako wykres kolumnowy grupowany.
- **Utwórz wykres kolumnowy grupowany** definiując poziomy grupowania dla kategorii.
- **Wstaw wykres serii danych**, aby dane były wyświetlane poprawnie.
- Zapisz gotową prezentację jako plik PPTX.

Upewnijmy się, że masz wszystko, co potrzebne, zanim przejdziemy do kodu.

## Szybkie odpowiedzi
- **Jaka jest główna klasa?** `Presentation` z `com.aspose.slides`.
- **Jaki typ wykresu jest używany?** `ChartType.ClusteredColumn`.
- **Czy potrzebna jest licencja do testów?** Darmowa wersja próbna działa, ale licencja usuwa ograniczenia wersji ewaluacyjnej.
- **Jaką wersję Javy obsługuje?** JDK 16 lub nowszą (przykład używa JDK 16).
- **Jak uruchomić przykład?** Dodaj zależność Maven/Gradle, skompiluj i uruchom metodę `main`.

## Co to jest „dodanie wykresu kolumnowego grupowanego”?

*Wykres kolumnowy grupowany* (zwany także wykresem kolumnowym grupowanym) wyświetla wiele serii danych obok siebie dla każdej kategorii, co ułatwia porównywanie wartości pomiędzy grupami. W PowerPoint ten typ wykresu jest idealny do prezentacji kwartalnych wyników sprzedaży, wyników ankiet lub dowolnego scenariusza, w którym trzeba zestawić kilka zestawów danych w ramach tej samej kategorii.

## Dlaczego używać Aspose.Slides do dodania wykresu kolumnowego grupowanego?

- **Pełna automatyzacja** – generuj dziesiątki slajdów bez ręcznej pracy.
- **Precyzyjna personalizacja** – kontroluj kolory, etykiety, poziomy grupowania i inne.
- **Cross‑platform** – działa na każdym systemie operacyjnym obsługującym Javę.
- **Brak wymogu instalacji Office** – generuj pliki PPTX na serwerach lub w pipeline'ach CI.

## Wymagania wstępne

- **Biblioteka Aspose.Slides for Java** (zalecana najnowsza wersja).  
- JDK 16 lub nowszy.  
- Narzędzie budowania Maven lub Gradle (lub możesz dodać plik JAR ręcznie).  
- IDE lub edytor tekstu do uruchamiania kodu Java.

## Konfiguracja Aspose.Slides for Java

Dodaj bibliotekę do swojego projektu, używając jednego z poniższych skryptów budowania.

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

Alternatywnie możesz bezpośrednio pobrać najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Uzyskanie licencji

Przed wdrożeniem do produkcji uzyskaj licencję:
- **Darmowa wersja próbna** – przetestuj wszystkie funkcje bez zakupu.
- **Licencja tymczasowa** – oceń rozszerzone możliwości przez krótki okres.
- **Pełna licencja** – odblokuj nieograniczone użycie. Uzyskaj ją na [stronie zakupu Aspose](https://purchase.aspose.com/buy).

## Przewodnik implementacji

Przejdziemy krok po kroku, wyjaśniając **jak dodać wykres** i **dostosować wykres PowerPoint** po drodze.

### Inicjalizacja prezentacji

Najpierw utwórz nowy obiekt `Presentation` i pobierz domyślny slajd.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Dodaj wykres do slajdu

Teraz **dodaj wykres do slajdu** używając typu `ClusteredColumn` i usuń wszelkie domyślne dane.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Przygotuj skoroszyt danych wykresu

Wykres przechowuje swoje dane w wewnętrznym skoroszycie. Wyczyść go, aby rozpocząć od nowa.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Dodaj kategorie z poziomami grupowania

Grupowanie kategorii tworzy efekt **wykresu kolumnowego grupowanego**. Każda kategoria może należeć do logicznej grupy.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Dodaj serie danych do wykresu

Tutaj **wstaw wykres serii danych**, które zostaną zwizualizowane jako oddzielne kolumny.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Zapisz prezentację z wykresem

Na koniec zapisz plik PPTX na dysku.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktyczne zastosowania

- **Raporty biznesowe** – porównaj kwartalne przychody w różnych regionach.  
- **Badania akademickie** – pokaż wyniki eksperymentów pogrupowane według warunków testowych.  
- **Zarządzanie projektami** – wizualizuj wskaźniki ukończenia zadań dla wielu zespołów na jednym slajdzie.

## Rozważania dotyczące wydajności

- **Zarządzanie pamięcią** – zwalniaj duże skoroszyty po użyciu.  
- **Operacje wsadowe** – unikaj aktualizacji wykresu w pętli; najpierw zbierz dane, potem zastosuj je.  
- **Wbudowane optymalizacje** – Aspose.Slides udostępnia metody takie jak `Presentation.optimize()` dla dużych plików.

## Częste pułapki i wskazówki

- **Pułapka:** Zapomnienie o wyczyszczeniu istniejących serii/kategorii może prowadzić do duplikacji danych.  
  **Wskazówka:** Zawsze wywołuj `clear()` przed wypełnianiem nowymi danymi.  
- **Pułapka:** Użycie niewłaściwego adresu komórki (np. `"c2"` zamiast `"C2"`).  
  **Wskazówka:** Odwołania do komórek nie rozróżniają wielkości liter, ale zachowaj spójność dla czytelności.  
- **Wskazówka:** Użyj `setGroupingItem`, aby utworzyć znaczące etykiety grup; pojawiają się automatycznie w legendzie wykresu.

## Najczęściej zadawane pytania

**Q1: Jak mogę dodać wiele serii do mojego wykresu?**  
A1: Wywołuj `ch.getChartData().getSeries().add()` wielokrotnie, podając unikalną nazwę i punkty danych dla każdej serii.

**Q2: Jakie są typowe problemy z wykresami Aspose.Slides?**  
A2: Problemy często wynikają z niepasujących zakresów danych lub brakujących komórek w skoroszycie. Upewnij się, że każda kategoria i każdy punkt danych ma odpowiadającą komórkę.

**Q3: Czy mogę używać Aspose.Slides w innych językach programowania?**  
A3: Tak, Aspose udostępnia równoważne biblioteki dla .NET, C++, Pythona i innych.

**Q4: Jak zaktualizować istniejący wykres w prezentacji?**  
A4: Załaduj prezentację, znajdź wykres za pomocą `slide.getShapes().get_Item(index)`, a następnie zmodyfikuj jego serie lub formatowanie w razie potrzeby.

**Q5: Czy istnieją ograniczenia typów wykresów w Aspose.Slides?**  
A5: Biblioteka obsługuje szeroką gamę typów wykresów, ale zawsze sprawdzaj najnowszą dokumentację pod kątem nowo dodanych lub wycofanych typów.

## Zasoby

- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Free Trial**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Temporary License**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Support Forum**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose