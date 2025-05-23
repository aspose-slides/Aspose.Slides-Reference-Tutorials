---
"description": "Dowiedz się, jak dostosować kąty linii łącznika w slajdach programu PowerPoint za pomocą Aspose.Slides dla .NET. Ulepsz swoje prezentacje z precyzją i łatwością."
"linktitle": "Dostosowywanie kątów linii łączących w slajdach prezentacji za pomocą Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Dostosuj kąty linii łączących w programie PowerPoint za pomocą Aspose.Slides"
"url": "/pl/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/"
"weight": 28
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dostosuj kąty linii łączących w programie PowerPoint za pomocą Aspose.Slides

## Wstęp
Tworzenie wizualnie atrakcyjnych slajdów prezentacji często wymaga precyzyjnych korekt linii łączników. W tym samouczku pokażemy, jak dostosować kąty linii łączników w slajdach prezentacji przy użyciu Aspose.Slides dla .NET. Aspose.Slides to potężna biblioteka, która umożliwia programistom programową pracę z plikami programu PowerPoint, zapewniająca szerokie możliwości tworzenia, modyfikowania i manipulowania prezentacjami.
## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:
- Podstawowa znajomość języka programowania C#.
- Zainstalowany program Visual Studio lub inne środowisko programistyczne C#.
- Biblioteka Aspose.Slides dla .NET. Możesz ją pobrać [Tutaj](https://releases.aspose.com/slides/net/).
- Plik prezentacji programu PowerPoint z liniami łączników, które chcesz dostosować.
## Importuj przestrzenie nazw
Aby rozpocząć, upewnij się, że w kodzie C# uwzględniłeś niezbędne przestrzenie nazw:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt C# w Visual Studio i zainstaluj pakiet Aspose.Slides NuGet. Skonfiguruj strukturę projektu z odwołaniem do biblioteki Aspose.Slides.
## Krok 2: Załaduj prezentację
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
Załaduj plik prezentacji PowerPoint do `Presentation` obiekt. Zastąp „Twój katalog dokumentów” rzeczywistą ścieżką do pliku.
## Krok 3: Uzyskaj dostęp do slajdu i kształtów
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Otwórz pierwszy slajd prezentacji i zainicjuj zmienną, która będzie reprezentować kształty na slajdzie.
## Krok 4: Iteruj po kształtach
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Kod do obsługi linii łączących
}
```
Przejrzyj każdy kształt na slajdzie, aby zidentyfikować i przetworzyć linie łączące.
## Krok 5: Dostosuj kąty linii łączących
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Kod do obsługi Autokształtów
}
else if (shape is Connector)
{
    // Kod do obsługi złączy
}
Console.WriteLine(dir);
```
Określ, czy kształt jest autokształtem czy łącznikiem i dostosuj kąty linii łącznika za pomocą dostarczonego `getDirection` metoda.
## Krok 6: Zdefiniuj `getDirection` Metoda
```csharp
public static double getDirection(float w, float h, bool flipH, bool flipV)
{
    // Kod do obliczania kierunku
	float endLineX = w * (flipH ? -1 : 1);
	float endLineY = h * (flipV ? -1 : 1);
	float endYAxisX = 0;
	float endYAxisY = h;
	double angle = (Math.Atan2(endYAxisY, endYAxisX) - Math.Atan2(endLineY, endLineX));
	if (angle < 0) angle += 2 * Math.PI;
    return angle * 180.0 / Math.PI;
}
```
Wdrożyć `getDirection` metoda obliczania kąta linii łącznika na podstawie jej wymiarów i orientacji.
## Wniosek
Dzięki tym krokom możesz programowo dostosować kąty linii łącznika w prezentacji PowerPoint za pomocą Aspose.Slides dla .NET. Ten samouczek zapewnia podstawę do zwiększenia atrakcyjności wizualnej slajdów.
## Często zadawane pytania
### Czy Aspose.Slides nadaje się zarówno do systemu Windows, jak i do aplikacji internetowych?
Tak, Aspose.Slides można używać zarówno w aplikacjach Windows, jak i internetowych.
### Czy mogę pobrać bezpłatną wersję próbną Aspose.Slides przed zakupem?
Tak, możesz pobrać bezpłatną wersję próbną [Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć kompleksową dokumentację Aspose.Slides dla .NET?
Dokumentacja jest dostępna [Tutaj](https://reference.aspose.com/slides/net/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides?
Możesz uzyskać tymczasową licencję [Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy istnieje forum wsparcia dla Aspose.Slides?
Tak, możesz odwiedzić forum wsparcia [Tutaj](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}