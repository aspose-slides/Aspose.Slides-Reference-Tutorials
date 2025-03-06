---
title: Z łatwością twórz kształt elipsy za pomocą Aspose.Slides .NET
linktitle: Tworzenie prostego kształtu elipsy na slajdach prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak tworzyć wspaniałe kształty elips na slajdach prezentacji za pomocą Aspose.Slides dla .NET. Proste kroki do dynamicznego projektowania!
weight: 11
url: /pl/net/shape-alignment-and-formatting-in-slides/creating-simple-ellipse-shape/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W dynamicznym świecie projektowania prezentacji włączenie kształtów takich jak elipsy może dodać odrobinę kreatywności i profesjonalizmu. Aspose.Slides dla .NET oferuje potężne rozwiązanie do programowego manipulowania plikami prezentacji. Ten samouczek poprowadzi Cię przez proces tworzenia prostego kształtu elipsy na slajdach prezentacji przy użyciu Aspose.Slides dla .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Aspose.Slides dla .NET: Upewnij się, że zainstalowałeś bibliotekę Aspose.Slides dla .NET. Można go pobrać z[strona z wydaniami](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: Skonfiguruj środowisko programistyczne .NET na swoim komputerze.
## Importuj przestrzenie nazw
W projekcie .NET zacznij od zaimportowania niezbędnych przestrzeni nazw:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
Te przestrzenie nazw udostępniają podstawowe klasy i metody wymagane do pracy ze slajdami i kształtami prezentacji.
## Krok 1: Skonfiguruj prezentację
Rozpocznij od utworzenia nowej prezentacji i uzyskania dostępu do pierwszego slajdu. Aby to osiągnąć, dodaj następujący kod:
```csharp
// Ścieżka do katalogu dokumentów.
string dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
// Klasa prezentacji natychmiastowej
using (Presentation pres = new Presentation())
{
    // Zdobądź pierwszy slajd
    ISlide sld = pres.Slides[0];
```
Ten kod inicjuje nową prezentację i wybiera pierwszy slajd do dalszej manipulacji.
## Krok 2: Dodaj kształt elipsy
 Teraz dodajmy kształt elipsy do slajdu za pomocą`AddAutoShape` metoda:
```csharp
// Dodaj autokształt typu elipsy
sld.Shapes.AddAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Ta linia kodu tworzy kształt elipsy o współrzędnych (50, 150) o szerokości 150 jednostek i wysokości 50 jednostek.
## Krok 3: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację na dysku pod określoną nazwą pliku, używając następującego kodu:
```csharp
// Zapisz plik PPTX na dysku
pres.Save(dataDir + "EllipseShp1_out.pptx", SaveFormat.Pptx);
```
Ten krok gwarantuje, że zmiany zostaną utrwalone, a wynikową prezentację będzie można wyświetlić z nowo dodanym kształtem elipsy.
## Wniosek
Congratulations! You've successfully created a simple ellipse shape in a presentation slide using Aspose.Slides for .NET. This tutorial provides a foundational understanding of working with shapes, setting up presentations, and saving the modified files.
---
## Często zadawane pytania
### Czy mogę bardziej dostosować kształt elipsy?
Tak, możesz modyfikować różne właściwości kształtu elipsy, takie jak kolor, rozmiar i położenie, aby spełnić określone wymagania projektowe.
### Czy Aspose.Slides jest kompatybilny z najnowszymi frameworkami .NET?
Tak, Aspose.Slides jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi frameworkami .NET.
### Gdzie mogę znaleźć więcej tutoriali i przykładów Aspose.Slides?
 Odwiedzić[dokumentacja](https://reference.aspose.com/slides/net/) obszerne przewodniki i przykłady.
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides?
 Podążaj za[tymczasowy link do licencji](https://purchase.aspose.com/temporary-license/) aby poprosić o tymczasową licencję do celów testowych.
### Potrzebujesz pomocy lub masz konkretne pytania?
 Odwiedzić[Forum wsparcia Aspose.Slides](https://forum.aspose.com/c/slides/11) aby uzyskać pomoc od społeczności i ekspertów.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
