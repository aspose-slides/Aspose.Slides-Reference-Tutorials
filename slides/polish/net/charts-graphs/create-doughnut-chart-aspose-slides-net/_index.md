---
"date": "2025-04-15"
"description": "Dowiedz się, jak tworzyć dynamiczne wykresy pierścieniowe za pomocą Aspose.Slides dla .NET. Postępuj zgodnie z tym przewodnikiem, aby uzyskać instrukcje krok po kroku, w tym dotyczące konfiguracji i zaawansowanych funkcji."
"title": "Przewodnik krok po kroku&#58; Tworzenie wykresu pierścieniowego za pomocą Aspose.Slides .NET | Wykresy i diagramy"
"url": "/pl/net/charts-graphs/create-doughnut-chart-aspose-slides-net/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Przewodnik krok po kroku: Tworzenie wykresu pierścieniowego za pomocą Aspose.Slides .NET

## Wstęp

Wyobraź sobie, że masz za zadanie przedstawić wyniki analizy danych swojemu zespołowi lub klientom i potrzebujesz angażującego sposobu na wizualizację informacji. Wprowadź wykres pierścieniowy — wszechstronne narzędzie, które może przekształcić surowe liczby w łatwo przyswajalne spostrzeżenia. Dzięki Aspose.Slides dla .NET tworzenie niestandardowego wykresu pierścieniowego na slajdach prezentacji jest proste i wydajne. Ten przewodnik przeprowadzi Cię przez korzystanie z Aspose.Slides w celu utworzenia atrakcyjnego wizualnie wykresu pierścieniowego, wraz z dostosowanymi konfiguracjami serii.

**Czego się nauczysz:**
- Konfigurowanie środowiska programistycznego z Aspose.Slides dla .NET
- Tworzenie i dostosowywanie wykresów pierścieniowych w prezentacjach
- Wdrażanie zaawansowanych funkcji, takich jak nazwy kategorii i linie odniesienia
- Optymalizacja wydajności dla dużych zestawów danych

Przyjrzyjmy się bliżej wymaganiom wstępnym, które musisz spełnić, aby zacząć.

## Wymagania wstępne

Przed wdrożeniem tej funkcji upewnij się, że Twoje środowisko programistyczne jest poprawnie skonfigurowane. Ten samouczek zakłada podstawową wiedzę na temat programowania .NET i znajomość Visual Studio lub podobnego IDE.

