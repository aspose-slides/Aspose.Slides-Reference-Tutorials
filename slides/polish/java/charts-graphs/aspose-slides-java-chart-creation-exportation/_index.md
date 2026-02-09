---
date: '2026-02-09'
description: Dowiedz się, jak tworzyć wykresy i eksportować je do Excela przy użyciu
  Aspose.Slides for Java. Opanuj wizualizację danych, slajdy raportów biznesowych
  i generowanie skoroszytów.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Jak utworzyć wykres przy użyciu Aspose.Slides Java
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć wykres przy użyciu Aspose.Slides for Java

**Opanuj techniki wizualizacji danych z Aspose.Slides for Java**

W dzisiejszym świecie napędzanym danymi, *how to create chart* programowo to umiejętność, która może przekształcić surowe liczby w przekonujące historie wizualne. Niezależnie od tego, czy tworzysz zestaw slajdów raportu biznesowego, czy interaktywny pulpit analityczny, Aspose.Slides for Java daje możliwość generowania, dostosowywania i eksportowania wykresów bezpośrednio z kodu. W tym samouczku nauczysz się, jak tworzyć obiekty wykresów, eksportować dane wykresu do Excela oraz łączyć wykresy z zewnętrznymi skoroszytami w celu płynnego zarządzania danymi.

## Szybkie odpowiedzi
- **Jakiej biblioteki potrzebujesz?** Aspose.Slides for Java (v25.4+).  
- **Czy mogę wyeksportować dane wykresu do Excela?** Tak – użyj `readWorkbookStream()` i zapisz bajty do pliku *.xlsx*.  
- **Jaka wersja Javy jest wymagana?** JDK 16 lub wyższa.  
- **Czy potrzebna jest licencja?** Darmowa wersja próbna wystarcza do oceny; do produkcji wymagana jest stała licencja.  
- **Jaki typ wykresu jest pokazany?** Wykres kołowy (Pie), ale to samo podejście działa dla wykresów słupkowych, liniowych i innych typów.

## Czym jest Aspose.Slides for Java?
Aspose.Slides for Java to czysto‑Java API, które pozwala programistom tworzyć, edytować i konwertować prezentacje PowerPoint bez Microsoft Office. Obsługuje pełen zakres typów wykresów, powiązania danych i możliwości eksportu, co czyni je idealnym dla projektów **data visualization java**.

## Dlaczego warto używać Aspose.Slides do tworzenia wykresu i eksportowania wykresu do Excela?
- **Brak instalacji Office** – działa na każdym serwerze lub w środowisku chmurowym.  
- **Bogata biblioteka wykresów** – dziesiątki typów wykresów i pełna kontrola stylizacji.  
- **Bezpośredni eksport do Excela** – generuje zewnętrzny skoroszyt do dalszej analizy.  
- **Skoncentrowany na wydajności** – niski zużycie pamięci i szybkie przetwarzanie dużych zestawów slajdów.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:

### Wymagane biblioteki i wersje
- **Aspose.Slides for Java** wersja 25.4 lub nowsza

### Wymagania dotyczące konfiguracji środowiska
- Java Development Kit (JDK) 16 lub wyższy  
- IDE, takie jak IntelliJ IDEA lub Eclipse (lub dowolny edytor tekstu, który preferujesz)

### Wymagania wiedzy
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
Aspose.Slides oferuje darmową licencję próbną, aby przetestować pełne możliwości. Możesz również ubiegać się o tymczasową licencję lub zakupić ją do długotrwałego użytku. Postępuj zgodnie z poniższymi krokami:

