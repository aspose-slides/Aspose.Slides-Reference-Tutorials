---
"description": "Dowiedz się, jak ustawić formuły komórek danych wykresu w prezentacjach PowerPoint w języku Java przy użyciu Aspose.Slides dla języka Java. Twórz dynamiczne wykresy za pomocą formuł."
"linktitle": "Formuły komórek danych wykresu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Formuły komórek danych wykresu w slajdach Java"
"url": "/pl/java/data-manipulation/chart-data-cell-formulas-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Formuły komórek danych wykresu w slajdach Java


## Wprowadzenie do formuł komórek danych wykresu w Aspose.Slides dla Java

W tym samouczku pokażemy, jak pracować z formułami komórek danych wykresu przy użyciu Aspose.Slides dla Java. Dzięki Aspose.Slides możesz tworzyć i manipulować wykresami w prezentacjach PowerPoint, w tym ustawiać formuły dla komórek danych.

## Wymagania wstępne

Zanim zaczniesz, upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides for Java. Możesz ją pobrać ze strony [Tutaj](https://releases.aspose.com/slides/java/).

## Krok 1: Utwórz prezentację PowerPoint

Najpierw utwórzmy nową prezentację programu PowerPoint i dodajmy do niej wykres.

```java
String outpptxFile = "Your Output Directory" + File.separator + "ChartDataCell_Formulas_out.pptx";
Presentation presentation = new Presentation();
try
{
    // Dodaj wykres do pierwszego slajdu
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 150, 150, 500, 300);
    
    // Pobierz skoroszyt dla danych wykresu
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

W powyższym kodzie ustawiamy formułę dla komórki B2, używając notacji A1. Formuła oblicza sumę komórek F2 do H5 i dodaje 1 do wyniku.

### Komórka 2: Używanie notacji R1C1

```java
IChartDataCell cell2 = workbook.getCell(0, "C2");
cell2.setR1C1Formula("MAX(R2C6:R5C8) / 3");
```

Tutaj ustawiamy formułę dla komórki C2 przy użyciu notacji R1C1. Formuła oblicza maksymalną wartość w zakresie od R2C6 do R5C8, a następnie dzieli ją przez 3.

## Krok 3: Oblicz wzory

Po ustawieniu wzorów należy je obliczyć, korzystając z następującego kodu:

```java
workbook.calculateFormulas();
```

Ten krok zapewnia, że wykres odzwierciedla zaktualizowane wartości na podstawie wzorów.

## Krok 4: Zapisz prezentację

Na koniec zapisz zmodyfikowaną prezentację do pliku.

```java
presentation.save(outpptxFile, SaveFormat.Pptx);
```

## Kompletny kod źródłowy dla formuł komórek danych wykresu w slajdach Java

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

W tym samouczku przyjrzeliśmy się sposobowi pracy z formułami komórek danych wykresu w Aspose.Slides dla Java. Omówiliśmy tworzenie prezentacji PowerPoint, dodawanie wykresu, ustawianie formuł dla komórek danych, obliczanie formuł i zapisywanie prezentacji. Teraz możesz wykorzystać te możliwości, aby tworzyć dynamiczne i zorientowane na dane wykresy w swoich prezentacjach.

## Często zadawane pytania

### Jak dodać wykres do konkretnego slajdu?

Aby dodać wykres do określonego slajdu, możesz użyć `getSlides().get_Item(slideIndex)` metodę dostępu do żądanego slajdu, a następnie użyj `addChart` metoda dodania wykresu.

### Czy mogę używać różnych typów formuł w komórkach danych?

Tak, w formułach komórek danych można używać różnych typów formuł, w tym operacji matematycznych, funkcji i odwołań do innych komórek.

### Jak zmienić typ wykresu?

Możesz zmienić typ wykresu, używając `setChartType` metoda na `IChart` obiekt i określenie pożądanego `ChartType`.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}