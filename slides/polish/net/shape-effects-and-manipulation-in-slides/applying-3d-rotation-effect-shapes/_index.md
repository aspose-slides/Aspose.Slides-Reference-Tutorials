---
title: Opanowanie rotacji 3D w prezentacjach za pomocą Aspose.Slides dla .NET
linktitle: Stosowanie efektu obrotu 3D na kształtach na slajdach prezentacji
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ulepsz swoje prezentacje dzięki Aspose.Slides dla .NET! W tym samouczku dowiesz się, jak stosować efekty obrotu 3D do kształtów. Twórz dynamiczną i oszałamiającą wizualnie prezentację.
weight: 23
url: /pl/net/shape-effects-and-manipulation-in-slides/applying-3d-rotation-effect-shapes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Opanowanie rotacji 3D w prezentacjach za pomocą Aspose.Slides dla .NET

## Wstęp
Tworzenie angażujących i dynamicznych slajdów prezentacji jest kluczowym aspektem skutecznej komunikacji. Aspose.Slides dla .NET zapewnia potężny zestaw narzędzi do ulepszania prezentacji, w tym możliwość stosowania efektów rotacji 3D do kształtów. W tym samouczku omówimy proces stosowania efektu rotacji 3D do kształtów na slajdach prezentacji przy użyciu Aspose.Slides dla .NET.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides dla .NET. Można go pobrać z[strona internetowa](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: skonfiguruj środowisko programistyczne .NET, takie jak Visual Studio, w celu pisania i uruchamiania kodu.
## Importuj przestrzenie nazw
W projekcie .NET zaimportuj niezbędne przestrzenie nazw, aby wykorzystać funkcjonalność Aspose.Slides. Na początku kodu umieść następujące przestrzenie nazw:
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt w preferowanym środowisku programistycznym .NET. Upewnij się, że dodałeś odniesienie Aspose.Slides do swojego projektu.
## Krok 2: Zainicjuj prezentację
Utwórz instancję klasy Prezentacja, aby rozpocząć pracę ze slajdami:
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
Dodanie efektów rotacji 3D do kształtów na slajdach prezentacji może znacząco poprawić ich atrakcyjność wizualną. Dzięki Aspose.Slides dla .NET proces ten staje się prosty, umożliwiając tworzenie urzekających prezentacji.
## Często zadawane pytania
### Czy mogę zastosować obrót 3D do pól tekstowych w Aspose.Slides dla .NET?
Tak, możesz zastosować efekty obrotu 3D do różnych kształtów, w tym pól tekstowych, za pomocą Aspose.Slides.
### Czy dostępna jest wersja próbna Aspose.Slides dla .NET?
 Tak, możesz uzyskać dostęp do wersji próbnej[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać wsparcie dla Aspose.Slides dla .NET?
 Odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za wsparcie społeczności i dyskusje.
### Czy mogę kupić tymczasową licencję na Aspose.Slides dla .NET?
 Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Slides dla .NET?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
