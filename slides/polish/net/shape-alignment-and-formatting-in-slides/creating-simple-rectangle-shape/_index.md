---
title: Tworzenie kształtów prostokątnych za pomocą Aspose.Slides dla platformy .NET
linktitle: Tworzenie prostego kształtu prostokąta na slajdach prezentacji przy użyciu Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Poznaj świat dynamicznych prezentacji PowerPoint dzięki Aspose.Slides dla .NET. Dzięki temu przewodnikowi krok po kroku dowiesz się, jak tworzyć atrakcyjne prostokątne kształty na slajdach.
weight: 12
url: /pl/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Jeśli chcesz ulepszyć swoje aplikacje .NET za pomocą dynamicznych i atrakcyjnych wizualnie prezentacji PowerPoint, Aspose.Slides dla .NET jest rozwiązaniem dla Ciebie. W tym samouczku przeprowadzimy Cię przez proces tworzenia prostego kształtu prostokąta na slajdach prezentacji przy użyciu Aspose.Slides dla .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Visual Studio: Upewnij się, że masz zainstalowany program Visual Studio na komputerze programistycznym.
-  Aspose.Slides dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Slides dla .NET z[Tutaj](https://releases.aspose.com/slides/net/).
- Podstawowa znajomość języka C#: Znajomość języka programowania C# jest niezbędna.
## Importuj przestrzenie nazw
W swoim projekcie C# zacznij od zaimportowania niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Krok 1: Skonfiguruj projekt
Rozpocznij od utworzenia nowego projektu C# w programie Visual Studio. Upewnij się, że w projekcie znajduje się prawidłowe odwołanie do Aspose.Slides for .NET.
## Krok 2: Zainicjuj obiekt prezentacji
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Twój kod kolejnych kroków znajdzie się tutaj.
}
```
## Krok 3: Zdobądź pierwszy slajd
```csharp
ISlide sld = pres.Slides[0];
```
## Krok 4: Dodaj autokształt prostokąta
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Ten kod dodaje kształt prostokąta o współrzędnych (50, 150) o szerokości 150 i wysokości 50.
## Krok 5: Zapisz prezentację
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Ten krok zapisuje prezentację z dodanym kształtem prostokąta we wskazanym katalogu.
## Wniosek
Gratulacje! Pomyślnie utworzyłeś prosty kształt prostokąta na slajdzie prezentacji przy użyciu Aspose.Slides dla .NET. To dopiero początek – Aspose.Slides oferuje szeroką gamę funkcji umożliwiających dalsze dostosowywanie i ulepszanie prezentacji.
## Często Zadawane Pytania
### Czy mogę używać Aspose.Slides dla .NET zarówno w środowisku Windows, jak i Linux?
Tak, Aspose.Slides dla .NET jest niezależny od platformy i może być używany zarówno w środowiskach Windows, jak i Linux.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
 Tak, możesz uzyskać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać wsparcie dla Aspose.Slides dla .NET?
 Odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za wsparcie społeczności.
### Czy mogę kupić tymczasową licencję na Aspose.Slides dla .NET?
 Tak, możesz kupić licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
 Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/slides/net/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
