---
"date": "2025-04-15"
"description": "Dowiedz się, jak tworzyć wizualnie atrakcyjne wykresy kolumnowe oparte na procentach przy użyciu Aspose.Slides dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby uzyskać przejrzystą wizualizację danych."
"title": "Jak tworzyć wykresy kolumnowe oparte na procentach w .NET przy użyciu Aspose.Slides"
"url": "/pl/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć wykres kolumnowy oparty na procentach przy użyciu Aspose.Slides dla .NET

## Wstęp

dziedzinie wizualizacji danych, jasne i skuteczne przedstawianie informacji jest kluczowe dla podejmowania skutecznych decyzji. Do intuicyjnego wyświetlania złożonych zestawów danych idealne są wykresy kolumnowe oparte na procentach. Ten przewodnik przeprowadzi Cię przez proces tworzenia tych wykresów przy użyciu Aspose.Slides dla .NET, solidnej biblioteki zaprojektowanej do manipulowania plikami prezentacji.

Dzięki temu samouczkowi dowiesz się:
- Konfigurowanie danych wykresu i formatów liczb.
- Dodawanie serii i dostosowywanie ich wyglądu.
- Formatowanie etykiet w celu zwiększenia czytelności.

Gotowy do nurkowania? Zacznijmy od wymagań wstępnych, których potrzebujesz!

## Wymagania wstępne

Przed utworzeniem wykresów kolumnowych opartych na procentach upewnij się, że Twoje środowisko jest poprawnie skonfigurowane. Będziesz potrzebować:

### Wymagane biblioteki, wersje i zależności
- **Aspose.Slides dla .NET**: Upewnij się, że ta biblioteka jest zainstalowana.

### Wymagania dotyczące konfiguracji środowiska
- Środowisko programistyczne z zainstalowanym pakietem .NET SDK.
- Visual Studio lub dowolne kompatybilne środowisko IDE do uruchamiania kodu C#.

### Wymagania wstępne dotyczące wiedzy
- Podstawowa znajomość programowania w języku C#.
- Znajomość konfiguracji projektów .NET i zarządzania pakietami.

## Konfigurowanie Aspose.Slides dla .NET

Aby rozpocząć tworzenie wykresów za pomocą Aspose.Slides, najpierw zainstaluj bibliotekę, korzystając z jednej z następujących metod:

**Interfejs wiersza poleceń .NET**
```bash
dotnet add package Aspose.Slides
```

**Menedżer pakietów**
```powershell
Install-Package Aspose.Slides
```

**Interfejs użytkownika menedżera pakietów NuGet**
- Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

### Etapy uzyskania licencji

Rozpocznij bezpłatny okres próbny, pobierając tymczasową licencję ze strony [Strona internetowa Aspose](https://purchase.aspose.com/temporary-license/). Aby kontynuować użytkowanie, należy rozważyć zakup pełnej licencji. 

Po skonfigurowaniu zainicjuj Aspose.Slides w swoim projekcie:
```csharp
using Aspose.Slides;
```

## Przewodnik wdrażania

Mając już gotowe środowisko, możemy podzielić proces tworzenia wykresu kolumnowego opartego na procentach na kilka kroków.

### Tworzenie i konfigurowanie wykresu

#### Przegląd
Utwórz instancję `Presentation` klasa, która jest niezbędna do pracy ze slajdami. Następnie dodaj i skonfiguruj wykres kolumnowy na slajdzie.

#### Dodawanie wykresu kolumnowego
```csharp
// Utwórz instancję klasy Presentation
document = new Presentation();

// Uzyskaj odniesienie do pierwszego slajdu
slide = document.Slides[0];

// Dodaj wykres kolumnowy procentowy w pozycji (20, 20) o rozmiarze (500x400)
chart = slide.Shapes.AddChart(ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

#### Konfigurowanie formatu liczb
Upewnij się, że Twoje dane są wyświetlane w postaci procentowej:
```csharp
// Skonfiguruj format liczbowy dla osi pionowej
columnChart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
columnChart.Axes.VerticalAxis.NumberFormat = "0.00%"; // Ustaw format liczbowy na procentowy
```

#### Dodawanie serii danych i punktów
Wyczyść istniejące dane serii i dodaj nowe:
```csharp
// Wyczyść wszelkie istniejące dane serii
columnChart.ChartData.Series.Clear();

int defaultWorksheetIndex = 0;

// Dostęp do skoroszytu danych wykresu
dataWorkbook = columnChart.ChartData.ChartDataWorkbook;

// Dodaj nową serię danych „Czerwoni”
series = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 1, "Reds"), columnChart.Type);
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 1, 0.30));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 1, 0.50));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 1, 0.80));
series.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 1, 0.65));

