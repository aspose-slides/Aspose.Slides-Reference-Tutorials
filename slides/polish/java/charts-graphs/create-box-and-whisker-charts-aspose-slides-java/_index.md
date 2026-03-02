---
date: '2026-03-02'
description: Poznaj sposób tworzenia wykresu pudełkowego w Javie, dodawania wykresu
  do slajdu oraz generowania wykresu pudełkowo‑wąsowego w PowerPoint przy użyciu Aspose.Slides
  for Java.
keywords:
- Aspose.Slides for Java
- Box-and-Whisker Charts
- PowerPoint Java
title: Utwórz wykres pudełkowy w Javie przy użyciu Aspose.Slides dla PowerPoint
url: /pl/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć wykresy pudełkowo‑wąsowe w PowerPoint przy użyciu Aspose.Slides dla Javy

W tym przewodniku **utworzysz wykres pudełkowy w Javie** przy pomocy Aspose.Slides, a następnie osadzisz wykres bezpośrednio na slajdzie PowerPoint. Tworzenie wizualnie atrakcyjnych prezentacji danych jest kluczowe w dzisiejszym świecie opartym na danych, a wykresy są niezbędnymi narzędziami w tym celu. Jeśli chcesz generować wykresy pudełkowo‑wąsowe w PowerPoint przy użyciu Javy, biblioteka Aspose.Slides oferuje solidne rozwiązanie. Ten tutorial przeprowadzi Cię krok po kroku przez tworzenie i konfigurowanie tych wykresów przy użyciu Aspose.Slides dla Javy.

## Czego się nauczysz

- Konfiguracja środowiska dla Aspose.Slides dla Javy
- Kroki, aby **dodać wykres do slajdu** i wygenerować wykres pudełkowo‑wąsowy w PowerPoint przy użyciu Javy
- Najlepsze praktyki optymalizacji wydajności przy pracy z Aspose.Slides
- Praktyczne zastosowania wykresów pudełkowo‑wąsowych

## Szybkie odpowiedzi
- **Jaką bibliotekę używać do tworzenia wykresu pudełkowego w Javie?** Aspose.Slides dla Javy.
- **Jaki typ wykresu jest używany?** `ChartType.BoxAndWhisker`.
- **Czy potrzebna jest licencja?** Darmowa wersja próbna działa w celach ewaluacyjnych; licencja komercyjna jest wymagana w produkcji.
- **Czy mogę dodać wiele serii?** Tak – powtórz blok tworzenia serii dla każdego zestawu danych.
- **Jaki jest format końcowego pliku?** PowerPoint PPTX (`SaveFormat.Pptx`).

## Wymagania wstępne

Aby podążać za tym tutorialem, upewnij się, że masz:

- **Java Development Kit (JDK)**: JDK 8 lub wyższy powinien być zainstalowany.
- **Aspose.Slides dla Javy**: Niezbędny do obsługi prezentacji PowerPoint w Javie.
- **IDE**: Zintegrowane środowisko programistyczne, takie jak IntelliJ IDEA lub Eclipse, do pisania i uruchamiania kodu.

## Konfiguracja Aspose.Slides dla Javy

Aby używać Aspose.Slides, dodaj go jako zależność. Możesz zarządzać tym przez Maven, Gradle lub bezpośrednie pobranie.

### Maven

