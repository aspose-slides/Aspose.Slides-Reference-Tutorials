---
title: Twórz oszałamiające szkicowane kształty za pomocą Aspose.Slides
linktitle: Tworzenie szkicowanych kształtów na slajdach prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak dodawać kreatywne, naszkicowane kształty do slajdów prezentacji za pomocą Aspose.Slides dla .NET. Zwiększ atrakcyjność wizualną bez wysiłku!
weight: 13
url: /pl/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Twórz oszałamiające szkicowane kształty za pomocą Aspose.Slides

## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym tworzenia szkicowanych kształtów na slajdach prezentacji przy użyciu Aspose.Slides dla .NET. Jeśli chcesz dodać odrobinę kreatywności do swoich prezentacji, szkicowane kształty zapewnią niepowtarzalną, ręcznie rysowaną estetykę. W tym samouczku przeprowadzimy Cię przez cały proces, dzieląc go na proste kroki, aby zapewnić płynne działanie.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET z preferowanym IDE.
## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw do projektu .NET. Ten krok zapewnia dostęp do klas i funkcjonalności wymaganych do pracy z Aspose.Slides.
```csharp
using System;
using System.Collections.Generic;
using System.Drawing.Imaging;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using Aspose.Slides.Util;
using Aspose.Slides.Export;
using Aspose.Slides.MathText;
```
## Krok 1: Skonfiguruj projekt
Rozpocznij od utworzenia nowego projektu .NET lub otwarcia istniejącego. Pamiętaj o uwzględnieniu Aspose.Slides w referencjach projektu.
## Krok 2: Zainicjuj Aspose.Slides
Zainicjuj Aspose.Slides, dodając następujący fragment kodu. Spowoduje to skonfigurowanie prezentacji i określenie ścieżek wyjściowych dla pliku prezentacji i obrazu miniatury.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Przejdź do kolejnych kroków...
}
```
## Krok 3: Dodaj naszkicowany kształt
Teraz dodajmy naszkicowany kształt do slajdu. W tym przykładzie dodamy prostokąt z efektem szkicu odręcznego.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Przekształć kształt w szkic w stylu odręcznym
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Krok 4: Wygeneruj miniaturę
Wygeneruj miniaturę slajdu, aby zwizualizować naszkicowany kształt. Zapisz miniaturę jako plik PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Krok 5: Zapisz prezentację
Zapisz plik prezentacji z naszkicowanym kształtem.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
Otóż to! Pomyślnie utworzyłeś prezentację z naszkicowanymi kształtami przy użyciu Aspose.Slides dla .NET.
## Wniosek
Dodawanie naszkicowanych kształtów do slajdów prezentacji może zwiększyć atrakcyjność wizualną i zaangażować odbiorców. Dzięki Aspose.Slides dla .NET proces staje się prosty, co pozwala uwolnić kreatywność bez wysiłku.
## Często zadawane pytania
### 1. Czy mogę dostosować szkicowany efekt?
 Tak, Aspose.Slides dla .NET zapewnia różne opcje dostosowywania efektów szkicowanych. Patrz[dokumentacja](https://reference.aspose.com/slides/net/) aby uzyskać szczegółowe informacje.
### 2. Czy dostępny jest bezpłatny okres próbny?
 Z pewnością! Możesz skorzystać z bezpłatnej wersji próbnej Aspose.Slides dla .NET[Tutaj](https://releases.aspose.com/).
### 3. Gdzie mogę uzyskać wsparcie?
 Aby uzyskać pomoc lub zadać pytania, odwiedź stronę[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Jak mogę kupić Aspose.Slides dla .NET?
 Aby kupić Aspose.Slides dla .NET, odwiedź stronę[strona zakupu](https://purchase.aspose.com/buy).
### 5. Czy oferujecie licencje tymczasowe?
 Tak, dostępne są licencje tymczasowe[Tutaj](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
