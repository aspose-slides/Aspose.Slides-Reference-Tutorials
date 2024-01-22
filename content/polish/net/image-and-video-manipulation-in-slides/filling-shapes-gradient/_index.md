---
title: Twórz wspaniałe gradienty w programie PowerPoint za pomocą Aspose.Slides
linktitle: Wypełnianie kształtów gradientem na slajdach prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ulepsz swoje prezentacje dzięki Aspose.Slides dla .NET! Poznaj krok po kroku proces wypełniania kształtów gradientami. Pobierz teraz bezpłatną wersję próbną!
type: docs
weight: 21
url: /pl/net/image-and-video-manipulation-in-slides/filling-shapes-gradient/
---
## Wstęp
Tworzenie atrakcyjnych wizualnie slajdów prezentacji jest niezbędne, aby przyciągnąć i utrzymać uwagę odbiorców. W tym samouczku przeprowadzimy Cię przez proces ulepszania slajdów poprzez wypełnienie elipsy gradientem za pomocą Aspose.Slides dla .NET.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
- Podstawowa znajomość języka programowania C#.
- Program Visual Studio zainstalowany na Twoim komputerze.
-  Aspose.Slides dla biblioteki .NET. Pobierz to[Tutaj](https://releases.aspose.com/slides/net/).
- Katalog projektu do porządkowania plików.
## Importuj przestrzenie nazw
W projekcie C# uwzględnij wymagane przestrzenie nazw dla Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Krok 1: Utwórz prezentację
Rozpocznij od utworzenia nowej prezentacji przy użyciu biblioteki Aspose.Slides:
```csharp
string dataDir = "Your Documents Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Twój kod trafia tutaj...
}
```
## Krok 2: Dodaj kształt elipsy
Wstaw kształt elipsy do pierwszego slajdu prezentacji:
```csharp
ISlide sld = pres.Slides[0];
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 75, 150);
```
## Krok 3: Zastosuj formatowanie gradientowe
Określ, że kształt ma być wypełniony gradientem i zdefiniuj charakterystykę gradientu:
```csharp
shp.FillFormat.FillType = FillType.Gradient;
shp.FillFormat.GradientFormat.GradientShape = GradientShape.Linear;
shp.FillFormat.GradientFormat.GradientDirection = GradientDirection.FromCorner2;
```
## Krok 4: Dodaj punkty gradientu
Zdefiniuj kolory i położenie punktów gradientu:
```csharp
shp.FillFormat.GradientFormat.GradientStops.Add((float)1.0, PresetColor.Purple);
shp.FillFormat.GradientFormat.GradientStops.Add((float)0, PresetColor.Red);
```
## Krok 5: Zapisz prezentację
Zapisz swoją prezentację z nowo dodanym kształtem wypełnionym gradientem:
```csharp
pres.Save(dataDir + "EllipseShpGrad_out.pptx", SaveFormat.Pptx);
```
Powtórz te kroki w kodzie C#, zapewniając odpowiednią sekwencję i wartości parametrów. W rezultacie plik prezentacji będzie miał atrakcyjny wizualnie kształt elipsy wypełnionej gradientem.
## Wniosek
With Aspose.Slides for .NET, you can effortlessly elevate the visual aesthetics of your presentations. By following this guide, you've learned how to fill shapes with gradients, giving your slides a professional and engaging look.
---
## Często zadawane pytania
### P: Czy mogę zastosować gradienty do kształtów innych niż elipsy?
Odp.: Oczywiście! Aspose.Slides dla .NET obsługuje wypełnianie gradientem różnych kształtów, takich jak prostokąty, wielokąty i inne.
### P: Gdzie mogę znaleźć dodatkowe przykłady i szczegółową dokumentację?
 O: Poznaj[Aspose.Slides dla dokumentacji .NET](https://reference.aspose.com/slides/net/) obszerne przewodniki i przykłady.
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
 Odp.: Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P: Jak mogę uzyskać wsparcie dla Aspose.Slides dla .NET?
 O: Poproś o pomoc i nawiąż kontakt ze społecznością na stronie[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### P: Czy mogę kupić tymczasową licencję na Aspose.Slides dla .NET?
 Odpowiedź: Oczywiście, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).