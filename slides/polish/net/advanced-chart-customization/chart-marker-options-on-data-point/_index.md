---
title: Korzystanie z opcji znaczników wykresu w punkcie danych w Aspose.Slides .NET
linktitle: Opcje znaczników wykresu w punkcie danych
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak ulepszyć wykresy programu PowerPoint za pomocą Aspose.Slides dla .NET. Dostosuj znaczniki punktów danych za pomocą obrazów. Twórz angażujące prezentacje.
type: docs
weight: 11
url: /pl/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

Podczas pracy z prezentacjami i wizualizacją danych Aspose.Slides dla .NET oferuje szeroką gamę zaawansowanych funkcji do tworzenia, dostosowywania i manipulowania wykresami. W tym samouczku omówimy, jak używać opcji znaczników wykresu na punktach danych w celu ulepszenia prezentacji wykresów. Ten przewodnik krok po kroku przeprowadzi Cię przez proces, począwszy od wymagań wstępnych i importowania przestrzeni nazw, aż po podzielenie każdego przykładu na wiele kroków.

## Warunki wstępne

Zanim zaczniemy używać opcji znaczników wykresu w punktach danych, upewnij się, że spełnione są następujące wymagania wstępne:

-  Aspose.Slides dla .NET: Upewnij się, że masz zainstalowany Aspose.Slides dla .NET. Można go pobrać z[strona internetowa](https://releases.aspose.com/slides/net/).

- Przykładowa prezentacja: w tym samouczku użyjemy przykładowej prezentacji o nazwie „Test.pptx”. Powinieneś mieć tę prezentację w swoim katalogu dokumentów.

Teraz zacznijmy od zaimportowania niezbędnych przestrzeni nazw.

## Importuj przestrzenie nazw

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Zaimportowaliśmy wymagane przestrzenie nazw i zainicjowaliśmy naszą prezentację. Przejdźmy teraz do korzystania z opcji znaczników wykresu na punktach danych.

## Krok 1: Tworzenie domyślnego wykresu

```csharp

// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Tworzenie domyślnego wykresu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Tworzymy domyślny wykres typu „LineWithMarkers” na slajdzie w określonym miejscu i rozmiarze.

## Krok 2: Pobieranie domyślnego indeksu arkusza danych wykresu

```csharp
// Pobieranie domyślnego indeksu arkusza danych wykresu
int defaultWorksheetIndex = 0;
```

Otrzymujemy tutaj indeks domyślnego arkusza danych wykresu.

## Krok 3: Pobieranie arkusza danych wykresu

```csharp
// Pobieranie arkusza danych wykresu
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Pobieramy skoroszyt danych wykresu, aby pracować z danymi wykresu.

## Krok 4: Modyfikowanie serii wykresów

```csharp
// Usuń serię demonstracyjną
chart.ChartData.Series.Clear();

// Dodaj nową serię
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

Na tym etapie usuwamy wszystkie istniejące serie demonstracyjne i dodajemy do wykresu nową serię o nazwie „Seria 1”.

## Krok 5: Ustawianie wypełnienia obrazem dla punktów danych

```csharp
// Ustaw obraz dla znaczników
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Weź pierwszą serię wykresów
IChartSeries series = chart.ChartData.Series[0];

// Dodaj nowe punkty danych z wypełnieniem obrazem
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

Ustawiamy znaczniki obrazu dla punktów danych, co pozwala dostosować sposób wyświetlania każdego punktu danych na wykresie.

## Krok 6: Zmiana rozmiaru znacznika serii wykresów

```csharp
// Zmiana rozmiaru znacznika serii wykresów
series.Marker.Size = 15;
```

Tutaj dostosowujemy rozmiar znacznika serii wykresu, aby był atrakcyjny wizualnie.

## Krok 7: Zapisywanie prezentacji

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Na koniec zapisujemy prezentację z nowymi ustawieniami wykresu.

## Wniosek

Aspose.Slides dla .NET umożliwia tworzenie wspaniałych prezentacji wykresów z różnymi opcjami dostosowywania. W tym samouczku skupiliśmy się na użyciu opcji znaczników wykresu na punktach danych w celu ulepszenia wizualnej reprezentacji danych. Dzięki Aspose.Slides dla .NET możesz przenieść swoje prezentacje na wyższy poziom, czyniąc je bardziej wciągającymi i pouczającymi.

Jeśli masz jakieś pytania lub potrzebujesz pomocy z Aspose.Slides dla .NET, zapraszamy do odwiedzenia strony[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/) lub skontaktuj się z[społeczność Aspose](https://forum.aspose.com/) dla wsparcia.

## Często zadawane pytania (FAQ)

### Czy mogę używać niestandardowych obrazów jako znaczników punktów danych w Aspose.Slides dla .NET?
Tak, możesz używać niestandardowych obrazów jako znaczników punktów danych w Aspose.Slides dla .NET, jak pokazano w tym samouczku.

### Jak mogę zmienić typ wykresu w Aspose.Slides dla .NET?
 Typ wykresu można zmienić, określając inny`ChartType` podczas tworzenia wykresu, np. „Słupkowy”, „Kołowy” lub „Obszar”.

### Czy Aspose.Slides for .NET jest kompatybilny z najnowszymi wersjami programu PowerPoint?
Aspose.Slides dla .NET jest zaprojektowany do pracy z różnymi formatami programu PowerPoint i jest regularnie aktualizowany, aby zachować kompatybilność z najnowszymi wersjami programu PowerPoint.

### Gdzie mogę znaleźć więcej samouczków i zasobów dotyczących Aspose.Slides dla .NET?
 Dodatkowe samouczki i zasoby można znaleźć w witrynie[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/net/).

### Czy dostępna jest wersja próbna Aspose.Slides dla .NET?
 Tak, możesz wypróbować Aspose.Slides dla .NET, pobierając bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).