---
title: Opanowanie efektów animacji końcowej w programie PowerPoint za pomocą Aspose.Slides
linktitle: Sterowanie po typie animacji na slajdzie
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak kontrolować efekty animacji końcowej na slajdach programu PowerPoint za pomocą Aspose.Slides dla .NET. Wzbogać swoje prezentacje dynamicznymi elementami wizualnymi.
weight: 11
url: /pl/net/slide-animation-control/control-after-animation-type/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Wzbogacanie prezentacji dynamicznymi animacjami jest kluczowym aspektem angażowania odbiorców. Aspose.Slides dla .NET zapewnia potężne rozwiązanie do kontrolowania efektów animacji na slajdach. W tym samouczku przeprowadzimy Cię przez proces używania Aspose.Slides dla .NET do manipulowania typem animacji końcowej na slajdach. Postępując zgodnie z tym przewodnikiem krok po kroku, będziesz w stanie tworzyć bardziej interaktywne i atrakcyjne wizualnie prezentacje.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz następujące elementy:
- Podstawowa znajomość programowania w C# i .NET.
-  Zainstalowana biblioteka Aspose.Slides dla .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/slides/net/).
- Zintegrowane środowisko programistyczne (IDE), takie jak Visual Studio.
## Importuj przestrzenie nazw
Zacznij od zaimportowania niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.Slides. Dodaj następujące linie do swojego kodu:
```csharp
using System.Drawing;
using System.IO;
using Aspose.Slides.Animation;
using Aspose.Slides.SlideShow;
using Aspose.Slides.Export;
```
Teraz podzielmy dostarczony kod na wiele kroków, aby lepiej zrozumieć:
## Krok 1: Skonfiguruj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Upewnij się, że określony katalog istnieje lub utwórz go, jeśli nie.
## Krok 2: Zdefiniuj ścieżkę pliku wyjściowego
```csharp
string outPath = Path.Combine(dataDir, "AnimationAfterEffect-out.pptx");
```
Określ ścieżkę pliku wyjściowego zmodyfikowanej prezentacji.
## Krok 3: Załaduj prezentację
```csharp
using (Presentation pres = new Presentation(dataDir + "AnimationAfterEffect.pptx"))
```
Utwórz instancję klasy Prezentacja i załaduj istniejącą prezentację.
## Krok 4: Zmodyfikuj efekty animacji na slajdzie 1
```csharp
ISlide slide1 = pres.Slides.AddClone(pres.Slides[0]);
ISequence seq = slide1.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideOnNextMouseClick;
```
Sklonuj pierwszy slajd, uzyskaj dostęp do jego sekwencji na osi czasu i ustaw efekt animacji końcowej na „Ukryj po następnym kliknięciu myszą”.
## Krok 5: Zmodyfikuj efekty animacji na slajdzie 2
```csharp
ISlide slide2 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide2.Timeline.MainSequence;
foreach (IEffect effect in seq)
{
    effect.AfterAnimationType = AfterAnimationType.Color;
    effect.AfterAnimationColor.Color = Color.Green;
}
```
Sklonuj ponownie pierwszy slajd, tym razem zmieniając efekt animacji na „Kolor” z zielonym kolorem.
## Krok 6: Zmodyfikuj efekty animacji na slajdzie 3
```csharp
ISlide slide3 = pres.Slides.AddClone(pres.Slides[0]);
seq = slide3.Timeline.MainSequence;
foreach (IEffect effect in seq)
    effect.AfterAnimationType = AfterAnimationType.HideAfterAnimation;
```
Sklonuj pierwszy slajd jeszcze raz, ustawiając efekt animacji końcowej na „Ukryj po animacji”.
## Krok 7: Zapisz zmodyfikowaną prezentację
```csharp
pres.Save(outPath, SaveFormat.Pptx);
```
Zapisz zmodyfikowaną prezentację z określoną ścieżką pliku wyjściowego.
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się kontrolować efekty animacji końcowej na slajdach za pomocą Aspose.Slides dla .NET. Eksperymentuj z różnymi typami animacji końcowych, aby tworzyć bardziej dynamiczne i wciągające prezentacje.
## Często zadawane pytania
### Czy mogę zastosować różne efekty animacji końcowej do poszczególnych elementów slajdu?
Tak, możesz. Iteruj po elementach i odpowiednio dostosowuj ich efekty po animacji.
### Czy Aspose.Slides jest kompatybilny z najnowszymi wersjami .NET?
Tak, Aspose.Slides jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi wersjami platformy .NET.
### Jak mogę dodać niestandardowe animacje do slajdów za pomocą Aspose.Slides?
 Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/slides/net/) aby uzyskać szczegółowe informacje na temat dodawania niestandardowych animacji.
### Jakie formaty plików obsługuje Aspose.Slides do zapisywania prezentacji?
Aspose.Slides obsługuje różne formaty, w tym PPTX, PPT, PDF i inne. Pełną listę znajdziesz w dokumentacji.
### Gdzie mogę uzyskać pomoc lub zadać pytania związane z Aspose.Slides?
 Odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za wsparcie i interakcję społeczną.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
