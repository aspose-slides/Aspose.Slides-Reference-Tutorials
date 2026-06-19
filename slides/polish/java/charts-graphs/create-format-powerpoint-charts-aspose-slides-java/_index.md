---
date: '2026-03-15'
description: Poznaj sposób dodawania wykresu słupkowego grupowanego do slajdu PowerPoint
  przy użyciu Aspose.Slides for Java, obejmujący kroki dodawania wykresu do slajdu
  oraz efektywne tworzenie slajdu PowerPoint w Javie.
keywords:
- Aspose.Slides for Java
- PowerPoint Charts
- Java PowerPoint Automation
title: Dodaj wykres słupkowy grupowany do PPT przy użyciu Aspose.Slides Java
url: /pl/java/charts-graphs/create-format-powerpoint-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dodaj wykres kolumnowy grupowany do PPT przy użyciu Aspose.Slides Java

## Wprowadzenie
W tym przewodniku **dodasz wykres kolumnowy grupowany** do prezentacji PowerPoint programowo przy użyciu Aspose.Slides dla Javy. Niezależnie od tego, czy tworzysz raporty biznesowe, prezentacje edukacyjne, czy materiały marketingowe, automatyzacja tworzenia wykresów oszczędza czas i zapewnia spójność. Przeprowadzimy Cię przez konfigurację biblioteki, tworzenie slajdu, dodawanie wykresu, stosowanie stylów linii i zaokrąglonych narożników oraz ostateczne zapisanie pliku. Po zakończeniu będziesz pewnie **dodawać wykresy do slajdu** i nawet **tworzyć slajdy PowerPoint w Javie**.

### Szybkie odpowiedzi
- **Jaka jest podstawowa klasa do rozpoczęcia?** `Presentation`
- **Jakiego typu wykres jest używany?** `ChartType.ClusteredColumn`
- **Jak włączyć zaokrąglone narożniki?** `chart.setRoundedCorners(true);`
- **Jaki format jest zalecany do zapisu?** `SaveFormat.Pptx`
- **Czy potrzebna jest licencja do rozwoju?** Darmowa wersja próbna działa do testów; licencja płatna jest wymagana w produkcji.

## Co to jest wykres kolumnowy grupowany?
Wykres kolumnowy grupowany grupuje wiele serii danych obok siebie dla każdej kategorii, co czyni go idealnym do porównywania wartości w różnych grupach. Aspose.Slides pozwala wygenerować ten typ wykresu w pełni w kodzie, bez otwierania PowerPointa.

## Dlaczego warto używać Aspose.Slides dla Javy do dodawania wykresu kolumnowego grupowanego?
- **Pełna automatyzacja** – Nie wymaga ręcznej interakcji z UI.  
- **Wieloplatformowość** – Działa na każdym systemie operacyjnym obsługującym Javę.  
- **Bogate formatowanie** – Kontrola stylów linii, wypełnień, zaokrąglonych narożników i nie tylko.  
- **Brak zależności COM** – W przeciwieństwie do Office Interop, działa bezpiecznie na serwerach.

## Wymagania wstępne
- **Aspose.Slides dla Javy** (v25.4 lub nowsza)  
- **JDK 16** (lub nowsza)  
- IDE, takie jak IntelliJ IDEA, Eclipse lub NetBeans  

## Konfiguracja Aspose.Slides dla Javy
Bibliotekę możesz dodać za pomocą Maven, Gradle lub pobrać bezpośrednio.

### Korzystanie z Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Korzystanie z Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Bezpośrednie pobranie
Pobierz najnowszą wersję z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroki uzyskania licencji
- **Darmowa wersja próbna** – Testuj wszystkie funkcje bez ograniczeń czasowych.  
- **Licencja tymczasowa** – Zamów ją w portalu Aspose w celu pełnej oceny funkcji.  
- **Zakup** – Uzyskaj stałą licencję do użytku produkcyjnego.

## Przewodnik implementacji

### Tworzenie prezentacji i dodawanie slajdu
#### Przegląd
Najpierw tworzymy nowy obiekt `Presentation` i pobieramy domyślny slajd, który znajduje się w nowo utworzonym pliku.

#### Krok po kroku
**1. Inicjalizacja obiektu Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. Dostęp do pierwszego slajdu**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Zwolnienie zasobów**  
```java
if (presentation != null) presentation.dispose();
```

### Dodawanie wykresu do slajdu
#### Przegląd
Teraz osadzamy **wykres kolumnowy grupowany** w przygotowanym slajdzie.

#### Krok po kroku
**1. Inicjalizacja obiektu Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. Dostęp do pierwszego slajdu**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Dodaj wykres kolumnowy grupowany**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Zwolnienie zasobów**  
```java
if (presentation != null) presentation.dispose();
```

