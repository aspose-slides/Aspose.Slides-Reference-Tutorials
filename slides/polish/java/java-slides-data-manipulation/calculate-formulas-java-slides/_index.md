---
title: Oblicz formuły w slajdach Java
linktitle: Oblicz formuły w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak obliczać formuły w Java Slides przy użyciu Aspose.Slides dla Java. Przewodnik krok po kroku z kodem źródłowym dynamicznych prezentacji PowerPoint.
weight: 10
url: /pl/java/data-manipulation/calculate-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Oblicz formuły w slajdach Java


## Wprowadzenie do obliczania formuł w slajdach Java przy użyciu Aspose.Slides

W tym przewodniku pokażemy, jak obliczać formuły w Java Slides przy użyciu Aspose.Slides for Java API. Aspose.Slides to potężna biblioteka do pracy z prezentacjami programu PowerPoint, która udostępnia funkcje umożliwiające manipulowanie wykresami i wykonywanie obliczeń formuł na slajdach.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że masz następujące elementy:

- Środowisko programistyczne Java
-  Biblioteka Aspose.Slides for Java (można ją pobrać z[Tutaj](https://releases.aspose.com/slides/java/)
- Podstawowa znajomość programowania w języku Java

## Krok 1: Utwórz nową prezentację

Najpierw utwórzmy nową prezentację PowerPoint i dodajmy do niej slajd. W tym przykładzie będziemy pracować z jednym slajdem.

```java
String resultPath = "Your Output Directory" + "CalculateFormulas_out.pptx";
Presentation presentation = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Dodajmy teraz do slajdu grupowany wykres kolumnowy. Wykorzystamy ten wykres do zademonstrowania obliczeń formuły.

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

// Ustaw wartość komórki A2
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

Na koniec zapiszmy zmodyfikowaną prezentację z obliczonymi formułami.

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

W tym przewodniku nauczyliśmy się, jak obliczać formuły w Java Slides przy użyciu Aspose.Slides dla Java. Stworzyliśmy nową prezentację, dodaliśmy do niej wykres, ustawiliśmy formuły i wartości dla komórek danych wykresu oraz zapisaliśmy prezentację z obliczonymi formułami.

## Często zadawane pytania

### Jak ustawić formuły dla komórek danych wykresu?

 Możesz ustawić formuły dla komórek danych wykresu za pomocą`setFormula` metoda`IChartDataCell` w Aspose.Slides.

### Jak ustawić wartości komórek danych wykresu?

 Wartości komórek danych wykresu można ustawić za pomocą opcji`setValue` metoda`IChartDataCell` w Aspose.Slides.

### Jak obliczać formuły w skoroszycie?

 Formuły w skoroszycie można obliczać za pomocą narzędzia`calculateFormulas` metoda`IChartDataWorkbook` w Aspose.Slides.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
