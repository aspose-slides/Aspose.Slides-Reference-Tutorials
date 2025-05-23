---
"date": "2025-04-17"
"description": "Dowiedz się, jak tworzyć, dostosowywać i zapisywać wykresy z etykietami procentowymi w prezentacjach Java przy użyciu Aspose.Slides. Udoskonal swoje umiejętności prezentacyjne już dziś!"
"title": "Tworzenie i dostosowywanie wykresów w prezentacjach Java przy użyciu Aspose.Slides"
"url": "/pl/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie i dostosowywanie wykresów w prezentacjach Java przy użyciu Aspose.Slides

## Wstęp
Tworzenie atrakcyjnych prezentacji często wymaga czegoś więcej niż tylko tekstu; wymaga dynamicznych wykresów, które skutecznie przekazują informacje. Jeśli chcesz ulepszyć swoje prezentacje oparte na Javie o zaawansowane funkcje wykresów przy użyciu Aspose.Slides, ten samouczek jest dla Ciebie. Poprowadzimy Cię przez proces tworzenia prezentacji, dodawania i konfigurowania wykresów, obliczania sum, wyświetlania etykiet procentowych i zapisywania Twojej pracy — wszystko w zaledwie kilku prostych krokach.

**Czego się nauczysz:**
- Jak tworzyć i dostosowywać prezentacje z wykresami przy użyciu Aspose.Slides dla Java
- Obliczanie sum kategorii na wykresach
- Wyświetlanie danych jako etykiet procentowych na wykresach
- Zapisywanie prezentacji z ulepszonymi funkcjami wykresów

Przyjrzyjmy się bliżej wymaganiom wstępnym, które musisz spełnić zanim zaczniesz.

## Wymagania wstępne
Aby skorzystać z tego samouczka, upewnij się, że posiadasz następujące elementy:

- **Zestaw narzędzi programistycznych Java (JDK)**: Wersja 8 lub nowsza.
- **Środowisko programistyczne (IDE)**: Takich jak IntelliJ IDEA, Eclipse lub dowolne środowisko IDE obsługujące Javę.
- **Aspose.Slides dla biblioteki Java**:Ma to kluczowe znaczenie w przypadku obsługi funkcji prezentacji.

### Wymagane biblioteki i wersje
Będziesz potrzebować Aspose.Slides dla Javy. Oto jak dołączyć go do swojego projektu:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Stopień:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatywnie możesz bezpośrednio pobrać najnowszą wersję z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

### Konfiguracja środowiska
Upewnij się, że środowisko programistyczne jest skonfigurowane do korzystania z JDK 8 lub nowszego i że Twoje środowisko IDE jest skonfigurowane do zarządzania zależnościami za pomocą Maven lub Gradle.

**Nabycie licencji:**
- **Bezpłatna wersja próbna**:Uzyskaj dostęp do podstawowych funkcji w celach testowych.
- **Licencja tymczasowa**:Testuj zaawansowane funkcje bez ograniczeń ewaluacyjnych.
- **Zakup**:W przypadku długoterminowego użytku komercyjnego należy rozważyć zakup licencji.

## Konfigurowanie Aspose.Slides dla Java
Zacznij od skonfigurowania biblioteki Aspose.Slides w swoim projekcie Java. Oto jak ją zainicjować i skonfigurować:

1. Dodaj zależność za pomocą Maven lub Gradle, jak pokazano powyżej.
2. Zaimportuj niezbędne pakiety Aspose.Slides:
   ```java
   import com.aspose.slides.*;
   ```

3. Zainicjuj nowy `Presentation` przykład:
   ```java
   Presentation presentation = new Presentation();
   ```

Ta konfiguracja umożliwi Ci rozpoczęcie tworzenia prezentacji programowo.

## Przewodnik wdrażania

### Twórz i dostosowuj wykresy w swojej prezentacji

#### Przegląd
Utworzenie wykresu polega na zainicjowaniu prezentacji, uzyskaniu dostępu do slajdów i dodaniu wykresu z określonymi atrybutami, takimi jak typ, pozycja i rozmiar.

**Kroki:**
1. **Utwórz instancję prezentacji**: Zacznij od utworzenia instancji `Presentation` klasa.
2. **Dostęp do slajdu**:Pobierz pierwszy slajd za pomocą `get_Item(0)`.
3. **Dodaj wykres**: Używać `addChart()` aby dodać wykres kolumnowy ułożony w stos przy określonych współrzędnych i zdefiniowanych wymiarach.

```java
// Funkcja: Tworzenie prezentacji z wykresem
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Oblicz sumy dla kategorii

#### Przegląd
Obliczanie sum kategorii polega na iteracyjnym przeglądaniu każdej serii na wykresie w celu zsumowania wartości dla każdej kategorii.

**Kroki:**
1. **Zainicjuj tablicę**:Utwórz tablicę, w której będą przechowywane wartości całkowite.
2. **Iteruj przez kategorie i serie**:Użyj pętli zagnieżdżonych w celu zgromadzenia sum dla każdej kategorii ze wszystkich serii.

```java
// Funkcja: Obliczanie sum dla kategorii na wykresie
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Wyświetlanie danych jako etykiet procentowych na wykresie

#### Przegląd
Funkcja ta koncentruje się na konfiguracji etykiet danych tak, aby wyświetlały wartości jako procenty, zapewniając przejrzystość wizualizacji.

**Kroki:**
1. **Konfiguruj etykiety serii**: Ustaw właściwości etykiety, takie jak rozmiar czcionki i widoczność klawiszy legendy.
2. **Oblicz procenty**:Oblicz procent dla każdego punktu danych w oparciu o całkowitą wartość kategorii.
3. **Ustaw tekst etykiety**: Formatuj etykiety tak, aby pokazywały procenty z dwoma miejscami po przecinku.

```java
// Funkcja: Wyświetlanie danych jako etykiet procentowych na wykresie
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Zapisz prezentację z wykresem

#### Przegląd
Na koniec zapisz prezentację w określonej ścieżce w formacie PPTX.

**Kroki:**
1. **Zapisz metodę**:Użyj `save()` metoda na `Presentation` przykład.
2. **Utylizuj zasoby**: Upewnij się, że zasoby zostaną zwolnione po zapisaniu.

```java
// Funkcja: Zapisz prezentację z wykresem
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Zastosowania praktyczne

1. **Sprawozdawczość finansowa**:Użyj wykresów, aby wyświetlić procentowy wzrost przychodów w poszczególnych działach.
2. **Analiza danych sprzedaży**:Wizualizacja danych sprzedaży według regionów z etykietami procentowymi dla uzyskania jaśniejszego obrazu.
3. **Prezentacje edukacyjne**:Ulepsz prezentacje naukowe za pomocą statystyk wizualnych.
4. **Kampanie marketingowe**:Wyświetlaj wskaźniki skuteczności kampanii w formie angażujących wizualizacji.
5. **Spotkania Strategii Biznesowej**:Używaj wykresów do przekazywania złożonych danych podczas dyskusji na temat planowania strategicznego.

## Rozważania dotyczące wydajności
- **Zarządzanie pamięcią**:Pozbądź się `Presentation` obiektów w celu szybkiego zwolnienia zasobów.
- **Zoptymalizuj ładowanie wykresu**: Jeśli to możliwe, ładuj do pamięci tylko niezbędne elementy wykresu.
- **Przetwarzanie wsadowe**:Podczas przetwarzania wielu prezentacji, rozważ przetwarzanie ich w partiach, aby efektywnie zarządzać zużyciem zasobów.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}