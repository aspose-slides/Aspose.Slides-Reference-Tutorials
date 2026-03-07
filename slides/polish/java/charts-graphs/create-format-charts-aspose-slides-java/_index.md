---
date: '2026-03-07'
description: Dowiedz się, jak tworzyć wykres liniowy w Javie przy użyciu Aspose.Slides,
  dodać tytuł wykresu, dodać linie siatki, sformatować etykiety wykresu i zapisać
  profesjonalne prezentacje.
keywords:
- Aspose.Slides Java
- create charts in Java
- format PowerPoint charts
title: Jak stworzyć wykres liniowy przy użyciu Aspose.Slides w Javie – Kompletny przewodnik
url: /pl/java/charts-graphs/create-format-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak stworzyć wykres liniowy przy użyciu Aspose.Slides w Javie

## Jak stworzyć wykres liniowy w Javie przy użyciu Aspose.Slides

### Wprowadzenie
Tworzenie atrakcyjnych wizualnie prezentacji jest kluczowe dla skutecznej komunikacji. Niezależnie od tego, czy jesteś profesjonalistą biznesowym, czy edukatorem, często musisz **tworzyć wykresy liniowe**, które są zarówno informacyjne, jak i estetycznie przyjemne. W tym samouczku przeprowadzimy Cię przez użycie **Aspose.Slides for Java** do generowania wykresu liniowego, dodawania tytułu wykresu, linii siatki, formatowania etykiet wykresu oraz zapisu wyniku jako pliku PowerPoint.

#### Szybkie odpowiedzi
- **Jaka biblioteka jest najlepsza do tworzenia wykresów w Javie?** Aspose.Slides for Java
- **Na jaki typ wykresu koncentruje się ten przewodnik?** Line chart with markers
- **Czy potrzebuję licencji, aby uruchomić przykład?** A free temporary license works for evaluation
- **Jakiego IDE mogę używać?** Any Java IDE such as IntelliJ IDEA, Eclipse, or NetBeans
- **Jak formatowane są elementy wykresu?** Using fluent API calls for titles, axes, grid lines, legends, and backgrounds

### Co to jest wykres liniowy i dlaczego używać Aspose.Slides?
Wykres liniowy wyświetla punkty danych połączone prostymi liniami, co czyni go idealnym do prezentowania trendów w czasie. Aspose.Slides pozwala tworzyć i w pełni dostosowywać te wykresy programowo, eliminując potrzebę ręcznej edycji PowerPointa.

### Wymagania wstępne
- **Java Development Kit (JDK) 8+** zainstalowany
- **IDE** (IntelliJ IDEA, Eclipse, NetBeans, itp.)
- **Aspose.Slides for Java** biblioteka (dodana przez Maven lub Gradle)

#### Wymagane biblioteki i zależności
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

