---
title: Przekształcanie slajdów prezentacji za pomocą Aspose.Slides dla .NET
linktitle: Zmiana kolejności kształtów na slajdach prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak zmieniać kształt slajdów prezentacji za pomocą Aspose.Slides dla .NET. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby zmienić kolejność kształtów i poprawić atrakcyjność wizualną.
type: docs
weight: 26
url: /pl/net/shape-effects-and-manipulation-in-slides/changing-order-shapes/
---
## Wstęp
Tworzenie atrakcyjnych wizualnie slajdów prezentacji jest kluczowym aspektem skutecznej komunikacji. Aspose.Slides dla .NET umożliwia programistom programowe manipulowanie slajdami, oferując szeroki zakres funkcjonalności. W tym samouczku zagłębimy się w proces zmiany kolejności kształtów na slajdach prezentacji za pomocą Aspose.Slides dla .NET.
## Warunki wstępne
Zanim wyruszymy w tę podróż, upewnijmy się, że spełniamy następujące warunki wstępne:
-  Aspose.Slides dla .NET: Upewnij się, że biblioteka Aspose.Slides jest zintegrowana z projektem .NET. Jeśli nie, możesz pobrać go ze strony[strona z wydaniami](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: skonfiguruj działające środowisko programistyczne za pomocą programu Visual Studio lub dowolnego innego narzędzia programistycznego .NET.
- Podstawowa znajomość języka C#: Zapoznaj się z podstawami języka programowania C#.
## Importuj przestrzenie nazw
W swoim projekcie C# uwzględnij niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Slides:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt w programie Visual Studio lub preferowanym środowisku programistycznym .NET. Upewnij się, że w Twoim projekcie znajduje się odniesienie do Aspose.Slides for .NET.
## Krok 2: Załaduj prezentację
```csharp
string dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Krok 3: Uzyskaj dostęp do slajdu i kształtów
```csharp
ISlide slide = presentation.Slides[0];
```
## Krok 4: Dodaj nowy kształt
```csharp
IAutoShape shp3 = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.FillFormat.FillType = FillType.NoFill;
shp3.AddTextFrame(" ");
```
## Krok 5: Zmodyfikuj tekst w kształcie
```csharp
ITextFrame txtFrame = shp3.TextFrame;
IParagraph para = txtFrame.Paragraphs[0];
IPortion portion = para.Portions[0];
portion.Text = "Watermark Text Watermark Text Watermark Text";
```
## Krok 6: Dodaj kolejny kształt
```csharp
shp3 = slide.Shapes.AddAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Krok 7: Zmień kolejność kształtów
```csharp
slide.Shapes.Reorder(2, shp3);
```
## Krok 8: Zapisz zmodyfikowaną prezentację
```csharp
presentation.Save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
To kończy przewodnik krok po kroku dotyczący zmiany kolejności kształtów na slajdach prezentacji przy użyciu Aspose.Slides dla .NET.
## Wniosek
Aspose.Slides dla .NET upraszcza zadanie programowego manipulowania slajdami prezentacji. Wykonując ten samouczek, nauczyłeś się zmieniać kolejność kształtów, co pozwala zwiększyć atrakcyjność wizualną prezentacji.
## Często zadawane pytania
### P: Czy mogę używać Aspose.Slides dla .NET zarówno w środowisku Windows, jak i Linux?
Odp.: Tak, Aspose.Slides dla .NET jest kompatybilny zarówno ze środowiskami Windows, jak i Linux.
### P: Czy istnieją jakieś uwagi licencyjne dotyczące używania Aspose.Slides w projekcie komercyjnym?
 O: Tak, szczegóły licencji i opcje zakupu można znaleźć na stronie[Strona zakupu Aspose.Slides](https://purchase.aspose.com/buy).
### P: Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
 Odp.: Tak, możesz eksplorować funkcje za pomocą[bezpłatna wersja próbna](https://releases.aspose.com/) dostępne na stronie internetowej Aspose.Slides.
### P: Gdzie mogę znaleźć pomoc lub zadać pytania związane z Aspose.Slides dla .NET?
O: Odwiedź[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) aby uzyskać wsparcie i nawiązać kontakt ze społecznością.
### P: Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla .NET?
 O: Możesz nabyć[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) w celach ewaluacyjnych.