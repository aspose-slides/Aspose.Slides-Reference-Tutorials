---
date: '2026-01-09'
description: Odkryj, jak używać Aspose.Slides Maven, aby dodać wykres do slajdu i
  dostosować wykres kołowy w prezentacjach Java. Krok po kroku konfiguracja, kod i
  przykłady z rzeczywistego świata.
keywords:
- add pie chart with Aspose.Slides Java
- Aspose.Slides for Java tutorial
- Java presentation automation
title: 'aspose slides maven - Dodaj wykres kołowy do prezentacji'
url: /pl/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak dodać wykres kołowy do prezentacji przy użyciu Aspose.Slides Java

## Wstęp
Tworzenie atrakcyjnych prezentacji jest kluczowe dla stosowania informacji, szczególnie gdy wizualizacja danych wejściowych jest dostępna. Jeśli chcesz zautomatyzować dziesięć procesów przy użyciu **aspose slides maven**, trafiłeś we właściwe miejsce. W tym samouczku dowiesz się, jak **dodaj wykres do slajdu** — konkretnie wykres kołowy — przy użyciu Aspose.Slides for Java oraz jak go dostosować do istniejących scenariuszy.

### Czego się nauczysz
- Jak można przedstawić obiekt w Javie.
- Kroki do **dodania wykresu kołowego Java** na pierwszym slajdzie prezentacji.
- Dostęp do skoroszytów danych wykresu i wyświetlanie list arkuszy w nich.

Zanurzmy się w to, jak można używać Aspose.Slides Java, aby wzbogacić swoje prezentacje o istniejące wykresy!

## Szybkie odpowiedzi
- **Jaka biblioteka dodaje wykresy przez Maven?**aspose slides maven
- **Jaki typ wykresu jest pokazany?**Wykres kołowy (dodaj wykres do slajdu)
- **Minimalna wymagana wersja Javy?**JDK16 lub nowsza
- **Czy istnieje licencjat do testów?**A bezpłatna wersja próbna działa; produkcja wymaga licencji
- **Gdzie można znaleźć rozwiązanie Maven?**W sekcji konfiguracji poniżej

## Co to jest Aspose Slides Maven?
Aspose.Slides for Java jest API, które pozwala na tworzenie programów, modyfikowanie i renderowanie plików programu PowerPoint. Pakiet Maven („aspose-slides”) upraszcza zarządzania zależnościami, włączając skupienie się na budowie i kontrolowaniu slajdów — takie jak właściwe wykresu kołowego — bez konieczności stosowania przez niskopoziomową obsługę plików.

## Dlaczego warto używać narzędzia Aspose.Slides Maven do dodawania wykresu do slajdu?
- **Automatyzacja:** Automatyczne generowanie awarii i ambony nawigacyjnej.
- **Precyzja:** Pełna kontrola nad typami wykresów, transmisja danych i stylizacja.
- **Międzyplatformowy:** Działa w każdym środowisku potwierdzam z Javą.

## Warunki wstępne
- **Aspose.Slides for Java** wersja 25.4 lub nowsza (Maven/Gradle).
- Zainstalowany JDK16+.
- IDE (IntelliJ IDEA, Eclipse, itp.).
- Podstawowa przyjemność Javy oraz Maven lub Gradle.

