---
date: '2026-01-17'
description: Dowiedz się, jak tworzyć wykres w Javie przy użyciu Aspose.Slides, dodać
  wykres słupkowy grupowany i zapisać prezentację jako pptx. Przewodnik krok po kroku
  dla programistów Javy.
keywords:
- Aspose.Slides for Java
- chart manipulation in presentations
- Java presentation library
title: Jak utworzyć wykres w Javie przy użyciu Aspose.Slides for Java
url: /pl/java/charts-graphs/aspose-slides-java-chart-manipulation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć wykres w Javie przy użyciu Aspose.Slides for Java

## Wprowadzenie
Tworzenie **create chart in java** o profesjonalnym wyglądzie nie musi być uciążliwe. Dzięki **Aspose.Slides for Java** możesz programowo dodawać, stylizować i zapisywać wykresy — np. wykres słupkowy grupowany — bezpośrednio w prezentacjach PowerPoint. W tym samouczku przeprowadzimy Cię przez konfigurację biblioteki, inicjalizację prezentacji, wstawienie wykresu słupkowego grupowanego, dostosowanie obszaru wykresu oraz zapis pliku jako PPTX. Na koniec otrzymasz gotowy fragment kodu, który możesz wykorzystać w dowolnym projekcie Java.

**Czego się nauczysz**
- Jak skonfigurować zależność Aspose.Slides w Maven lub Gradle  
- Jak **create chart in java** i dodać wykres słupkowy grupowany  
- Jak skonfigurować obszar wykresu (pozycję, rozmiar, układ)  
- Jak **save presentation as pptx** z prawidłowym zarządzaniem zasobami  

Gotowy, aby Twoje dane przemówiły wizualnie? Zaczynajmy!

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebuję?** Aspose.Slides for Java (Maven/Gradle).  
- **Jaki typ wykresu jest pokazany?** Wykres słupkowy grupowany.  
- **Jak zapisać plik?** Użyj `presentation.save(..., SaveFormat.Pptx)`.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna wystarczy do rozwoju; pełna licencja jest wymagana w produkcji.  
- **Czy mogę zmienić obszar wykresu?** Tak, możesz ustawić X, Y, width, height oraz typ docelowego układu.

## Co to jest create chart in java?
Tworzenie wykresu w Javie oznacza użycie biblioteki do generowania obiektów wykresu, wypełniania ich danymi i osadzania w dokumencie — w tym przypadku w slajdzie PowerPoint. Aspose.Slides ukrywa szczegóły niskopoziomowego Office Open XML, pozwalając skupić się na efekcie wizualnym.

## Dlaczego dodać wykres słupkowy grupowany przy użyciu Aspose.Slides?
Wykres słupkowy grupowany jest idealny do porównywania wielu serii danych obok siebie. Jest szeroko stosowany w raportach biznesowych, dashboardach i prezentacjach. Aspose.Slides daje pełną kontrolę nad kolorami, znacznikami, osiami i układem bez konieczności ręcznego otwierania PowerPointa.

## Wymagania wstępne
- Biblioteka **Aspose.Slides for Java** (wersja 25.4 lub nowsza).  
- **JDK 16** (lub nowszy) zainstalowany.  
- IDE, takie jak IntelliJ IDEA lub Eclipse.  
- Podstawowa znajomość składni Java.

