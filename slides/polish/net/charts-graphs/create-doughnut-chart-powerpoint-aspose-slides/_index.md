---
"date": "2025-04-15"
"description": "Dowiedz się, jak tworzyć dynamiczne i atrakcyjne wizualnie wykresy pierścieniowe w prezentacjach programu PowerPoint, korzystając z zaawansowanej biblioteki Aspose.Slides for .NET."
"title": "Jak utworzyć wykres pierścieniowy w programie PowerPoint przy użyciu Aspose.Slides dla platformy .NET"
"url": "/pl/net/charts-graphs/create-doughnut-chart-powerpoint-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć wykres pierścieniowy w programie PowerPoint przy użyciu Aspose.Slides dla platformy .NET
Tworzenie wizualnie angażujących wykresów jest niezbędne do skutecznej prezentacji danych. Wykresy pierścieniowe są idealne do ilustrowania części całości, co czyni je idealnymi do wizualizacji danych opartych na procentach. Ten samouczek przeprowadzi Cię przez proces tworzenia dynamicznego wykresu pierścieniowego w programie PowerPoint przy użyciu potężnej biblioteki Aspose.Slides for .NET.

## Wstęp
Prezentacje często wymagają wizualnych reprezentacji złożonych zestawów danych, w których tradycyjne wykresy słupkowe lub liniowe mogą okazać się niewystarczające. Wykres pierścieniowy okazuje się wszechstronnym narzędziem do skutecznej komunikacji danych procentowych ze stylem i przejrzystością. W tym samouczku przyjrzymy się, w jaki sposób Aspose.Slides for .NET upraszcza proces tworzenia tych wykresów bezpośrednio w programie PowerPoint.

**Czego się nauczysz:**
- Konfigurowanie Aspose.Slides dla .NET
- Instrukcje krok po kroku dotyczące tworzenia wykresu pierścieniowego
- Dodawanie serii i kategorii do wykresu
- Konfigurowanie etykiet danych w celu zwiększenia przejrzystości
- Zapisywanie ostatecznej prezentacji

Przyjrzyjmy się bliżej, jak można wykorzystać Aspose.Slides dla platformy .NET do wzbogacenia prezentacji o niestandardowe wykresy pierścieniowe.

## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
- **Biblioteka Aspose.Slides dla .NET**: Dostępne poprzez NuGet lub do pobrania bezpośrednio.
- **Środowisko programistyczne**:W przypadku projektów .NET zaleca się korzystanie z programu Visual Studio.
- Podstawowa znajomość języka C# i znajomość struktury programu PowerPoint.

## Konfigurowanie Aspose.Slides dla .NET
Aby rozpocząć tworzenie wykresów, musisz najpierw skonfigurować bibliotekę Aspose.Slides w swoim projekcie. Oto kilka sposobów jej zainstalowania:

**Korzystanie z interfejsu wiersza poleceń .NET:**

```bash
dotnet add package Aspose.Slides
```

**Korzystanie z konsoli Menedżera pakietów:**

```powershell
Install-Package Aspose.Slides
```

**Za pomocą interfejsu użytkownika Menedżera pakietów NuGet:**
Wyszukaj „Aspose.Slides” i zainstaluj najnowszą wersję.

Po zainstalowaniu możesz rozpocząć konfigurowanie swojego projektu. Jeśli jesteś nowy w Aspose.Slides, rozważ uzyskanie tymczasowej licencji lub bezpłatnej wersji próbnej, aby odkryć jego pełne możliwości bez ograniczeń.

### Zainicjuj swój projekt
Oto jak możesz zainicjować Aspose.Slides w swojej aplikacji:

```csharp
using Aspose.Slides;

class Program
{
    static void Main()
    {
        // Utwórz instancję klasy Presentation
        Presentation presentation = new Presentation();
        
        // Twój kod do manipulowania prezentacją znajduje się tutaj
        
        // Zapisz prezentację
        presentation.Save("output.pptx", SaveFormat.Pptx);
    }
}
```

## Przewodnik wdrażania
### Tworzenie wykresu pierścieniowego
#### Przegląd
Najpierw utworzymy pusty wykres pierścieniowy na slajdzie programu PowerPoint. Będzie on podstawą do dodawania danych i dostosowywania ich wyglądu.

**Krok 1: Dodaj wykres pierścieniowy**

