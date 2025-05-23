---
"date": "2025-04-17"
"description": "Dowiedz się, jak tworzyć i dostosowywać wykresy pierścieniowe w prezentacjach Java za pomocą Aspose.Slides, m.in. jak skonfigurować środowisko i dostosować estetykę wykresu."
"title": "Jak tworzyć wykresy pierścieniowe w Javie przy użyciu Aspose.Slides do prezentacji"
"url": "/pl/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć wykresy pierścieniowe w Javie przy użyciu Aspose.Slides do prezentacji

## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji jest niezbędne do skutecznego przekazywania informacji. Wykresy są kluczowymi elementami, które zwiększają zrozumienie dystrybucji danych. Ten samouczek przeprowadzi Cię przez tworzenie dostosowywalnych wykresów pierścieniowych przy użyciu Aspose.Slides dla Java, umożliwiając bezproblemowe generowanie wykresów z rozbudowanymi opcjami dostosowywania, takimi jak rozmiar otworów i pozycjonowanie.

**Czego się nauczysz:**
- Konfigurowanie Aspose.Slides dla Java
- Tworzenie i konfigurowanie wykresów pierścieniowych w prezentacjach
- Dostosowywanie estetyki wykresu, np. rozmiaru otworów
- Zapisywanie prezentacji z nowym wykresem

Zacznijmy od skonfigurowania naszego środowiska!

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że spełniłeś następujące wymagania wstępne:

### Wymagane biblioteki i wersje
Aby pracować z Aspose.Slides dla Java, dołącz go do projektu za pomocą Maven lub Gradle, albo pobierz bezpośrednio.

#### Wymagania dotyczące konfiguracji środowiska
- Działający pakiet Java Development Kit (JDK), najlepiej w wersji 8 lub nowszej.
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse.

### Wymagania wstępne dotyczące wiedzy
Znajomość Javy i podstawowych pojęć programowania jest korzystna. Podstawowa znajomość Maven lub Gradle pomoże usprawnić proces konfiguracji.

## Konfigurowanie Aspose.Slides dla Java
Istnieje kilka sposobów włączenia Aspose.Slides do projektu:

**Maven:**
Dodaj tę zależność do swojego `pom.xml` plik:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Stopień:**
Uwzględnij to w swoim `build.gradle` plik:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Bezpośrednie pobieranie:**
Alternatywnie, pobierz najnowszą wersję z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

### Nabycie licencji
- **Bezpłatna wersja próbna**: Zacznij od pobrania wersji próbnej, aby zapoznać się z funkcjami Aspose.Slides.
- **Licencja tymczasowa**:Uzyskaj tymczasową licencję zapewniającą rozszerzoną funkcjonalność bez ograniczeń.
- **Zakup**:Do dalszego użytkowania wymagany jest zakup licencji.

Gdy biblioteka będzie już skonfigurowana, a środowisko przygotowane, możemy zająć się implementacją naszego wykresu pierścieniowego.

## Przewodnik wdrażania

### Tworzenie wykresu pierścieniowego
Tworzenie prezentacji z niestandardowym wykresem pierścieniowym przy użyciu Aspose.Slides obejmuje kilka kroków. Podzielimy je dla jasności:

#### Zainicjuj obiekt prezentacji
Zacznij od utworzenia instancji `Presentation` klasa, reprezentująca Twój dokument PowerPoint.
```java
// Utwórz instancję klasy Presentation, aby reprezentować dokument PPTX
Presentation presentation = new Presentation();
```
Ten krok inicjuje prezentację, do której możesz dodać slajdy i wykresy.

#### Dodaj wykres pierścieniowy do slajdu
Otwórz pierwszy slajd (lub utwórz nowy, jeśli to konieczne) i dodaj wykres kołowy:
```java
// Uzyskaj dostęp do pierwszego slajdu prezentacji
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Pozycja w (50, 50) o rozmiarze 400x400
```
Ten fragment kodu dodaje wykres pierścieniowy do pierwszego slajdu. Parametry definiują jego położenie i wymiary na slajdzie.

#### Konfigurowanie rozmiaru otworu pierścieniowego
Aby nadać wykresowi pierścieniowemu wyjątkowy wygląd, dostosuj rozmiar otworów:
```java
// Ustaw rozmiar otworu dla wykresu pierścieniowego na 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```
Tutaj ustawiamy rozmiar otworu na 90%, co czyni go niemal pełnym okręgiem. Dostosuj tę wartość w zależności od potrzeb projektu.

#### Zapisz prezentację
Po skonfigurowaniu wykresu zapisz prezentację:
```java
// Zapisz prezentację na dysku w formacie PPTX w określonym katalogu
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```
Ten wiersz zapisuje zmiany do pliku o nazwie `DoughnutHoleSize_out.pptx` wyznaczonym przez Ciebie katalogu.

