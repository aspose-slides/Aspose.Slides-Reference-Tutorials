---
"date": "2025-04-17"
"description": "Dowiedz się, jak tworzyć i dostosowywać dynamiczne wykresy giełdowe w programie PowerPoint przy użyciu Aspose.Slides dla języka Java. Ten przewodnik obejmuje inicjowanie prezentacji, dodawanie serii danych, formatowanie wykresów i zapisywanie plików."
"title": "Tworzenie dynamicznych wykresów giełdowych w programie PowerPoint za pomocą Aspose.Slides dla języka Java"
"url": "/pl/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Tworzenie dynamicznych wykresów giełdowych w programie PowerPoint za pomocą Aspose.Slides dla języka Java

## Wstęp

Ulepsz swoje prezentacje PowerPoint, włączając dynamiczne wykresy giełdowe. Niezależnie od tego, czy jesteś analitykiem finansowym, profesjonalistą biznesowym czy nauczycielem, który potrzebuje skutecznej wizualizacji trendów danych, ten samouczek przeprowadzi Cię przez proces tworzenia i dostosowywania wykresów giełdowych przy użyciu Aspose.Slides dla Java. Pod koniec tego przewodnika będziesz w stanie załadować istniejące pliki PowerPoint, dodać szczegółowe wykresy giełdowe z niestandardowymi seriami i kategoriami, sformatować je w piękny sposób i zapisać ulepszoną prezentację.

**Czego się nauczysz:**
- Zainicjuj prezentację w Javie za pomocą Aspose.Slides
- Dodawaj i dostosowuj wykresy giełdowe
- Wyczyść serie danych i kategorie
- Wprowadź nowe punkty danych w celu przeprowadzenia kompleksowej analizy
- Formatuj linie i paski wykresu w sposób efektywny
- Zapisz zaktualizowaną prezentację

Gotowy do tworzenia wizualnie atrakcyjnych prezentacji? Zaczynajmy!

## Wymagania wstępne

Zanim zaczniemy, upewnij się, że masz następujące rzeczy:

- **Zestaw narzędzi programistycznych Java (JDK)**Upewnij się, że JDK jest zainstalowany w systemie.
- **Środowisko programistyczne (IDE)**:Użyj dowolnego środowiska IDE, takiego jak IntelliJ IDEA lub Eclipse, do pisania i uruchamiania kodu Java.
- **Aspose.Slides dla biblioteki Java**:Do tego samouczka wymagana jest wersja 25.4 Aspose.Slides for Java.

### Konfigurowanie Aspose.Slides dla Java

