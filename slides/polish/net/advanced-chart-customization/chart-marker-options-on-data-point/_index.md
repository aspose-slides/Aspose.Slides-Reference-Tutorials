---
"description": "Dowiedz się, jak ulepszyć wykresy PowerPoint za pomocą Aspose.Slides dla .NET. Dostosuj znaczniki punktów danych za pomocą obrazów. Twórz angażujące prezentacje."
"linktitle": "Opcje znaczników wykresu w punkcie danych"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Korzystanie z opcji znacznika wykresu w punkcie danych w Aspose.Slides .NET"
"url": "/pl/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Korzystanie z opcji znacznika wykresu w punkcie danych w Aspose.Slides .NET


Podczas pracy z prezentacjami i wizualizacją danych Aspose.Slides for .NET oferuje szeroki zakres zaawansowanych funkcji do tworzenia, dostosowywania i manipulowania wykresami. W tym samouczku przyjrzymy się, jak używać opcji znaczników wykresu w punktach danych, aby ulepszyć prezentacje wykresów. Ten przewodnik krok po kroku przeprowadzi Cię przez proces, zaczynając od wymagań wstępnych i importowania przestrzeni nazw, aż po rozbicie każdego przykładu na wiele kroków.

## Wymagania wstępne

Zanim przejdziemy do korzystania z opcji znaczników wykresu w punktach danych, upewnij się, że spełnione są następujące wymagania wstępne:

- Aspose.Slides dla .NET: Upewnij się, że masz zainstalowany Aspose.Slides dla .NET. Możesz go pobrać ze strony [strona internetowa](https://releases.aspose.com/slides/net/).

- Przykładowa prezentacja: W tym samouczku użyjemy przykładowej prezentacji o nazwie „Test.pptx”. Powinieneś mieć tę prezentację w swoim katalogu dokumentów.

Teraz zacznijmy od zaimportowania niezbędnych przestrzeni nazw.

## Importuj przestrzenie nazw

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Zaimportowaliśmy wymagane przestrzenie nazw i zainicjowaliśmy naszą prezentację. Teraz przejdźmy do użycia opcji znaczników wykresu w punktach danych.

## Krok 1: Tworzenie domyślnego wykresu

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Tworzenie domyślnego wykresu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Tworzymy domyślny wykres typu „LineWithMarkers” na slajdzie w określonym miejscu i rozmiarze.

## Krok 2: Uzyskanie domyślnego indeksu arkusza danych wykresu

```csharp
// Pobieranie domyślnego indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
```

Tutaj pobieramy indeks domyślnego arkusza danych wykresu.

## Krok 3: Pobieranie arkusza danych wykresu

```csharp
// Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Pobieramy skoroszyt z danymi wykresu, aby pracować z danymi wykresu.

## Krok 4: Modyfikowanie serii wykresów

```csharp
// Usuń serię demonstracyjną
chart.ChartData.Series.Clear();

// Dodaj nową serię
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Na tym etapie usuniemy wszelkie istniejące serie demonstracyjne i dodamy do wykresu nową serię o nazwie „Seria 1”.

## Krok 5: Ustawianie wypełnienia obrazem dla punktów danych

```csharp
// Ustaw obrazek dla znaczników
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Weź pierwszą serię wykresów
IChartSeries series = chart.ChartData.Series[0];

// Dodaj nowe punkty danych z wypełnieniem obrazkowym
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Ustawiamy znaczniki graficzne dla punktów danych, co pozwala dostosować sposób wyświetlania każdego punktu danych na wykresie.

## Krok 6: Zmiana rozmiaru znacznika serii wykresu

```csharp
// Zmiana rozmiaru znacznika serii wykresu
series.Marker.Size = 15;
```

Tutaj dostosowujemy rozmiar znacznika serii wykresu, aby był bardziej atrakcyjny wizualnie.

## Krok 7: Zapisywanie prezentacji

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Na koniec zapisujemy prezentację z nowymi ustawieniami wykresu.

## Wniosek

Aspose.Slides for .NET umożliwia tworzenie oszałamiających prezentacji wykresów z różnymi opcjami dostosowywania. W tym samouczku skupiliśmy się na używaniu opcji znaczników wykresu w punktach danych, aby ulepszyć wizualną reprezentację danych. Dzięki Aspose.Slides for .NET możesz przenieść swoje prezentacje na wyższy poziom, czyniąc je bardziej angażującymi i pouczającymi.

Jeśli masz jakiekolwiek pytania lub potrzebujesz pomocy w zakresie Aspose.Slides dla .NET, odwiedź stronę [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/) lub skontaktuj się z [Społeczność Aspose](https://forum.aspose.com/) o wsparcie.

## Często zadawane pytania (FAQ)

### Czy mogę używać niestandardowych obrazów jako znaczników punktów danych w Aspose.Slides dla .NET?
Tak, możesz używać niestandardowych obrazów jako znaczników punktów danych w Aspose.Slides dla .NET, jak pokazano w tym samouczku.

### Jak mogę zmienić typ wykresu w Aspose.Slides dla .NET?
Możesz zmienić typ wykresu, określając inny `ChartType` podczas tworzenia wykresu, takiego jak „Słupkowy”, „Kołowy” lub „Obszarowy”.

### Czy Aspose.Slides dla .NET jest zgodny z najnowszymi wersjami programu PowerPoint?
Aspose.Slides for .NET został zaprojektowany do współpracy z różnymi formatami programu PowerPoint i jest regularnie aktualizowany w celu zachowania zgodności z najnowszymi wersjami programu PowerPoint.

### Gdzie mogę znaleźć więcej samouczków i zasobów dotyczących Aspose.Slides dla platformy .NET?
Możesz zapoznać się z dodatkowymi samouczkami i zasobami w [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/).

### Czy jest dostępna wersja próbna Aspose.Slides dla platformy .NET?
Tak, możesz wypróbować Aspose.Slides dla .NET, pobierając bezpłatną wersję próbną ze strony [Tutaj](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}