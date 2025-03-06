---
title: Zaawansowane dostosowywanie wykresów w Aspose.Slides
linktitle: Zaawansowane dostosowywanie wykresów w Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Poznaj zaawansowane dostosowywanie wykresów w Aspose.Slides dla .NET. Twórz atrakcyjne wizualnie wykresy, korzystając ze wskazówek krok po kroku.
weight: 10
url: /pl/net/advanced-chart-customization/advanced-chart-customization/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


Tworzenie atrakcyjnych wizualnie i informacyjnych wykresów jest istotną częścią prezentacji danych w wielu aplikacjach. Aspose.Slides dla .NET zapewnia solidne narzędzia do dostosowywania wykresów, umożliwiając dostrojenie każdego aspektu wykresów. W tym samouczku omówimy zaawansowane techniki dostosowywania wykresów przy użyciu Aspose.Slides dla .NET.

## Warunki wstępne

Zanim zagłębisz się w zaawansowane dostosowywanie wykresów za pomocą Aspose.Slides dla .NET, upewnij się, że spełniasz następujące wymagania wstępne:

1. Biblioteka Aspose.Slides dla .NET: Musisz mieć zainstalowaną i poprawnie skonfigurowaną bibliotekę Aspose.Slides w swoim projekcie .NET. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/net/).

2. Środowisko programistyczne .NET: Należy mieć skonfigurowane środowisko programistyczne .NET, w tym Visual Studio lub dowolne inne wybrane IDE.

3. Podstawowa znajomość C#: Znajomość języka programowania C# będzie pomocna, ponieważ będziemy pisać kod C# do pracy z Aspose.Slides.

Podzielmy teraz zaawansowane dostosowywanie wykresu na wiele kroków, które poprowadzą Cię przez cały proces.

## Krok 1: Utwórz prezentację

Najpierw utwórz nową prezentację za pomocą Aspose.Slides.

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

Na tym etapie inicjujemy nową prezentację, która będzie zawierać nasz wykres.

## Krok 2: Uzyskaj dostęp do pierwszego slajdu

Następnie przejdź do pierwszego slajdu prezentacji, do którego chcesz dodać wykres.

```csharp
// Dostęp do pierwszego slajdu
ISlide slide = pres.Slides[0];
```

Ten fragment kodu umożliwia pracę z pierwszym slajdem w prezentacji.

## Krok 3: Dodawanie przykładowego wykresu

Dodajmy teraz do slajdu przykładowy wykres. W tym przykładzie utworzymy wykres liniowy ze znacznikami.

```csharp
// Dodanie przykładowego wykresu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Tutaj określamy rodzaj wykresu (LineWithMarkers) oraz jego położenie i wymiary na slajdzie.

## Krok 4: Ustawianie tytułu wykresu

Ustawmy tytuł wykresu, aby zapewnić kontekst.

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

Ten kod ustawia tytuł wykresu, określając jego tekst, wygląd i styl czcionki.

## Krok 5: Dostosuj główne linie siatki

Teraz dostosujmy główne linie siatki dla osi wartości.

```csharp
// Ustawianie formatu głównych linii siatki dla osi wartości
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Ten krok konfiguruje wygląd głównych linii siatki na osi wartości.

## Krok 6: Dostosuj mniejsze linie siatki

Podobnie możemy dostosować mniejsze linie siatki dla osi wartości.

```csharp
// Ustawianie formatu mniejszych linii siatki dla osi wartości
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Ten kod dostosowuje wygląd mniejszych linii siatki na osi wartości.

## Krok 7: Zdefiniuj format numeru osi wartości

Dostosuj format liczb dla osi wartości.

```csharp
// Ustawianie formatu numeru osi wartości
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Ten krok umożliwia sformatowanie liczb wyświetlanych na osi wartości.

## Krok 8: Ustaw wartości maksymalne i minimalne wykresu

Zdefiniuj wartości maksymalne i minimalne dla wykresu.

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

Tutaj określasz zakres wartości, jakie ma wyświetlać oś wykresu.

## Krok 9: Dostosuj właściwości tekstu osi wartości

Można także dostosować właściwości tekstu osi wartości.

```csharp
// Ustawianie właściwości tekstu osi wartości
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Ten kod umożliwia dostosowanie stylu czcionki i wyglądu etykiet osi wartości.

## Krok 10: Dodaj tytuł osi wartości

Jeśli wykres wymaga tytułu osi wartości, możesz go dodać w tym kroku.

```csharp
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

W tym kroku możesz ustawić tytuł osi wartości.