1. Odwiedź [stronę zakupu Aspose](https://purchase.aspose.com/buy), aby uzyskać licencję.  
2. Aby uzyskać darmową wersję próbną, pobierz z [Releases](https://releases.aspose.com/slides/java/).  
3. Złóż wniosek o tymczasową licencję [tutaj](https://purchase.aspose.com/temporary-license/).

Po uzyskaniu pliku licencji, zainicjalizuj go w aplikacji Java:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Przewodnik krok po kroku

### Jak utworzyć wykres – Załaduj prezentację
Załadowanie istniejącego pliku PowerPoint to pierwszy krok, zanim będziesz mógł dodać lub modyfikować wykresy.

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

**Wyjaśnienie:**  
- `Presentation` reprezentuje plik PowerPoint.  
- Zawsze wywołuj `dispose()`, aby zwolnić zasoby natywne.

### Jak utworzyć wykres – Dodaj wykres kołowy do slajdu
Teraz wstawimy wykres kołowy, który jest idealny do przedstawiania danych proporcjonalnych.

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

**Wyjaśnienie:**  
- `addChart` wstawia wykres na pierwszym slajdzie.  
- Parametry określają typ wykresu, pozycję X/Y oraz rozmiar.

### Jak wyeksportować wykres do Excela – Eksport danych wykresu
Eksportowanie danych wykresu pozwala analitykom pracować z liczbami w Excelu, umożliwiając głębsze wnioski.

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

**Wyjaśnienie:**  
- `readWorkbookStream()` wyodrębnia podstawowy skoroszyt Excel wykresu jako tablicę bajtów.  
- Tablica bajtów jest zapisywana do `externalWorkbook1.xlsx`, dostarczając gotowy do użycia plik Excel.

### Jak utworzyć wykres – Ustaw zewnętrzny skoroszyt dla danych dynamicznych
Połączenie wykresu z zewnętrznym skoroszytem umożliwia aktualizację wykresu poprzez edycję pliku Excel.

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

**Wyjaśnienie:**  
- `setExternalWorkbook` wiąże wykres z określonym plikiem Excel, umożliwiając aktualizacje danych w czasie rzeczywistym bez ponownego budowania slajdu.

## Praktyczne zastosowania
Aspose.Slides oferuje wszechstronne rozwiązania dla różnych scenariuszy rzeczywistych:

1. **Slajdy raportu biznesowego:** Automatycznie generuj wykresy kwartalnych wyników z Twoich potoków danych.  
2. **Prezentacje akademickie:** Przekształcaj dane badawcze w przejrzyste wizualizacje bez ręcznego tworzenia wykresów.  
3. **Analiza finansowa:** Eksportuj dane wykresu do Excela, aby audytorzy mogli zweryfikować liczby.  
4. **Analityka marketingowa:** Wizualizuj metryki kampanii i udostępniaj edytowalne skoroszyty interesariuszom.

## Typowe problemy i rozwiązywanie
- **`FileNotFoundException`** – Sprawdź, czy `dataDir` wskazuje na istniejący folder i czy ścieżka wyjściowa jest zapisywalna.  
- **Wycieki pamięci** – Zawsze wywołuj `pres.dispose()` w bloku `finally`, aby zwolnić zasoby natywne.  
- **Wykres nie wyświetla się** – Upewnij się, że indeks slajdu (`get_Item(0)`) odpowiada istniejącemu slajdowi.

## Najczęściej zadawane pytania

**Q: Czy mogę użyć innego typu wykresu (np. słupkowego, liniowego) z tym samym kodem?**  
A: Tak. Zamień `ChartType.Pie` na dowolną inną wartość wyliczenia `ChartType`, taką jak `ChartType.Bar` lub `ChartType.Line`.

**Q: Czy można zaktualizować zewnętrzny skoroszyt po utworzeniu wykresu?**  
A: Oczywiście. Zmodyfikuj plik Excel bezpośrednio; połączony wykres odzwierciedli zmiany przy następnym otwarciu prezentacji.

**Q: Czy potrzebna jest osobna licencja na funkcję eksportu do Excela?**  
A: Nie. Funkcjonalność eksportu do Excela jest zawarta w standardowej licencji Aspose.Slides for Java.

**Q: Jakie wersje Javy są wspierane?**  
A: Aspose.Slides for Java obsługuje JDK 16 i nowsze; wcześniejsze wersje mogą działać, ale nie są oficjalnie testowane.

**Q: Jak mogę osadzić wygenerowany skoroszyt Excel wewnątrz pliku PPTX?**  
A: Użyj `chart.getChartData().setExternalWorkbook(null)`, aby osadzić skoroszyt, lub zachowaj zewnętrzny link dla dynamicznych aktualizacji.

---

**Ostatnia aktualizacja:** 2026-02-09  
**Testowano z:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}