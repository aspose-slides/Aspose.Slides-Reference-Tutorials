---
date: '2026-05-29'
description: Dowiedz się, jak utworzyć pie chart Aspose przy użyciu Aspose.Slides
  Maven, dodać pie chart Java do slajdu i dostosować chart data. Przewodnik krok po
  kroku z konfiguracją Maven i praktycznymi przykładami.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Utwórz pie chart Aspose – Dodaj wykres do prezentacji przy użyciu Maven
url: /pl/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak dodać wykres kołowy do prezentacji przy użyciu Aspose.Slides Java

## Wstęp
W tym przewodniku **utworzysz wykres kołowy aspose** przy użyciu Aspose.Slides Maven i zobaczysz, jak osadzić go w slajdzie PowerPoint. Tworzenie atrakcyjnych wizualnie prezentacji jest kluczowe dla skutecznego przekazywania informacji, szczególnie gdy wizualizacja danych odgrywa istotną rolę. Jeśli chcesz zautomatyzować ten proces przy użyciu **aspose slides maven**, trafiłeś we właściwe miejsce. Przeprowadzimy Cię przez dodawanie wykresu do slajdu — konkretnie wykresu kołowego — i jego dostosowywanie do rzeczywistych scenariuszy.

### Czego się nauczysz
- Jak zainicjalizować obiekt prezentacji w Javie.  
- Kroków do **dodania wykresu kołowego java** na pierwszym slajdzie prezentacji.  
- Dostępu do skoroszytów danych wykresu i wyświetlania arkuszy w nich zawartych.  

Zanurzmy się w to, jak możesz wykorzystać Aspose.Slides Java do wzbogacenia swoich prezentacji o dynamiczne wykresy!

## Szybkie odpowiedzi
- **Jaką bibliotekę dodaje wykresy przez Maven?** aspose slides maven  
- **Jaki typ wykresu jest pokazany?** Wykres kołowy (add chart to slide)  
- **Minimalna wymagana wersja Javy?** JDK 16 lub nowsza  
- **Czy potrzebna jest licencja do testów?** Działa darmowa wersja próbna; produkcja wymaga licencji  
- **Gdzie znaleźć zależność Maven?** W sekcji konfiguracji poniżej  

## Co to jest Aspose Slides Maven?
Aspose.Slides for Java to potężne API, które pozwala programistom tworzyć, modyfikować i renderować pliki PowerPoint programowo. Pakiet Maven (`aspose-slides`) upraszcza zarządzanie zależnościami, umożliwiając skupienie się na budowaniu i dostosowywaniu slajdów — np. dodawaniu wykresu kołowego — bez konieczności obsługi niskopoziomowego przetwarzania plików.

## Dlaczego warto używać Aspose.Slides Maven do dodawania wykresu do slajdu?
Użycie Aspose.Slides Maven pozwala generować wykresy bezpośrednio z kodu Java, bez ręcznej edycji PowerPointa. Zapewnia pełną kontrolę programistyczną nad typami wykresów, źródłami danych i stylizacją, gwarantując spójność marki i dokładność. Artefakt Maven obsługuje wszystkie wymagane zależności, upraszczając budowanie i umożliwiając płynną integrację w pipeline’ach CI/CD.

## Wymagania wstępne
- **Aspose.Slides for Java** w wersji 25.4 lub nowszej (Maven/Gradle).  
- Zainstalowany JDK 16+.  
- IDE (IntelliJ IDEA, Eclipse itp.).  
- Podstawowa znajomość Javy oraz Maven lub Gradle.

