---
title: Opanowywanie kształtów geometrycznych za pomocą ShapeUtil - Aspose.Slides .NET
linktitle: Używanie narzędzia ShapeUtil do określania kształtu geometrii na slajdach prezentacji
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Odkryj moc Aspose.Slides dla .NET z ShapeUtil dla dynamicznych kształtów geometrycznych. Twórz angażujące prezentacje bez wysiłku. Pobierz teraz! Dowiedz się, jak ulepszyć prezentacje programu PowerPoint za pomocą Aspose.Slides. Poznaj narzędzie ShapeUtil do manipulacji kształtami geometrycznymi. Przewodnik krok po kroku z kodem źródłowym .NET. Skutecznie optymalizuj prezentacje.
weight: 17
url: /pl/net/shape-geometry-and-positioning-in-slides/using-shapeutil-geometry-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Tworzenie atrakcyjnych wizualnie i dynamicznych slajdów prezentacyjnych jest niezbędną umiejętnością, a Aspose.Slides dla .NET zapewnia potężny zestaw narzędzi, aby to osiągnąć. W tym samouczku omówimy wykorzystanie narzędzia ShapeUtil do obsługi kształtów geometrycznych na slajdach prezentacji. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz z Aspose.Slides, ten przewodnik przeprowadzi Cię przez proces wykorzystania ShapeUtil do ulepszania prezentacji.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w C# i .NET.
-  Zainstalowano bibliotekę Aspose.Slides dla .NET. Jeśli nie, możesz go pobrać[Tutaj](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne skonfigurowane do uruchamiania aplikacji .NET.
## Importuj przestrzenie nazw
Upewnij się, że w kodzie C# zaimportowałeś niezbędne przestrzenie nazw, aby uzyskać dostęp do funkcjonalności Aspose.Slides. Dodaj następujący tekst na początku skryptu:
```csharp
using System.Drawing;
using System.Drawing.Drawing2D;
using System.IO;
using Aspose.Slides.Export;
using Aspose.Slides.Util;
```
Podzielmy teraz podany przykład na kilka kroków, aby utworzyć przewodnik krok po kroku dotyczący używania narzędzia ShapeUtil do kształtów geometrycznych na slajdach prezentacji.
## Krok 1: Skonfiguruj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
Upewnij się, że zastąpiłeś „Twój katalog dokumentów” rzeczywistą ścieżką, w której chcesz zapisać prezentację.
## Krok 2: Zdefiniuj nazwę pliku wyjściowego
```csharp
string resultPath = Path.Combine(dataDir, "GeometryShapeUsingShapeUtil.pptx");
```
Określ żądaną nazwę pliku wyjściowego, łącznie z rozszerzeniem pliku.
## Krok 3: Utwórz prezentację
```csharp
using (Presentation pres = new Presentation())
```
Zainicjuj nowy obiekt prezentacji, korzystając z biblioteki Aspose.Slides.
## Krok 4: Dodaj kształt geometryczny
```csharp
GeometryShape shape = (GeometryShape)pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
Dodaj kształt prostokąta do pierwszego slajdu prezentacji.
## Krok 5: Uzyskaj oryginalną ścieżkę geometrii
```csharp
IGeometryPath originalPath = shape.GetGeometryPaths()[0];
originalPath.FillMode = PathFillModeType.None;
```
Pobierz ścieżkę geometrii kształtu i ustaw tryb wypełnienia.
## Krok 6: Utwórz ścieżkę graficzną z tekstem
```csharp
GraphicsPath graphicsPath = new GraphicsPath();
graphicsPath.AddString("Text in shape", new FontFamily("Arial"), 1, 40, new PointF(10, 10), StringFormat.GenericDefault);
```
Wygeneruj ścieżkę graficzną z tekstem, który zostanie dodany do kształtu.
## Krok 7: Konwertuj ścieżkę graficzną na ścieżkę geometryczną
```csharp
IGeometryPath textPath = ShapeUtil.GraphicsPathToGeometryPath(graphicsPath);
textPath.FillMode = PathFillModeType.Normal;
```
Użyj ShapeUtil, aby przekonwertować ścieżkę graficzną na ścieżkę geometryczną i ustawić tryb wypełnienia.
## Krok 8: Ustaw połączone ścieżki geometrii dla kształtu
```csharp
shape.SetGeometryPaths(new[] { originalPath, textPath });
```
Połącz nową ścieżkę geometrii ze ścieżką oryginalną i ustaw ją na kształt.
## Krok 9: Zapisz prezentację
```csharp
pres.Save(resultPath, SaveFormat.Pptx);
```
Zapisz zmodyfikowaną prezentację z nowym kształtem geometrii.
## Wniosek
Gratulacje! Pomyślnie zapoznałeś się z wykorzystaniem ShapeUtil do obsługi kształtów geometrycznych na slajdach prezentacji przy użyciu Aspose.Slides dla .NET. Ta zaawansowana funkcja umożliwia łatwe tworzenie dynamicznych i wciągających prezentacji.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides dla .NET z innymi językami programowania?
Aspose.Slides obsługuje przede wszystkim języki .NET. Jednak Aspose udostępnia podobne biblioteki dla innych platform i języków.
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Slides dla .NET?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/slides/net/).
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla .NET?
 Tak, możesz znaleźć bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać wsparcie dla Aspose.Slides dla .NET?
 Odwiedź forum wsparcia społeczności[Tutaj](https://forum.aspose.com/c/slides/11).
### Czy mogę kupić tymczasową licencję na Aspose.Slides dla .NET?
 Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