Alternatywnie, pobierz najnowszy plik JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Uzyskanie licencji
- Uzyskaj [bezpłatną licencję próbną](https://purchase.aspose.com/temporary-license/) do testów.
- Kup pełną licencję na [oficjalnej stronie Aspose](https://purchase.aspose.com/buy) do użytku produkcyjnego.

### Konfiguracja Aspose.Slides dla Javy
1. **Dodaj zależność** pokazaną powyżej do swojego projektu.
2. **Zastosuj licencję** (jeśli ją posiadasz) przed tworzeniem jakichkolwiek obiektów prezentacji.

```java
import com.aspose.slides.Presentation;
// Initialize the Presentation object
Presentation pres = new Presentation();
```

## Implementacja krok po kroku

### Krok 1: Utwórz katalog wyjściowy (create directory java)
```java
import java.io.File;
// Define the target directory
String dataDir = "YOUR_DOCUMENT_DIRECTORY";

// Check if directory exists; create it if not
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs(); // Create directories recursively
}
```
*Dlaczego to ważne:* Zapewnienie, że folder istnieje, zapobiega `FileNotFoundException` podczas późniejszego zapisywania prezentacji.

### Krok 2: Dodaj slajd i wstaw wykres liniowy
```java
import com.aspose.slides.*;
// Create a new presentation
Presentation pres = new Presentation();
try {
    // Access the first slide
    ISlide slide = pres.getSlides().get_Item(0);

    // Add a chart to the slide
    IChart chart = slide.getShapes().addChart(
        ChartType.LineWithMarkers, 50, 50, 500, 400);
```
*Wyjaśnienie:* Tworzy nowy slajd i umieszcza **wykres liniowy z markerami** w określonych współrzędnych.

### Krok 3: Dodaj tytuł wykresu (add chart title)
```java
// Enable and format the title
chart.setTitle(true);
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding()
    .getParagraphs().get_Item(0).getPortions().get_Item(0);

chartTitle.setText("Sample Line Chart");
chartTitle.getPortionFormat().setFontBold(NullableBool.True);
chartTitle.getPortionFormat().setFillType(FillType.Solid);
chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
chartTitle.getPortionFormat().setFontHeight(20);
```
*Wskazówka:* Użycie pogrubionego, szarego tytułu sprawia, że wykres jest od razu rozpoznawalny.

### Krok 4: Formatuj osie i dodaj linie siatki (add grid lines)
#### Formatowanie osi pionowej
```java
IChartAxis verticalAxis = chart.getAxes().getVerticalAxis();

// Format major grid lines
verticalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.BLUE);
verticalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Configure axis properties
verticalAxis.setNumberFormat("0.0%");
verticalAxis.setMaxValue(15f);
verticalAxis.setMinValue(-2f);
```

#### Formatowanie osi poziomej
```java
IChartAxis horizontalAxis = chart.getAxes().getHorizontalAxis();

// Format major grid lines
horizontalAxis.getMajorGridLinesFormat().getLine()
    .setFillType(FillType.Solid)
    .getFillFormat().getSolidFillColor().setColor(Color.GREEN);
horizontalAxis.getMajorGridLinesFormat().getLine().setWidth(5);

// Set label positions and rotations
horizontalAxis.setTickLabelPosition(TickLabelPositionType.Low);
horizontalAxis.setTickLabelRotationAngle(45);
```
*Dlaczego to ważne:* Czytelne linie siatki i obrócone etykiety poprawiają czytelność, szczególnie gdy punkty danych są gęste.

### Krok 5: Dostosuj legendę (add chart title – already covered, but legend is part of overall formatting)
```java
IChartPortionFormat txtLeg = chart.getLegend().getTextFormat().getPortionFormat();
txtLeg.setFontBold(NullableBool.True);
txtLeg.getFillFormat().setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.RED);

// Prevent overlap with the chart area
chart.getLegend().setOverlay(true);
```

### Krok 6: Ustaw kolory tła (format chart labels – part of overall visual styling)
```java
chart.getBackWall().setThickness(1);
chart.getBackWall().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(Color.ORANGE);

chart.getPlotArea().getFormat().getFill()
    .setFillType(FillType.Solid)
    .getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
```

### Krok 7: Zapisz prezentację
```java
// Save the presentation to disk
pres.save("YOUR_OUTPUT_DIRECTORY/FormattedChart_out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose(); // Clean up resources
}
```
*Wynik:* Masz teraz plik PowerPoint (`FormattedChart_out.pptx`) zawierający w pełni sformatowany wykres liniowy.

## Praktyczne zastosowania
- **Raporty biznesowe:** Prezentuj wyniki kwartalne za pomocą linii trendu.
- **Slajdy edukacyjne:** Wizualizuj dane naukowe na wykładach.
- **Propozycje projektów:** Podkreśl kamienie milowe i prognozy.
- **Analiza marketingowa:** Przedstaw trendy ROI kampanii.
- **Integracja z pulpitami:** Eksportuj dane na żywo do PowerPointa na spotkania z interesariuszami.

## Rozważania dotyczące wydajności
- **Zarządzanie pamięcią:** Zawsze wywołuj `dispose()` na obiekcie `Presentation`, aby szybko zwolnić zasoby natywne.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **Licencja nie zastosowana** | Załaduj licencję próbną/pełną przed tworzeniem jakichkolwiek obiektów `Presentation`. |
| **Wykres jest pusty** | Sprawdź, czy slajd rzeczywiście zawiera serie danych; dodaj serie w razie potrzeby. |
| **Plik nie został zapisany** | Upewnij się, że katalog wyjściowy istnieje (użyj kroku „create directory java”). |
| **Kolory nie zostały zastosowane** | Użyj stałych `Color` z `java.awt.Color` lub `PresetColor`. |

## Najczęściej zadawane pytania

**Q: Czy mogę tworzyć inne typy wykresów oprócz wykresów liniowych?**  
A: Tak, Aspose.Slides obsługuje wykresy słupkowe, kołowe, punktowe i wiele innych typów wykresów.

**Q: Jak dodać wiele serii danych do wykresu liniowego?**  
A: Użyj `chart.getChartData().getSeries().add(...)`, aby wstawić dodatkowe serie przed formatowaniem.

**Q: Czy można wyeksportować wykres jako obraz?**  
A: Oczywiście. Wywołaj `chart.getChartData().getChartDataWorkbook().save(...)` lub renderuj slajd do formatu obrazu.

**Q: Czy potrzebuję płatnej licencji do programowania?**  
A: Bezpłatna licencja tymczasowa działa w celach ewaluacyjnych; licencja komercyjna jest wymagana przy wdrożeniach produkcyjnych.

**Q: Jakie wersje Javy są wspierane?**  
A: Biblioteka działa z JDK 8 aż do JDK 22 (użyj odpowiedniego klasyfikatora, np. `jdk16`). 

---

**Ostatnia aktualizacja:** 2026-03-07  
**Testowano z:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}