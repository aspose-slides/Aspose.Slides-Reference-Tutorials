---
"date": "2025-04-15"
"description": "Dowiedz się, jak tworzyć i dostosowywać wykresy za pomocą Aspose.Slides dla .NET, w tym wyświetlać procenty jako etykiety danych. Postępuj zgodnie z tym przewodnikiem krok po kroku."
"title": "Jak tworzyć i dostosowywać wykresy za pomocą Aspose.Slides .NET&#58; Wyświetlanie procentów jako etykiet"
"url": "/pl/net/charts-graphs/create-customize-charts-aspose-slides-dotnet/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak tworzyć i dostosowywać wykresy za pomocą Aspose.Slides .NET: Wyświetlanie procentów jako etykiet

## Wstęp

Skuteczne prezentowanie danych jest kluczowe w wielu dziedzinach, a wykresy odgrywają istotną rolę, przekształcając złożone informacje w przejrzyste wizualizacje. Tworzenie idealnego wykresu obejmuje zadania dostosowywania, takie jak wyświetlanie procentów na etykietach — zadanie ułatwione dzięki Aspose.Slides dla .NET. Ta biblioteka upraszcza proces tworzenia i modyfikowania wykresów w prezentacjach PowerPoint.

tym samouczku dowiesz się, jak używać Aspose.Slides dla .NET, aby od podstaw tworzyć wykres kolumnowy i dostosowywać go, wyświetlając wartości procentowe jako etykiety danych. Wykonując te kroki, wzbogacisz swoje slajdy o precyzyjne i atrakcyjne wizualnie reprezentacje danych.

**Czego się nauczysz:**
- Inicjalizacja Aspose.Slides dla .NET
- Tworzenie wykresu kolumnowego ułożonego w stos
- Obliczanie i wyświetlanie procentów na etykietach danych
- Najlepsze praktyki optymalizacji wydajności wykresów

Zanim przejdziemy do realizacji, upewnijmy się, że wszystko jest gotowe do rozpoczęcia pracy.

## Wymagania wstępne

Aby skutecznie skorzystać z tego samouczka, upewnij się, że posiadasz:
- **Zestaw SDK .NET Core** zainstalowany na Twoim komputerze.
- Podstawowa znajomość języków programowania C# i .NET.
- Visual Studio lub podobne środowisko IDE do pisania i uruchamiania kodu C#.

Aby tworzyć wykresy, potrzebny jest Aspose.Slides dla platformy .NET, dlatego upewnij się, że jest on skonfigurowany zgodnie z poniższym opisem.

## Konfigurowanie Aspose.Slides dla .NET

Aspose.Slides dla .NET to potężna biblioteka, która umożliwia programową pracę z prezentacjami PowerPoint. Oto jak dodać ją do projektu:

### Instalacja

**Interfejs wiersza poleceń .NET:**
```bash
dotnet add package Aspose.Slides
```

**Konsola Menedżera Pakietów:**
```powershell
Install-Package Aspose.Slides
```

**Interfejs użytkownika Menedżera pakietów NuGet:** 
- Otwórz NuGet Package Manager i wyszukaj „Aspose.Slides”. Zainstaluj najnowszą wersję.

### Nabycie licencji

