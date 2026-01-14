---
date: '2026-01-14'
description: Dowiedz się, jak wyeksportować wykres do Excela przy użyciu Aspose.Slides
  for Java i dodać slajd z wykresem kołowym do prezentacji. Przewodnik krok po kroku
  z kodem.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Eksport wykresu do Excela przy użyciu Aspose.Slides Java
url: /pl/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Eksport wykresu do Excela przy użyciu Aspose.Slides for Java

**Opanuj techniki wizualizacji danych z Aspose.Slides for Java**

W dzisiejszym świecie napędzanym danymi możliwość **eksportu wykresu do excela** bezpośrednio z aplikacji Java może przekształcić statyczne wizualizacje PowerPointa w wielokrotnego użytku, analizowalne zestawy danych. Niezależnie od tego, czy musisz generować raporty, zasilać potoki analityczne, czy po prostu umożliwić użytkownikom biznesowym edycję danych wykresu w Excelu, Aspose.Slides czyni to prostym. Ten samouczek przeprowadzi Cię przez tworzenie wykresu, dodanie slajdu z wykresem kołowym oraz eksport danych wykresu do skoroszytu Excel.

**Czego się nauczysz:**
- Łatwe ładowanie i manipulowanie plikami prezentacji
- **Dodawanie slajdu z wykresem kołowym** oraz innych typów wykresów do slajdów
- **Eksport wykresu do excela** (generowanie pliku Excel z wykresu) w celu dalszej analizy
- Ustawianie ścieżki zewnętrznego skoroszytu w celu **osadzenia wykresu w prezentacji** i synchronizacji danych

Zanurzmy się!

## Szybkie odpowiedzi
- **Jaki jest główny cel?** Eksport danych wykresu ze slajdu PowerPoint do pliku Excel.  
- **Jakiej wersji biblioteki potrzebujesz?** Aspose.Slides for Java 25.4 lub nowszej.  
- **Czy potrzebna jest licencja?** Bezpłatna wersja próbna wystarczy do oceny; licencja komercyjna jest wymagana w środowisku produkcyjnym.  
- **Czy mogę dodać slajd z wykresem kołowym?** Tak – w samouczku pokazano, jak dodać wykres kołowy.  
- **Czy Java 16 jest minimalna?** Tak, zalecany jest JDK 16 lub wyższy.

## Jak wyeksportować wykres do excela przy użyciu Aspose.Slides?
Eksportowanie danych wykresu do Excela jest tak proste, jak załadowanie prezentacji, utworzenie wykresu i zapisanie strumienia skoroszytu wykresu do pliku. Poniższe kroki przeprowadzą Cię przez cały proces, od konfiguracji projektu po ostateczną weryfikację.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz przygotowane następujące elementy:

### Wymagane biblioteki i wersje
- **Aspose.Slides for Java** w wersji 25.4 lub nowszej

### Wymagania środowiskowe
- Java Development Kit (JDK) 16 lub wyższy
- Edytor kodu lub IDE, takie jak IntelliJ IDEA lub Eclipse

### Wymagania wiedzy
- Podstawowe umiejętności programowania w Javie
- Znajomość systemów budowania Maven lub Gradle

