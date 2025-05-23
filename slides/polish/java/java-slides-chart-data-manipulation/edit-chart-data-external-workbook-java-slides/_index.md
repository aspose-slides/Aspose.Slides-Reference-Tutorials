---
"description": "Dowiedz się, jak edytować dane wykresu w zewnętrznym skoroszycie, używając Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym."
"linktitle": "Edytuj dane wykresu w skoroszycie zewnętrznym w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Edytuj dane wykresu w skoroszycie zewnętrznym w slajdach Java"
"url": "/pl/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Edytuj dane wykresu w skoroszycie zewnętrznym w slajdach Java


## Wprowadzenie do edycji danych wykresu w skoroszycie zewnętrznym w slajdach Java

W tym przewodniku pokażemy, jak edytować dane wykresu w zewnętrznym skoroszycie za pomocą Aspose.Slides dla Java. Dowiesz się, jak programowo modyfikować dane wykresu w prezentacji PowerPoint. Upewnij się, że biblioteka Aspose.Slides dla Java jest zainstalowana i skonfigurowana w Twoim projekcie.

## Wymagania wstępne

- Aspose.Slides dla Java
- Środowisko programistyczne Java

## Krok 1: Załaduj prezentację

Najpierw musimy załadować prezentację PowerPoint zawierającą wykres, którego dane chcemy edytować. Zastąp `"Your Document Directory"` z rzeczywistą ścieżką do pliku prezentacji.

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Krok 2: Uzyskaj dostęp do wykresu

Po załadowaniu prezentacji musimy uzyskać dostęp do wykresu w prezentacji. W tym przykładzie zakładamy, że wykres znajduje się na pierwszym slajdzie i jest pierwszym kształtem na tym slajdzie.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Krok 3: Modyfikuj dane wykresu

Teraz zmodyfikujmy dane wykresu. Skupimy się na zmianie konkretnego punktu danych na wykresie. W tym przykładzie ustawiliśmy wartość pierwszego punktu danych w pierwszej serii na 100. Możesz dostosować tę wartość według potrzeb.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Krok 4: Zapisz prezentację

Po wprowadzeniu niezbędnych zmian do danych wykresu zapisz zmodyfikowaną prezentację do nowego pliku. Możesz określić ścieżkę i format pliku wyjściowego zgodnie ze swoimi wymaganiami.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Krok 5: Czyszczenie

Nie zapomnij pozbyć się obiektu prezentacji, aby zwolnić zasoby.

```java
if (pres != null) pres.dispose();
```

Teraz udało Ci się edytować dane wykresu w zewnętrznym skoroszycie w prezentacji PowerPoint przy użyciu Aspose.Slides dla Java. Możesz dostosować ten kod do swoich konkretnych potrzeb i zintegrować go z aplikacjami Java.

## Kompletny kod źródłowy

```java
        // Zwróć uwagę, że ścieżka do zewnętrznego skoroszytu jest rzadko zapisywana w prezentacji
        // więc proszę skopiować plik externalWorkbook.xlsx z katalogu Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ przed uruchomieniem przykładu
        // Ścieżka do katalogu dokumentów.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Wniosek

W tym kompleksowym przewodniku zbadaliśmy, jak edytować dane wykresu w zewnętrznych skoroszytach w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Postępując zgodnie z instrukcjami krok po kroku i przykładami kodu źródłowego, zdobyłeś wiedzę i umiejętności, aby programowo modyfikować dane wykresu z łatwością.

## Najczęściej zadawane pytania

### Jak określić inny wykres lub slajd?

Aby uzyskać dostęp do innego wykresu lub slajdu, zmodyfikuj odpowiedni indeks w `getSlides().get_Item()` I `getShapes().get_Item()` metody. Pamiętaj, że indeksowanie zaczyna się od 0.

### Czy mogę edytować dane na wielu wykresach w tej samej prezentacji?

Tak, możesz edytować dane na wielu wykresach w tej samej prezentacji, powtarzając kroki modyfikacji danych wykresu dla każdego wykresu.

### Co zrobić, jeśli chcę edytować dane w zewnętrznym skoroszycie w innym formacie?

Możesz dostosować kod do obsługi różnych formatów skoroszytów zewnętrznych, używając odpowiednich klas i metod Aspose.Cells do odczytu i zapisu danych w tym formacie.

### Jak mogę zautomatyzować ten proces dla wielu prezentacji?

Możesz utworzyć pętlę, aby przetwarzać wiele prezentacji, ładować każdą z nich, wprowadzać żądane zmiany i zapisywać zmodyfikowane prezentacje jedną po drugiej.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}