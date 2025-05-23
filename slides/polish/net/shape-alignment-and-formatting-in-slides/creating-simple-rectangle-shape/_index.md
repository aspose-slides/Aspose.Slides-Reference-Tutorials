---
"description": "Poznaj świat dynamicznych prezentacji PowerPoint z Aspose.Slides dla .NET. Dowiedz się, jak tworzyć angażujące kształty prostokątów na slajdach dzięki temu przewodnikowi krok po kroku."
"linktitle": "Tworzenie prostego prostokąta w slajdach prezentacji przy użyciu Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Tworzenie kształtów prostokątnych za pomocą Aspose.Slides dla .NET"
"url": "/pl/net/shape-alignment-and-formatting-in-slides/creating-simple-rectangle-shape/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tworzenie kształtów prostokątnych za pomocą Aspose.Slides dla .NET

## Wstęp
Jeśli chcesz ulepszyć swoje aplikacje .NET dynamicznymi i atrakcyjnymi wizualnie prezentacjami PowerPoint, Aspose.Slides for .NET jest rozwiązaniem dla Ciebie. W tym samouczku przeprowadzimy Cię przez proces tworzenia prostego kształtu prostokąta w slajdach prezentacji przy użyciu Aspose.Slides for .NET.
## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Visual Studio: Upewnij się, że na komputerze deweloperskim jest zainstalowany program Visual Studio.
- Aspose.Slides dla .NET: Pobierz i zainstaluj bibliotekę Aspose.Slides dla .NET z [Tutaj](https://releases.aspose.com/slides/net/).
- Podstawowa wiedza o języku C#: Znajomość języka programowania C# jest niezbędna.
## Importuj przestrzenie nazw
W swoim projekcie C# zacznij od zaimportowania niezbędnych przestrzeni nazw, aby uzyskać dostęp do funkcjonalności Aspose.Slides:
```csharp
using System.IO;
using Aspose.Slides;
using Aspose.Slides.Export;
```
## Krok 1: Konfiguracja projektu
Zacznij od utworzenia nowego projektu C# w Visual Studio. Upewnij się, że Aspose.Slides dla .NET jest poprawnie przywoływany w Twoim projekcie.
## Krok 2: Zainicjuj obiekt prezentacji
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Kod dla kolejnych kroków będzie umieszczony tutaj.
}
```
## Krok 3: Pobierz pierwszy slajd
```csharp
ISlide sld = pres.Slides[0];
```
## Krok 4: Dodaj Autokształt Prostokąta
```csharp
sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Ten kod dodaje kształt prostokąta o współrzędnych (50, 150) o szerokości 150 i wysokości 50.
## Krok 5: Zapisz prezentację
```csharp
pres.Save(dataDir + "RectShp1_out.pptx", SaveFormat.Pptx);
```
Ten krok powoduje zapisanie prezentacji z dodanym prostokątnym kształtem w określonym katalogu.
## Wniosek
Gratulacje! Udało Ci się utworzyć prosty prostokątny kształt w slajdzie prezentacji przy użyciu Aspose.Slides dla .NET. To dopiero początek – Aspose.Slides oferuje szeroki zakres funkcji, które pozwolą Ci jeszcze bardziej dostosować i ulepszyć Twoje prezentacje.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides dla .NET w środowiskach Windows i Linux?
Tak, Aspose.Slides for .NET jest niezależny od platformy i można go używać zarówno w środowiskach Windows, jak i Linux.
### Czy jest dostępna bezpłatna wersja próbna Aspose.Slides dla .NET?
Tak, możesz otrzymać bezpłatną wersję próbną [Tutaj](https://releases.aspose.com/).
### Jak mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides dla platformy .NET?
Odwiedź [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) o wsparcie społeczności.
### Czy mogę kupić tymczasową licencję na Aspose.Slides dla platformy .NET?
Tak, możesz kupić licencję tymczasową [Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla .NET?
Zapoznaj się z dokumentacją [Tutaj](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}