### Formatowanie stylu linii wykresu i ustawianie zaokrąglonych narożników
#### Przegląd
Popraw wygląd, stosując jednolite wypełnienie linii, pojedynczy styl linii oraz zaokrąglone narożniki.

#### Krok po kroku
**1. Inicjalizacja obiektu Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. Dostęp do pierwszego slajdu**  
```java
ISlide slide = presentation.getSlides().get_Item(0);
```

**3. Dodaj wykres kolumnowy grupowany**  
```java
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

**4. Ustaw format linii na typ wypełnienia stałego**  
```java
chart.getLineFormat().getFillFormat().setFillType(FillType.Solid);
```

**5. Zastosuj pojedynczy styl linii**  
```java
chart.getLineFormat().setStyle(LineStyle.Single);
```

**6. Włącz zaokrąglone narożniki dla obszaru wykresu**  
```java
chart.setRoundedCorners(true);
```

**7. Zwolnienie zasobów**  
```java
if (presentation != null) presentation.dispose();
```

### Zapis prezentacji
#### Przegląd
Na koniec zapisujemy prezentację na dysku w formacie PPTX.

#### Krok po kroku
**1. Inicjalizacja obiektu Presentation**  
```java
Presentation presentation = new Presentation();
```

**2. Definicja katalogu wyjściowego i nazwy pliku**  
```java
String dataDir = "YOUR_DOCUMENT_DIRECTORY/";
String outputFile = dataDir + "out.pptx";
```

**3. Zapis prezentacji w formacie PPTX**  
```java
presentation.save(outputFile, SaveFormat.Pptx);
```

**4. Zwolnienie zasobów**  
```java
if (presentation != null) presentation.dispose();
```

## Praktyczne zastosowania
- **Raporty biznesowe** – Automatyzuj kwartalne prezentacje finansowe z dynamicznymi wykresami.  
- **Treści edukacyjne** – Generuj slajdy wykładowe pobierające dane z bazy danych.  
- **Prezentacje marketingowe** – Wizualizuj trendy produktów przy użyciu dopracowanych wykresów.

## Rozważania dotyczące wydajności
- **Zarządzanie zasobami** – Zawsze wywołuj `dispose()` lub używaj try‑with‑resources.  
- **Optymalizacja pamięci** – Przetwarzaj duże zestawy danych w mniejszych partiach.  
- **Najlepsze praktyki** – Gdy to możliwe, preferuj niezmienne struktury danych dla serii wykresu.

## Typowe problemy i rozwiązania
| Problem | Rozwiązanie |
|-------|----------|
| **`NullPointerException` przy `getSlides()`** | Upewnij się, że obiekt `Presentation` został pomyślnie zainicjowany przed dostępem do slajdów. |
| **Wykres się nie wyświetla** | Sprawdź, czy wymiary wykresu (x, y, szerokość, wysokość) mieszczą się w granicach slajdu. |
| **Licencja nie została zastosowana** | Załaduj plik licencji przed utworzeniem obiektu `Presentation`: `License license = new License(); license.setLicense("path/to/license.xml");` |

## Najczęściej zadawane pytania

**P: Jak dodać różne typy wykresów przy użyciu Aspose.Slides?**  
O: Zastąp `ChartType.ClusteredColumn` inną wartością wyliczenia, np. `ChartType.Pie`, `ChartType.Line` lub `ChartType.Bar`.

**P: Co zrobić, gdy pojawią się błędy kompilacji?**  
O: Sprawdź, czy używasz JDK 16 lub nowszej oraz czy zależność Maven/Gradle odpowiada wersji podanej powyżej.

**P: Czy mogę wypełnić wykres danymi z bazy danych?**  
O: Tak. Uzyskaj dostęp do kolekcji `getChartData()` wykresu, utwórz serie i kategorie oraz wypełnij je wartościami pobranymi w czasie wykonywania.

**P: Jak poprawić wydajność przy bardzo dużych prezentacjach?**  
O: Podziel pracę na wiele instancji `Presentation`, ponownie używaj szablonów wykresów i zawsze szybko zwalniaj obiekty.

## Zakończenie
Masz teraz kompletny, krok po kroku przepis na **dodanie wykresu kolumnowego grupowanego** do slajdu PowerPoint przy użyciu Aspose.Slides dla Javy. Eksperymentuj z innymi typami wykresów, podłączaj źródła danych w czasie rzeczywistym i integruj tę logikę z większymi pipeline'ami raportowymi, aby zautomatyzować przepływ pracy prezentacji.

---

**Ostatnia aktualizacja:** 2026-03-15  
**Testowano z:** Aspose.Slides 25.4 dla Javy (JDK 16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}