---
date: '2026-02-17'
description: Dowiedz się, jak dodawać wykresy kołowe do prezentacji PowerPoint przy
  użyciu Aspose.Slides for Java. Skorzystaj z tego przewodnika krok po kroku, aby
  tworzyć i dostosowywać profesjonalne wykresy kołowe.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Jak dodać wykres kołowy w PowerPoint przy użyciu Aspose.Slides for Java
url: /pl/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie i dostosowywanie wykresów kołowych w PowerPoint przy użyciu Aspose.Slides dla Javy

## Wprowadzenie

Czy masz problem z efektywną wizualizacją danych w swoich prezentacjach PowerPoint? **Adding a pie chart PowerPoint** slajd może natychmiast przekształcić surowe liczby w klarowną historię wizualną. Dzięki Aspose.Slides for Java możesz programowo **add pie chart PowerPoint** pliki, uzyskując pełną kontrolę nad projektem i danymi bez ręcznego otwierania PowerPointa. W tym samouczku przeprowadzimy Cię przez cały proces — od konfiguracji biblioteki po dostosowanie poszczególnych punktów danych — abyś mógł w kilka minut dostarczyć dopracowane, oparte na danych slajdy.

### Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Slides for Java (najnowsza wersja).  
- **Czy mogę utworzyć wykres bez zainstalowanego PowerPoint?** Tak, API działa całkowicie offline.  
- **Jakiej wersji Javy wymaga?** Zalecany JDK 16 lub nowszy.  
- **Jak zmienić kolor kawałka?** Użyj metod `setFillType` i `setSolidFillColor` na punkcie danych.  
- **Czy licencja jest obowiązkowa?** Wersja próbna działa w fazie rozwoju; pełna licencja usuwa ograniczenia oceny.

### Czego się nauczysz
- Jak programowo **add pie chart PowerPoint** przy użyciu Javy.  
- Sposoby dostosowywania eksplozji kawałków, kolorów i innych właściwości wizualnych.  
- Najlepsze praktyki zarządzania zasobami i wydajnością przy obsłudze dużych prezentacji.

## Dlaczego dodać **pie chart PowerPoint** przy użyciu Aspose.Slides for Java?
Osadzanie wykresu kołowego bezpośrednio z kodu pozwala generować aktualne raporty, automatyzować miesięczne pulpity nawigacyjne lub tworzyć spersonalizowane zestawy slajdów w locie. Eliminuje ręczne błędy kopiowania‑wklejania, zapewnia spójność w całych prezentacjach i płynnie integruje się z istniejącymi back‑endami Javy.

## Wymagania wstępne

Przed rozpoczęciem upewnij się, że masz:

- **Aspose.Slides for Java library** – tutorial odnosi się do wersji 25.4 (najnowsze wydanie w momencie pisania).  
- Kompatybilny **Java Development Kit (JDK)** – zalecany JDK 16+.  
- Podstawowa znajomość **Maven** lub **Gradle** do zarządzania zależnościami.  

## Konfigurowanie Aspose.Slides dla Javy

Aby rozpocząć, dołącz bibliotekę Aspose.Slides do swojego projektu.

### Maven
Dodaj tę zależność do pliku `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Umieść poniższe w pliku `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatywnie, pobierz najnowszą wersję bezpośrednio z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licencjonowanie
Aby używać Aspose.Slides bez ograniczeń:

