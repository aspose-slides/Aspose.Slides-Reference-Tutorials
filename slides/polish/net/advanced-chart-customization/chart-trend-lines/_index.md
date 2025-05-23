---
"description": "Dowiedz się, jak dodawać różne linie trendu do wykresów za pomocą Aspose.Slides dla .NET w tym przewodniku krok po kroku. Ulepsz swoje umiejętności wizualizacji danych z łatwością!"
"linktitle": "Wykres linii trendu"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Eksploracja linii trendów wykresów w Aspose.Slides dla .NET"
"url": "/pl/net/advanced-chart-customization/chart-trend-lines/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Eksploracja linii trendów wykresów w Aspose.Slides dla .NET


W świecie wizualizacji i prezentacji danych włączanie wykresów może być potężnym sposobem na skuteczne przekazywanie informacji. Aspose.Slides dla .NET zapewnia bogaty w funkcje zestaw narzędzi do pracy z wykresami, w tym możliwość dodawania linii trendu do wykresów. W tym samouczku zagłębimy się w proces dodawania linii trendu do wykresu krok po kroku przy użyciu Aspose.Slides dla .NET. 

## Wymagania wstępne

Zanim zaczniesz pracę z Aspose.Slides dla platformy .NET, musisz się upewnić, że spełnione są następujące wymagania wstępne:

1. Aspose.Slides dla .NET: Aby uzyskać dostęp do biblioteki i jej używać, musisz mieć zainstalowany Aspose.Slides dla .NET. Bibliotekę możesz pobrać z [strona do pobrania](https://releases.aspose.com/slides/net/).

2. Środowisko programistyczne: Należy przygotować środowisko programistyczne, najlepiej wykorzystując zintegrowane środowisko programistyczne .NET, np. Visual Studio.

3. Podstawowa znajomość języka C#: Podstawowa znajomość programowania w języku C# będzie przydatna, ponieważ będziemy używać tego języka do pracy z Aspose.Slides dla .NET.

Teraz, gdy omówiliśmy już wymagania wstępne, możemy omówić krok po kroku proces dodawania linii trendu do wykresu.

## Importowanie przestrzeni nazw

Najpierw upewnij się, że importujesz niezbędne przestrzenie nazw do swojego projektu C#. Te przestrzenie nazw są niezbędne do pracy z Aspose.Slides dla .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Krok 1: Utwórz prezentację

W tym kroku utworzymy pustą prezentację, z którą będziemy pracować.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";

// Utwórz katalog, jeśli jeszcze go nie ma.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Tworzenie pustej prezentacji
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Następnie dodajemy do slajdu wykres kolumnowy klastrowany.

```csharp
// Tworzenie wykresu kolumnowego klastrowanego
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Krok 3: Dodaj linie trendu do wykresu

Teraz dodamy do serii wykresów różne rodzaje linii trendu.

### Dodawanie linii trendu wykładniczego

```csharp
// Dodanie linii trendu wykładniczego dla serii wykresów 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Dodawanie liniowej linii trendu

```csharp
// Dodawanie liniowej linii trendu dla serii wykresów 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Dodawanie linii trendu logarytmicznego

```csharp
// Dodanie linii trendu logarytmicznego dla serii wykresów 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Dodawanie linii trendu średniej ruchomej

```csharp
// Dodanie linii trendu średniej ruchomej dla serii wykresów 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Dodawanie linii trendu wielomianowego

```csharp
// Dodanie linii trendu wielomianowego dla serii wykresów 3
ITrendline tredLinePol = chart.ChartData.Series[2].TrendLines.Add(TrendlineType.Polynomial);
tredLinePol.Forward = 1;
tredLinePol.Order = 3;
```

### Dodawanie linii trendu mocy

```csharp
// Dodanie linii trendu mocy dla serii wykresów 3
ITrendline tredLinePower = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Power);
tredLinePower.Backward = 1;
```

## Krok 4: Zapisz prezentację

Po dodaniu linii trendu do wykresu zapisz prezentację.

```csharp
// Zapisywanie prezentacji
pres.Save(dataDir + "ChartTrendLines_out.pptx", SaveFormat.Pptx);
```

To wszystko! Udało Ci się dodać różne linie trendu do wykresu za pomocą Aspose.Slides dla .NET.

## Wniosek

Aspose.Slides for .NET to wszechstronna biblioteka, która umożliwia łatwe tworzenie i manipulowanie wykresami. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz dodawać różne typy linii trendu do wykresów, ulepszając wizualną reprezentację danych.

### Często zadawane pytania

### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
Możesz uzyskać dostęp do dokumentacji [Tutaj](https://reference.aspose.com/slides/net/).

### Jak mogę pobrać Aspose.Slides dla platformy .NET?
Możesz pobrać Aspose.Slides dla .NET ze strony pobierania [Tutaj](https://releases.aspose.com/slides/net/).

### Czy jest dostępna bezpłatna wersja próbna Aspose.Slides dla .NET?
Tak, możesz wypróbować Aspose.Slides dla .NET za darmo, odwiedzając stronę [ten link](https://releases.aspose.com/).

### Gdzie mogę kupić Aspose.Slides dla platformy .NET?
Aby zakupić Aspose.Slides dla .NET, odwiedź stronę zakupu [Tutaj](https://purchase.aspose.com/buy).

### Czy potrzebuję tymczasowej licencji na Aspose.Slides dla .NET?
Tymczasową licencję na Aspose.Slides dla .NET można uzyskać na stronie [ten link](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}