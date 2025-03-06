---
title: Wykres linii trendu w slajdach Java
linktitle: Wykres linii trendu w slajdach Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać różne linie trendu do slajdów Java za pomocą Aspose.Slides dla Java. Przewodnik krok po kroku z przykładami kodu umożliwiającymi efektywną wizualizację danych.
type: docs
weight: 15
url: /pl/java/data-manipulation/chart-trend-lines-java-slides/
---

## Wprowadzenie do linii trendu wykresów w slajdach Java: przewodnik krok po kroku

W tym obszernym przewodniku przyjrzymy się, jak tworzyć linie trendu na wykresie w Java Slides za pomocą Aspose.Slides dla Java. Wykresy linii trendu mogą być cennym dodatkiem do prezentacji, pomagając skutecznie wizualizować i analizować trendy danych. Przeprowadzimy Cię przez cały proces, korzystając z jasnych wyjaśnień i przykładów kodu.

## Warunki wstępne

Zanim zajmiemy się tworzeniem linii trendu na wykresie, upewnij się, że spełnione są następujące wymagania wstępne:

- Środowisko programistyczne Java
- Aspose.Slides dla biblioteki Java
- Edytor kodu według własnego wyboru

## Krok 1: Pierwsze kroki

Zacznijmy od skonfigurowania niezbędnego środowiska i stworzenia nowej prezentacji:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Tworzenie pustej prezentacji
Presentation pres = new Presentation();
```

Zainicjowaliśmy naszą prezentację i teraz możemy dodać grupowany wykres kolumnowy:

```java
// Tworzenie grupowanego wykresu kolumnowego
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Krok 2: Dodawanie linii trendu wykładniczego

Zacznijmy od dodania linii trendu wykładniczego do naszej serii wykresów:

```java
// Dodawanie linii trendu wykładniczego dla serii wykresów 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Krok 3: Dodawanie linii trendu liniowego

Następnie dodamy liniową linię trendu do naszej serii wykresów:

```java
// Dodawanie linii trendu liniowego dla serii wykresów 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Krok 4: Dodawanie logarytmicznej linii trendu

Dodajmy teraz logarytmiczną linię trendu do innej serii wykresów:

```java
// Dodanie logarytmicznej linii trendu dla serii wykresów 2
ITrendline trendLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
trendLineLog.setTrendlineType(TrendlineType.Logarithmic);
trendLineLog.addTextFrameForOverriding("New log trend line");
```

## Krok 5: Dodawanie linii trendu średniej ruchomej

Możemy również dodać linię trendu średniej ruchomej:

```java
// Dodanie linii trendu średniej ruchomej dla serii wykresów 2
ITrendline trendLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
trendLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
trendLineMovAvg.setPeriod((byte) 3);
trendLineMovAvg.setTrendlineName("New TrendLine Name");
```

## Krok 6: Dodawanie linii trendu wielomianowego

Dodawanie linii trendu wielomianowego:

```java
// Dodawanie linii trendu wielomianowego dla serii wykresów 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Krok 7: Dodawanie linii trendu mocy

Na koniec dodajmy linię trendu mocy:

```java
// Dodanie linii trendu mocy dla serii wykresów 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Krok 8: Zapisywanie prezentacji

Teraz, gdy dodaliśmy do naszego wykresu różne linie trendu, zapiszmy prezentację:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Gratulacje! Pomyślnie utworzyłeś prezentację z różnymi typami linii trendu w Java Slides przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy linii trendu wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Tworzenie pustej prezentacji
Presentation pres = new Presentation();
// Tworzenie grupowanego wykresu kolumnowego
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Dodanie potencjalnej linii trendu dla serii wykresów 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Dodanie linii trendu liniowego dla serii wykresów 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Dodanie linii trendu logarytmicznego dla serii wykresów 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Dodanie linii trendu MovingAverage dla serii wykresów 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Dodanie linii trendu wielomianowego dla serii wykresów 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Dodanie linii trendu mocy dla serii wykresów 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Zapisywanie prezentacji
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Wniosek

W tym samouczku nauczyliśmy się, jak dodawać różne typy linii trendu do wykresów w aplikacji Java Slides przy użyciu biblioteki Aspose.Slides for Java. Niezależnie od tego, czy pracujesz nad analizą danych, czy tworzysz prezentacje informacyjne, umiejętność wizualizacji trendów może być potężnym narzędziem.

## Często zadawane pytania

### Jak zmienić kolor linii trendu w Aspose.Slides dla Java?

 Aby zmienić kolor linii trendu, możesz użyć opcji`getSolidFillColor().setColor(Color)` metodę, jak pokazano w przykładzie dodawania linii trendu liniowego.

### Czy mogę dodać wiele linii trendu do jednej serii wykresów?

Tak, możesz dodać wiele linii trendu do jednej serii wykresów. Po prostu zadzwoń`getTrendLines().add()` dla każdej linii trendu, którą chcesz dodać.

### Jak usunąć linię trendu z wykresu w Aspose.Slides dla Java?

 Aby usunąć linię trendu z wykresu, możesz użyć opcji`removeAt(int index)` metodę, określając indeks linii trendu, którą chcesz usunąć.

### Czy można dostosować wyświetlanie równań linii trendu?

 Tak, możesz dostosować wyświetlanie równania linii trendu za pomocą`setDisplayEquation(boolean)` sposób, jak pokazano na przykładzie.

### Jak mogę uzyskać dostęp do większej liczby zasobów i przykładów Aspose.Slides dla Java?

 Możesz uzyskać dostęp do dodatkowych zasobów, dokumentacji i przykładów Aspose.Slides dla Java na stronie[Strona Aspose](https://reference.aspose.com/slides/java/).