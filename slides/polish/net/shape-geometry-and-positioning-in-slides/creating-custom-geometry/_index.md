---
title: Tworzenie niestandardowej geometrii w C# za pomocą Aspose.Slides dla .NET
linktitle: Tworzenie niestandardowej geometrii w kształcie geometrii przy użyciu Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak tworzyć niestandardową geometrię w Aspose.Slides dla .NET. Podnieś poziom swoich prezentacji dzięki unikalnym kształtom. Przewodnik krok po kroku dla programistów C#.
weight: 15
url: /pl/net/shape-geometry-and-positioning-in-slides/creating-custom-geometry/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie niestandardowej geometrii w C# za pomocą Aspose.Slides dla .NET

## Wstęp
dynamicznym świecie prezentacji dodanie unikalnych kształtów i geometrii może podnieść poziom treści, czyniąc ją bardziej wciągającą i atrakcyjną wizualnie. Aspose.Slides dla .NET zapewnia potężne rozwiązanie do tworzenia niestandardowych geometrii w kształtach, pozwalając uwolnić się od konwencjonalnych projektów. Ten samouczek poprowadzi Cię przez proces tworzenia niestandardowej geometrii w GeometryShape przy użyciu Aspose.Slides dla .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania C#.
- Biblioteka Aspose.Slides dla .NET zainstalowana w Twoim środowisku programistycznym.
- Skonfigurowano program Visual Studio lub dowolne preferowane środowisko programistyczne C#.
## Importuj przestrzenie nazw
Aby rozpocząć, zaimportuj niezbędne przestrzenie nazw do swojego projektu C#:
```csharp
using System;
using System.Collections.Generic;
using System.Diagnostics;
using System.Drawing;
using System.IO;
using Aspose.Slides.Export;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt C# w preferowanym środowisku programistycznym. Upewnij się, że Aspose.Slides dla .NET jest poprawnie zainstalowany.
## Krok 2: Zdefiniuj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
bool isExists = Directory.Exists(dataDir);
if (!isExists)
    Directory.CreateDirectory(dataDir);
```
## Krok 3: Ustaw zewnętrzny i wewnętrzny promień gwiazdy
```csharp
float R = 100, r = 50; // Zewnętrzny i wewnętrzny promień gwiazdy
```
## Krok 4: Utwórz ścieżkę geometrii gwiazdy
```csharp
GeometryPath starPath = CreateStarGeometry(R, r);
```
## Krok 5: Utwórz prezentację
```csharp
using (Presentation pres = new Presentation())
{
    // Utwórz nowy kształt
    GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, R * 2, R * 2);
    // Ustaw nową ścieżkę geometrii do kształtu
    shape.SetGeometryPath(starPath);
    // Zapisz prezentację
    string resultPath = Path.Combine(dataDir, "GeometryShapeCreatesCustomGeometry.pptx");
    pres.Save(resultPath, SaveFormat.Pptx);
}
```
## Krok 6: Zdefiniuj metodę CreateStarGeometry
```csharp
private static GeometryPath CreateStarGeometry(float outerRadius, float innerRadius)
{
    GeometryPath starPath = new GeometryPath();
    List<PointF> points = new List<PointF>();
    int step = 72;
    for (int angle = -90; angle < 270; angle += step)
    {
        double radians = angle * (Math.PI / 180f);
        double x = outerRadius * Math.Cos(radians);
        double y = outerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
        radians = Math.PI * (angle + step / 2) / 180.0;
        x = innerRadius * Math.Cos(radians);
        y = innerRadius * Math.Sin(radians);
        points.Add(new PointF((float)x + outerRadius, (float)y + outerRadius));
    }
    starPath.MoveTo(points[0]);
    for (int i = 1; i < points.Count; i++)
    {
        starPath.LineTo(points[i]);
    }
    starPath.CloseFigure();
    return starPath;
}
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak tworzyć niestandardową geometrię w GeometryShape przy użyciu Aspose.Slides dla .NET. Otwiera to świat możliwości tworzenia unikalnych i oszałamiających wizualnie prezentacji.
## Często zadawane pytania
### 1. Czy mogę używać Aspose.Slides dla .NET z innymi językami programowania?
Tak, Aspose.Slides obsługuje różne języki programowania, ale ten samouczek koncentruje się na języku C#.
### 2. Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
 Odwiedzić[dokumentacja](https://reference.aspose.com/slides/net/) aby uzyskać szczegółowe informacje.
### 3. Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
 Tak, możesz poznać m.in[bezpłatna wersja próbna](https://releases.aspose.com/) aby doświadczyć funkcji.
### 4. Jak mogę uzyskać wsparcie dla Aspose.Slides dla .NET?
 Szukaj pomocy i nawiązuj kontakt ze społecznością na stronie[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 5. Gdzie mogę kupić Aspose.Slides dla .NET?
 Możesz kupić Aspose.Slides dla .NET[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
