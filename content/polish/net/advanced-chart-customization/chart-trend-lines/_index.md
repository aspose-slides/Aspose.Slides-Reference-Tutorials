---
title: Odkrywanie linii trendu wykresu w Aspose.Slides dla .NET
linktitle: Wykres linii trendu
second_title: Aspose.Slides .NET PowerPoint Processing API
description: W tym przewodniku krok po kroku dowiesz się, jak dodawać różne linie trendu do wykresów za pomocą Aspose.Slides dla .NET. Z łatwością zwiększ swoje umiejętności wizualizacji danych!
type: docs
weight: 12
url: /pl/net/advanced-chart-customization/chart-trend-lines/
---

świecie wizualizacji i prezentacji danych wykresy mogą być skutecznym sposobem skutecznego przekazywania informacji. Aspose.Slides dla .NET zapewnia bogaty w funkcje zestaw narzędzi do pracy z wykresami, w tym możliwość dodawania linii trendu do wykresów. W tym samouczku zajmiemy się procesem dodawania linii trendu do wykresu krok po kroku za pomocą Aspose.Slides dla .NET. 

## Warunki wstępne

Zanim zaczniemy pracować z Aspose.Slides dla .NET, musisz upewnić się, że masz następujące wymagania wstępne:

1.  Aspose.Slides dla .NET: Aby uzyskać dostęp do biblioteki i z niej korzystać, musisz mieć zainstalowany Aspose.Slides dla .NET. Bibliotekę można pobrać ze strony[strona pobierania](https://releases.aspose.com/slides/net/).

2. Środowisko programistyczne: Należy mieć skonfigurowane środowisko programistyczne, najlepiej przy użyciu zintegrowanego środowiska programistycznego .NET, takiego jak Visual Studio.

3. Podstawowa znajomość języka C#: Podstawowa znajomość programowania w języku C# jest korzystna, ponieważ będziemy używać języka C# do pracy z Aspose.Slides dla .NET.

Teraz, gdy omówiliśmy wymagania wstępne, przeanalizujmy krok po kroku proces dodawania linii trendu do wykresu.

## Importowanie przestrzeni nazw

Najpierw upewnij się, że zaimportowałeś niezbędne przestrzenie nazw do projektu C#. Te przestrzenie nazw są niezbędne do pracy z Aspose.Slides dla .NET.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

## Krok 1: Utwórz prezentację

Na tym etapie tworzymy pustą prezentację, z którą będziemy pracować.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";

// Utwórz katalog, jeśli jeszcze nie istnieje.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Tworzenie pustej prezentacji
Presentation pres = new Presentation();
```

## Krok 2: Dodaj wykres do slajdu

Następnie do slajdu dodajemy grupowany wykres kolumnowy.

```csharp
// Tworzenie grupowanego wykresu kolumnowego
IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.ClusteredColumn, 20, 20, 500, 400);
```

## Krok 3: Dodaj linie trendu do wykresu

Teraz do serii wykresów dodajemy różne rodzaje linii trendu.

### Dodawanie wykładniczej linii trendu

```csharp
// Dodawanie linii trendu wykładniczego dla serii wykresów 1
ITrendline tredLineExp = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Exponential);
tredLineExp.DisplayEquation = false;
tredLineExp.DisplayRSquaredValue = false;
```

### Dodawanie linii trendu liniowego

```csharp
// Dodawanie linii trendu liniowego dla serii wykresów 1
ITrendline tredLineLin = chart.ChartData.Series[0].TrendLines.Add(TrendlineType.Linear);
tredLineLin.Format.Line.FillFormat.FillType = FillType.Solid;
tredLineLin.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
```

### Dodawanie logarytmicznej linii trendu

```csharp
// Dodanie logarytmicznej linii trendu dla serii wykresów 2
ITrendline tredLineLog = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.Logarithmic);
tredLineLog.AddTextFrameForOverriding("New log trend line");
```

### Dodanie linii trendu średniej ruchomej

```csharp
// Dodanie linii trendu średniej ruchomej dla serii wykresów 2
ITrendline tredLineMovAvg = chart.ChartData.Series[1].TrendLines.Add(TrendlineType.MovingAverage);
tredLineMovAvg.Period = 3;
tredLineMovAvg.TrendlineName = "New TrendLine Name";
```

### Dodawanie linii trendu wielomianowego

```csharp
// Dodawanie linii trendu wielomianowego dla serii wykresów 3
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

Otóż to! Pomyślnie dodałeś różne linie trendu do swojego wykresu za pomocą Aspose.Slides dla .NET.

## Wniosek

Aspose.Slides dla .NET to wszechstronna biblioteka, która pozwala z łatwością tworzyć wykresy i manipulować nimi. Postępując zgodnie z tym przewodnikiem krok po kroku, możesz dodawać do wykresów różne typy linii trendu, poprawiając wizualną reprezentację danych.

### Często zadawane pytania

### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
 Można uzyskać dostęp do dokumentacji[Tutaj](https://reference.aspose.com/slides/net/).

### Jak mogę pobrać Aspose.Slides dla .NET?
 Możesz pobrać Aspose.Slides dla .NET ze strony pobierania[Tutaj](https://releases.aspose.com/slides/net/).

### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
 Tak, możesz bezpłatnie wypróbować Aspose.Slides dla .NET, odwiedzając stronę[ten link](https://releases.aspose.com/).

### Gdzie mogę kupić Aspose.Slides dla .NET?
 Aby kupić Aspose.Slides dla .NET, odwiedź stronę zakupu[Tutaj](https://purchase.aspose.com/buy).

### Czy potrzebuję tymczasowej licencji na Aspose.Slides dla .NET?
 Możesz uzyskać tymczasową licencję na Aspose.Slides dla .NET od[ten link](https://purchase.aspose.com/temporary-license/).