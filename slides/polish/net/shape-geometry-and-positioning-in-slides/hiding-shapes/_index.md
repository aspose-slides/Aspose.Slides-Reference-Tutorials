---
"description": "Dowiedz się, jak ukrywać kształty w slajdach programu PowerPoint za pomocą Aspose.Slides dla .NET. Dostosuj prezentacje programowo za pomocą tego przewodnika krok po kroku."
"linktitle": "Ukrywanie kształtów w slajdach prezentacji za pomocą Aspose.Slides"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Ukrywanie kształtów w programie PowerPoint za pomocą samouczka Aspose.Slides .NET"
"url": "/pl/net/shape-geometry-and-positioning-in-slides/hiding-shapes/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ukrywanie kształtów w programie PowerPoint za pomocą samouczka Aspose.Slides .NET

## Wstęp
W dynamicznym świecie prezentacji, personalizacja jest kluczowa. Aspose.Slides for .NET zapewnia potężne rozwiązanie do programowego manipulowania prezentacjami PowerPoint. Jednym z powszechnych wymagań jest możliwość ukrywania określonych kształtów na slajdzie. Ten samouczek przeprowadzi Cię przez proces ukrywania kształtów na slajdach prezentacji przy użyciu Aspose.Slides for .NET.
## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
- Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides. Możesz ją pobrać [Tutaj](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: Skonfiguruj preferowane środowisko programistyczne dla platformy .NET.
- Podstawowa znajomość języka C#: Zapoznaj się z językiem C#, ponieważ przykłady kodu są napisane w tym języku.
## Importuj przestrzenie nazw
Aby rozpocząć pracę z Aspose.Slides, zaimportuj niezbędne przestrzenie nazw w swoim projekcie C#. Dzięki temu masz dostęp do wymaganych klas i metod.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Teraz podzielimy przykładowy kod na kilka kroków, aby ułatwić jego zrozumienie.
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt C# i upewnij się, że zawiera bibliotekę Aspose.Slides.
## Krok 2: Utwórz prezentację
Utwórz instancję `Presentation` klasa, reprezentująca plik PowerPoint. Dodaj slajd i uzyskaj do niego odniesienie.
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
Presentation pres = new Presentation();
ISlide sld = pres.Slides[0];
```
## Krok 3: Dodaj kształty do slajdu
Dodaj do slajdu autokształty, takie jak prostokąty i księżyce, o określonych wymiarach.
```csharp
IShape shp1 = sld.Shapes.AddAutoShape(ShapeType.Rectangle, 50, 40, 150, 50);
IShape shp2 = sld.Shapes.AddAutoShape(ShapeType.Moon, 160, 40, 150, 50);
```
## Krok 4: Ukryj kształty na podstawie tekstu alternatywnego
Określ tekst alternatywny i ukryj kształty, które pasują do tego tekstu.
```csharp
String alttext = "User Defined";
int iCount = sld.Shapes.Count;
for (int i = 0; i < iCount; i++)
{
    AutoShape ashp = (AutoShape)sld.Shapes[i];
    if (String.Compare(ashp.AlternativeText, alttext, StringComparison.Ordinal) == 0)
    {
        ashp.Hidden = true;
    }
}
```
## Krok 5: Zapisz prezentację
Zapisz zmodyfikowaną prezentację na dysku w formacie PPTX.
```csharp
pres.Save(dataDir + "Hiding_Shapes_out.pptx", SaveFormat.Pptx);
```
## Wniosek
Gratulacje! Udało Ci się ukryć kształty w prezentacji za pomocą Aspose.Slides dla .NET. Otwiera to świat możliwości tworzenia dynamicznych i dostosowanych slajdów programowo.
---
## Często zadawane pytania
### Czy Aspose.Slides jest kompatybilny z .NET Core?
Tak, Aspose.Slides obsługuje platformę .NET Core, co zapewnia elastyczność środowiska programistycznego.
### Czy mogę ukryć kształty na podstawie innych warunków niż tekst alternatywny?
Oczywiście! Możesz dostosować logikę ukrywania na podstawie różnych atrybutów, takich jak typ kształtu, kolor lub pozycja.
### Gdzie mogę znaleźć dodatkową dokumentację Aspose.Slides?
Przeglądaj dokumentację [Tutaj](https://reference.aspose.com/slides/net/) aby uzyskać szczegółowe informacje i przykłady.
### Czy na Aspose.Slides są dostępne licencje tymczasowe?
Tak, możesz uzyskać tymczasową licencję [Tutaj](https://purchase.aspose.com/temporary-license/) w celach testowych.
### W jaki sposób mogę uzyskać wsparcie społeczności dla Aspose.Slides?
Dołącz do społeczności Aspose.Slides na [forum](https://forum.aspose.com/c/slides/11) w celu omówienia i uzyskania pomocy.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}