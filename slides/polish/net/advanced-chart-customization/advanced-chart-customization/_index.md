---
"description": "Poznaj zaawansowaną personalizację wykresów w Aspose.Slides dla .NET. Twórz atrakcyjne wizualnie wykresy dzięki instrukcjom krok po kroku."
"linktitle": "Zaawansowana personalizacja wykresów w Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Zaawansowana personalizacja wykresów w Aspose.Slides"
"url": "/pl/net/advanced-chart-customization/advanced-chart-customization/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zaawansowana personalizacja wykresów w Aspose.Slides


Tworzenie atrakcyjnych wizualnie i informacyjnych wykresów jest istotną częścią prezentacji danych w wielu aplikacjach. Aspose.Slides for .NET zapewnia solidne narzędzia do dostosowywania wykresów, umożliwiając dostrojenie każdego aspektu wykresów. W tym samouczku przyjrzymy się zaawansowanym technikom dostosowywania wykresów przy użyciu Aspose.Slides for .NET.

## Wymagania wstępne

Zanim przejdziesz do zaawansowanych funkcji dostosowywania wykresów za pomocą Aspose.Slides dla platformy .NET, upewnij się, że spełnione są następujące wymagania wstępne:

1. Aspose.Slides dla biblioteki .NET: Musisz mieć zainstalowaną bibliotekę Aspose.Slides i poprawnie ją skonfigurować w swoim projekcie .NET. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/net/).

2. Środowisko programistyczne .NET: Należy mieć skonfigurowane środowisko programistyczne .NET, obejmujące program Visual Studio lub inne wybrane przez siebie środowisko IDE.

3. Podstawowa znajomość języka C#: Znajomość języka programowania C# będzie pomocna, ponieważ będziemy pisać kod C# do pracy z Aspose.Slides.

Teraz podzielimy proces zaawansowanego dostosowywania wykresu na kilka kroków, które poprowadzą Cię przez cały proces.

## Krok 1: Utwórz prezentację

Najpierw utwórz nową prezentację za pomocą Aspose.Slides.

```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";

// Utwórz katalog, jeśli jeszcze go nie ma.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Tworzenie prezentacji
Presentation pres = new Presentation();
```

W tym kroku inicjujemy nową prezentację, która będzie zawierać nasz wykres.

## Krok 2: Dostęp do pierwszego slajdu

Następnie przejdź do pierwszego slajdu prezentacji, do którego chcesz dodać wykres.

```csharp
// Dostęp do pierwszego slajdu
ISlide slide = pres.Slides[0];
```

Ten fragment kodu umożliwia pracę nad pierwszym slajdem prezentacji.

## Krok 3: Dodawanie przykładowego wykresu

Teraz dodajmy przykładowy wykres do slajdu. W tym przykładzie utworzymy wykres liniowy ze znacznikami.

```csharp
// Dodawanie przykładowego wykresu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Tutaj określamy typ wykresu (LineWithMarkers) oraz jego pozycję i wymiary na slajdzie.

## Krok 4: Ustawianie tytułu wykresu

Nadajmy wykresowi tytuł, aby nadać mu kontekst.

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

Teraz dostosujemy główne linie siatki dla osi wartości.

```csharp
// Ustawianie formatu głównych linii siatki dla osi wartości
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Ten krok umożliwia konfigurację wyglądu głównych linii siatki na osi wartości.

## Krok 6: Dostosuj linie siatki pomocniczej

W podobny sposób możemy dostosować pomocnicze linie siatki dla osi wartości.

```csharp
// Ustawianie formatu linii siatki pomocniczej dla osi wartości
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Ten kod dostosowuje wygląd mniejszych linii siatki na osi wartości.

## Krok 7: Zdefiniuj format liczbowy osi wartości

Dostosuj format liczbowy dla osi wartości.

```csharp
// Ustawianie formatu liczby osi wartości
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Ten krok umożliwia sformatowanie liczb wyświetlanych na osi wartości.

## Krok 8: Ustaw maksymalne i minimalne wartości wykresu

Zdefiniuj wartości maksymalne i minimalne dla wykresu.