## Konfiguracja Aspose.Slides for Java
Najpierw dodaj Aspose.Slides do swojego projektu za pomocą Maven lub Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatywnie możesz [pobrać najnowszą wersję](https://releases.aspose.com/slides/java/) bezpośrednio ze strony Aspose.

### Uzyskanie licencji
Aspose.Slides for Java oferuje darmową wersję próbną z tymczasową licencją do testów. Do nieograniczonego użytku produkcyjnego należy zakupić licencję poprzez [stronę zakupu](https://purchase.aspose.com/buy).

## Przewodnik implementacji
Poniżej dzielimy rozwiązanie na dwie funkcje: dodawanie wykresu kołowego oraz dostęp do jego skoroszytu danych.

### Funkcja 1: Tworzenie prezentacji i dodawanie wykresu
#### Przegląd
Ta część pokazuje, jak utworzyć nową prezentację i **dodać wykres kołowy** do pierwszego slajdu.

#### Jak stworzyć wykres kołowy aspose?
Załaduj klasę `Presentation`, dodaj wykres typu `ChartType.Pie` i zapisz plik. Cała operacja wymaga tylko trzech wywołań API i trwa poniżej sekundy dla typowego zestawu 10 slajdów, co czyni ją idealną do automatycznego generowania raportów.

#### Krok po kroku

**Krok 1: Zainicjalizuj nowy obiekt Presentation**  
Klasa `Presentation` jest obiektem najwyższego poziomu Aspose.Slides, który reprezentuje plik PowerPoint w pamięci.  
```java
Presentation pres = new Presentation();
```
*Tworzy instancję `Presentation`, która będzie przechowywać wszystkie slajdy.*

**Krok 2: Dodaj wykres kołowy**  
`ChartType.Pie` instruuje Aspose, aby wyrenderował wykres kołowy.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Umieszcza wykres kołowy w współrzędnych (50, 50) o szerokości 400 i wysokości 500.*

**Krok 3: Zwolnij zasoby**  
Wywołanie `dispose()` zwalnia zasoby natywne i zapobiega wyciekom pamięci.  
```java
if (pres != null) pres.dispose();
```
*Zwalnia zasoby natywne; zawsze wywołuj `dispose()`, gdy skończysz.*

### Funkcja 2: Dostęp do skoroszytu danych wykresu i arkuszy
#### Przegląd
Dowiedz się, jak uzyskać dostęp do wewnętrznego skoroszytu przechowującego dane wykresu i iterować po jego arkuszach.

#### Jak uzyskać dostęp do skoroszytu danych wykresu?
Pobierz `IChartDataWorkbook` z wykresu, a następnie przeiteruj kolekcję `Worksheets`. Ten skoroszyt naśladuje plik Excel, umożliwiając odczyt, modyfikację lub dodawanie serii danych programowo, co wykres odzwierciedli natychmiast po odświeżeniu w czasie działania bez ponownego uruchamiania.

#### Krok po kroku

**Krok 1: (Ponowne użycie) Zainicjalizuj nowy obiekt Presentation**  
*Tak jak w Funkcji 1, Krok 1.*

**Krok 2: (Ponowne użycie) Dodaj wykres kołowy**  
*Tak jak w Funkcji 1, Krok 2.*

**Krok 3: Pobierz skoroszyt danych wykresu**  
`IChartDataWorkbook` to interfejs zapewniający odczyt/zapis do wewnętrznego skoroszytu wykresu podobnego do Excela.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Pobiera `IChartDataWorkbook` powiązany z wykresem.*

**Krok 4: Iteruj przez arkusze**  
Obiekty `Worksheet` reprezentują poszczególne arkusze w skoroszycie.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Wypisuje nazwę każdego arkusza, umożliwiając weryfikację struktury danych.*

**Krok 5: Zwolnij zasoby**  
*Tak jak w Funkcji 1, Krok 3.*

## Praktyczne zastosowania
- **Raportowanie danych:** Automatyczne generowanie zestawów slajdów z aktualnymi metrykami dla Business Intelligence.  
- **Prezentacje akademickie:** Wizualizacja wyników badań bez ręcznego tworzenia wykresów.  
- **Materiały marketingowe:** Prezentacja wyników produktów lub ankiet w czasie rzeczywistym.

## Wskazówki wydajnościowe
- Aspose.Slides obsługuje **ponad 50 formatów wejścia i wyjścia** oraz przetwarza prezentacje setek stron bez ładowania całego pliku do pamięci.  
- Zachowaj rozsądny licznik slajdów i wykresów; każdy wykres zużywa pamięć natywną.  
- Zawsze wywołuj `dispose()`, aby szybko zwolnić zasoby.  
- Optymalizuj obsługę danych w skoroszycie — unikaj ładowania ogromnych zestawów danych do jednego wykresu.

## Zakończenie
Omówiliśmy, jak **aspose slides maven** umożliwia **programowe dodawanie wykresu do slajdu** oraz pracę ze skoroszytem danych wykresu. Dzięki tym elementom możesz zautomatyzować każdy proces raportowania wymagający eleganckiego wyjścia w formacie PowerPoint.

### Kolejne kroki
- Eksploruj opcje stylizacji wykresów (kolory, legendy, etykiety danych).  
- Połącz się z zewnętrznymi źródłami danych (CSV, bazy danych), aby dynamicznie wypełniać wykresy.  
- Łącz różne typy wykresów w jednej prezentacji, aby uzyskać bogatszą narrację.

## Najczęściej zadawane pytania

**P: Jak zainstalować Aspose.Slides for Java?**  
O: Użyj zależności Maven lub Gradle pokazanej powyżej, albo pobierz bibliotekę ze strony wydań.

**P: Jakie są wymagania systemowe dla Aspose.Slides?**  
O: JDK 16 lub nowszy; biblioteka działa na każdej platformie obsługującej Javę.

**P: Czy mogę dodać inne typy wykresów oprócz kołowych?**  
O: Tak, Aspose.Slides obsługuje wykresy słupkowe, liniowe, punktowe, radarowe i ponad 20 innych typów.

**P: Jak efektywnie obsługiwać duże prezentacje?**  
O: Zwalniaj obiekty na bieżąco, ograniczaj obrazy wysokiej rozdzielczości i ponownie używaj szablonów wykresów, aby utrzymać niskie zużycie pamięci.

**P: Gdzie mogę znaleźć więcej informacji o funkcjach Aspose.Slides?**  
O: Odwiedź [dokumentację Aspose](https://reference.aspose.com/slides/java/) po pełną referencję API.

**P: Czy licencja jest wymagana do użytku komercyjnego?**  
O: Tak, do produkcji wymagana jest ważna licencja; wersja próbna jest dostępna do oceny.

**P: Czy pakiet Maven zawiera wszystkie możliwości wykresów?**  
O: Tak, artefakt `aspose-slides` Maven zawiera pełny silnik wykresów.

## Zasoby
- Dokumentacja: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)  
- Pobieranie: [Latest Releases](https://releases.aspose.com/slides/java/)  
- Zakup i wersja próbna: [Purchase Page](https://purchase.aspose.com/buy)  
- Darmowa wersja próbna: [Trial Downloads](https://releases.aspose.com/slides/java/)  
- Tymczasowa licencja: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)  
- Forum wsparcia: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Ostatnia aktualizacja:** 2026-05-29  
**Testowane z:** Aspose.Slides 25.4 for Java (jdk16)  
**Autor:** Aspose

## Powiązane tutoriale

- [Jak dostosować kolory wykresu kołowego w Javie z Aspose.Slides – Kompletny przewodnik](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Tworzenie wykresu kołowego w wykresie kołowym w Javie z Aspose.Slides: Kompletny przewodnik](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animowanie wykresów w PowerPoint przy użyciu Aspose.Slides for Java – Przewodnik krok po kroku](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}