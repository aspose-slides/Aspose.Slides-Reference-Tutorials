---
"description": "Dowiedz się, jak dodawać różne linie trendu do slajdów Java Slides przy użyciu Aspose.Slides for Java. Przewodnik krok po kroku z przykładami kodu do efektywnej wizualizacji danych."
"linktitle": "Wykresy linii trendu w slajdach Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Wykresy linii trendu w slajdach Java"
"url": "/pl/java/data-manipulation/chart-trend-lines-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Wykresy linii trendu w slajdach Java


## Wprowadzenie do wykresów linii trendu w Java Slides: Przewodnik krok po kroku

tym kompleksowym przewodniku przyjrzymy się, jak tworzyć linie trendów wykresów w Java Slides przy użyciu Aspose.Slides for Java. Linie trendów wykresów mogą być cennym dodatkiem do prezentacji, pomagając skutecznie wizualizować i analizować trendy danych. Przeprowadzimy Cię przez proces za pomocą jasnych wyjaśnień i przykładów kodu.

## Wymagania wstępne

Zanim przejdziemy do tworzenia linii trendu na wykresie, upewnij się, że spełnione są następujące warunki wstępne:

- Środowisko programistyczne Java
- Aspose.Slides dla biblioteki Java
- Edytor kodu według Twojego wyboru

## Krok 1: Rozpoczęcie pracy

Zacznijmy od skonfigurowania niezbędnego środowiska i utworzenia nowej prezentacji:

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze go nie ma.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
// Tworzenie pustej prezentacji
Presentation pres = new Presentation();
```

Zainicjowaliśmy naszą prezentację i teraz możemy dodać wykres kolumnowy klastrowany:

```java
// Tworzenie wykresu kolumnowego klastrowanego
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Krok 2: Dodawanie linii trendu wykładniczego

Zacznijmy od dodania do naszej serii wykresów linii trendu wykładniczego:

```java
// Dodanie linii trendu wykładniczego dla serii wykresów 1
ITrendline trendLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
trendLineExp.setDisplayEquation(false);
trendLineExp.setDisplayRSquaredValue(false);
```

## Krok 3: Dodawanie liniowej linii trendu

Następnie dodamy do naszej serii wykresów liniową linię trendu:

```java
// Dodawanie liniowej linii trendu dla serii wykresów 1
ITrendline trendLineLinear = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
trendLineLinear.setTrendlineType(TrendlineType.Linear);
trendLineLinear.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
trendLineLinear.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
```

## Krok 4: Dodawanie linii trendu logarytmicznego

Teraz dodajmy linię trendu logarytmicznego do innej serii wykresów:

```java
// Dodanie linii trendu logarytmicznego dla serii wykresów 2
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
// Dodanie linii trendu wielomianowego dla serii wykresów 3
ITrendline trendLinePolynomial = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
trendLinePolynomial.setTrendlineType(TrendlineType.Polynomial);
trendLinePolynomial.setForward(1);
trendLinePolynomial.setOrder((byte) 3);
```

## Krok 7: Dodawanie linii trendu mocy

Na koniec dodajmy linię trendu:

```java
// Dodanie linii trendu mocy dla serii wykresów 3
ITrendline trendLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
trendLinePower.setTrendlineType(TrendlineType.Power);
trendLinePower.setBackward(1);
```

## Krok 8: Zapisywanie prezentacji

Teraz, gdy dodaliśmy do naszego wykresu różne linie trendu, możemy zapisać prezentację:

```java
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

Gratulacje! Udało Ci się utworzyć prezentację z różnymi typami linii trendu w Java Slides przy użyciu Aspose.Slides for Java.

## Kompletny kod źródłowy dla linii trendu wykresu w slajdach Java

```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze go nie ma.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Tworzenie pustej prezentacji
Presentation pres = new Presentation();
// Tworzenie wykresu kolumnowego klastrowanego
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
// Dodanie potencjalnej linii trendu dla serii wykresów 1
ITrendline tredLinep = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
tredLinep.setDisplayEquation(false);
tredLinep.setDisplayRSquaredValue(false);
// Dodawanie liniowej linii trendu dla serii wykresów 1
ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
tredLineLin.setTrendlineType(TrendlineType.Linear);
tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
// Dodanie linii trendu logarytmicznego dla serii wykresów 2
ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
tredLineLog.setTrendlineType(TrendlineType.Logarithmic);
tredLineLog.addTextFrameForOverriding("New log trend line");
// Dodawanie linii trendu MovingAverage dla serii wykresów 2
ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
tredLineMovAvg.setTrendlineType(TrendlineType.MovingAverage);
tredLineMovAvg.setPeriod((byte) 3);
tredLineMovAvg.setTrendlineName("New TrendLine Name");
// Dodawanie linii trendu wielomianowego dla serii wykresów 3
ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
tredLinePol.setTrendlineType(TrendlineType.Polynomial);
tredLinePol.setForward(1);
tredLinePol.setOrder((byte) 3);
// Dodawanie linii trendu mocy dla serii wykresów 3
ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
tredLinePower.setTrendlineType(TrendlineType.Power);
tredLinePower.setBackward(1);
// Zapisywanie prezentacji
pres.save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

## Wniosek

tym samouczku nauczyliśmy się, jak dodawać różne typy linii trendu do wykresów w Java Slides, korzystając z biblioteki Aspose.Slides for Java. Niezależnie od tego, czy pracujesz nad analizą danych, czy tworzysz prezentacje informacyjne, możliwość wizualizacji trendów może być potężnym narzędziem.

## Najczęściej zadawane pytania

### Jak zmienić kolor linii trendu w Aspose.Slides dla Java?

Aby zmienić kolor linii trendu, możesz użyć `getSolidFillColor().setColor(Color)` metodę, jak pokazano w przykładzie dodawania liniowej linii trendu.

### Czy mogę dodać wiele linii trendu do jednej serii wykresów?

Tak, możesz dodać wiele linii trendu do jednej serii wykresów. Po prostu wywołaj `getTrendLines().add()` wybierz metodę dla każdej linii trendu, którą chcesz dodać.

### Jak usunąć linię trendu z wykresu w Aspose.Slides dla Java?

Aby usunąć linię trendu z wykresu, możesz użyć `removeAt(int index)` metodę, określając indeks linii trendu, którą chcesz usunąć.

### Czy można dostosować sposób wyświetlania równania linii trendu?

Tak, możesz dostosować wyświetlanie równania linii trendu za pomocą `setDisplayEquation(boolean)` metodę, jak pokazano w przykładzie.

### Jak mogę uzyskać dostęp do większej ilości materiałów i przykładów dla Aspose.Slides dla Java?

Dodatkowe zasoby, dokumentację i przykłady dotyczące Aspose.Slides dla języka Java można uzyskać na stronie [Strona internetowa Aspose](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}