Aby w pełni wykorzystać Aspose.Slides, zacznij od bezpłatnego okresu próbnego. W przypadku dłuższego użytkowania rozważ nabycie licencji tymczasowej lub zakup jednej z [Postawić](https://purchase.aspose.com/buy). Postępuj zgodnie z ich wytycznymi, aby skonfigurować licencję w środowisku swojego projektu.

### Podstawowa inicjalizacja

Po zainstalowaniu zainicjuj `Presentation` klasa, aby rozpocząć tworzenie slajdów:
```csharp
using Aspose.Slides;

// Zainicjuj instancję klasy Prezentacja
tPresentation presentation = new Presentation();
```

Teraz zajmiemy się implementacją funkcji tworzenia i dostosowywania wykresów za pomocą Aspose.Slides dla .NET.

## Przewodnik wdrażania

### Utwórz wykres kolumnowy

Naszym celem jest stworzenie wykresu kolumnowego i dostosowanie go poprzez wyświetlanie procentów jako etykiet danych. Oto jak to zrobić:

#### Zainicjuj prezentację

Zacznij od utworzenia instancji `Presentation`:
```csharp
using Aspose.Slides;

// Zainicjuj instancję klasy Prezentacja
tPresentation presentation = new Presentation();
ISlide slide = presentation.Slides[0];
```

#### Dodaj wykres do slajdu

Dodaj wykres kolumnowy do pierwszego slajdu o określonych współrzędnych i wymiarach:
```csharp
IChart chart = slide.Shapes.AddChart(ChartType.StackedColumn, 20, 20, 400, 400);
```
Ta linia tworzy `StackedColumn` wykres na pozycji (20, 20) o szerokości i wysokości 400.

#### Oblicz wartości całkowite do obliczenia procentowego

Aby wyświetlić procenty, oblicz całkowitą wartość dla każdej kategorii we wszystkich seriach:
```csharp
IChartSeries series;
double[] total_for_Cat = new double[chart.ChartData.Categories.Count];

for (int k = 0; k < chart.ChartData.Categories.Count; k++)
{
    IChartCategory cat = chart.ChartData.Categories[k];
    // Podsumuj wartości wszystkich serii dla każdej kategorii
    for (int i = 0; i < chart.ChartData.Series.Count; i++)
    {
        total_for_Cat[k] += Convert.ToDouble(chart.ChartData.Series[i].DataPoints[k].Value.Data);
    }
}
```

#### Dostosuj etykiety danych, aby wyświetlać wartości procentowe

Następnie przejrzyj każdą serię i dostosuj etykiety danych:
```csharp
for (int x = 0; x < chart.ChartData.Series.Count; x++)
{
    series = chart.ChartData.Series[x];
    series.Labels.DefaultDataLabelFormat.ShowLegendKey = false;

    for (int j = 0; j < series.DataPoints.Count; j++)
    {
        IDataLabel lbl = series.DataPoints[j].Label;
        
        // Oblicz procent
        double dataPontPercent = (Convert.ToDouble(series.DataPoints[j].Value.Data) / total_for_Cat[j]) * 100;
        IPortion port = new Portion();
        port.Text = String.Format("{0:F2} %", dataPontPercent);
        port.PortionFormat.FontHeight = 8f;

        lbl.TextFrameForOverriding.Text = ""; // Wyczyść tekst, aby uniknąć nakładania się
        IParagraph para = lbl.TextFrameForOverriding.Paragraphs[0];
        para.Portions.Add(port);

        // Skonfiguruj format etykiety, aby ukryć domyślne etykiety danych
        lbl.DataLabelFormat.ShowSeriesName = false;
        lbl.DataLabelFormat.ShowPercentage = false; 
        lbl.DataLabelFormat.ShowLegendKey = false;
        lbl.DataLabelFormat.ShowCategoryName = false;
        lbl.DataLabelFormat.ShowBubbleSize = false;
    }
}
```

Ta sekcja oblicza wartość procentową dla każdego punktu danych i ustawia go jako etykietę niestandardową, zapewniając, że nie będzie się ona pokrywać z etykietami domyślnymi.

#### Zapisz prezentację

Na koniec zapisz prezentację, aby zobaczyć wynik:
```csharp
string outputDir = "YOUR_OUTPUT_DIRECTORY";
presentation.Save(outputDir + "/DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
```

## Zastosowania praktyczne

Wyświetlanie procentów na wykresach może być szczególnie przydatne w następujących sytuacjach:
1. **Sprawozdawczość finansowa:** Pokaż rozkłady portfela lub zwroty z inwestycji jako procenty.
2. **Analiza sprzedaży:** Przedstaw dane dotyczące udziału w rynku w postaci procentowej, aby pokazać wyniki w poszczególnych regionach.
3. **Wyniki ankiety:** Wyświetlaj odpowiedzi z ankiety jako procenty, aby ułatwić wizualne porównanie.
4. **Zarządzanie projektami:** Użyj wykresów kołowych z procentami, aby zilustrować alokację zasobów.
5. **Edukacja:** Wyjaśnij pojęcia statystyczne, korzystając z czytelnych wizualizacji opartych na procentach.

Zintegrowanie tych dostosowanych wykresów z systemami typu CRM lub ERP może udoskonalić pulpity nawigacyjne i raporty, wspomagając proces podejmowania decyzji.

## Rozważania dotyczące wydajności

Podczas pracy z Aspose.Slides dla .NET, zwłaszcza w przypadku dużych zestawów danych:
- **Zarządzanie pamięcią:** Usuń obiekty prezentacji prawidłowo, aby zwolnić pamięć. Użyj `using` oświadczenia, w stosownych przypadkach.
- **Efektywne przetwarzanie danych:** W miarę możliwości wykonuj obliczenia poza pętlami, aby zmniejszyć obciążenie obliczeniowe.
- **Równoważenie obciążenia:** W przypadku aplikacji internetowych należy upewnić się, że zasoby serwera są odpowiednio przydzielone do obsługi równoczesnych żądań generowania wykresów.

## Wniosek

W tym samouczku omówiono tworzenie i dostosowywanie wykresów za pomocą Aspose.Slides dla .NET, wyświetlając wartości procentowe jako etykiety. Opanowanie tych technik pozwala wzbogacić prezentacje o szczegółowe i atrakcyjne wizualnie reprezentacje danych.

W kolejnym kroku zapoznaj się z innymi typami wykresów i opcjami dostosowywania dostępnymi w Aspose.Slides. Eksperymentuj z różnymi zestawami danych, aby przekształcić je w potężne wizualizacje, które jasno przekazują spostrzeżenia.

## Sekcja FAQ

**P1: Jak radzić sobie z dużymi zbiorami danych podczas tworzenia wykresów w Aspose.Slides dla platformy .NET?**
A1: W przypadku dużych zestawów danych optymalizuj obliczenia i stosuj wydajne techniki zarządzania pamięcią. Podziel zadania przetwarzania, aby uniknąć przeciążenia pamięci.

**P2: Czy mogę używać Aspose.Slides for .NET w aplikacji internetowej?**
A2: Tak, można go zintegrować z aplikacjami ASP.NET. Zapewnij odpowiednią alokację zasobów serwera dla optymalnej wydajności.

**P3: Czy można eksportować wykresy utworzone w Aspose.Slides do innych formatów?**
A3: Oczywiście! Możesz eksportować prezentacje zawierające Twoje spersonalizowane wykresy do różnych formatów, takich jak pliki PDF i obrazy, korzystając z możliwości biblioteki.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}