---
"description": "Dowiedz się, jak obliczać formuły w Java Slides przy użyciu Aspose.Slides for Java. Przewodnik krok po kroku z kodem źródłowym dla dynamicznych prezentacji PowerPoint."
"linktitle": "Oblicz formuły w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Oblicz formuły w slajdach Java"
"url": "/pl/java/data-manipulation/calculate-formulas-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Oblicz formuły w slajdach Java


## Wprowadzenie do obliczania formuł w Java Slajdy z użyciem Aspose.Slides

tym przewodniku pokażemy, jak obliczać formuły w Java Slides przy użyciu Aspose.Slides for Java API. Aspose.Slides to potężna biblioteka do pracy z prezentacjami PowerPoint, która udostępnia funkcje do manipulowania wykresami i wykonywania obliczeń formuł w slajdach.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz następujące rzeczy:

- Środowisko programistyczne Java
- Biblioteka Aspose.Slides dla Java (można ją pobrać ze strony [Tutaj](https://releases.aspose.com/slides/java/)
- Podstawowa znajomość programowania w Javie

## Krok 1: Utwórz nową prezentację

Najpierw utwórzmy nową prezentację PowerPoint i dodajmy do niej slajd. W tym przykładzie będziemy pracować z jednym slajdem.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Teraz dodajmy do slajdu wykres kolumnowy klastrowany. Użyjemy tego wykresu, aby zademonstrować obliczenia formuł.

```java
IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
```

## Krok 3: Ustaw formuły i wartości

Następnie ustawimy formuły i wartości dla komórek danych wykresu za pomocą interfejsu API Aspose.Slides. Obliczymy formuły dla tych komórek.

```java
IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();

// Ustaw formułę dla komórki A1
IChartDataCell cell = workbook.getCell(0, "A1");
cell.setFormula("ABS(A2) + MAX(B2:C2)");

// Ustaw wartość dla komórki A2
workbook.getCell(0, "A2").setValue(-1);
workbook.calculateFormulas();

// Ustaw formułę dla komórki B2
workbook.getCell(0, "B2").setFormula("2");
workbook.calculateFormulas();

// Ustaw formułę dla komórki C2
workbook.getCell(0, "C2").setFormula("A2 + 4");
workbook.calculateFormulas();

// Ustaw ponownie formułę dla komórki A1
cell.setFormula("MAX(2:2)");
workbook.calculateFormulas();
```

## Krok 4: Zapisz prezentację

Na koniec zapiszemy zmodyfikowaną prezentację z obliczonymi wzorami.

```java
presentation.save(resultPath, SaveFormat.Pptx);
```

## Kompletny kod źródłowy do obliczania formuł w slajdach Java

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
try {
	IChart s_chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 10, 10, 600, 300);
	IChartDataWorkbook workbook = s_chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell = workbook.getCell(0, "A1");
	cell.setFormula("ABS(A2) + MAX(B2:C2)");
	workbook.getCell(0, "A2").setValue(-1);
	workbook.calculateFormulas();
	workbook.getCell(0, "B2").setFormula("2");
	workbook.calculateFormulas();
	workbook.getCell(0, "C2").setFormula("A2 + 4");
	workbook.calculateFormulas();
	cell.setFormula("MAX(2:2)");
	workbook.calculateFormulas();
	presentation.save(resultPath, SaveFormat.Pptx);
} finally {
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym przewodniku nauczyliśmy się, jak obliczać formuły w Java Slides przy użyciu Aspose.Slides for Java. Utworzyliśmy nową prezentację, dodaliśmy do niej wykres, ustawiliśmy formuły i wartości dla komórek danych wykresu i zapisaliśmy prezentację z obliczonymi formułami.

## Najczęściej zadawane pytania

### Jak ustawić formuły dla komórek danych wykresu?

Można ustawić formuły dla komórek danych wykresu za pomocą `setFormula` metoda `IChartDataCell` w Aspose.Slides.

### Jak ustawić wartości dla komórek danych wykresu?

Możesz ustawić wartości dla komórek danych wykresu za pomocą `setValue` metoda `IChartDataCell` w Aspose.Slides.

### Jak obliczać formuły w skoroszycie?

Możesz obliczać formuły w skoroszycie, używając `calculateFormulas` metoda `IChartDataWorkbook` w Aspose.Slides.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}