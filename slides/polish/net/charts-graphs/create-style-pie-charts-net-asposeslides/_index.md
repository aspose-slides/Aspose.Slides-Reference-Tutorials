---
"date": "2025-04-15"
"description": "Dowiedz się, jak zautomatyzować tworzenie wykresów kołowych w prezentacjach .NET za pomocą Aspose.Slides, bez wysiłku udoskonalając wizualizację danych."
"title": "Jak tworzyć i dostosowywać wykresy kołowe w prezentacjach .NET przy użyciu Aspose.Slides"
"url": "/pl/net/charts-graphs/create-style-pie-charts-net-asposeslides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć i dostosowywać wykresy kołowe w prezentacjach .NET przy użyciu Aspose.Slides

## Wstęp
Tworzenie angażujących i pouczających prezentacji jest kluczowe dla skutecznej komunikacji, niezależnie od tego, czy prezentujesz dane w pracy, czy prezentujesz najnowsze odkrycia projektu. Jednym z potężnych sposobów wizualizacji danych są wykresy kołowe, które mogą zwięźle reprezentować części całości. Jednak ręczne tworzenie tych wykresów w oprogramowaniu do prezentacji, takim jak PowerPoint, może być czasochłonne i może nie zapewniać elastyczności wymaganej do dynamicznych aktualizacji.

Tutaj wkracza Aspose.Slides dla .NET. Ta kompleksowa biblioteka pozwala programowo tworzyć, modyfikować i stylizować prezentacje, co czyni ją nieocenionym narzędziem dla programistów, którzy chcą zautomatyzować swój przepływ pracy i zapewnić spójność prezentacji.

W tym samouczku pokażemy, jak używać Aspose.Slides dla .NET do tworzenia i dostosowywania wykresów kołowych w prezentacjach. Dowiesz się, jak:
- **Utwórz prezentację i uzyskaj dostęp do slajdów**
- **Dodawaj i konfiguruj wykresy kołowe**
- **Dostosuj dane i serie wykresów**
- **Styl wykresu kołowego sektorów**
- **Dodaj niestandardowe etykiety**
- **Skonfiguruj właściwości wyświetlania i zapisz prezentację**

Gotowy, aby z łatwością zanurzyć się w tworzeniu oszałamiających wykresów kołowych? Zaczynajmy!

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące ustawienia:

### Wymagane biblioteki
- Aspose.Slides dla .NET (zalecana wersja 21.11 lub nowsza)

### Konfiguracja środowiska
- Środowisko programistyczne obsługujące .NET Framework lub .NET Core/5+/6+
- Edytor kodu, taki jak Visual Studio

### Wymagania wstępne dotyczące wiedzy
- Podstawowa znajomość programowania w języku C#
- Znajomość koncepcji obiektowych

## Konfigurowanie Aspose.Slides dla .NET
Aby rozpocząć, musisz zainstalować bibliotekę Aspose.Slides. Możesz to zrobić za pomocą dowolnej z następujących metod:

**Interfejs wiersza poleceń .NET**
```bash
dotnet add package Aspose.Slides
```

**Konsola Menedżera Pakietów**
```powershell
Install-Package Aspose.Slides
```

**Interfejs użytkownika menedżera pakietów NuGet**
- Otwórz projekt w programie Visual Studio.
- Przejdź do „Narzędzia” > „Menedżer pakietów NuGet” > „Zarządzaj pakietami NuGet dla rozwiązania”.
- Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

