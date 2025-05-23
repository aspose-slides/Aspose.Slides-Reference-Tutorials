---
"description": "Ulepsz swoje prezentacje dzięki Aspose.Slides dla .NET! Naucz się stosować efekty obrotu 3D do kształtów w tym samouczku. Twórz dynamiczne i wizualnie oszałamiające prezentacje."
"linktitle": "Stosowanie efektu obrotu 3D do kształtów na slajdach prezentacji"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Opanowanie obrotu 3D w prezentacjach z Aspose.Slides dla .NET"
"url": "/pl/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie obrotu 3D w prezentacjach z Aspose.Slides dla .NET

## Wstęp
Tworzenie angażujących i dynamicznych slajdów prezentacji jest kluczowym aspektem skutecznej komunikacji. Aspose.Slides for .NET zapewnia potężny zestaw narzędzi do ulepszania prezentacji, w tym możliwość stosowania efektów obrotu 3D do kształtów. W tym samouczku przejdziemy przez proces stosowania efektu obrotu 3D do kształtów w slajdach prezentacji przy użyciu Aspose.Slides for .NET.
## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
- Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides dla .NET. Możesz ją pobrać ze strony [strona internetowa](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: Skonfiguruj środowisko programistyczne .NET, takie jak Visual Studio, aby pisać i uruchamiać kod.
## Importuj przestrzenie nazw
W swoim projekcie .NET zaimportuj niezbędne przestrzenie nazw, aby wykorzystać funkcjonalność Aspose.Slides. Dołącz następujące przestrzenie nazw na początku swojego kodu:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt w preferowanym środowisku programistycznym .NET. Upewnij się, że dodałeś odwołanie Aspose.Slides do swojego projektu.
## Krok 2: Zainicjuj prezentację
Utwórz klasę Prezentacja, aby rozpocząć pracę ze slajdami:
```csharp
Presentation pres = new Presentation();
```
## Krok 3: Dodaj Autokształt
Dodaj Autokształt do slajdu, określając jego typ, położenie i wymiary:
```csharp
IShape autoShape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
## Krok 4: Ustaw efekt obrotu 3D
Skonfiguruj efekt obrotu 3D dla Autokształtu:
```csharp
autoShape.ThreeDFormat.Depth = 6;
autoShape.ThreeDFormat.Camera.SetRotation(40, 35, 20);
autoShape.ThreeDFormat.Camera.CameraType = CameraPresetType.IsometricLeftUp;
autoShape.ThreeDFormat.LightRig.LightType = LightRigPresetType.Balanced;
```
## Krok 5: Zapisz prezentację
Zapisz zmodyfikowaną prezentację z zastosowanym efektem obrotu 3D:
```csharp
pres.Save("Your Document Directory" + "Rotation_out.pptx", SaveFormat.Pptx);
```
## Krok 6: Powtórz dla innych kształtów
Jeśli masz dodatkowe kształty, powtórz kroki od 3 do 5 dla każdego kształtu.
## Wniosek
Dodanie efektów obrotu 3D do kształtów na slajdach prezentacji może znacznie poprawić ich atrakcyjność wizualną. Dzięki Aspose.Slides dla .NET proces ten staje się prosty, umożliwiając tworzenie wciągających prezentacji.
## Często zadawane pytania
### Czy mogę zastosować obrót 3D w polach tekstowych w Aspose.Slides dla .NET?
Tak, możesz stosować efekty obrotu 3D do różnych kształtów, w tym pól tekstowych, używając Aspose.Slides.
### Czy jest dostępna wersja próbna Aspose.Slides dla platformy .NET?
Tak, możesz uzyskać dostęp do wersji próbnej [Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides dla platformy .NET?
Odwiedź [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) w celu uzyskania wsparcia społeczności i dyskusji.
### Czy mogę kupić tymczasową licencję na Aspose.Slides dla platformy .NET?
Tak, możesz uzyskać tymczasową licencję [Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Slides dla .NET?
Dokumentacja jest dostępna [Tutaj](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}