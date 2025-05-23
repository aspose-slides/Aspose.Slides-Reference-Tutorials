---
"date": "2025-04-15"
"description": "Dowiedz się, jak tworzyć wykresy liniowe ze znacznikami za pomocą Aspose.Slides dla .NET. Ten przewodnik krok po kroku obejmuje konfigurację, tworzenie wykresów i dostosowywanie."
"title": "Jak utworzyć wykres liniowy ze znacznikami w języku C# przy użyciu Aspose.Slides dla platformy .NET"
"url": "/pl/net/charts-graphs/create-line-chart-markers-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć wykres liniowy ze znacznikami w języku C# przy użyciu Aspose.Slides dla platformy .NET

## Wstęp
Tworzenie atrakcyjnych wizualnie i informacyjnych wykresów liniowych jest niezbędne do efektywnej prezentacji danych w języku C#. **Aspose.Slides dla .NET** upraszcza proces dodawania profesjonalnie wyglądających wykresów, w tym tych ze znacznikami. Ten samouczek przeprowadzi Cię przez proces tworzenia wykresu liniowego z domyślnymi znacznikami przy użyciu Aspose.Slides dla .NET.

W tym samouczku dowiesz się:
- Konfigurowanie środowiska w celu użycia Aspose.Slides dla .NET.
- Tworzenie i dostosowywanie prezentacji przy użyciu wykresu liniowego zawierającego znaczniki.
- Konfigurowanie właściwości wykresu, takich jak kategorie, serie i punkty danych.
- Zapisywanie końcowego pliku prezentacji.

Zacznijmy od omówienia warunków wstępnych, które trzeba spełnić, zanim wdrożymy nasze rozwiązanie.

## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:
- **Wymagane biblioteki:** Aspose.Slides dla .NET instaluje się w środowisku programistycznym za pomocą NuGet.
- **Wymagania dotyczące konfiguracji środowiska:** Działające środowisko programistyczne C#, takie jak Visual Studio i .NET Framework zainstalowane na Twoim komputerze.
- **Wymagania wstępne dotyczące wiedzy:** Podstawowa znajomość programowania w języku C# i znajomość tworzenia prezentacji programowo.

## Konfigurowanie Aspose.Slides dla .NET
### Informacje o instalacji
Aby rozpocząć korzystanie z pakietu Aspose.Slides dla platformy .NET, dodaj go do projektu za pomocą jednej z następujących metod:

**Korzystanie z interfejsu wiersza poleceń .NET:**
```bash
dotnet add package Aspose.Slides
```

**Za pomocą konsoli Menedżera pakietów w programie Visual Studio:**
```powershell
Install-Package Aspose.Slides
```

**Interfejs użytkownika Menedżera pakietów NuGet:**
- Otwórz swoje rozwiązanie w programie Visual Studio.
- Przejdź do „Zarządzaj pakietami NuGet dla rozwiązania...”
- Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

