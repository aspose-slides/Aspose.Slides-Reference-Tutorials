---
title: Tworzenie pięknych wykresów za pomocą Aspose.Slides dla platformy .NET
linktitle: Elementy wykresu i formatowanie
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak tworzyć wspaniałe wykresy za pomocą Aspose.Slides dla .NET. Ulepsz swoją grę w wizualizację danych, korzystając z naszego przewodnika krok po kroku.
weight: 13
url: /pl/net/advanced-chart-customization/chart-entities/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie pięknych wykresów za pomocą Aspose.Slides dla platformy .NET


W dzisiejszym świecie opartym na danych skuteczna wizualizacja danych jest kluczem do przekazywania informacji odbiorcom. Aspose.Slides dla .NET to potężna biblioteka, która umożliwia tworzenie wspaniałych prezentacji i slajdów, w tym przyciągających wzrok wykresów. W tym samouczku przeprowadzimy Cię przez proces tworzenia pięknych wykresów za pomocą Aspose.Slides dla .NET. Podzielimy każdy przykład na wiele kroków, aby pomóc Ci zrozumieć i wdrożyć elementy wykresu oraz formatowanie. Więc zacznijmy!

## Warunki wstępne

Zanim zagłębimy się w tworzenie pięknych wykresów za pomocą Aspose.Slides dla .NET, musisz upewnić się, że spełniasz następujące wymagania wstępne:

1.  Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides dla .NET. Można go pobrać z[strona internetowa](https://releases.aspose.com/slides/net/).

2. Środowisko programistyczne: Powinieneś mieć działające środowisko programistyczne z Visual Studio lub dowolnym innym IDE obsługującym programowanie .NET.

3. Podstawowa znajomość języka C#: Znajomość programowania w języku C# jest niezbędna w tym samouczku.

Teraz, gdy mamy już posortowane wymagania wstępne, przejdźmy do tworzenia pięknych wykresów za pomocą Aspose.Slides dla .NET.

## Importuj przestrzenie nazw

Najpierw musisz zaimportować niezbędne przestrzenie nazw do pracy z Aspose.Slides dla .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Krok 1: Utwórz prezentację

Zaczynamy od stworzenia nowej prezentacji, z którą będziemy pracować. Ta prezentacja posłuży jako płótno dla naszego wykresu.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";

// Utwórz katalog, jeśli jeszcze nie istnieje.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Prezentacja instancyjna
Presentation pres = new Presentation();
```

## Krok 2: Uzyskaj dostęp do pierwszego slajdu

Przejdźmy do pierwszego slajdu prezentacji, na którym umieścimy nasz wykres.

```csharp
// Dostęp do pierwszego slajdu
ISlide slide = pres.Slides[0];
```

## Krok 3: Dodaj przykładowy wykres

Teraz dodamy przykładowy wykres do naszego slajdu. W tym przykładzie utworzymy wykres liniowy ze znacznikami.

```csharp
// Dodanie przykładowego wykresu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Krok 4: Ustaw tytuł wykresu

Nadajemy naszemu wykresowi tytuł, dzięki czemu będzie on bardziej informacyjny i atrakcyjny wizualnie.

```csharp
// Ustawianie tytułu wykresu
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Krok 5: Dostosuj linie siatki osi pionowej

tym kroku dostosujemy linie siatki osi pionowej, aby nasz wykres był bardziej atrakcyjny wizualnie.

```csharp
// Ustawianie formatu głównych linii siatki dla osi wartości
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Ustawianie formatu mniejszych linii siatki dla osi wartości
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Ustawianie formatu numeru osi wartości
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Krok 6: Zdefiniuj zakres osi pionowej

W tym kroku ustawimy wartości maksymalne, minimalne i jednostkowe dla osi pionowej.

```csharp
// Tabela ustawień wartości maksymalnych i minimalnych
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Krok 7: Dostosuj tekst na osi pionowej

Dostosujemy teraz wygląd tekstu na osi pionowej.

```csharp
// Ustawianie właściwości tekstu osi wartości
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Ustawianie tytułu osi wartości
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Krok 8: Dostosuj linie siatki osi poziomej

Teraz dostosujmy linie siatki dla osi poziomej.

```csharp
// Ustawianie formatu głównych linii siatki dla osi kategorii
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Ustawianie formatu mniejszych linii siatki dla osi kategorii
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Ustawianie właściwości tekstu osi kategorii
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Krok 9: Dostosuj etykiety osi poziomej

W tym kroku dostosujemy położenie i obrót etykiet osi poziomej.

```csharp
// Ustawianie pozycji etykiety osi kategorii
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Ustawianie kąta obrotu etykiety osi kategorii
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Krok 10: Dostosuj legendy

Poprawmy legendy w naszym wykresie, aby zapewnić lepszą czytelność.

```csharp
// Ustawianie właściwości tekstu legendy
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Ustaw wyświetlanie legend wykresów bez nakładania się wykresów
chart.Legend.Overlay = true;
```

## Krok 11: Dostosuj tło wykresu

Dostosujemy kolory tła wykresu, tylnej ściany i podłogi.

```csharp
// Ustawianie koloru tylnej ściany wykresu
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Ustawianie koloru obszaru działki
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Krok 12: Zapisz prezentację

Na koniec zapiszmy naszą prezentację ze sformatowanym wykresem.

```csharp
// Zapisz prezentację
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Wniosek

Tworzenie pięknych i pouczających wykresów w prezentacjach jest teraz łatwiejsze niż kiedykolwiek dzięki Aspose.Slides dla .NET. W tym samouczku omówiliśmy podstawowe kroki umożliwiające dostosowanie różnych aspektów wykresu, dzięki czemu będzie on atrakcyjny wizualnie i zawierał wiele informacji. Dzięki tym technikom możesz tworzyć wspaniałe wykresy, które skutecznie przekazują dane odbiorcom.

Zacznij eksperymentować z Aspose.Slides dla .NET i przenieś swoją wizualizację danych na wyższy poziom!

## Często Zadawane Pytania

### 1. Co to jest Aspose.Slides dla .NET?

Aspose.Slides dla .NET to potężna biblioteka, która pozwala programistom .NET tworzyć, manipulować i konwertować prezentacje Microsoft PowerPoint. Zapewnia szeroką gamę funkcji do pracy ze slajdami, kształtami, wykresami i nie tylko.

### 2. Skąd mogę pobrać Aspose.Slides dla .NET?

 Możesz pobrać Aspose.Slides dla .NET ze strony internetowej[Tutaj](https://releases.aspose.com/slides/net/).

### 3. Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?

 Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Slides dla .NET od[Tutaj](https://releases.aspose.com/).

### 4. Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla .NET?

 Jeśli potrzebujesz licencji tymczasowej, możesz ją uzyskać od[ten link](https://purchase.aspose.com/temporary-license/).

### 5. Czy istnieje forum społeczności lub wsparcia dla Aspose.Slides dla .NET?

 Tak, możesz znaleźć społeczność i forum wsparcia Aspose.Slides[Tutaj](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
