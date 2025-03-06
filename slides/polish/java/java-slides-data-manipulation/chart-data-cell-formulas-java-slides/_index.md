---
title: Wykresy formuł komórek danych w slajdach Java
linktitle: Wykresy formuł komórek danych w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić formuły komórek danych wykresu w prezentacjach Java PowerPoint przy użyciu Aspose.Slides dla Java. Twórz dynamiczne wykresy za pomocą formuł.
weight: 11
url: /pl/java/data-manipulation/chart-data-cell-formulas-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Wprowadzenie do formuł komórek danych wykresów w Aspose.Slides dla Java

W tym samouczku omówimy, jak pracować z formułami komórek danych wykresu za pomocą Aspose.Slides dla Java. Dzięki Aspose.Slides możesz tworzyć wykresy i manipulować nimi w prezentacjach programu PowerPoint, w tym ustawiać formuły dla komórek danych.

## Warunki wstępne

 Zanim zaczniesz, upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides for Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Utwórz prezentację programu PowerPoint

Najpierw utwórzmy nową prezentację PowerPoint i dodajmy do niej wykres.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Dodaj wykres do pierwszego slajdu
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Pobierz skoroszyt zawierający dane wykresu
    IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    
    // Kontynuuj operacje na komórkach danych
    // ...
    
    // Zapisz prezentację
    presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
    if (presentation != null) presentation.dispose();
}
```

## Krok 2: Ustaw formuły dla komórek danych

Teraz ustawmy formuły dla konkretnych komórek danych na wykresie. W tym przykładzie ustawimy formuły dla dwóch różnych komórek.

### Komórka 1: Używanie notacji A1

```java
IChartDataCell cell1 = workbook.getCell(0, "B2");
cell1.setFormula("1 + SUM(F2:H5)");
```

W powyższym kodzie ustawiamy formułę dla komórki B2 przy użyciu notacji A1. Formuła oblicza sumę komórek od F2 do H5 i dodaje 1 do wyniku.

### Komórka 2: Korzystanie z notacji R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Tutaj ustawiamy formułę dla komórki C2 przy użyciu notacji R1C1. Formuła oblicza maksymalną wartość z zakresu R2C6 do R5C8, a następnie dzieli ją przez 3.

## Krok 3: Oblicz formuły

Po ustaleniu formuł należy je koniecznie obliczyć za pomocą poniższego kodu:

```java
workbook.calculateFormulas();
```

Ten krok zapewnia, że wykres odzwierciedla zaktualizowane wartości na podstawie formuł.

## Krok 4: Zapisz prezentację

Na koniec zapisz zmodyfikowaną prezentację do pliku.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Kompletny kod źródłowy formuł komórek danych wykresów w slajdach Java

```java
String outpptxFile = "Your Output Directory" + File.pathSeparator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
	IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
	IChartDataCell cell1 = workbook.getCell(0, "B2");
	cell1.setFormula("1 + SUM(F2:H5)");
	IChartDataCell cell2 = workbook.getCell(0, "C2");
	cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
	workbook.calculateFormulas();
	presentation.save(outpptxFile, SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Wniosek

W tym samouczku omówiliśmy, jak pracować z formułami komórek danych wykresu w Aspose.Slides dla Java. Omówiliśmy tworzenie prezentacji programu PowerPoint, dodawanie wykresu, ustawianie formuł dla komórek danych, obliczanie formuł i zapisywanie prezentacji. Możesz teraz wykorzystać te możliwości do tworzenia dynamicznych wykresów opartych na danych w swoich prezentacjach.

## Często zadawane pytania

### Jak dodać wykres do konkretnego slajdu?

 Aby dodać wykres do konkretnego slajdu, możesz użyć opcji`getSlides().get_Item(slideIndex)` aby uzyskać dostęp do żądanego slajdu, a następnie użyj przycisku`addChart` metoda dodania wykresu.

### Czy mogę używać różnych typów formuł w komórkach danych?

Tak, w formułach komórek danych można używać różnych typów formuł, w tym operacji matematycznych, funkcji i odwołań do innych komórek.

### Jak zmienić typ wykresu?

 Typ wykresu można zmienić za pomocą opcji`setChartType` metoda na`IChart` obiekt i określenie pożądanego`ChartType`.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