// Ustaw kolor wypełnienia dla serii na czerwony
series.Format.Fill.FillType = FillType.Solid;
series.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Red;

// Konfigurowanie właściwości formatu etykiety dla serii „Reds”
series.Labels.DefaultDataLabelFormat.ShowValue = true;
series.Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Ustaw format procentowy
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[0].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

// Dodaj kolejną serię „Blues”
series2 = columnChart.ChartData.Series.Add(dataWorkbook.GetCell(defaultWorksheetIndex, 0, 2, "Blues"), chart.Type);
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 1, 2, 0.70));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 2, 2, 0.50));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 3, 2, 0.20));
series2.DataPoints.AddDataPointForBarSeries(dataWorkbook.GetCell(defaultWorksheetIndex, 4, 2, 0.35));

// Ustaw kolor wypełnienia dla serii na niebieski
series2.Format.Fill.FillType = FillType.Solid;
series2.Format.Fill.SolidFillColor.Color = System.Drawing.Color.Blue;
series2.Labels.DefaultDataLabelFormat.ShowValue = true;
columnChart.Series[1].Labels.DefaultDataLabelFormat.IsNumberFormatLinkedToSource = false;
series2.Labels.DefaultDataLabelFormat.NumberFormat = "0.0%"; // Ustaw format procentowy
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FontHeight = 10;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
columnChart.Series[1].Labels.DefaultDataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
```

#### Zapisywanie prezentacji
Zapisz prezentację do pliku:
```csharp
// Zapisz prezentację w formacie PPTX
document.Save("YOUR_OUTPUT_DIRECTORY/SetDataLabelsPercentageSign_out.pptx");
```

### Porady dotyczące rozwiązywania problemów
- Sprawdź, czy wszystkie przestrzenie nazw zostały poprawnie zaimportowane.
- Sprawdź, czy w nazwach właściwości i wywołaniach metod nie ma literówek.
- Sprawdź, czy ścieżki do zapisywania plików istnieją i mają właściwe uprawnienia.

## Zastosowania praktyczne

Oto kilka scenariuszy, w których wykresy kolumnowe oparte na procentach mogą okazać się przydatne:
1. **Analiza sprzedaży**:Wizualizacja wyników sprzedaży produktów w różnych regionach jako proporcji do całkowitej sprzedaży.
2. **Alokacja budżetu**:Pokaż, w jaki sposób poszczególne działy rozdzielają swój budżet w odniesieniu do ogólnych wydatków firmy.
3. **Badania rynku**:Porównaj preferencje konsumentów dotyczące różnych kategorii produktów na przestrzeni czasu.
4. **Dane edukacyjne**:Wyświetl rozkład ocen uczniów z różnych przedmiotów.
5. **Statystyki opieki zdrowotnej**:Przedstaw dane demograficzne pacjentów w różnych stanach zdrowia.

## Rozważania dotyczące wydajności

Aby uzyskać optymalną wydajność, należy wziąć pod uwagę następujące kwestie:
- Ograniczenie liczby punktów danych do niezbędnego minimum.
- Wstępne ładowanie danych w celu zminimalizowania przetwarzania w czasie wykonywania.
- Korzystanie z efektywnych praktyk zarządzania pamięcią w Aspose.Slides dla .NET.

## Wniosek

Gratulacje! Udało Ci się nauczyć, jak utworzyć oparty na procentach wykres kolumnowy za pomocą Aspose.Slides dla .NET. To narzędzie ulepsza prezentacje, czyniąc złożone dane bardziej zrozumiałymi i atrakcyjnymi wizualnie.

Następne kroki? Przeglądaj inne typy wykresów dostępne w Aspose.Slides lub zintegruj tę funkcjonalność z większymi aplikacjami. Miłego kodowania!

## Sekcja FAQ

**P1: Czy mogę używać Aspose.Slides za darmo?**
A1: Tak, możesz zacząć od bezpłatnego okresu próbnego, aby przetestować funkcje Aspose.Slides.

**P2: Jakie typy wykresów są obsługiwane przez Aspose.Slides dla platformy .NET?**
A2: Obsługuje różne wykresy, takie jak wykres kołowy, słupkowy, kolumnowy, liniowy i inne.

**P3: Jak rozpocząć korzystanie z Aspose.Slides dla platformy .NET?**
A3: Zainstaluj bibliotekę za pomocą NuGet lub .NET CLI, jak opisano powyżej. Postępuj zgodnie z naszą dokumentacją, aby utworzyć swój pierwszy wykres.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}