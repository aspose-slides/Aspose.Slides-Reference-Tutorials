---
"date": "2025-04-15"
"description": "Dowiedz się, jak ulepszyć swoje prezentacje za pomocą wykresów punktowych przy użyciu Aspose.Slides dla .NET. Postępuj zgodnie z tym kompleksowym przewodnikiem, aby skutecznie tworzyć i dostosowywać wykresy."
"title": "Dodawanie wykresów punktowych do prezentacji za pomocą Aspose.Slides .NET&#58; Przewodnik krok po kroku"
"url": "/pl/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Dodawanie wykresów punktowych do prezentacji przy użyciu Aspose.Slides .NET: przewodnik krok po kroku

## Wstęp
Czy chcesz ulepszyć swoje prezentacje, bez wysiłku integrując wykresy punktowe? Dzięki mocy Aspose.Slides dla .NET tworzenie i dostosowywanie wykresów staje się dziecinnie proste. Ten samouczek przeprowadzi Cię przez proces dodawania wykresów punktowych do slajdów za pomocą Aspose.Slides dla .NET. Opanowując te techniki, będziesz prezentować dane bardziej efektywnie i tworzyć atrakcyjne wizualnie prezentacje.

**Czego się nauczysz:**
- Konfigurowanie Aspose.Slides dla .NET w projekcie
- Tworzenie nowej prezentacji i dostęp do jej pierwszego slajdu
- Dodawanie wykresów punktowych z gładkimi liniami do slajdów
- Czyszczenie istniejących serii i dodawanie nowych do wykresów
- Modyfikowanie punktów danych i stylów znaczników w celu udoskonalenia wizualizacji
- Zapisywanie prezentacji w określonym katalogu

Zacznijmy od przeglądu wymagań wstępnych.

## Wymagania wstępne
Przed wdrożeniem Aspose.Slides dla platformy .NET upewnij się, że masz następujące elementy:
- **Biblioteka Aspose.Slides dla .NET**: Wersja 23.7 lub nowsza.
- **Środowisko programistyczne**:Visual Studio 2019 lub nowszy z .NET Framework 4.6.1+ lub .NET Core/5+.
- **Podstawowa wiedza o C#**:Znajomość programowania obiektowego w języku C#.

## Konfigurowanie Aspose.Slides dla .NET
Aby zacząć używać Aspose.Slides, musisz zainstalować bibliotekę w swoim projekcie. Oto jak to zrobić:

**Korzystanie z interfejsu wiersza poleceń .NET:**
```bash
dotnet add package Aspose.Slides
```

**Korzystanie z konsoli Menedżera pakietów:**
```powershell
Install-Package Aspose.Slides
```

**Interfejs użytkownika Menedżera pakietów NuGet:**
- Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

### Nabycie licencji
Możesz zacząć od bezpłatnego okresu próbnego lub ubiegać się o tymczasową licencję, aby poznać wszystkie funkcje. Aby dokonać zakupu, wykonaj następujące kroki:
1. Odwiedzać [Kup Aspose.Slides](https://purchase.aspose.com/buy) aby kupić pełną licencję.
2. Aby uzyskać tymczasową licencję, odwiedź stronę [Strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).

Po uzyskaniu pliku licencji dodaj go do projektu za pomocą:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Przewodnik wdrażania
Podzielimy implementację na logiczne sekcje w oparciu o funkcje.

### Utwórz prezentację i dodaj slajd
W tej sekcji dowiesz się, jak utworzyć prezentację i uzyskać dostęp do jej pierwszego slajdu.

#### Przegląd
Zacznij od utworzenia instancji `Presentation` klasa, która reprezentuje plik PowerPoint. Dostęp do slajdów jest prosty przy użyciu tego modelu obiektowego.

#### Etapy wdrażania
**Krok 1: Zainicjuj prezentację**
```csharp
using Aspose.Slides;

// Utwórz nową prezentację
t Presentation pres = new Presentation();
```
Ten kod inicjuje nowy dokument prezentacji.

**Krok 2: Dostęp do pierwszego slajdu**
```csharp
// Uzyskaj dostęp do pierwszego slajdu prezentacji
ISlide slide = pres.Slides[0];
```
Tutaj, `pres.Slides[0]` uzyskuje dostęp do pierwszego slajdu. 

### Dodaj wykres punktowy do slajdu
Teraz dodajmy wykres punktowy do Twojej prezentacji.

#### Przegląd
Dodawanie wykresów może pomóc w wizualnym przedstawianiu danych w prezentacjach. Aspose.Slides ułatwia włączanie różnych typów wykresów, w tym wykresów punktowych.

#### Etapy wdrażania
**Krok 1: Utwórz i dodaj wykres punktowy**
```csharp
using Aspose.Slides.Charts;

// Utwórz i dodaj domyślny wykres punktowy z gładkimi liniami
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Ten fragment kodu dodaje wykres punktowy w określonym położeniu i rozmiarze.

### Wyczyść i dodaj serie do danych wykresu
#### Przegląd
Być może będziesz musiał dostosować swój wykres, czyszcząc istniejące serie i dodając nowe. Ta sekcja obejmuje tę funkcjonalność.

#### Etapy wdrażania
**Krok 1: Dostęp do skoroszytu danych wykresu**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Wyczyść wszystkie istniejące serie
chart.ChartData.Series.Clear();
```
Ten kod czyści istniejące dane, aby móc zacząć od nowa z nową serią.

**Krok 2: Dodaj nową serię**
```csharp
// Dodaj nową serię o nazwie „Seria 1”
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Dodaj kolejną serię o nazwie „Seria 2”
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Te kroki dodają dwie nowe serie do wykresu.

### Modyfikuj punkty danych pierwszej serii i styl znacznika
#### Przegląd
Dostosuj punkty danych i style znaczników, aby lepiej wizualizować wykresy punktowe.

#### Etapy wdrażania
**Krok 1: Dostęp i dodawanie punktów danych**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Dodaj punkty danych (1, 3) i (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Krok 2: Modyfikuj styl znacznika**
```csharp
// Zmień typ serii i zmodyfikuj styl znacznika
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Modyfikuj punkty danych drugiej serii i styl znacznika
#### Przegląd
Podobnie, dostosuj drugą serię do potrzeb swojej prezentacji.

#### Etapy wdrażania
**Krok 1: Dostęp i dodawanie wielu punktów danych**
```csharp
// Uzyskaj dostęp do drugiej serii wykresów
series = chart.ChartData.Series[1];

// Dodaj wiele punktów danych
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Krok 2: Modyfikuj styl znacznika**
```csharp
// Zmień rozmiar znacznika i symbol dla drugiej serii
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Zapisz prezentację
Na koniec zapisz prezentację w wybranym katalogu.

#### Etapy wdrażania
**Krok 1: Zdefiniuj katalog**
Upewnij się, że katalog wyjściowy istnieje. Jeśli nie, utwórz go:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Zapisz prezentację
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Ten kod zapisuje plik prezentacji w określonej lokalizacji.

## Wniosek
Udało Ci się dodać wykresy punktowe do prezentacji przy użyciu Aspose.Slides dla .NET. Kontynuuj eksplorację dodatkowych funkcji i dostosowań dostępnych w bibliotece, aby udoskonalić swoje umiejętności wizualizacji danych.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}