```csharp
using Aspose.Slides;

class CreateDoughnutChart
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        
        // Dodaj wykres kołowy do pierwszego slajdu na pozycji (10, 10) o rozmiarze (500, 500)
        IChart chart = slide.getShapes().addChart(
            ChartType.Doughnut, 10, 10, 500, 500, false
        );

        // Wyczyść istniejące serie i kategorie
        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getCategories().clear();

        // Wyłącz legendę, aby uzyskać bardziej przejrzysty wygląd
        chart.setHasLegend(false);

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Wyjaśnienie:**
- **dodajwykres**: Wstawia nowy wykres kołowy na slajdzie.
- **pobierzWykresDaneWorkbook**:Umożliwia dostęp do komórek danych na wykresie w celu manipulacji.

### Dodawanie serii i kategorii
#### Przegląd
Następnie wypełnimy Twój wykres istotnymi danymi poprzez dodanie serii i kategorii.

**Krok 2: Dodaj serię danych**

```csharp
using Aspose.Slides;

class AddSeriesAndCategories
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        // Dodaj serię
        for (int seriesIndex = 0; seriesIndex < 15; seriesIndex++)
        {
            IChartSeries series = chart.getChartData()
                .getSeries()
                .add(
                    workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
                    chart.getType()
                );

            // Dostosowywanie otworu w kształcie pączka i kąta początkowego
            series.setExplosion(0);
            series.getParentSeriesGroup().setDoughnutHoleSize((byte)20);
            series.getParentSeriesGroup().setFirstSliceAngle(351);
        }

        // Dodaj kategorie
        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            chart.getChartData()
                .getCategories()
                .add(workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex));

            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = iCS
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Formatowanie wypełnienia i linii punktu danych
                dataPoint.getFormat().getFill().setFillType(FillType.Solid);
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .setFillType(FillType.Solid);
                
                dataPoint.getFormat().getLine()
                    .getFillFormat()
                    .getSolidFillColor()
                    .setColor(Color.WHITE);
                
                dataPoint.getFormat().getLine().setWidth(1.0);
                dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
                dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Wyjaśnienie:**
- **dodać**: Wstawia nowe serie i kategorie do wykresu.
- **ustawRozmiarOtworuPączka**Konfiguruje rozmiar otworu w pączku, zwiększając jego atrakcyjność wizualną.

### Konfigurowanie etykiet danych
#### Przegląd
Etykiety danych zapewniają kontekst do danych wykresu. Zwiększmy czytelność, dostosowując je.

**Krok 3: Dostosuj etykiety danych**

```csharp
using Aspose.Slides;

class ConfigureDataLabels
{
    public static void Main(String[] args)
    {
        string dataDir = "YOUR_DOCUMENT_DIRECTORY";
        Presentation pres = new Presentation(dataDir + "/testc.pptx");
        ISlide slide = pres.getSlides().get_Item(0);
        IChart chart = (IChart)slide.getShapes().get_Item(1);

        IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

        for (int categoryIndex = 0; categoryIndex < 15; categoryIndex++)
        {
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                IChartSeries series = chart.getChartData().getSeries().get_Item(i);
                IChartDataPoint dataPoint = series
                    .getDataPoints()
                    .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

                // Dostosowywanie etykiet danych
                IDataLabel lbl = dataPoint.getLabel();
                lbl.getDataLabelFormat().setTextFormat()
                    .setCenterText(NullableBool.True)
                    .setShowPercentage(true);
                lbl.setVisible(true);
            }
        }

        pres.Save("YOUR_OUTPUT_DIRECTORY/chart.pptx", SaveFormat.Pptx);
    }
}
```

**Wyjaśnienie:**
- **Etykieta IData**:Dostosowuje etykiety danych w celu zapewnienia przejrzystości i prezentacji.
- **ustawCenterText**, **pokażProcent**: Popraw czytelność etykiety poprzez wyśrodkowanie tekstu i wyświetlanie procentów.

## Wniosek
Dzięki temu przewodnikowi nauczyłeś się, jak utworzyć dynamiczny wykres pierścieniowy w programie PowerPoint przy użyciu Aspose.Slides dla .NET. Ta potężna biblioteka umożliwia szeroką personalizację, dzięki czemu możesz dostosować wykresy dokładnie do potrzeb prezentacji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}