### Etapy uzyskania licencji
Aby korzystać z Aspose.Slides, możesz rozpocząć bezpłatny okres próbny, pobierając tymczasową licencję. Odwiedź [Strona internetowa Aspose](https://purchase.aspose.com/temporary-license/) aby ją uzyskać. W celu ciągłego użytkowania, rozważ zakup pełnej licencji.

### Podstawowa inicjalizacja i konfiguracja
Po zainstalowaniu zainicjuj klasę Presentation, która reprezentuje plik PPTX:

```csharp
using Aspose.Slides;

Presentation presentation = new Presentation();
```

## Przewodnik wdrażania
Podzielimy proces tworzenia wykresu kołowego na łatwe do opanowania sekcje. Każda sekcja jest zaprojektowana tak, aby skupiać się na konkretnej funkcji, umożliwiając stopniowe budowanie wiedzy.

### Utwórz prezentację i uzyskaj dostęp do slajdów
**Przegląd:** Zacznij od utworzenia nowej prezentacji i uzyskania dostępu do jej pierwszego slajdu. To przygotowuje grunt pod dodawanie wykresów i innych elementów.

```csharp
using Aspose.Slides;

public static void CreatePresentationAndAccessSlide()
{
    // Utwórz klasę prezentacji reprezentującą plik PPTX
    Presentation presentation = new Presentation();
    
    // Dostęp do pierwszego slajdu
    ISlide slides = presentation.Slides[0];
}
```

### Dodaj i skonfiguruj wykres kołowy
**Przegląd:** Dowiedz się, jak dodać wykres kołowy do slajdu i ustawić jego tytuł na podstawie kontekstu.

```csharp
using Aspose.Slides;
using Aspose.Slides.Charts;

public static void AddAndConfigurePieChart()
{
    // Utwórz klasę prezentacji reprezentującą plik PPTX
    Presentation presentation = new Presentation();
    
    // Dostęp do pierwszego slajdu
    ISlide slides = presentation.Slides[0];
    
    // Dodaj wykres z domyślnymi danymi do slajdu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Ustawienie tytułu wykresu
    chart.ChartTitle.AddTextFrameForOverriding("Sample Title");
    chart.ChartTitle.TextFrameForOverriding.TextFrameFormat.CenterText = NullableBool.True;
    chart.ChartTitle.Height = 20;
    chart.HasTitle = true;
}
```

### Dostosuj dane i serie wykresów
**Przegląd:** Dostosuj kategorie i serie danych do swoich konkretnych wymagań.

```csharp
using Aspose.Slides.Charts;

public static void CustomizeChartDataAndSeries()
{
    // Utwórz klasę prezentacji reprezentującą plik PPTX
    Presentation presentation = new Presentation();
    
    // Dostęp do pierwszego slajdu
    ISlide slides = presentation.Slides[0];
    
    // Dodaj wykres z domyślnymi danymi do slajdu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Ustaw pierwszą serię na Pokaż wartości
    chart.ChartData.Series[0].Labels.DefaultDataLabelFormat.ShowValue = true;
    
    // Ustawianie indeksu arkusza danych wykresu
    int defaultWorksheetIndex = 0;
    
    // Pobieranie arkusza danych wykresu
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    
    // Usuń domyślnie wygenerowane serie i kategorie
    chart.ChartData.Series.Clear();
    chart.ChartData.Categories.Clear();
    
    // Dodawanie nowych kategorii
    chart.ChartData.Categories.Add(fact.GetCell(0, 1, 0, "First Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 2, 0, "2nd Qtr"));
    chart.ChartData.Categories.Add(fact.GetCell(0, 3, 0, "3rd Qtr"));
    
    // Dodawanie nowej serii
    IChartSeries series = chart.ChartData.Series.Add(fact.GetCell(0, 0, 1, "Series 1"), chart.Type);
    
    // Teraz wypełniamy dane serii
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, 20));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 50));
    series.DataPoints.AddDataPointForPieSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 30));
}
```

### Dostosuj style sektorów wykresu kołowego
**Przegląd:** Nadaj styl poszczególnym sektorom wykresu kołowego, aby zwiększyć jego atrakcyjność wizualną i podkreślić kluczowe punkty danych.

```csharp
using Aspose.Slides.Charts;
using System.Drawing;

public static void CustomizePieChartSectorStyles()
{
    // Utwórz klasę prezentacji reprezentującą plik PPTX
    Presentation presentation = new Presentation();
    
    // Dostęp do pierwszego slajdu
    ISlide slides = presentation.Slides[0];
    
    // Dodaj wykres z domyślnymi danymi do slajdu
    IChart chart = slides.Shapes.AddChart(ChartType.Pie, 100, 100, 400, 400);
    
    // Pobierz serię z wykresu
    IChartSeries series = chart.ChartData.Series[0];
    
    // Dostosowywanie stylów sektorów dla każdego punktu danych w serii
    IChartDataPoint point = series.DataPoints[0];
    point.Format.Fill.FillType = FillType.Solid;
    point.Format.Fill.SolidFillColor.Color = Color.Cyan;
    
    // Ustawianie granicy sektora
    point.Format.Line.FillFormat.FillType = FillType.Solid;
    point.Format.Line.FillFormat.SolidFillColor.Color = Color.Gray;
    point.Format.Line.Width = 3.0;
    point.Format.Line.Style = LineStyle.ThinThick;
    point.Format.Line.DashStyle = LineDashStyle.DashDot;

    IChartDataPoint point1 = series.DataPoints[1];
    point1.Format.Fill.FillType = FillType.Solid;
    point1.Format.Fill.SolidFillColor.Color = Color.Green;
    
    // Ustawianie granicy sektora
    point1.Format.Line.FillFormat.FillType = FillType.Solid;
    point1.Format.Line.FillFormat.SolidFillColor.Color = Color.Black;
    point1.Format.Line.Width = 2.0;
    point1.Format.Line.Style = LineStyle.Solid;

    IChartDataPoint point2 = series.DataPoints[2];
    point2.Format.Fill.FillType = FillType.Solid;
    point2.Format.Fill.SolidFillColor.Color = Color.Yellow;
    
    // Ustawianie granicy sektora
    point2.Format.Line.FillFormat.FillType = FillType.Solid;
    point2.Format.Line.FillFormat.SolidFillColor.Color = Color.Red;
    point2.Format.Line.Width = 2.0;
    point2.Format.Line.Style = LineStyle.Dot;
}
```

### Dodaj niestandardowe etykiety do wykresu kołowego
**Przegląd:** Ulepsz swój wykres kołowy, dodając niestandardowe etykiety w celu uzyskania bardziej przejrzystej reprezentacji danych.

```csharp
public static void AddCustomLabelsToPieChart(IChart chart)
{
    IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
    IChartSeries series = chart.ChartData.Series[0];

    foreach (IChartDataPoint point in series.DataPoints)
    {
        IDataLabel lbl = point.Label;
        lbl.TextFrameForOverriding.Text = $"{point.Value}";
        lbl.Position = LegendPositionType.Center; // razie potrzeby dostosuj położenie etykiety
    }
}
```

### Wniosek
Teraz wiesz, jak tworzyć i dostosowywać wykresy kołowe w prezentacjach .NET przy użyciu Aspose.Slides. Ta automatyzacja może znacznie usprawnić działania związane z wizualizacją danych, oszczędzając czas i zapewniając spójność w prezentacjach.

Aby jeszcze lepiej poznać możliwości pakietu Aspose.Slides dla platformy .NET, warto zapoznać się z dodatkowymi funkcjami, takimi jak tworzenie innych typów wykresów lub integrowanie bardziej złożonych elementów projektu ze slajdami.

Miłego kodowania!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}