```csharp
// Ustawianie maksymalnych i minimalnych wartości wykresu
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

Tutaj możesz określić zakres wartości, jakie ma wyświetlać oś wykresu.

## Krok 9: Dostosuj właściwości tekstu osi wartości

Można również dostosować właściwości tekstowe osi wartości.

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

Jeśli wykres wymaga tytułu dla osi wartości, możesz go dodać w tym kroku.

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

tym kroku możesz ustawić tytuł osi wartości.

## Krok 11: Dostosuj główne linie siatki dla osi kategorii

Teraz skupmy się na głównych liniach siatki dla osi kategorii.

```csharp
// Ustawianie formatu głównych linii siatki dla osi kategorii
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Ten kod konfiguruje wygląd głównych linii siatki na osi kategorii.

## Krok 12: Dostosuj linie siatki pomocniczej dla osi kategorii

Podobnie jak w przypadku osi wartości, możesz dostosować pomocnicze linie siatki dla osi kategorii.

```csharp
// Ustawianie formatu linii siatki pomocniczej dla osi kategorii
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

Jeśli zajdzie taka potrzeba, możesz również dodać tytuł do osi kategorii.

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

tym kroku możesz ustawić tytuł dla osi kategorii.

## Krok 15: Dodatkowe dostosowania

Możesz eksplorować dalsze dostosowania, takie jak legendy, tylna ściana wykresu, podłoga i kolory obszaru wykresu. Te dostosowania pozwalają na zwiększenie atrakcyjności wizualnej wykresu.

```csharp
// Dodatkowe dostosowania (opcjonalne)

// Ustawianie właściwości tekstu legend
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Ustaw legendy wykresu bez nakładania się wykresu
chart.Legend.Overlay = true;

// Wykreślanie pierwszej serii na osi wartości drugorzędnych (jeśli to konieczne)
// Wykres.DaneWykresu.Seria[0].WykresNaDrugiejOsi = prawda;

// Ustawianie koloru tylnej ściany wykresu
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Ustawianie koloru podłogi wykresu
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Ustawianie koloru obszaru wykresu
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Zapisz prezentację
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Te dodatkowe dostosowania są opcjonalne i można je zastosować na podstawie konkretnych wymagań dotyczących projektu wykresu.

## Wniosek

tym przewodniku krok po kroku omówiliśmy zaawansowaną personalizację wykresów przy użyciu Aspose.Slides dla .NET. Nauczyłeś się, jak utworzyć prezentację, dodać wykres i dostroić jego wygląd, w tym linie siatki, etykiety osi i inne elementy wizualne. Dzięki potężnym opcjom personalizacji oferowanym przez Aspose.Slides możesz tworzyć wykresy, które skutecznie przekazują dane i angażują odbiorców.

Jeśli masz jakiekolwiek pytania lub napotkasz jakiekolwiek trudności podczas pracy z Aspose.Slides dla .NET, możesz zapoznać się z dokumentacją [Tutaj](https://reference.aspose.com/slides/net/) lub poszukaj pomocy w Aspose.Slides [forum](https://forum.aspose.com/).

## Często zadawane pytania

### Jakie wersje platformy .NET są obsługiwane przez Aspose.Slides dla platformy .NET?
Aspose.Slides for .NET obsługuje różne wersje .NET, w tym .NET Framework i .NET Core. Pełną listę obsługiwanych wersji można znaleźć w dokumentacji.

### Czy mogę tworzyć wykresy ze źródeł danych, takich jak pliki Excel, korzystając z Aspose.Slides dla .NET?
Tak, Aspose.Slides dla .NET umożliwia tworzenie wykresów z zewnętrznych źródeł danych, takich jak arkusze kalkulacyjne Excel. Szczegółowe przykłady można znaleźć w dokumentacji.

### Jak mogę dodać niestandardowe etykiety danych do serii wykresów?
Aby dodać niestandardowe etykiety danych do serii wykresów, możesz uzyskać dostęp do `DataLabels` właściwość serii i dostosuj etykiety według potrzeb. Zapoznaj się z dokumentacją, aby uzyskać przykłady kodu.

### Czy można wyeksportować wykres do innych formatów plików, np. PDF lub formatów graficznych?
Tak, Aspose.Slides dla .NET oferuje opcje eksportowania prezentacji z wykresami do różnych formatów, w tym PDF i obrazów. Możesz użyć biblioteki, aby zapisać swoją pracę w pożądanym formacie wyjściowym.

### Gdzie mogę znaleźć więcej samouczków i przykładów dla Aspose.Slides dla .NET?
Na stronie Aspose.Slides znajdziesz mnóstwo samouczków, przykładów kodu i dokumentacji [strona internetowa](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}