## Krok 11: Dostosuj główne linie siatki dla osi kategorii

Teraz skupmy się na głównych liniach siatki osi kategorii.

```csharp
// Ustawianie formatu głównych linii siatki dla osi kategorii
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Ten kod konfiguruje wygląd głównych linii siatki na osi kategorii.

## Krok 12: Dostosuj mniejsze linie siatki dla osi kategorii

Podobnie jak w przypadku osi wartości, można dostosować mniejsze linie siatki dla osi kategorii.

```csharp
// Ustawianie formatu mniejszych linii siatki dla osi kategorii
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Tutaj możesz dostosować wygląd mniejszych linii siatki na osi kategorii.

## Krok 13: Dostosuj właściwości tekstu osi kategorii

Dostosuj właściwości tekstu etykiet osi kategorii.

```csharp
// Ustawianie właściwości tekstu osi kategorii
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Ten kod umożliwia dostosowanie stylu czcionki i wyglądu etykiet osi kategorii.

## Krok 14: Dodaj tytuł osi kategorii

W razie potrzeby możesz także dodać tytuł do osi kategorii.

```csharp
// Ustawianie tytułu kategorii
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

W tym kroku możesz ustawić tytuł osi kategorii.

## Krok 15: Dodatkowe dostosowania

Możesz eksplorować dalsze dostosowania, takie jak legendy, tylna ściana wykresu, podłoga i kolory obszaru wykresu. Te dostosowania pozwalają poprawić atrakcyjność wizualną wykresu.

```csharp
// Dodatkowe dostosowania (opcjonalnie)

// Ustawianie właściwości tekstu legendy
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Ustaw wyświetlanie legend wykresów bez nakładania się wykresów
chart.Legend.Overlay = true;

// Wykreślanie pierwszej serii na dodatkowej osi wartości (w razie potrzeby)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// Ustawianie koloru tylnej ściany wykresu
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Ustawianie koloru podłogi wykresu
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Ustawianie koloru obszaru działki
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Zapisz prezentację
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Te dodatkowe dostosowania są opcjonalne i można je zastosować w zależności od konkretnych wymagań dotyczących projektu wykresu.

## Wniosek

tym przewodniku krok po kroku omówiliśmy zaawansowane dostosowywanie wykresów za pomocą Aspose.Slides dla .NET. Nauczyłeś się, jak tworzyć prezentację, dodawać wykres i dostosowywać jego wygląd, w tym linie siatki, etykiety osi i inne elementy wizualne. Dzięki potężnym opcjom dostosowywania udostępnianym przez Aspose.Slides możesz tworzyć wykresy, które skutecznie przekazują dane i angażują odbiorców.

 Jeśli masz jakieś pytania lub napotkasz jakieś wyzwania podczas pracy z Aspose.Slides dla .NET, nie wahaj się zapoznać z dokumentacją[Tutaj](https://reference.aspose.com/slides/net/) lub poproś o pomoc w Aspose.Slides[forum](https://forum.aspose.com/).

## Często zadawane pytania

### Jakie wersje .NET są obsługiwane przez Aspose.Slides dla .NET?
Aspose.Slides dla .NET obsługuje różne wersje .NET, w tym .NET Framework i .NET Core. Pełną listę obsługiwanych wersji można znaleźć w dokumentacji.

### Czy mogę tworzyć wykresy ze źródeł danych, takich jak pliki Excel, używając Aspose.Slides dla .NET?
Tak, Aspose.Slides dla .NET umożliwia tworzenie wykresów z zewnętrznych źródeł danych, takich jak arkusze kalkulacyjne Excel. Szczegółowe przykłady można znaleźć w dokumentacji.

### Jak mogę dodać niestandardowe etykiety danych do serii wykresów?
 Aby dodać niestandardowe etykiety danych do serii wykresów, możesz uzyskać dostęp do:`DataLabels` właściwość serii i dostosuj etykiety według potrzeb. Przykłady kodu i przykłady można znaleźć w dokumentacji.

### Czy można wyeksportować wykres do różnych formatów plików, takich jak PDF lub formaty graficzne?
Tak, Aspose.Slides dla .NET zapewnia opcje eksportu prezentacji z wykresami do różnych formatów, w tym formatów PDF i obrazów. Możesz użyć biblioteki, aby zapisać swoją pracę w żądanym formacie wyjściowym.

### Gdzie mogę znaleźć więcej samouczków i przykładów Aspose.Slides dla .NET?
 W witrynie Aspose.Slides można znaleźć mnóstwo samouczków, przykładów kodu i dokumentacji[strona internetowa](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
