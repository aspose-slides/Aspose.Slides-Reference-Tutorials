---
title: Ustaw zewnętrzny skoroszyt z danymi wykresu aktualizacji w slajdach Java
linktitle: Ustaw zewnętrzny skoroszyt z danymi wykresu aktualizacji w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić zewnętrzne skoroszyty i zaktualizować dane wykresów w Java Slides przy użyciu Aspose.Slides dla Java. Popraw swoje umiejętności automatyzacji programu PowerPoint.
weight: 20
url: /pl/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wprowadzenie do ustawiania skoroszytu zewnętrznego z danymi wykresu aktualizacji w slajdach Java

tym obszernym przewodniku przeprowadzimy Cię przez proces konfigurowania zewnętrznego skoroszytu ze zaktualizowanymi danymi wykresów w Java Slides przy użyciu Aspose.Slides for Java API. Ta potężna biblioteka umożliwia programowe manipulowanie prezentacjami programu PowerPoint, co ułatwia automatyzację zadań, takich jak aktualizowanie danych wykresów ze źródła zewnętrznego. Pod koniec tego samouczka będziesz jasno wiedział, jak wykonać to zadanie, korzystając z instrukcji krok po kroku i dołączonego kodu Java.

## Warunki wstępne

Zanim przejdziemy do wdrożenia, upewnij się, że spełnione są następujące wymagania wstępne:

1.  Aspose.Slides for Java: Powinieneś mieć zainstalowaną bibliotekę Aspose.Slides for Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

2. Środowisko programistyczne Java: Upewnij się, że w systemie skonfigurowano środowisko programistyczne Java.

## Krok 1: Utwórz nową prezentację

Na początek utwórzmy nową prezentację programu PowerPoint przy użyciu Aspose.Slides dla Java. Oto kod Java, który to umożliwia:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres

Dodajmy teraz wykres do naszej prezentacji. W tym przykładzie utworzymy wykres kołowy:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Krok 3: Ustaw zewnętrzny skoroszyt

tym miejscu ustawiamy zewnętrzny skoroszyt jako źródło danych dla naszego wykresu. Musisz podać adres URL zewnętrznego skoroszytu, nawet jeśli na razie nie istnieje:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://ścieżka/nie/istnieje”, false);
```

## Krok 4: Zapisz prezentację

Na koniec zapisz prezentację ze zaktualizowanymi danymi wykresu:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Kompletny kod źródłowy zestawu zewnętrznego skoroszytu z danymi wykresu aktualizacji w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://ścieżka/nie/istnieje”, false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Wniosek

Gratulacje! Nauczyłeś się, jak ustawić zewnętrzny skoroszyt ze zaktualizowanymi danymi wykresów w Java Slides przy użyciu Aspose.Slides dla Java. Może to być niezwykle przydatne do dynamicznego aktualizowania wykresów w prezentacjach programu PowerPoint z zewnętrznych źródeł danych.

## Często zadawane pytania

### Jak mogę zaktualizować dane zewnętrznego skoroszytu dla wykresu?

Aby zaktualizować dane zewnętrznego skoroszytu dla wykresu, wystarczy zmodyfikować dane w zewnętrznym skoroszycie pod określonym adresem URL. Gdy następnym razem otworzysz prezentację, Aspose.Slides for Java pobierze zaktualizowane dane z zewnętrznego skoroszytu i odpowiednio zaktualizuje wykres.

### Czy mogę użyć pliku lokalnego jako zewnętrznego skoroszytu?

Tak, możesz użyć pliku lokalnego jako zewnętrznego skoroszytu, podając ścieżkę pliku zamiast adresu URL. Upewnij się tylko, że ścieżka pliku jest poprawna i dostępna z poziomu aplikacji Java.

### Czy są jakieś ograniczenia w korzystaniu z zewnętrznych skoroszytów z Aspose.Slides dla Java?

Chociaż korzystanie z zewnętrznych skoroszytów jest potężną funkcją, należy pamiętać, że dostępność danych zewnętrznego skoroszytu zależy od ich dostępności pod podanym adresem URL lub ścieżką pliku. Upewnij się, że zewnętrzne źródło danych jest dostępne po otwarciu prezentacji, aby uniknąć problemów z pobieraniem danych.

### Czy mogę dostosować wygląd wykresu po ustawieniu zewnętrznego skoroszytu?

Tak, możesz dostosować wygląd wykresu, w tym jego tytuł, etykiety, kolory i inne elementy, nawet po ustawieniu zewnętrznego skoroszytu. Aspose.Slides dla Java zapewnia rozbudowane opcje formatowania wykresów, aby spełnić Twoje potrzeby.

### Gdzie mogę znaleźć więcej dokumentacji i zasobów dotyczących Aspose.Slides for Java?

 Aby uzyskać szczegółową dokumentację i dodatkowe zasoby, odwiedź dokumentację Aspose.Slides for Java pod adresem[Tutaj](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