## Konfiguracja Aspose.Slides for Java
Aby rozpocząć korzystanie z Aspose.Slides, dodaj go do swojego projektu przy użyciu Maven lub Gradle.

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
Aspose.Slides oferuje bezpłatną licencję próbną, abyś mógł poznać pełne możliwości. Możesz także ubiegać się o licencję tymczasową lub zakupić licencję na dłuższy okres. Postępuj zgodnie z poniższymi krokami:
1. Odwiedź stronę [Aspose Purchase](https://purchase.aspose.com/buy), aby uzyskać licencję.  
2. Aby uzyskać wersję próbną, pobierz ją z [Releases](https://releases.aspose.com/slides/java/).  
3. Złóż wniosek o licencję tymczasową [tutaj](https://purchase.aspose.com/temporary-license/).

Po uzyskaniu pliku licencji zainicjalizuj go w aplikacji Java:
```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Przewodnik po implementacji

### Funkcja 1: Ładowanie prezentacji
Ładowanie prezentacji jest pierwszym krokiem w każdej operacji manipulacji.

#### Przegląd
Ta funkcja demonstruje, jak wczytać istniejący plik PowerPoint przy użyciu Aspose.Slides for Java.

#### Implementacja krok po kroku
**Ładowanie prezentacji**
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
- `Presentation` jest inicjalizowana ze ścieżką do pliku `.pptx`.  
- Zawsze zwalniaj obiekt `Presentation`, aby zwolnić zasoby natywne.

### Funkcja 2: Dodawanie slajdu z wykresem kołowym
Dodanie wykresu może znacząco podnieść jakość prezentacji danych, a wielu programistów pyta **jak dodać slajd z wykresem** w Javie.

#### Przegląd
Ta funkcja pokazuje, jak dodać **wykres kołowy** (klasyczny scenariusz „dodaj wykres kołowy”) do pierwszego slajdu prezentacji.

#### Implementacja krok po kroku
**Dodawanie wykresu kołowego**
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
- `addChart` wstawia wykres kołowy.  
- Parametry określają typ wykresu oraz jego pozycję/rozmiar na slajdzie.

### Funkcja 3: Generowanie Excela z wykresu
Eksportowanie danych wykresu pozwala **generować excel z wykresu** w celu głębszej analizy.

#### Przegląd
Ta funkcja demonstruje eksport danych wykresu z prezentacji do zewnętrznego skoroszytu Excel.

#### Implementacja krok po kroku
**Eksport danych**
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
- `readWorkbookStream` pobiera dane skoroszytu wykresu.  
- Tablica bajtów jest zapisywana do pliku `.xlsx` przy użyciu `FileOutputStream`.

### Funkcja 4: Osadzanie wykresu w prezentacji z zewnętrznym skoroszytem
Połączenie wykresu z zewnętrznym skoroszytem umożliwia **osadzenie wykresu w prezentacji** i utrzymanie synchronizacji danych.

#### Przegląd
Ta funkcja demonstruje ustawienie ścieżki do zewnętrznego skoroszytu, aby wykres mógł odczytywać i zapisywać dane bezpośrednio z Excela.

#### Implementacja krok po kroku
**Ustawienie ścieżki do zewnętrznego skoroszytu**
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
- `setExternalWorkbook` łączy wykres z plikiem Excel, umożliwiając dynamiczne aktualizacje bez konieczności ponownego budowania slajdu.

## Praktyczne zastosowania
Aspose.Slides oferuje wszechstronne rozwiązania dla różnych scenariuszy:

1. **Raporty biznesowe:** Twórz szczegółowe raporty z wykresami bezpośrednio z aplikacji Java.  
2. **Prezentacje akademickie:** Wzbogacaj wykłady interaktywnymi slajdami z wykresem kołowym.  
3. **Analiza finansowa:** **Eksport wykresu do excela** w celu dogłębnego modelowania finansowego.  
4. **Analityka marketingowa:** Wizualizuj wyniki kampanii i **generuj excel z wykresu** dla zespołu analityków.

## Najczęściej zadawane pytania

**P: Czy mogę używać tego podejścia z innymi typami wykresów (np. słupkowy, liniowy)?**  
O: Oczywiście. Zamień `ChartType.Pie` na dowolną inną wartość enum `ChartType`.

**P: Czy potrzebuję osobnej biblioteki Excel do odczytu wyeksportowanego pliku?**  
O: Nie. Wyeksportowany plik `.xlsx` jest standardowym skoroszytem Excel, który można otworzyć w dowolnej aplikacji arkusza kalkulacyjnego.

**P: Jak zewnętrzny skoroszyt wpływa na rozmiar slajdu?**  
O: Połączenie z zewnętrznym skoroszytem nie zwiększa znacząco rozmiaru pliku PPTX; wykres odwołuje się do skoroszytu w czasie uruchomienia.

**P: Czy można zaktualizować dane w Excelu i mieć je automatycznie odzwierciedlone na slajdzie?**  
O: Tak. Po wywołaniu `setExternalWorkbook` wszelkie zmiany zapisane w skoroszycie będą widoczne po ponownym otwarciu prezentacji.

**P: Co zrobić, jeśli muszę wyeksportować wiele wykresów z tej samej prezentacji?**  
O: Przejdź po kolekcji wykresów każdego slajdu, wywołaj `readWorkbookStream()` dla każdego i zapisz do osobnych plików skoroszytu.

---

**Ostatnia aktualizacja:** 2026-01-14  
**Testowano z:** Aspose.Slides 25.4 for Java  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}