---
title: Przewodnik po osadzaniu obiektów OLE w Aspose.Slides dla .NET
linktitle: Zastępowanie tytułu obrazu ramki obiektu OLE na slajdach prezentacji
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak ulepszyć slajdy prezentacji za pomocą dynamicznych obiektów OLE przy użyciu Aspose.Slides dla .NET. Postępuj zgodnie z naszym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
type: docs
weight: 15
url: /pl/net/shape-alignment-and-formatting-in-slides/substituting-picture-title-ole-object-frame/
---
## Wstęp
Tworzenie dynamicznych i angażujących slajdów prezentacyjnych często wiąże się z włączeniem różnych elementów multimedialnych. W tym samouczku dowiemy się, jak zastąpić tytuł obrazu ramki obiektu OLE (łączenie i osadzanie obiektów) na slajdach prezentacji przy użyciu potężnej biblioteki Aspose.Slides dla .NET. Aspose.Slides upraszcza proces obsługi obiektów OLE, zapewniając programistom narzędzia umożliwiające łatwe ulepszanie ich prezentacji.
## Warunki wstępne
Zanim przejdziemy do przewodnika krok po kroku, upewnij się, że spełnione są następujące wymagania wstępne:
-  Biblioteka Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides dla .NET. Można go pobrać z[Dokumentacja Aspose.Slides .NET](https://reference.aspose.com/slides/net/).
- Przykładowe dane: Przygotuj przykładowy plik Excel (np. „ExcelObject.xlsx”), który chcesz osadzić jako obiekt OLE w prezentacji. Dodatkowo przygotuj plik obrazu (np. „Image.png”), który będzie służył jako ikona obiektu OLE.
- Środowisko programistyczne: Skonfiguruj środowisko programistyczne z niezbędnymi narzędziami, takimi jak Visual Studio lub inne preferowane IDE do programowania .NET.
## Importuj przestrzenie nazw
W projekcie .NET pamiętaj o zaimportowaniu wymaganych przestrzeni nazw do pracy z Aspose.Slides:
```csharp
using Aspose.Slides;
using Aspose.Slides.Examples.CSharp;
using System;
using System.Collections.Generic;
using System.Drawing;
using System.IO;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using Aspose.Slides.DOM.Ole;
```
## Krok 1: Skonfiguruj katalog dokumentów
```csharp
string dataDir = "Your Document Directory";
```
Pamiętaj, aby zastąpić „Twój katalog dokumentów” rzeczywistą ścieżką do katalogu dokumentów.
## Krok 2: Zdefiniuj ścieżki pliku źródłowego OLE i pliku ikony
```csharp
string oleSourceFile = dataDir + "ExcelObject.xlsx";
string oleIconFile = dataDir + "Image.png";
```
Zaktualizuj te ścieżki rzeczywistymi ścieżkami do przykładowego pliku Excel i pliku obrazu.
## Krok 3: Utwórz instancję prezentacji
```csharp
using (Presentation pres = new Presentation())
{
    // Tutaj będzie umieszczony kod kolejnych kroków
}
```
 Zainicjuj nową instancję`Presentation` klasa.
## Krok 4: Dodaj ramkę obiektu OLE
```csharp
ISlide slide = pres.Slides[0];
byte[] allbytes = File.ReadAllBytes(oleSourceFile);
IOleEmbeddedDataInfo dataInfo = new OleEmbeddedDataInfo(allbytes, "xlsx");
IOleObjectFrame oof = slide.Shapes.AddOleObjectFrame(20, 20, 50, 50, dataInfo);
oof.IsObjectIcon = true;
```
Dodaj ramkę obiektu OLE do slajdu, określając jej położenie i wymiary.
## Krok 5: Dodaj obiekt obrazu
```csharp
byte[] imgBuf = File.ReadAllBytes(oleIconFile);
using (MemoryStream ms = new MemoryStream(imgBuf))
{
    IPPImage image = pres.Images.AddImage(new Bitmap(ms));
}
```
Przeczytaj plik obrazu i dodaj go do prezentacji jako obiekt obrazu.
## Krok 6: Ustaw podpis na ikonę OLE
```csharp
oof.SubstitutePictureTitle = "Caption example";
```
Ustaw żądany podpis ikony OLE.
## Wniosek
Włączanie obiektów OLE do slajdów prezentacji za pomocą Aspose.Slides dla .NET jest prostym procesem. Ten samouczek poprowadził Cię przez najważniejsze kroki, od skonfigurowania katalogu dokumentów po dodawanie i dostosowywanie obiektów OLE. Eksperymentuj z różnymi typami plików i podpisami, aby poprawić atrakcyjność wizualną swoich prezentacji.
## Często zadawane pytania
### Czy mogę osadzać inne typy plików jako obiekty OLE przy użyciu Aspose.Slides?
Tak, Aspose.Slides obsługuje osadzanie różnych typów plików, takich jak arkusze kalkulacyjne Excel, dokumenty Word i inne.
### Czy ikonę obiektu OLE można dostosować?
Absolutnie. Możesz zastąpić domyślną ikonę dowolnym wybranym obrazem, aby lepiej pasował do tematu prezentacji.
### Czy Aspose.Slides zapewnia obsługę animacji z obiektami OLE?
Od najnowszej wersji Aspose.Slides koncentruje się na osadzaniu i wyświetlaniu obiektów OLE i nie obsługuje bezpośrednio animacji w obiektach OLE.
### Czy mogę programowo manipulować obiektami OLE po dodaniu ich do slajdu?
Z pewnością. Masz pełną programową kontrolę nad obiektami OLE, co pozwala na modyfikowanie ich właściwości i wyglądu według potrzeb.
### Czy istnieją jakieś ograniczenia dotyczące rozmiaru osadzonych obiektów OLE?
Chociaż istnieją ograniczenia dotyczące rozmiaru, są one na ogół hojne. Zaleca się przetestowanie w konkretnym przypadku użycia, aby zapewnić optymalną wydajność.