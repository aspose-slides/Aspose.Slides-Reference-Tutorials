---
"description": "Dowiedz się, jak dodawać kreatywne szkice kształtów do slajdów prezentacji za pomocą Aspose.Slides dla .NET. Zwiększ atrakcyjność wizualną bez wysiłku!"
"linktitle": "Tworzenie szkicowanych kształtów w slajdach prezentacji za pomocą Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Twórz oszałamiające szkice kształtów za pomocą Aspose.Slides"
"url": "/pl/net/shape-alignment-and-formatting-in-slides/creating-sketched-shapes/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Twórz oszałamiające szkice kształtów za pomocą Aspose.Slides

## Wstęp
Witamy w naszym przewodniku krok po kroku dotyczącym tworzenia szkicowanych kształtów w slajdach prezentacji przy użyciu Aspose.Slides dla .NET. Jeśli chcesz dodać odrobinę kreatywności do swoich prezentacji, szkicowane kształty zapewniają wyjątkową i ręcznie rysowaną estetykę. W tym samouczku przeprowadzimy Cię przez proces, dzieląc go na proste kroki, aby zapewnić płynne działanie.
## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
- Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides dla .NET. Możesz ją pobrać [Tutaj](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET przy użyciu preferowanego środowiska IDE.
## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw w projekcie .NET. Ten krok zapewnia dostęp do klas i funkcjonalności wymaganych do pracy z Aspose.Slides.
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
## Krok 1: Konfiguracja projektu
Zacznij od utworzenia nowego projektu .NET lub otwarcia istniejącego. Upewnij się, że Aspose.Slides jest zawarte w odniesieniach do projektu.
## Krok 2: Zainicjuj Aspose.Slides
Zainicjuj Aspose.Slides, dodając następujący fragment kodu. Spowoduje to skonfigurowanie prezentacji i określenie ścieżek wyjściowych dla pliku prezentacji i obrazu miniatury.
```csharp
string dataDir = "Your Document Directory";
string outPptxFile = Path.Combine(dataDir, "SketchedShapes_out.pptx");
string outPngFile = Path.Combine(dataDir, "SketchedShapes_out.png");
using (Presentation pres = new Presentation())
{
    // Przejdź do następnych kroków...
}
```
## Krok 3: Dodaj szkicowany kształt
Teraz dodajmy szkicowany kształt do slajdu. W tym przykładzie dodamy prostokąt z efektem szkicu odręcznego.
```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 20, 20, 300, 150);
shape.FillFormat.FillType = FillType.NoFill;
// Przekształć kształt w szkic w stylu odręcznym
shape.LineFormat.SketchFormat.SketchType = LineSketchType.Scribble;
```
## Krok 4: Generowanie miniatury
Wygeneruj miniaturę slajdu, aby zwizualizować naszkicowany kształt. Zapisz miniaturę jako plik PNG.
```csharp
pres.Slides[0].GetThumbnail(4/3f, 4/3f).Save(outPngFile, ImageFormat.Png);
```
## Krok 5: Zapisz prezentację
Zapisz plik prezentacji ze szkicem kształtu.
```csharp
pres.Save(outPptxFile, SaveFormat.Pptx);
```
To wszystko! Udało Ci się utworzyć prezentację ze szkicowanymi kształtami przy użyciu Aspose.Slides dla .NET.
## Wniosek
Dodawanie szkicowanych kształtów do slajdów prezentacji może zwiększyć atrakcyjność wizualną i zaangażować odbiorców. Dzięki Aspose.Slides dla .NET proces ten staje się prosty, pozwalając uwolnić kreatywność bez wysiłku.
## Często zadawane pytania
### 1. Czy mogę dostosować efekt szkicu?
Tak, Aspose.Slides dla .NET zapewnia różne opcje dostosowywania dla efektów szkicowych. Zapoznaj się z [dokumentacja](https://reference.aspose.com/slides/net/) Aby uzyskać szczegółowe informacje.
### 2. Czy jest dostępna bezpłatna wersja próbna?
Oczywiście! Możesz wypróbować bezpłatną wersję próbną Aspose.Slides dla .NET [Tutaj](https://releases.aspose.com/).
### 3. Gdzie mogę uzyskać pomoc?
W celu uzyskania pomocy lub w razie pytań odwiedź stronę [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### 4. Jak mogę zakupić Aspose.Slides dla platformy .NET?
Aby zakupić Aspose.Slides dla .NET, odwiedź stronę [strona zakupu](https://purchase.aspose.com/buy).
### 5. Czy oferujecie licencje tymczasowe?
Tak, licencje tymczasowe są dostępne [Tutaj](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}