### Wymagane biblioteki i wersje
- **Aspose.Slides dla .NET**: Upewnij się, że wersja jest zgodna z najnowszą wersją, sprawdzając jej kompatybilność. [oficjalna dokumentacja](https://reference.aspose.com/slides/net/).

### Wymagania dotyczące konfiguracji środowiska
- Działające środowisko .NET.
- Dostęp do edytora kodu, takiego jak Visual Studio.

### Wymagania wstępne dotyczące wiedzy
- Podstawowa znajomość języka C# i środowiska .NET.
- Znajomość koncepcji oprogramowania do prezentacji (opcjonalna, ale pomocna).

## Konfigurowanie Aspose.Slides dla .NET

Aby rozpocząć korzystanie z Aspose.Slides w projekcie, musisz zainstalować go za pomocą NuGet. Oto dostępne metody:

**Korzystanie z interfejsu wiersza poleceń .NET:**
```bash
dotnet add package Aspose.Slides
```

**Korzystanie z Menedżera pakietów:**
```powershell
Install-Package Aspose.Slides
```

**Interfejs użytkownika Menedżera pakietów NuGet:**
Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

### Etapy uzyskania licencji

1. **Bezpłatna wersja próbna**:Zacznij od [bezpłatny okres próbny](https://releases.aspose.com/slides/net/) aby zapoznać się z podstawowymi funkcjonalnościami.
2. **Licencja tymczasowa**:Uzyskaj tymczasową licencję, jeśli potrzebujesz dostępu do pełnych funkcji w celach ewaluacyjnych, odwiedzając stronę [Tutaj](https://purchase.aspose.com/temporary-license/).
3. **Zakup**:Do użytku komercyjnego należy zakupić licencję od [Strona internetowa Aspose](https://purchase.aspose.com/buy).

Po zainstalowaniu i uzyskaniu licencji zainicjuj Aspose.Slides w swoim projekcie:
```csharp
using Aspose.Slides;

// Zainicjuj Aspose.Slides dla .NET
var presentation = new Presentation();
```

## Przewodnik wdrażania

### Tworzenie nowej prezentacji i dodawanie wykresu pierścieniowego

#### Przegląd
Zaczniemy od utworzenia nowej prezentacji i dodania wykresu pierścieniowego do pierwszego slajdu. Ta sekcja obejmuje ładowanie istniejącej prezentacji, dostęp do slajdów i wstawianie wykresów.

**Krok 1: Załaduj lub utwórz prezentację**
Najpierw określ katalog dokumentów i załaduj istniejącą prezentację:
```csharp
string dataDir = \@"YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation(dataDir + "testc.pptx");
```
Jeśli nie masz istniejącego pliku, utwórz nowy za pomocą `new Presentation()`.

**Krok 2: Dostęp do pierwszego slajdu**
Uzyskaj dostęp do pierwszego slajdu, na którym dodamy nasz wykres:
```csharp
ISlide slide = pres.Slides[0];
```

**Krok 3: Dodaj wykres pierścieniowy**
Dodaj wykres pierścieniowy o określonych współrzędnych i wymiarach:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurowanie skoroszytu danych

#### Przegląd
W tej sekcji wyjaśniono, jak skonfigurować skoroszyt danych powiązany z wykresem pierścieniowym.

**Krok 4: Uzyskaj dostęp i wyczyść istniejące dane**
Uzyskaj dostęp do skoroszytu danych wykresu. Następnie wyczyść wszelkie istniejące serie lub kategorie:
```csharp
IChartDataWorkbook workBook = chart.ChartData.ChartDataWorkbook;
chart.ChartData.Series.Clear();
chart.ChartData.Categories.Clear();
```

**Krok 5: Wyłącz legendę i dodaj serię**
Wyłącz legendę, aby wykres był przejrzysty, a następnie dodaj maksymalnie 15 serii z niestandardowymi konfiguracjami:
```csharp
chart.HasLegend = false;

int seriesIndex = 0;
while (seriesIndex < 15)
{
    IChartSeries series = chart.ChartData.Series.Add(workBook.GetCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex), chart.Type);
    series.Explosion = 0;
    series.ParentSeriesGroup.DoughnutHoleSize = (byte)20;
    series.ParentSeriesGroup.FirstSliceAngle = 351;
    seriesIndex++;
}
```

### Dodawanie kategorii i punktów danych

#### Przegląd
Teraz uzupełnijmy wykres kategoriami i punktami danych dla każdej serii.

**Krok 6: Dodaj kategorie**
Przejdź przez pętlę, aby dodać 15 kategorii:
```csharp
int categoryIndex = 0;
while (categoryIndex < 15)
{
    chart.ChartData.Categories.Add(workBook.GetCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));
```

**Krok 7: Wypełnij punkty danych**
Dodaj punkty danych dla każdej serii w ramach bieżącej kategorii:
```csharp
int i = 0;
while (i < chart.ChartData.Series.Count)
{
    IChartSeries iCS = chart.ChartData.Series[i];
    IChartDataPoint dataPoint = iCS.DataPoints.AddDataPointForDoughnutSeries(workBook.GetCell(0, categoryIndex + 1, i + 1, 1));

    // Dostosuj wygląd
    dataPoint.Format.Fill.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.FillType = FillType.Solid;
    dataPoint.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;
    dataPoint.Format.Line.Width = 1;
    dataPoint.Format.Line.Style = LineStyle.Single;
    dataPoint.Format.Line.DashStyle = LineDashStyle.Solid;

    // Skonfiguruj format etykiety dla ostatniej serii
    if (i == chart.ChartData.Series.Count - 1)
    {
        IDataLabel lbl = dataPoint.Label;
        lbl.TextFormat.TextBlockFormat.AutofitType = TextAutofitType.Shape;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontBold = NullableBool.True;
        lbl.DataLabelFormat.TextFormat.PortionFormat.LatinFont = new FontData("DINPro-Bold");
        lbl.DataLabelFormat.TextFormat.PortionFormat.FontHeight = 12;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
        lbl.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = System.Drawing.Color.LightGray;
        lbl.DataLabelFormat.Format.Line.FillFormat.SolidFillColor.Color = System.Drawing.Color.White;

        // Konfiguruj wyświetlanie etykiet
        lbl.DataLabelFormat.ShowValue = false;
        lbl.DataLabelFormat.ShowCategoryName = true;
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowLeaderLines = true;

        chart.ValidateChartLayout();
        lbl.AsILayoutable.X += 0.5f;
        lbl.AsILayoutable.Y += 0.5f;
    }
    i++;
}
categoryIndex++;
```

### Zapisywanie prezentacji

**Krok 8: Zapisz plik**
Na koniec zapisz prezentację w określonym katalogu:
```csharp
pres.Save(dataDir + "chart.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}