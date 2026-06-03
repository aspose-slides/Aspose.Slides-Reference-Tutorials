---
date: '2026-06-03'
description: Dowiedz się, jak eksportować wykres do Excela i tworzyć wykresy w Javie
  przy użyciu Aspose.Slides for Java. Opanuj data visualization, business report slides
  i workbook generation.
keywords:
- export chart to excel
- create chart java
- how to create chart
- add chart to powerpoint
- java chart visualization
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  headline: Export Chart to Excel and Create Charts with Aspose.Slides
  type: TechArticle
- description: Learn how to export chart to Excel and create chart Java using Aspose.Slides
    for Java. Master data visualization, business report slides, and workbook generation.
  name: Export Chart to Excel and Create Charts with Aspose.Slides
  steps:
  - name: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
    text: Visit the [Aspose Purchase page](https://purchase.aspose.com/buy) to get
      your license.
  - name: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
    text: For a free trial, download from [Releases](https://releases.aspose.com/slides/java/).
  - name: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
    text: Apply for a temporary license [here](https://purchase.aspose.com/temporary-license/).
  - name: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
    text: '**Business Report Slides:** Generate quarterly performance charts automatically
      from your data pipelines.'
  - name: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
    text: '**Academic Presentations:** Turn research data into clear visualizations
      without manual charting.'
  - name: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
    text: '**Financial Analysis:** Export chart data to Excel for auditors to verify
      numbers, reducing manual errors.'
  - name: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
    text: '**Marketing Analytics:** Visualize campaign metrics and share editable
      workbooks with stakeholders for collaborative decision‑making.'
  - name: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
    text: '**Automated Dashboard Generation:** Combine the chart‑creation API with
      scheduled jobs to produce up‑to‑date slide decks each morning.'
  type: HowTo
- questions:
  - answer: Yes. Replace `ChartType.Pie` with any other `ChartType` enum value such
      as `ChartType.Bar` or `ChartType.Line`.
    question: Can I use a different chart type (e.g., Bar, Line) with the same code?
  - answer: Absolutely. Modify the Excel file directly; the linked chart will reflect
      the changes the next time the presentation is opened.
    question: Is it possible to update the external workbook after the chart is created?
  - answer: No. The Excel export capability is included in the standard Aspose.Slides
      for Java license.
    question: Do I need a separate license for the Excel export feature?
  - answer: Aspose.Slides for Java supports JDK 16 and newer; earlier versions may
      work but are not officially tested.
    question: Which Java versions are supported?
  - answer: Use `chart.getChartData().setExternalWorkbook(null)` to embed the workbook,
      or keep the external link for dynamic updates.
    question: How can I embed the generated Excel workbook inside the PPTX file?
  type: FAQPage
title: Eksportuj wykres do Excela i twórz wykresy za pomocą Aspose.Slides
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Eksportuj wykres do Excela i twórz wykresy za pomocą Aspose.Slides

**Mistrzowskie techniki wizualizacji danych z Aspose.Slides for Java**

W dzisiejszym świecie napędzanym danymi, programowe *export chart to excel* to umiejętność, która może przekształcić surowe liczby w przekonujące historie wizualne. Niezależnie od tego, czy tworzysz zestaw slajdów raportu biznesowego, czy interaktywny pulpit analityczny, Aspose.Slides for Java daje możliwość generowania, dostosowywania i eksportowania wykresów bezpośrednio z kodu. W tym samouczku nauczysz się, jak tworzyć obiekty wykresów, eksportować dane wykresu do Excela oraz łączyć wykresy z zewnętrznymi skoroszytami w celu płynnego zarządzania danymi.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Slides for Java (v25.4+).  
- **Czy mogę eksportować dane wykresu do Excela?** Tak – użyj `readWorkbookStream()` i zapisz bajty do pliku *.xlsx*.  
- **Jakiej wersji Java wymaga?** JDK 16 lub wyższej.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna działa w ocenie; stała licencja jest wymagana w produkcji.  
- **Jaki typ wykresu jest pokazany?** Wykres kołowy, ale to samo podejście działa dla wykresów słupkowych, liniowych i innych typów.

## Czym jest Aspose.Slides for Java?
Aspose.Slides for Java to czysto‑Java API, które umożliwia programistom tworzenie, edytowanie i konwertowanie prezentacji PowerPoint bez Microsoft Office. Dostarcza obszernego zestawu klas do manipulacji slajdami, generowania wykresów i konwersji formatów, umożliwiając automatyczne rozwiązania raportowe. Obsługuje **ponad 50 typów wykresów**, pełne powiązanie danych oraz bezpośredni eksport do Excela, co czyni je idealnym dla projektów **data visualization java**.

## Dlaczego warto używać Aspose.Slides do tworzenia wykresu i eksportu wykresu do Excela?
Eksportuj wykres do Excela szybko i niezawodnie. Aspose.Slides eliminuje potrzebę instalacji Office, oferuje **ponad 50 wbudowanych stylów wykresów**, i przetwarza prezentacje **do 300 MB w mniej niż 30 sekund** na standardowym sprzęcie serwerowym. Otrzymujesz także natywne generowanie skoroszytów Excel, co pozwala analitykom pracować z surowymi liczbami bez ręcznego kopiowania‑wklejania.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące:

### Wymagane biblioteki i wersje
- **Aspose.Slides for Java** wersja 25.4 lub nowsza (obsługuje JDK 16+)

### Wymagania dotyczące konfiguracji środowiska
- Java Development Kit (JDK) 16 lub wyższy  
- IDE, takie jak IntelliJ IDEA lub Eclipse (lub dowolny edytor tekstu, który preferujesz)

### Wymagania dotyczące wiedzy
- Podstawowe umiejętności programowania w Javie  
- Znajomość narzędzi budowania Maven lub Gradle

## Konfiguracja Aspose.Slides for Java
Dodaj bibliotekę do swojego projektu, używając ulubionego systemu budowania.

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

Alternatywnie możesz [pobrać najnowszą wersję bezpośrednio](https://releases.aspose.com/slides/java/).

### Kroki uzyskania licencji
Aspose.Slides oferuje bezpłatną wersję próbną, aby przetestować pełne możliwości. Możesz również ubiegać się o tymczasową licencję lub zakupić licencję na dłuższy okres. Postępuj zgodnie z poniższymi krokami:

1. Odwiedź [stronę zakupu Aspose](https://purchase.aspose.com/buy), aby uzyskać licencję.  
2. W celu uzyskania wersji próbnej, pobierz z [Releases](https://releases.aspose.com/slides/java/).  
3. Złóż wniosek o tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

Po uzyskaniu pliku licencji, zainicjuj go w swojej aplikacji Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Przewodnik krok po kroku

### Jak utworzyć wykres – Załaduj prezentację
Załaduj istniejący plik PowerPoint, zanim będziesz mógł dodawać lub modyfikować wykresy.  
Klasa `Presentation` reprezentuje plik PowerPoint w pamięci, udostępniając slajdy, kształty i obiekty wykresów.  
Załaduj plik za pomocą `new Presentation("input.pptx")`, a następnie pracuj z pierwszym slajdem używając `presentation.getSlides().get_Item(0)`. Zawsze wywołuj `presentation.dispose()` w bloku `finally`, aby zwolnić zasoby natywne.

### Jak utworzyć wykres – Dodaj wykres kołowy do slajdu
Wstaw wykres kołowy, idealny do prezentacji danych proporcjonalnych.  
Interfejs `IChart` jest głównym punktem wejścia do manipulacji wykresami; `addChart` tworzy nowy wykres na docelowym slajdzie. Podaj typ wykresu (`ChartType.Pie`), współrzędne X/Y oraz szerokość/wysokość. Po utworzeniu możesz dostosować tytuły, legendę i serie danych poprzez obiekt `ChartData`.

### Jak eksportować wykres do Excela – Eksportuj dane wykresu
Eksport danych wykresu pozwala analitykom pracować z liczbami w Excelu, umożliwiając głębsze analizy.  
`readWorkbookStream()` zwraca podstawowy skoroszyt Excel wykresu jako tablicę bajtów. Wywołaj `chart.getChartData().readWorkbookStream()`, aby pobrać skoroszyt i zapisz tę tablicę do pliku o nazwie `externalWorkbook1.xlsx` przy użyciu standardowego I/O Javy. Powstały plik Excel zawiera dokładne dane użyte w wykresie, gotowe do dalszej analizy.

### Jak utworzyć wykres – Ustaw zewnętrzny skoroszyt dla danych dynamicznych
Połącz wykres z zewnętrznym skoroszytem, aby umożliwić aktualizacje danych w czasie rzeczywistym bez ponownego budowania slajdu.  
`setExternalWorkbook()` wiąże wykres z zewnętrznym plikiem Excel w celu dynamicznych aktualizacji danych. Użyj `chart.getChartData().setExternalWorkbook("externalWorkbook1.xlsx")`, aby powiązać wykres z tym plikiem. Gdy skoroszyt Excel zostanie zmodyfikowany, wykres automatycznie odzwierciedli zmiany przy następnym otwarciu prezentacji, wspierając scenariusze raportowania dynamicznego.

## Praktyczne zastosowania
Aspose.Slides oferuje wszechstronne rozwiązania dla różnych scenariuszy rzeczywistych:

1. **Slajdy raportów biznesowych:** Automatycznie generuj wykresy wyników kwartalnych z Twoich przepływów danych.  
2. **Prezentacje akademickie:** Przekształć dane badawcze w przejrzyste wizualizacje bez ręcznego tworzenia wykresów.  
3. **Analiza finansowa:** Eksportuj dane wykresu do Excela, aby audytorzy mogli zweryfikować liczby, zmniejszając błędy ręczne.  
4. **Analityka marketingowa:** Wizualizuj metryki kampanii i udostępniaj edytowalne skoroszyty interesariuszom w celu współpracy przy podejmowaniu decyzji.  
5. **Automatyczne generowanie pulpitów:** Połącz API tworzenia wykresów z zadaniami zaplanowanymi, aby codziennie rano tworzyć aktualne zestawy slajdów.

## Typowe problemy i rozwiązywanie
- **`FileNotFoundException`** – Upewnij się, że `dataDir` wskazuje prawidłowy folder i że ścieżka wyjściowa jest zapisywalna.  
- **Wycieki pamięci** – Zawsze wywołuj `presentation.dispose()` w bloku `finally`, aby zwolnić zasoby natywne.  
- **Wykres nie wyświetla się** – Upewnij się, że indeks slajdu (`get_Item(0)`) odpowiada istniejącemu slajdowi oraz że wymiary wykresu mieszczą się w granicach slajdu.  
- **Eksport do Excela tworzy pusty plik** – Potwierdź, że wykres rzeczywiście zawiera serie danych przed wywołaniem `readWorkbookStream()`.

## Najczęściej zadawane pytania

**P: Czy mogę użyć innego typu wykresu (np. słupkowy, liniowy) z tym samym kodem?**  
O: Tak. Zastąp `ChartType.Pie` dowolną inną wartością wyliczenia `ChartType`, taką jak `ChartType.Bar` lub `ChartType.Line`.

**P: Czy można zaktualizować zewnętrzny skoroszyt po utworzeniu wykresu?**  
O: Zdecydowanie. Zmodyfikuj plik Excel bezpośrednio; połączony wykres odzwierciedli zmiany przy następnym otwarciu prezentacji.

**P: Czy potrzebuję osobnej licencji na funkcję eksportu do Excela?**  
O: Nie. Funkcjonalność eksportu do Excela jest wliczona w standardową licencję Aspose.Slides for Java.

**P: Jakie wersje Java są obsługiwane?**  
O: Aspose.Slides for Java obsługuje JDK 16 i nowsze; wcześniejsze wersje mogą działać, ale nie są oficjalnie testowane.

**P: Jak mogę osadzić wygenerowany skoroszyt Excel wewnątrz pliku PPTX?**  
O: Użyj `chart.getChartData().setExternalWorkbook(null)`, aby osadzić skoroszyt, lub zachowaj zewnętrzny link dla aktualizacji dynamicznych.

---

**Ostatnia aktualizacja:** 2026-06-03  
**Testowano z:** Aspose.Slides for Java 25.4 (klasyfikator JDK 16)  
**Autor:** Aspose  

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Utwórz wykres w Javie z Aspose.Slides – Dodaj i zweryfikuj wykresy](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Odzyskaj dane skoroszytu z wykresów PowerPoint przy użyciu Aspose.Slides Java](/slides/java/charts-graphs/recover-workbook-data-powerpoint-charts-aspose-slides-java/)
- [Jak zaktualizować zakres danych wykresu PowerPoint przy użyciu Aspose.Slides for Java](/slides/java/charts-graphs/aspose-slides-java-modify-chart-data-range/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}