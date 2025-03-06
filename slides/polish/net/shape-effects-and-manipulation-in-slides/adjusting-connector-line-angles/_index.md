---
title: Dostosuj kąty linii łączników w programie PowerPoint za pomocą Aspose.Slides
linktitle: Dostosowywanie kątów linii łączników na slajdach prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak dostosować kąty linii łączników na slajdach programu PowerPoint za pomocą Aspose.Slides dla .NET. Ulepsz swoje prezentacje z precyzją i łatwością.
weight: 28
url: /pl/net/shape-effects-and-manipulation-in-slides/adjusting-connector-line-angles/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dostosuj kąty linii łączników w programie PowerPoint za pomocą Aspose.Slides

## Wstęp
Tworzenie atrakcyjnych wizualnie slajdów prezentacyjnych często wiąże się z precyzyjnym dopasowaniem linii łączących. W tym samouczku przyjrzymy się, jak dostosować kąty linii łączników na slajdach prezentacji za pomocą Aspose.Slides dla .NET. Aspose.Slides to potężna biblioteka, która umożliwia programistom programową pracę z plikami programu PowerPoint, zapewniając szerokie możliwości tworzenia, modyfikowania i manipulowania prezentacjami.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:
- Podstawowa znajomość języka programowania C#.
- Zainstalowany program Visual Studio lub dowolne inne środowisko programistyczne C#.
-  Aspose.Slides dla biblioteki .NET. Możesz go pobrać[Tutaj](https://releases.aspose.com/slides/net/).
- Plik prezentacji programu PowerPoint z liniami łączącymi, które chcesz dostosować.
## Importuj przestrzenie nazw
Aby rozpocząć, pamiętaj o uwzględnieniu niezbędnych przestrzeni nazw w kodzie C#:
```csharp
using System.IO;
using Aspose.Slides;
using System;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt C# w programie Visual Studio i zainstaluj pakiet Aspose.Slides NuGet. Skonfiguruj strukturę projektu z odniesieniem do biblioteki Aspose.Slides.
## Krok 2: Załaduj prezentację
```csharp
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ConnectorLineAngle.pptx");
```
 Załaduj plik prezentacji programu PowerPoint do pliku`Presentation`obiekt. Zastąp „Twój katalog dokumentów” rzeczywistą ścieżką do pliku.
## Krok 3: Uzyskaj dostęp do slajdu i kształtów
```csharp
Slide slide = (Slide)pres.Slides[0];
Shape shape;
```
Uzyskaj dostęp do pierwszego slajdu w prezentacji i zainicjuj zmienną reprezentującą kształty na slajdzie.
## Krok 4: Iteruj po kształtach
```csharp
for (int i = 0; i < slide.Shapes.Count; i++)
{
    // Kod do obsługi linii łączących
}
```
Przejrzyj każdy kształt na slajdzie, aby zidentyfikować i przetworzyć linie łączące.
## Krok 5: Dostosuj kąty linii łączącej
```csharp
double dir = 0.0;
shape = (Shape)slide.Shapes[i];
if (shape is AutoShape)
{
    // Kod do obsługi Autokształtów
}
else if (shape is Connector)
{
    // Kod do obsługi łączników
}
Console.WriteLine(dir);
```
 Określ, czy kształt jest Autokształtem, czy Łącznikiem, i dostosuj kąty linii łącznika, korzystając z dostarczonych narzędzi`getDirection` metoda.
##  Krok 6: Zdefiniuj`getDirection` Method
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
 Wdrażaj`getDirection` metoda obliczania kąta linii łącznika na podstawie jej wymiarów i orientacji.
## Wniosek
Wykonując te kroki, możesz programowo dostosować kąty linii łączników w prezentacji programu PowerPoint za pomocą Aspose.Slides dla .NET. Ten samouczek stanowi podstawę do poprawy atrakcyjności wizualnej slajdów.
## Często zadawane pytania
### Czy Aspose.Slides jest odpowiedni zarówno dla systemu Windows, jak i aplikacji internetowych?
Tak, Aspose.Slides może być używany zarówno w aplikacjach Windows, jak i internetowych.
### Czy przed zakupem mogę pobrać bezpłatną wersję próbną Aspose.Slides?
 Tak, możesz pobrać bezpłatną wersję próbną[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć obszerną dokumentację Aspose.Slides dla .NET?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/slides/net/).
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides?
 Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Czy istnieje forum pomocy technicznej dla Aspose.Slides?
 Tak, możesz odwiedzić forum pomocy technicznej[Tutaj](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