Dodaj następującą zależność w swoim `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

W swoim `build.gradle` umieść:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download

Alternatywnie pobierz najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition

- **Free Trial**: Rozpocznij od darmowej wersji próbnej, aby poznać funkcje.  
- **Temporary License**: Uzyskaj tymczasową licencję do celów ewaluacyjnych.  
- **Purchase**: Aby uzyskać pełną funkcjonalność, rozważ zakup licencji.

Aby zainicjować Aspose.Slides, upewnij się, że biblioteka znajduje się w classpath i skonfiguruj wymagania licencyjne w razie potrzeby.

## Przewodnik implementacji

Teraz przejdźmy do kodu krok po kroku. Każdy blok jest wyjaśniony przed fragmentem, abyś dokładnie wiedział, co robi.

### Czym jest wykres pudełkowy i dlaczego używać go w Javie?

Wykres pudełkowo‑wąsowy (często nazywany *box plot*) wizualizuje rozkład danych — medianę, kwartyle i wartości odstające — w zwartej formie. W Javie generowanie takiego wykresu programowo pozwala osadzić statystyczne wnioski bezpośrednio w prezentacjach PowerPoint, eliminując ręczne tworzenie wykresów.

### Dlaczego dodawać wykres do slajdu przy użyciu Aspose.Slides?

Aspose.Slides ukrywa szczegóły niskopoziomowego OpenXML, oferując płynne API do tworzenia, stylizacji i eksportu wykresów. Dzięki temu możesz automatyzować generowanie raportów, utrzymywać spójną identyfikację wizualną i integrować wykresy z większymi przepływami pracy w Javie.

### Krok 1: Utwórz lub otwórz prezentację

Najpierw otwórz istniejący plik PPTX lub rozpocznij nowy:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Pro tip:** Jeśli plik nie istnieje, Aspose.Slides utworzy nową pustą prezentację.

### Krok 2: Dodaj wykres pudełkowo‑wąsowy do slajdu

Umieść wykres w wybranym miejscu, określając pozycję i rozmiar (w punktach):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Krok 3: Wyczyść istniejące dane

Przed wprowadzeniem nowych danych usuń wszelkie placeholdery kategorii lub serii:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Krok 4: Skonfiguruj kategorie

Dodaj kategorie (etykiety osi X), które pojawią się pod każdym pudełkiem:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Note:** Dostosuj tekst etykiety, aby odpowiadał Twojej domenie danych (np. „Q1”, „Produkt A”).

### Krok 5: Utwórz i dostosuj serię

Teraz utwórz serię, ustaw opcje wizualne i wprowadź wartości liczbowe:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Możesz zamienić tablicę `int[] data` na wartości odczytane z bazy danych, pliku CSV lub innego źródła.

### Krok 6: Zapisz prezentację

Zachowaj zmiany w nowym pliku PPTX:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Krok 7: Posprzątaj zasoby

Zawsze zwalniaj obiekt `Presentation`, aby zwolnić zasoby natywne:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Praktyczne zastosowania

Wykresy pudełkowo‑wąsowe są nieocenione w analizie statystycznej i prezentacji danych. Oto kilka scenariuszy, w których błyszczą:

1. **Analiza finansowa** – Wizualizacja rozkładu przychodów w różnych regionach.  
2. **Kontrola jakości** – Wykrywanie wartości odstających w pomiarach produkcyjnych.  
3. **Badania akademickie** – Pokazywanie zmienności wyników eksperymentalnych.  
4. **Badania rynkowe** – Porównywanie wydajności produktów w różnych grupach demograficznych.

Integracja tych wykresów w prezentacjach PowerPoint pozwala interesariuszom szybko zrozumieć złożone dane.

## Rozważania dotyczące wydajności

Pracując z Aspose.Slides w Javie, pamiętaj o następujących wskazówkach:

- **Memory Management** – Niezwłocznie zwalniaj obiekty `Presentation`.  
- **Data Handling** – Ładuj tylko niezbędne dane; unikaj wprowadzania ogromnych zestawów danych bezpośrednio do skoroszytu wykresu.  
- **Lazy Loading** – Jeśli generujesz wiele slajdów, rozważ tworzenie wykresów wyłącznie dla tych, które będą wyświetlane.

## Typowe problemy i rozwiązania

| Problem | Przyczyna | Rozwiązanie |
|-------|-------|----------|
| **Chart appears blank** | Komórki danych nie zostały poprawnie wypełnione | Zweryfikuj, czy `wb.getCell` odwołuje się do właściwego wiersza/kolumny i czy wartość nie jest `null`. |
| **Outliers not shown** | `setShowOutlierPoints` ustawione na `false` | Upewnij się, że wywołano `series.setShowOutlierPoints(true)`. |
| **Memory leak** | Prezentacja nie została zwolniona | Zawsze otaczaj użycie w `try/finally` i wywołuj `dispose()`. |
| **Incorrect quartiles** | Użyto domyślnej metody `Inclusive` | Przełącz na `Exclusive` poprzez `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Najczęściej zadawane pytania

**Q1: Czym jest wykres pudełkowo‑wąsowy?**  
Wykres pudełkowo‑wąsowy, znany również jako wykres pudełkowy, przedstawia rozkład danych na podstawie pięciu statystyk podsumowujących: minimum, pierwszy kwartyl, mediana, trzeci kwartyl i maksimum, a także wszelkie wartości odstające.

**Q2: Czy mogę dostosować wygląd wykresu pudełkowo‑wąsowego?**  
Tak. Aspose.Slides umożliwia zmianę kolorów, stylów linii, kształtów znaczników oraz dodawanie etykiet danych poprzez API formatowania wykresu.

**Q3: Czy można obsłużyć wiele serii w jednym wykresie?**  
Oczywiście. Powtórz blok tworzenia serii dla każdego zestawu danych, który chcesz zwizualizować.

**Q4: Jak rozwiązać problemy z niewyświetlającymi się danymi?**  
Upewnij się, że dane są poprawnie zapisane w komórkach skoroszytu oraz że właściwości widoczności, takie jak `setShowMeanLine`, są włączone.

**Q5: Gdzie mogę uzyskać wsparcie w razie problemów?**  
Odwiedź [forum Aspose.Slides](https://forum.aspose.com/c/slides/11) po pomoc społeczności lub zapoznaj się z oficjalną dokumentacją.

**Q6: Czy Aspose.Slides obsługuje inne typy wykresów?**  
Tak, obsługuje wykresy liniowe, słupkowe, kołowe, punktowe, radarowe i wiele innych.

**Q7: Czy mogę generować wykresy w środowisku serwerowym bez interfejsu graficznego?**  
Biblioteka działa w pełni w scenariuszach po stronie serwera; nie wymaga UI.

## Zasoby

- **Documentation**: Explore detailed API references at [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Download**: Access Aspose.Slides releases [here](https://releases.aspose.com/slides/java/)  
- **Purchase**: Buy a license to unlock full features at [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Free Trial & Temporary License**: Start with a free trial or request a temporary license [here](https://releases.aspose.com/slides/java/)

Postępując zgodnie z tym przewodnikiem, jesteś teraz gotowy do programowego generowania wnikliwych wykresów pudełkowo‑wąsowych w aplikacjach Java i osadzania ich bezpośrednio w prezentacjach PowerPoint. Powodzenia w kodowaniu!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Ostatnia aktualizacja:** 2026-03-02  
**Testowano z:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Autor:** Aspose