## Konfigurowanie Aspose.Slides dla Java
Najpierw dołącz Aspose.Slides do swojego projektu za pomoc Maven lub Gradle.

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatywnie możesz [pobrać najnowszą wersję](https://releases.aspose.com/slides/java/) bezpośrednio ze strony Aspose.

### Nabycie licencji
Aspose.Slides for Java oferuje bezpłatną wersję próbną z tymczasową licencją do testowania. Aby uzyskać nieograniczone możliwości produkcyjne, kup licencję na [stronie zakupu](https://purchase.aspose.com/buy).

## Przewodnik wdrażania
Poniżej znajdują się rozwiązania na dwie funkcje: załącznik wykresu kołowego oraz dostęp do jego skoroszytu danych.

### Funkcja 1: Tworzenie prezentacji i dodawanie wykresu
#### Przegląd
Ta część zawiera nową prezentację i **dodaj wykres kołowy** na pierwszym slajdzie.

#### Krok po kroku

**Krok 1: Zainicjuj nowy obiekt prezentacji** 
```java
Presentation pres = new Presentation();
```
*Dwie instancje `Prezentacja`, które będą podzielone na wszystkie slajdy.*

**Krok 2: Dodaj wykres kołowy** 
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Umieścił wykres kołowy we współrzędnych (50,50) o szerokości400 i wysokość500. Enum `ChartType.Pie` wykorzystania Aspose, aby renderował wykres kołowy.*

**Krok 3: Pozbądź się zasobów** 
```java
if (pres != null) pres.dispose();
```
*Zwalnia zasobów naturalnych; zawsze wywołuj `dispose()`, gdy zakończysz.*

### Funkcja 2: Dostęp do skoroszytu i arkuszy danych wykresów
#### Przegląd
Naucz się, jak uzyskać dostęp do podstawowego skoroszytu przechowującego dane wykresu i iterować po jego arkuszach.

#### Krok po kroku

**Krok 1: (Użyj ponownie) Zainicjuj nowy obiekt prezentacji**
*Tak jak w Funkcji1, Krok1.*

**Krok 2: (Użyj ponownie) Dodaj wykres kołowy**
*Tak jak w Funkcji1, Krok2.*

**Krok 3: Pobierz skoroszyt danych wykresu** 
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Pobiera `IMartDataWorkbook` powiązany z wykresem.*

**Krok 4: Iteruj po arkuszach** 
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Wypisuje nazwę każdego arkusza, umożliwiając weryfikację struktury danych.*

**Krok 5: Pozbądź się zasobów**
*Tak jak w Funkcji1, Krok3.*

## Praktyczne zastosowania
- **Raportowanie danych:** Automatyczne generowanie zestawu slajdów z aktualnymi metrykami dla Business Intelligence.
- **Prezentacje akademickie:** Wizualizacja wyników badań bez ręcznego tworzenia wykresów.
- **Materiały marketingowe:** Prezentacja wydajności produktu lub natychmiastowo.

## Względy wydajności
- Utrzymuj rozsądną liczbę slajdów i wykresów; każdy zużywa pamięć.
- Zawsze wywołuj `dispose()`, aby zwolnić zasoby natywne.
- Zoptymalizuj obsługę danych w skoroszycie — unikaj ładowania ogromnych zbiorów danych do jednego wykresu.

## Wniosek
Opowiedział, jak **aspose slides maven** umożliwia **dodaj wykres do slajdu** programowo oraz jak pracować ze skoroszytem danych wykresu. Dzięki temu elementowi możesz zautomatyzować każdy proces raportowania, który jest dostępny w programie PowerPoint.

### Następne kroki
- Poznaj opcje stylów wykresów (kolory, legendy, etykiety danych).
- Połącz się z zewnętrznymi źródłami danych (pliki CSV, bazy danych), aby dynamicznie wypełniać wykresy.
- Połącz wiele typów wykresów w jedną prezentację, aby wzbogacić narrację.

## Często zadawane pytania

**P: Jak zainstalować Aspose.Slides dla Javy?**
O: Użyj zależności Maven lub Gradle pokazanej powyżej lub pobierz bibliotekę ze strony z wersjami.

**P: Jakie są wymagania systemowe Aspose.Slides?**
O: JDK16 lub nowszy; biblioteka jest niezależna od platformy.

**P: Czy mogę dodać inne typy wykresów oprócz wykresów kołowych?**
O: Tak, Aspose.Slides obsługuje wykresy słupkowe, liniowe, punktowe i wiele innych.

**P: Jak efektywnie obsługiwać duże prezentacje?**
O: Szybko usuwaj obiekty, ogranicz liczbę obrazów o wysokiej rozdzielczości i ponownie wykorzystuj szablony wykresów, gdy to możliwe.

**P: Gdzie mogę znaleźć więcej informacji na temat funkcji Aspose.Slides?**
O: Odwiedź [dokumentację Aspose](https://reference.aspose.com/slides/java/), aby uzyskać pełną dokumentację API.

**P: Czy licencja jest wymagana do użytku komercyjnego?**
O: Do użytku produkcyjnego wymagana jest ważna licencja; dostępna jest bezpłatna wersja próbna w celu przetestowania.

**P: Czy pakiet Maven zawiera wszystkie funkcje wykresów?**
O: Tak, artefakt Maven `aspose-slides` zawiera pełny silnik wykresów.

## Zasoby
- Dokumentacja: [Dokumentacja API Java Aspose.Slides](https://reference.aspose.com/slides/java/)
- Pobieranie: [Najnowsze wersje](https://releases.aspose.com/slides/java/)
- Zakup i wersja próbna: [Strona zakupu](https://purchase.aspose.com/buy)
- Bezpłatna wersja próbna: [Pobieranie wersji próbnych](https://releases.aspose.com/slides/java/)
- Licencja tymczasowa: [Złóż wniosek o licencję tymczasową](https://purchase.aspose.com/temporary-license/)
- Forum wsparcia: [Forum społeczności Aspose](https://forum.aspose.com/c/slides/11)

---

**Ostatnia aktualizacja:** 2026-01-09
**Testowano z:** Aspose.Slides 25.4 dla Javy (jdk16)
**Autor:** Aspose 

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
