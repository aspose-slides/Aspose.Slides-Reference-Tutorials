---
title: Kolorowanie wykresów za pomocą Aspose.Slides dla .NET
linktitle: Dodaj kolor do punktów danych na wykresie
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak dodać kolor do punktów danych na wykresie za pomocą Aspose.Slides dla .NET. Wzbogać swoje prezentacje wizualnie i skutecznie zaangażuj odbiorców.
weight: 12
url: /pl/net/licensing-and-formatting/add-color-to-data-points/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


W tym przewodniku krok po kroku przeprowadzimy Cię przez proces dodawania koloru do punktów danych na wykresie za pomocą Aspose.Slides dla .NET. Aspose.Slides to potężna biblioteka do pracy z prezentacjami programu PowerPoint w aplikacjach .NET. Dodanie koloru do punktów danych na wykresie może sprawić, że prezentacje będą bardziej atrakcyjne wizualnie i łatwiejsze do zrozumienia.

## Warunki wstępne

Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:

1. Visual Studio: Musisz zainstalować Visual Studio na swoim komputerze.

2.  Aspose.Slides dla .NET: Pobierz i zainstaluj Aspose.Slides dla .NET z[link do pobrania](https://releases.aspose.com/slides/net/).

3. Podstawowe zrozumienie języka C#: Powinieneś posiadać podstawową wiedzę na temat programowania w języku C#.

4. Twój katalog dokumentów: Zastąp „Twój katalog dokumentów” w kodzie rzeczywistą ścieżką do katalogu dokumentów.

## Importowanie przestrzeni nazw

Zanim będziesz mógł pracować z Aspose.Slides dla .NET, musisz zaimportować niezbędne przestrzenie nazw. 

```csharp
﻿using Aspose.Slides.Charts;
using Aspose.Slides.Export;
using Aspose.Slides;
```


W tym przykładzie dodamy kolor do punktów danych na wykresie przy użyciu typu wykresu Sunburst.

```csharp
using (Presentation pres = new Presentation())
{
    // Ścieżka do katalogu dokumentów.
    string dataDir = "Your Document Directory";

    IChart chart = pres.Slides[0].Shapes.AddChart(ChartType.Sunburst, 100, 100, 450, 400);
    
    // Pozostała część kodu zostanie dodana w kolejnych krokach.
}
```

## Krok 1: Dostęp do punktów danych

Aby dodać kolor do określonych punktów danych na wykresie, musisz uzyskać dostęp do tych punktów danych. W tym przykładzie skupimy się na punkcie danych 3.

```csharp
IChartDataPointCollection dataPoints = chart.ChartData.Series[0].DataPoints;
dataPoints[3].DataPointLevels[0].Label.DataLabelFormat.ShowValue = true;
```

## Krok 2: Dostosowywanie etykiet danych

Teraz dostosujmy etykiety danych dla punktu danych 0. Ukryjemy nazwę kategorii i pokażemy nazwę serii.

```csharp
IDataLabel branch1Label = dataPoints[0].DataPointLevels[2].Label;
branch1Label.DataLabelFormat.ShowCategoryName = false;
branch1Label.DataLabelFormat.ShowSeriesName = true;
```

## Krok 3: Ustawianie formatu tekstu i koloru wypełnienia

Możemy dodatkowo poprawić wygląd etykiet danych, ustawiając format tekstu i kolor wypełnienia. W tym kroku ustawimy kolor tekstu na żółty dla punktu danych 0.

```csharp
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.FillType = FillType.Solid;
branch1Label.DataLabelFormat.TextFormat.PortionFormat.FillFormat.SolidFillColor.Color = Color.Yellow;
```

## Krok 4: Dostosowywanie koloru wypełnienia punktu danych

Teraz zmieńmy kolor wypełnienia punktu danych 9. Ustawimy go na określony kolor.

```csharp
IFormat steam4Format = dataPoints[9].Format;
steam4Format.Fill.FillType = FillType.Solid;
steam4Format.Fill.SolidFillColor.Color = Color.FromArgb(0, 176, 240, 255);
```

## Krok 5: Zapisywanie prezentacji

Po dostosowaniu wykresu możesz zapisać prezentację ze zmianami.

```csharp
pres.Save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

Gratulacje! Pomyślnie dodałeś kolor do punktów danych na wykresie za pomocą Aspose.Slides dla .NET. Może to znacznie poprawić atrakcyjność wizualną i przejrzystość prezentacji.

## Wniosek

Dodanie koloru do punktów danych na wykresie to skuteczny sposób na uczynienie prezentacji bardziej wciągającymi i pouczającymi. Dzięki Aspose.Slides dla .NET masz narzędzia do tworzenia atrakcyjnych wizualnie wykresów, które skutecznie przekazują Twoje dane.

## Często zadawane pytania (FAQ)

### Co to jest Aspose.Slides dla .NET?
   Aspose.Slides dla .NET to biblioteka, która umożliwia programistom .NET programową pracę z prezentacjami programu PowerPoint.

### Czy mogę dostosować inne właściwości wykresu za pomocą Aspose.Slides?
   Tak, możesz dostosować różne aspekty wykresów, takie jak etykiety danych, czcionki, kolory i inne, używając Aspose.Slides dla .NET.

### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
    Szczegółową dokumentację można znaleźć na stronie[łącze do dokumentacji](https://reference.aspose.com/slides/net/).

### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
    Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).

### Jak uzyskać wsparcie dla Aspose.Slides dla .NET?
    Aby uzyskać wsparcie i dyskusje, odwiedź stronę[Forum Aspose.Slides](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
