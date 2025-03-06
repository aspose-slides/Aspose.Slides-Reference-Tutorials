---
title: Zmiana danych obiektu OLE w prezentacji za pomocą Aspose.Slides
linktitle: Zmiana danych obiektu OLE w prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Odkryj moc Aspose.Slides dla .NET w łatwej zmianie danych obiektów OLE. Wzbogać swoje prezentacje dynamiczną zawartością.
weight: 25
url: /pl/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Tworzenie dynamicznych i interaktywnych prezentacji PowerPoint jest powszechnym wymogiem w dzisiejszym cyfrowym świecie. Potężnym narzędziem do osiągnięcia tego celu jest Aspose.Slides dla .NET, solidna biblioteka, która pozwala programistom programowo manipulować i ulepszać prezentacje programu PowerPoint. W tym samouczku zagłębimy się w proces zmiany danych obiektowych OLE (łączenie i osadzanie obiektów) w slajdach prezentacji za pomocą Aspose.Slides.
## Warunki wstępne
Zanim zaczniesz pracować z Aspose.Slides dla .NET, upewnij się, że masz spełnione następujące wymagania wstępne:
1. Środowisko programistyczne: Skonfiguruj środowisko programistyczne z zainstalowaną platformą .NET.
2.  Biblioteka Aspose.Slides: Pobierz i zainstaluj bibliotekę Aspose.Slides dla .NET. Możesz znaleźć drogę do biblioteki[Tutaj](https://releases.aspose.com/slides/net/).
3. Podstawowe zrozumienie: Zapoznaj się z podstawowymi koncepcjami programowania w języku C# i prezentacjami programu PowerPoint.
## Importuj przestrzenie nazw
W swoim projekcie C# zaimportuj niezbędne przestrzenie nazw, aby móc korzystać z funkcjonalności Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Krok 1: Skonfiguruj swój projekt
Rozpocznij od utworzenia nowego projektu C# i zaimportowania biblioteki Aspose.Slides. Upewnij się, że projekt jest poprawnie skonfigurowany i masz wymagane zależności.
## Krok 2: Uzyskaj dostęp do prezentacji i slajdu
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Krok 3: Zlokalizuj obiekt OLE
Przejrzyj wszystkie kształty na slajdzie, aby znaleźć ramkę obiektu OLE:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## Krok 4: Przeczytaj i zmodyfikuj dane skoroszytu
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Odczyt danych obiektowych w skoroszycie
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Modyfikowanie danych skoroszytu
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Zmiana danych obiektu ramki Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Krok 5: Zapisz prezentację
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Wniosek
Wykonując poniższe kroki, możesz bezproblemowo zmieniać dane obiektów OLE na slajdach prezentacji za pomocą Aspose.Slides dla .NET. Otwiera to świat możliwości tworzenia dynamicznych i spersonalizowanych prezentacji dostosowanych do Twoich konkretnych potrzeb.
## Często Zadawane Pytania
### Co to jest Aspose.Slides dla .NET?
Aspose.Slides dla .NET to potężna biblioteka, która umożliwia programistom programową pracę z prezentacjami programu PowerPoint, umożliwiając łatwą manipulację i ulepszanie.
### Gdzie mogę znaleźć dokumentację Aspose.Slides?
 Można znaleźć dokumentację Aspose.Slides dla .NET[Tutaj](https://reference.aspose.com/slides/net/).
### Jak pobrać Aspose.Slides dla .NET?
 Bibliotekę można pobrać ze strony wydania[Tutaj](https://releases.aspose.com/slides/net/).
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides?
 Tak, możesz uzyskać dostęp do bezpłatnego okresu próbnego[Tutaj](https://releases.aspose.com/).
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla .NET?
 Aby uzyskać wsparcie i dyskusje, odwiedź stronę[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