## Konfiguracja Aspose.Slides for Java
### Maven
Dodaj zależność do swojego `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Umieść bibliotekę w `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Alternatywnie pobierz najnowszą wersję ze [strony oficjalnej Aspose](https://releases.aspose.com/slides/java/).

#### Uzyskanie licencji
Użyj bezpłatnej wersji próbnej lub tymczasowej licencji do testów. Zakup pełną licencję do wdrożeń produkcyjnych.

### Podstawowa inicjalizacja i konfiguracja
Utwórz nową klasę Java i zaimportuj główną klasę:

```java
import com.aspose.slides.Presentation;
```

## Przewodnik implementacji
Przejdziemy krok po kroku, wyjaśniając każdy etap.

### Inicjalizacja prezentacji i manipulacja slajdami
#### Przegląd
Najpierw utwórz nową prezentację i pobierz pierwszy slajd, na którym będzie znajdował się wykres.

**1. Utwórz i zainicjalizuj Presentation**

```java
Presentation presentation = new Presentation();
```

**2. Uzyskaj dostęp do pierwszego slajdu**

```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Dodaj wykres słupkowy grupowany**

```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

> **Pro tip:** Zawsze otaczaj użycie prezentacji blokiem `try‑finally` i wywołuj `presentation.dispose()` w sekcji `finally`, aby zwolnić zasoby natywne.

### Konfiguracja obszaru wykresu
#### Przegląd
Dostosuj obszar wykresu, aby kontrolować, gdzie dane są wyświetlane na slajdzie.

**1. Ustaw pozycję i rozmiar**

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
```

**2. Zdefiniuj typ docelowego układu**

```java
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

### Zapis prezentacji
#### Przegląd
Po dostosowaniu wykresu zapisz prezentację jako plik PPTX.

**1. Zapisz do pliku**

```java
presentation.save(YOUR_OUTPUT_DIRECTORY + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

> **Ostrzeżenie:** Upewnij się, że katalog docelowy istnieje i aplikacja ma uprawnienia do zapisu; w przeciwnym razie operacja zapisu się nie powiedzie.

## Typowe scenariusze użycia
- **Raporty biznesowe:** Osadzanie trendów sprzedaży i wskaźników KPI.  
- **Slajdy edukacyjne:** Wizualizacja wyników eksperymentów lub danych statystycznych.  
- **Propozycje projektowe:** Podkreślenie kamieni milowych i alokacji zasobów.  
- **Prezentacje marketingowe:** Pokazanie wyników kampanii za pomocą wyrazistych wykresów.  
- **Planowanie wydarzeń:** Wyświetlanie demografii uczestników lub podziału harmonogramu.

## Uwagi dotyczące wydajności
- Niezwłocznie zwalniaj obiekty `Presentation`, aby uniknąć wycieków pamięci.  
- Przy dużych zestawach danych wypełniaj serie wykresu stopniowo, zamiast ładować wszystko naraz.  
- Korzystaj z wbudowanych narzędzi profilujących Javy, aby monitorować zużycie pamięci podczas generowania wykresów.

## Najczęściej zadawane pytania

**Q: Jak dodać inne typy wykresów?**  
A: Użyj wyliczenia `ChartType` (np. `ChartType.Pie`, `ChartType.Line`) przy wywołaniu `addChart`.

**Q: Czy mogę dostosować kolory wykresu?**  
A: Tak, zmodyfikuj format wypełnienia serii lub paletę wykresu za pomocą API `IChart`.

**Q: Moja prezentacja nie zapisuje się — co jest nie tak?**  
A: Sprawdź, czy `YOUR_OUTPUT_DIRECTORY` jest poprawny, istnieje i ma prawa zapisu. Również zweryfikuj, czy nie ma otwartych blokad plików.

**Q: Jak efektywnie obsługiwać bardzo duże prezentacje?**  
A: Przetwarzaj slajdy partiami, zwalniaj każdy `Presentation` po użyciu i rozważ zwiększenie rozmiaru sterty JVM, jeśli to konieczne.

**Q: Czy Aspose.Slides jest darmowy dla projektów komercyjnych?**  
A: Dostępna jest wersja próbna do oceny, ale do wdrożeń komercyjnych wymagana jest zakupiona licencja.

## Zasoby
- [Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides](https://releases.aspose.com/slides/java/)
- [Purchase License](https://purchase.aspose.com/buy)
- [Free Trial](https://releases.aspose.com/slides/java/)
- [Temporary License](https://purchase.aspose.com/temporary-license/)
- [Support Forum](https://forum.aspose.com/c/slides/11)

Rozpocznij tworzenie wizualnie imponujących prezentacji z Aspose.Slides for Java już dziś!

---

**Ostatnia aktualizacja:** 2026-01-17  
**Testowano z:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose  

---

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