### Nabycie licencji
Przed użyciem Aspose.Slides należy uzyskać wersję próbną lub zakupić licencję:
1. **Bezpłatna wersja próbna:** Odwiedzać [Strona bezpłatnej wersji próbnej Aspose](https://releases.aspose.com/slides/net/) aby szybko zacząć.
2. **Licencja tymczasowa:** Aby uzyskać rozszerzony dostęp, odwiedź stronę [Strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).
3. **Zakup:** Aby używać Aspose.Slides w środowisku produkcyjnym, należy zakupić licencję na stronie [Zakup Aspose](https://purchase.aspose.com/buy).

### Podstawowa inicjalizacja
Po skonfigurowaniu projektu i uzyskaniu niezbędnych licencji zainicjuj Aspose.Slides w następujący sposób:
```csharp
using Aspose.Slides;
// Utwórz instancję klasy Presentation
Presentation pres = new Presentation();
```
Teraz, gdy skonfigurowaliśmy nasze środowisko, możemy utworzyć wykres liniowy ze znacznikami.

## Przewodnik wdrażania
### Tworzenie wykresu liniowego za pomocą znaczników
W tej sekcji poznasz każdy krok potrzebny do utworzenia i skonfigurowania wykresu liniowego z domyślnymi znacznikami w prezentacji przy użyciu Aspose.Slides dla .NET.

#### Krok 1: Utwórz obiekt prezentacji
Zacznij od utworzenia instancji `Presentation` klasa:
```csharp
using (Presentation pres = new Presentation())
{
    ISlide slide = pres.Slides[0];
```
Tutaj mamy dostęp do pierwszego slajdu nowo utworzonej prezentacji.

#### Krok 2: Dodaj wykres liniowy ze znacznikami
Następnie dodaj do slajdu wykres liniowy ze znacznikami:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 10, 10, 400, 400);
```
Ten kod dodaje nowy wykres typu `LineWithMarkers` na współrzędnych `(10, 10)` z wymiarami `400x400`.

#### Krok 3: Wyczyść istniejące serie i kategorie
Przed dodaniem danych wyczyść wszelkie istniejące serie lub kategorie:
```csharp
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```
Dzięki temu mamy pewność, że nasz wykres zaczyna się od czystej karty.

#### Krok 4: Konfigurowanie skoroszytu danych wykresu
Uzyskaj dostęp do `ChartDataWorkbook` aby zarządzać danymi wykresu:
```csharp
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```
Obiekt ten jest niezbędny do zarządzania komórkami zawierającymi dane serii i kategorii.

#### Krok 5: Dodaj serie i kategorie
Dodaj nową serię do wykresu i wypełnij ją punktami danych:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
IChartSeries series = chart.ChartData.Series[0];

// Zdefiniuj kategorie i odpowiadające im punkty danych
chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "C1"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 1, 24));
chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "C2"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 1, 23));
chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "C3"));
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 1, -10));
chart.ChartData.Categories.Add(fact.GetCell(0, 4, 0, "C4"));

// Dodaj punkt danych zerowych, aby pokazać sposób postępowania z wartościami brakującymi
series.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 1, (double?)null));
```
Tutaj wypełniamy wykres kategoriami i odpowiadającymi im danymi serii. Zauważ, jak `null` wartość jest traktowana jako demonstracja.

#### Krok 6: Dodaj kolejną serię
Powtórz proces, aby dodać kolejną serię:
```csharp
chart.ChartData.Series.Add(fact.GetCell(0, 0, 2, "Series 2"), chart.Type);
IChartSeries series2 = chart.ChartData.Series[1];

series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 1, 2, 30));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 2, 2, 10));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 3, 2, 60));
series2.DataPoints.AddDataPointForLineSeries(fact.GetCell(0, 4, 2, 40));
```

#### Krok 7: Włącz i skonfiguruj legendę
Włącz legendę wykresu, aby poprawić czytelność:
```csharp
chart.HasLegend = true;
chart.Legend.Overlay = false;
```
Dzięki temu legenda jest widoczna i nie jest nałożona na wykres.

#### Krok 8: Zapisz prezentację
Na koniec zapisz prezentację z nowo dodanym wykresem:
```csharp
pres.Save("DefaultMarkersInChart.pptx");
}
```
### Porady dotyczące rozwiązywania problemów
- **Błędy wiązania danych:** Upewnij się, że punkty danych poprawnie odpowiadają kategoriom.
- **Wykres nie jest wyświetlany:** Sprawdź, czy `chart.HasLegend` a inne właściwości są odpowiednio ustawione.

## Zastosowania praktyczne
1. **Raporty biznesowe:** Użyj wykresów liniowych ze znacznikami, aby śledzić wyniki sprzedaży na przestrzeni czasu i przedstawiać trendy w miesięcznych przychodach.
2. **Analiza finansowa:** Wizualizuj ruchy cen akcji za pomocą domyślnych znaczników, aby wyróżnić szczyty i dołki.
3. **Badania naukowe:** Przedstaw wyniki eksperymentów, w których punkty danych wymagają wyraźnego rozgraniczenia w celu umożliwienia analizy.

## Rozważania dotyczące wydajności
- Optymalizuj, ograniczając liczbę serii danych i kategorii podczas pracy z dużymi zbiorami danych.
- W środowisku .NET można stosować techniki zarządzania pamięcią, takie jak szybkie usuwanie obiektów, aby zmniejszyć wykorzystanie zasobów.

## Wniosek
W tym samouczku nauczysz się, jak utworzyć wykres liniowy ze znacznikami za pomocą Aspose.Slides dla .NET. Wykonując te kroki, możesz wzbogacić swoje prezentacje o szczegółowe i profesjonalnie wyglądające wykresy. Rozważ zapoznanie się z innymi funkcjami Aspose.Slides, aby jeszcze bardziej wzbogacić swoje pokazy slajdów.

### Następne kroki
- Eksperymentuj z różnymi typami wykresów dostępnymi w Aspose.Slides.
- Dostosuj wygląd wykresów, aby uzyskać lepszy efekt wizualny.
- Zapoznaj się z dodatkową dokumentacją Aspose.Slides, aby poznać bardziej zaawansowane funkcje.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}