#### Zasoby do sprzątania
Na koniec upewnij się, że usunąłeś obiekt prezentacji:
```java
// Usuń obiekt prezentacji, aby zwolnić zasoby
if (presentation != null) presentation.dispose();
```
Ten krok jest kluczowy dla zarządzania zasobami i uniknięcia wycieków pamięci.

### Zastosowania praktyczne
Wykresy pierścieniowe są wszechstronne. Oto kilka scenariuszy, w których się sprawdzają:
1. **Alokacja budżetu**:Pokaż, w jaki sposób budżet jest dzielony pomiędzy poszczególne działy.
2. **Wyniki ankiety**:Wizualizacja odpowiedzi na pytania z odpowiedziami wielokrotnego wyboru.
3. **Źródła ruchu w witrynie**:Pokaż procent ruchu pochodzącego z różnych źródeł.

### Rozważania dotyczące wydajności
Podczas pracy z Aspose.Slides należy wziąć pod uwagę poniższe wskazówki, aby uzyskać optymalną wydajność:
- Zarządzaj pamięcią, usuwając obiekty, gdy nie są już potrzebne.
- W przypadku dużych zbiorów danych należy używać strumieni, aby zminimalizować użycie pamięci.
- Zoptymalizuj swój kod, wykorzystując ponownie wystąpienia, gdy jest to możliwe.

## Wniosek
Gratulacje! Nauczyłeś się, jak tworzyć i dostosowywać wykres pierścieniowy za pomocą Aspose.Slides dla Java. Ten samouczek obejmował konfigurację biblioteki, dodawanie wykresów do prezentacji i dostosowywanie ich wyglądu.

Aby w dalszym ciągu odkrywać możliwości Aspose.Slides, rozważ eksperymentowanie z innymi typami wykresów lub zapoznaj się bliżej z funkcjami automatyzacji prezentacji.

**Następne kroki:**
- Eksperymentuj z różnymi konfiguracjami wykresów.
- Zapoznaj się z dodatkową dokumentacją Aspose.Slides, aby poznać bardziej zaawansowane funkcje.

Gotowy na stworzenie własnych wykresów pierścieniowych? Spróbuj wdrożyć to rozwiązanie w swoim kolejnym projekcie!

## Sekcja FAQ
1. **Czy mogę dostosować kolory segmentów wykresu pierścieniowego?**
   Tak, możesz dostosować kolory segmentów za pomocą `chart.getChartData().getSeries(i).getDataPointsForBarChart().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid);` aby ustawić jednolity typ wypełnienia i określić żądany kolor.

2. **Jak dodać etykiety danych do wykresu?**
   Używać `chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category"));` i podobne metody dodawania punktów danych i etykiet programowo.

3. **Czy można zapisywać wykresy w formatach innych niż PPTX?**
   Oczywiście! Aspose.Slides obsługuje różne formaty wyjściowe, takie jak PDF, XPS i formaty obrazów, takie jak PNG lub JPEG.

4. **Co zrobić, jeśli podczas zapisywania prezentacji wystąpi błąd?**
   Upewnij się, że ścieżka do katalogu jest poprawna i że masz uprawnienia do zapisu dla określonej lokalizacji. Sprawdź, czy wersja Aspose.Slides, której używasz, obsługuje format pliku, w którym próbujesz zapisać.

5. **Czy mogę zautomatyzować aktualizację wykresów, korzystając ze źródeł danych na żywo?**
   Tak, integrując interfejsy API i bazy danych z aplikacją Java, możesz dynamicznie aktualizować dane na wykresach i odświeżać prezentacje według potrzeb.

## Zasoby
- **Dokumentacja**:Przeglądaj szczegółowe odniesienia do API na stronie [Aspose.Slides dla Java](https://reference.aspose.com/slides/java/).
- **Pobierać**:Pobierz najnowszą wersję biblioteki z [Wydania Aspose.Slides](https://releases.aspose.com/slides/java/).
- **Zakup**:Aby uzyskać pełny dostęp, należy zakupić licencję na stronie [Zakup Aspose](https://purchase.aspose.com/buy).
- **Bezpłatna wersja próbna**:Przetestuj Aspose.Slides, korzystając z bezpłatnej wersji próbnej dostępnej na stronie pobierania.
- **Licencja tymczasowa**:Uzyskaj tymczasową licencję na rozszerzone testy bez ograniczeń.
- **Wsparcie**: Masz pytania? Odwiedź [Forum Aspose](https://forum.aspose.com/c/slides/11) po pomoc.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}