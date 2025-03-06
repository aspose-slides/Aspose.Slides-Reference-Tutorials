---
title: Ulepsz prezentacje - sformatuj kształty prostokątów za pomocą Aspose.Slides
linktitle: Formatowanie kształtu prostokąta na slajdach prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak formatować kształty prostokątów w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla .NET. Podnieś poziom swoich slajdów dzięki dynamicznym elementom wizualnym.
weight: 12
url: /pl/net/shape-geometry-and-positioning-in-slides/formatting-rectangle-shape/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Aspose.Slides dla .NET to potężna biblioteka ułatwiająca pracę z prezentacjami programu PowerPoint w środowisku .NET. Jeśli chcesz ulepszyć swoje prezentacje poprzez dynamiczne formatowanie prostokątów, ten samouczek jest dla Ciebie. W tym przewodniku krok po kroku przeprowadzimy Cię przez proces formatowania kształtu prostokąta w prezentacji przy użyciu Aspose.Slides dla .NET.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Środowisko programistyczne z zainstalowanym Aspose.Slides for .NET.
- Podstawowa znajomość języka programowania C#.
- Znajomość tworzenia i manipulowania prezentacjami PowerPoint.
Teraz zacznijmy od samouczka!
## Importuj przestrzenie nazw
W kodzie C# musisz zaimportować niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności Aspose.Slides. Dodaj następujące przestrzenie nazw na początku kodu:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
```
## Krok 1: Skonfiguruj katalog dokumentów
 Rozpocznij od skonfigurowania katalogu, w którym chcesz zapisać plik prezentacji programu PowerPoint. Zastępować`"Your Document Directory"` z rzeczywistą ścieżką do katalogu.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## Krok 2: Utwórz obiekt prezentacji
 Utwórz instancję`Presentation` klasa reprezentująca plik PPTX. Będzie to podstawa Twojej prezentacji w programie PowerPoint.
```csharp
using (Presentation pres = new Presentation())
{
    // Twój kod trafia tutaj
}
```
## Krok 3: Zdobądź pierwszy slajd
Uzyskaj dostęp do pierwszego slajdu w prezentacji, ponieważ będzie to płótno, na którym dodasz i sformatujesz kształt prostokąta.
```csharp
ISlide sld = pres.Slides[0];
```
## Krok 4: Dodaj kształt prostokąta
 Użyj`Shapes`właściwość slajdu, aby dodać automatyczny kształt typu prostokąta. Określ położenie i wymiary prostokąta.
```csharp
IShape shp = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
## Krok 5: Zastosuj formatowanie do kształtu prostokąta
Teraz zastosujmy pewne formatowanie do kształtu prostokąta. Ustaw kolor wypełnienia, kolor linii i szerokość kształtu, aby dostosować jego wygląd.
```csharp
shp.FillFormat.FillType = FillType.Solid;
shp.FillFormat.SolidFillColor.Color = Color.Chocolate;
shp.LineFormat.FillFormat.FillType = FillType.Solid;
shp.LineFormat.FillFormat.SolidFillColor.Color = Color.Black;
shp.LineFormat.Width = 5;
```
## Krok 6: Zapisz prezentację
 Zapisz zmodyfikowaną prezentację na dysku za pomocą pliku`Save` metodę, określając format pliku jako PPTX.
```csharp
pres.Save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Gratulacje! Pomyślnie sformatowałeś kształt prostokąta w prezentacji przy użyciu Aspose.Slides dla .NET.
## Wniosek
W tym samouczku omówiliśmy podstawy pracy z kształtami prostokątnymi w Aspose.Slides dla .NET. Nauczyłeś się, jak skonfigurować projekt, utworzyć prezentację, dodać kształt prostokąta i zastosować formatowanie, aby poprawić jego atrakcyjność wizualną. Kontynuując eksplorację Aspose.Slides, odkryjesz jeszcze więcej sposobów na ulepszenie prezentacji PowerPoint.
## Często zadawane pytania
### P1: Czy mogę używać Aspose.Slides dla .NET z innymi językami .NET?
Tak, Aspose.Slides obsługuje inne języki .NET, takie jak VB.NET i F#, oprócz C#.
### P2: Gdzie mogę znaleźć dokumentację Aspose.Slides?
 Możesz zapoznać się z dokumentacją[Tutaj](https://reference.aspose.com/slides/net/).
### P3: Jak mogę uzyskać wsparcie dla Aspose.Slides?
 Aby uzyskać wsparcie i dyskusje, odwiedź stronę[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### P4: Czy dostępny jest bezpłatny okres próbny?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### P5: Gdzie mogę kupić Aspose.Slides dla .NET?
 Możesz kupić Aspose.Slides dla .NET[Tutaj](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
