---
"description": "Dowiedz się, jak ustawić zewnętrzne skoroszyty i zaktualizować dane wykresu w Java Slides przy użyciu Aspose.Slides for Java. Udoskonal swoje umiejętności automatyzacji programu PowerPoint."
"linktitle": "Ustaw zewnętrzny skoroszyt z danymi wykresu aktualizacji w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw zewnętrzny skoroszyt z danymi wykresu aktualizacji w slajdach Java"
"url": "/pl/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw zewnętrzny skoroszyt z danymi wykresu aktualizacji w slajdach Java


## Wprowadzenie do ustawiania zewnętrznego skoroszytu z danymi wykresu aktualizacji w slajdach Java

tym kompleksowym przewodniku przeprowadzimy Cię przez proces ustawiania zewnętrznego skoroszytu z zaktualizowanymi danymi wykresu w Java Slides przy użyciu Aspose.Slides for Java API. Ta potężna biblioteka umożliwia programowe manipulowanie prezentacjami PowerPoint, ułatwiając automatyzację zadań, takich jak aktualizowanie danych wykresu ze źródła zewnętrznego. Pod koniec tego samouczka będziesz mieć jasne zrozumienie, jak wykonać to zadanie, dzięki instrukcjom krok po kroku i towarzyszącemu kodowi Java.

## Wymagania wstępne

Zanim przejdziemy do wdrożenia, upewnij się, że spełnione są następujące wymagania wstępne:

1. Aspose.Slides dla Java: Powinieneś mieć zainstalowaną bibliotekę Aspose.Slides dla Java. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).

2. Środowisko programistyczne Java: Upewnij się, że w swoim systemie masz skonfigurowane środowisko programistyczne Java.

## Krok 1: Utwórz nową prezentację

Na początek utwórzmy nową prezentację PowerPoint przy użyciu Aspose.Slides dla Java. Oto kod Java, który to umożliwia:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres

Teraz dodajmy wykres do naszej prezentacji. W tym przykładzie utworzymy wykres kołowy:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Krok 3: Ustaw zewnętrzny skoroszyt

Tutaj ustawiamy zewnętrzny skoroszyt jako źródło danych dla naszego wykresu. Musisz podać adres URL do zewnętrznego skoroszytu, nawet jeśli na razie nie istnieje:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://ścieżka/nie/istnieje", false);
```

## Krok 4: Zapisz prezentację

Na koniec zapisz prezentację z zaktualizowanymi danymi wykresu:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla zestawu zewnętrznego skoroszytu z danymi wykresu aktualizacji w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://ścieżka/nie/istnieje", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

Gratulacje! Nauczyłeś się, jak ustawić zewnętrzny skoroszyt z zaktualizowanymi danymi wykresu w Java Slides przy użyciu Aspose.Slides for Java. Może to być niezwykle przydatne do dynamicznego aktualizowania wykresów w prezentacjach PowerPoint z zewnętrznych źródeł danych.

## Najczęściej zadawane pytania

### Jak mogę zaktualizować dane zewnętrznego skoroszytu dla wykresu?

Aby zaktualizować dane zewnętrznego skoroszytu dla wykresu, wystarczy zmodyfikować dane w zewnętrznym skoroszycie pod określonym adresem URL. Następnym razem, gdy otworzysz prezentację, Aspose.Slides for Java pobierze zaktualizowane dane z zewnętrznego skoroszytu i odpowiednio zaktualizuje wykres.

### Czy mogę użyć pliku lokalnego jako skoroszytu zewnętrznego?

Tak, możesz użyć pliku lokalnego jako zewnętrznego skoroszytu, podając ścieżkę pliku zamiast adresu URL. Upewnij się tylko, że ścieżka pliku jest poprawna i dostępna z aplikacji Java.

### Czy istnieją jakieś ograniczenia w korzystaniu z zewnętrznych skoroszytów w Aspose.Slides dla Java?

Chociaż korzystanie z zewnętrznych skoroszytów jest potężną funkcją, pamiętaj, że dostępność danych zewnętrznego skoroszytu zależy od jego dostępności pod podanym adresem URL lub ścieżką pliku. Upewnij się, że zewnętrzne źródło danych jest dostępne po otwarciu prezentacji, aby uniknąć problemów z pobieraniem danych.

### Czy mogę dostosować wygląd wykresu po ustawieniu skoroszytu zewnętrznego?

Tak, możesz dostosować wygląd wykresu, w tym jego tytuł, etykiety, kolory i inne, nawet po ustawieniu zewnętrznego skoroszytu. Aspose.Slides for Java oferuje rozbudowane opcje formatowania wykresów, aby spełnić Twoje potrzeby.

### Gdzie mogę znaleźć więcej dokumentacji i zasobów dla Aspose.Slides dla Java?

Aby uzyskać szczegółową dokumentację i dodatkowe zasoby, odwiedź dokumentację Aspose.Slides for Java pod adresem [Tutaj](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}