- Rozpocznij od **bezpłatnej wersji próbnej**, aby ocenić API.  
- Poproś o **tymczasową licencję** na rozszerzone testy na stronie [Temporary License](https://purchase.aspose.com/temporary-license/).  
- Kup pełną subskrypcję poprzez [Purchase page](https://purchase.aspose.com/buy).

## Jak dodać **pie chart PowerPoint** przy użyciu Aspose.Slides for Java

Poniżej znajduje się przewodnik krok po kroku, który dokładnie pokazuje, jak utworzyć i dostosować wykres kołowy.

### Krok 1: Inicjalizacja prezentacji
Najpierw utwórz nowy obiekt `Presentation`. Reprezentuje on pusty plik PowerPoint.
```java
Presentation pres = new Presentation();
```

### Krok 2: Dodaj wykres kołowy
Wstaw wykres kołowy na pierwszym slajdzie. Współrzędne (50, 50) i rozmiar (600 × 400) dobrze pasują do standardowego slajdu 16:9.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Krok 3: Zapisz prezentację
Zapisz prezentację na dysku. Zastąp `YOUR_OUTPUT_DIRECTORY` folderem, w którym chcesz zapisać plik.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Krok 4: Zwolnij zasoby
Zwolnij obiekt `Presentation`, aby uwolnić zasoby natywne.
```java
if (pres != null) pres.dispose();
```

## Dostosowywanie eksplozji punktu danych i koloru

Dostosowywanie indywidualnych kawałków ułatwia odczyt wykresu, szczególnie gdy chcesz wyróżnić konkretną wartość.

### Krok 1: Załaduj istniejącą prezentację (lub użyj tej właśnie utworzonej)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Krok 2: Uzyskaj dostęp do wykresu i docelowego punktu danych
Tutaj pobieramy drugi punkt danych (indeks 1) z pierwszej serii.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Krok 3: Zastosuj eksplozję i kolor
Oddziel wizualnie kawałek i zmień jego kolor wypełnienia na niebieski.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Krok 4: Zapisz i zwolnij
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Praktyczne zastosowania
- **Raporty sprzedaży:** Podkreśl najlepiej sprzedające się produkty za pomocą wybuchających kawałków.  
- **Analiza budżetu:** Przypisz różne kolory działom dla szybkiego porównania wizualnego.  
- **Slajdy edukacyjne:** Rozbij skomplikowane koncepcje na łatwo przyswajalne segmenty wykresu.

## Rozważania dotyczące wydajności
- **Zwalniaj obiekty** niezwłocznie, aby uniknąć wycieków pamięci, szczególnie przy generowaniu wielu slajdów w pętli.  
- **Monitoruj zużycie sterty** przy dużych prezentacjach; rozważ strumieniowy zapis przy użyciu przeciążeń `Save` akceptujących `OutputStream`.  
- Używaj **JDK 16+**, aby korzystać z najnowszych usprawnień garbage collection.

## Podsumowanie
Masz teraz kompletny, gotowy do produkcji proces, aby **add pie chart PowerPoint** pliki przy użyciu Aspose.Slides for Java. Eksperymentuj z różnymi odległościami eksplozji, kolorami i zestawami danych, aby dopasować je do swojej marki. Gdy będziesz gotowy, odkryj inne typy wykresów — słupkowe, liniowe lub punktowe — aby zbudować pełny pulpit analityczny w PowerPoint.

## Sekcja FAQ
1. **Jaka jest główna zaleta używania Aspose.Slides for Java?**  
   - Uproszcza tworzenie i manipulację plikami PowerPoint programowo, oferując szeroką gamę funkcji.  
2. **Czy mogę dostosować inne typy wykresów za pomocą Aspose.Slides?**  
   - Oczywiście! Aspose.Slides obsługuje różne typy wykresów, takie jak słupkowe, liniowe i punktowe.  
3. **Jak obsłużyć wiele slajdów przy tworzeniu wykresów?**  
   - Uzyskaj dostęp do każdego slajdu po indeksie, używając metody `get_Item()`, aby zastosować zmiany na różnych slajdach.  
4. **Co zrobić, gdy mój wykres kołowy nie wyświetla się prawidłowo po dostosowaniu?**  
   - Sprawdź współrzędne i wymiary użyte w `addChart()`, upewniając się, że mieszczą się w układzie slajdu.  
5. **Gdzie mogę znaleźć bardziej zaawansowane funkcje Aspose.Slides?**  
   - Przeglądaj [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/), aby poznać dodatkowe możliwości i opcje.

## Zasoby
- **Dokumentacja:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Pobierz bibliotekę:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Kup licencję:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Bezpłatna wersja próbna:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Licencja tymczasowa:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Forum wsparcia:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Ostatnia aktualizacja:** 2026-02-17  
**Testowano z:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}