#### Maven
Aby zintegrować Aspose.Slides ze swoim projektem za pomocą Maven, dodaj następującą zależność do swojego `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Użytkownicy Gradle powinni uwzględnić to w swoim `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Bezpośrednie pobieranie
Alternatywnie, pobierz najnowszy plik JAR z [Aspose.Slides dla wydań Java](https://releases.aspose.com/slides/java/).

**Nabycie licencji**: Możesz zacząć od bezpłatnego okresu próbnego lub poprosić o tymczasową licencję. W przypadku dłuższego użytkowania rozważ zakup pełnej licencji.

## Przewodnik wdrażania

Przyjrzyjmy się bliżej każdej funkcji krok po kroku.

### Zainicjuj prezentację
#### Przegląd
Na początek wczytaj istniejący plik programu PowerPoint, aby przygotować go do modyfikacji.

#### Przewodnik krok po kroku
1. **Importuj bibliotekę**:
   
   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Załaduj plik prezentacji**:
   
   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Gotowość do wykonywania operacji na 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Dodaj wykres giełdowy do slajdu
#### Przegląd
Ten krok polega na dodaniu wykresu giełdowego do pierwszego slajdu prezentacji.

3. **Dodaj wykres**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Wyczyść istniejące serie danych i kategorie na wykresie
#### Przegląd
Usuń z wykresu wszelkie istniejące serie danych lub kategorie, aby zacząć od nowa.

4. **Wyczyść dane**:
   
   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Dodaj kategorie do danych wykresu
#### Przegląd
Dodaj niestandardowe kategorie, aby zapewnić lepszą segmentację i zrozumienie danych.

5. **Wstaw kategorie**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Dodaj kategorie
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Dodaj serię danych do wykresu
#### Przegląd
Zintegruj różne serie danych, takie jak otwarcie, maksimum, minimum i zamknięcie, aby uzyskać kompleksową analizę.

6. **Dodaj serię danych**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Dodaj serie dla „Otwarcia”, „Wysokości”, „Niskości” i „Zamknięcia”
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Dodaj punkty danych do serii
#### Przegląd
Wypełnij każdą serię konkretnymi punktami danych, aby uzyskać dokładne przedstawienie.

7. **Wstaw punkty danych**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Dodaj punkty danych do serii „Otwórz”
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Dodaj punkty danych do serii „Wysokie”
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Dodaj punkty danych do serii „Niski”
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Dodaj punkty danych do serii „Zamknij”
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formatuj linie High-Low i paski wzrostowe/spadkowe
#### Przegląd
Dostosuj wygląd linii maks.-min. oraz pasków wzrostowych/spadkowych, aby uzyskać lepszą wizualizację.

8. **Formatuj linie wysokie-niskie**:
   
   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Formatuj linie od góry do dołu dla serii „Zamknij”
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

9. **Wyświetlaj paski w górę/w dół**:
   
   ```java
   // Wyświetlaj paski w górę/w dół dla grupy serii wykresów giełdowych
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Dostosuj etykiety danych na liniach High-Low
#### Przegląd
Dodawaj i formatuj etykiety danych, aby wyświetlać wartości w wierszach maks.-min.

10. **Pokaż wartości na paskach wzrostowych/spadkowych**:
    
    ```java
    // Pokaż wartości na słupkach w górę/w dół dla każdej serii w grupie wykresów
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Ustaw kolor wypełnienia pasków w dół
#### Przegląd
Ustaw niestandardowy kolor wypełnienia pasków w górę/w dół, aby poprawić ich widoczność.

11. **Zmień kolory pasków góra/dół**:
    
    ```java
    // Zmień kolory pasków góra/dół dla każdej serii w grupie wykresów
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // Seria „Otwarte”
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Słupki w górę w kolorze cyjanowym
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // Seria „Wysoka”
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Paski dolne w kolorze ciemnej morskiej zieleni
        }
    }
    ```

### Zapisz plik PowerPoint
#### Przegląd
Zapisz zmiany w nowym pliku programu PowerPoint.

12. **Zapisz prezentację**:
    
    ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Wniosek

Gratulacje! Udało Ci się utworzyć i dostosować dynamiczne wykresy giełdowe w programie PowerPoint przy użyciu Aspose.Slides dla języka Java. Ten proces wzbogaca Twoje prezentacje o atrakcyjne wizualnie wizualizacje danych, umożliwiając skuteczną komunikację spostrzeżeń finansowych. Jeśli jesteś zainteresowany dalszą personalizacją lub eksploracją innych typów wykresów, rozważ zanurzenie się w kompleksowym [Dokumentacja Aspose.Slides](https://docs.aspose.com/slides/java/).

## Dalsza lektura i odniesienia
- Dokumentacja Aspose.Slides dla Java: Zapoznaj się ze szczegółowymi przewodnikami dotyczącymi korzystania z różnych funkcji Aspose.Slides.
- Omówienie narzędzi do tworzenia wykresów w programie PowerPoint: Poznaj różne narzędzia do tworzenia wykresów dostępne w programie Microsoft PowerPoint.
- Najlepsze praktyki wizualizacji danych: Dowiedz się, jak skutecznie prezentować dane za pomocą środków wizualnych.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}