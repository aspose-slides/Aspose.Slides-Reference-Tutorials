---
title: Ukryj kształty w programie PowerPoint za pomocą samouczka Aspose.Slides .NET
linktitle: Ukrywanie kształtów na slajdach prezentacji za pomocą Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Dowiedz się, jak ukrywać kształty na slajdach programu PowerPoint za pomocą Aspose.Slides dla .NET. Programowo dostosowuj prezentacje, korzystając z tego przewodnika krok po kroku.
type: docs
weight: 21
url: /pl/net/shape-geometry-and-positioning-in-slides/hiding-shapes/
---
## Wstęp
dynamicznym świecie prezentacji dostosowanie jest kluczem. Aspose.Slides dla .NET zapewnia potężne rozwiązanie do programowego manipulowania prezentacjami programu PowerPoint. Jednym z typowych wymagań jest możliwość ukrycia określonych kształtów na slajdzie. Ten samouczek poprowadzi Cię przez proces ukrywania kształtów na slajdach prezentacji przy użyciu Aspose.Slides dla .NET.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
-  Aspose.Slides dla .NET: Upewnij się, że masz zainstalowaną bibliotekę Aspose.Slides. Możesz go pobrać[Tutaj](https://releases.aspose.com/slides/net/).
- Środowisko programistyczne: skonfiguruj preferowane środowisko programistyczne dla platformy .NET.
- Podstawowa znajomość języka C#: Zapoznaj się z językiem C#, ponieważ podane przykłady kodu są w tym języku.
## Importuj przestrzenie nazw
Aby rozpocząć pracę z Aspose.Slides, zaimportuj niezbędne przestrzenie nazw do swojego projektu C#. Dzięki temu masz dostęp do wymaganych klas i metod.
```csharp
using System;
using Aspose.Slides.Export;
using Aspose.Slides;
```
Podzielmy teraz przykładowy kod na wiele kroków, aby uzyskać jasne i zwięzłe zrozumienie.
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt C# i pamiętaj o dołączeniu biblioteki Aspose.Slides.
## Krok 2: Utwórz prezentację
 Utwórz instancję`Presentation` class, reprezentujący plik programu PowerPoint. Dodaj slajd i uzyskaj do niego odniesienie.
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
Określ tekst alternatywny i ukryj kształty pasujące do tego tekstu.
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
Congratulations! You've successfully hidden shapes in your presentation using Aspose.Slides for .NET. This opens up a world of possibilities for creating dynamic and customized slides programmatically.
---
## Często zadawane pytania
### Czy Aspose.Slides jest kompatybilny z .NET Core?
Tak, Aspose.Slides obsługuje .NET Core, zapewniając elastyczność w Twoim środowisku programistycznym.
### Czy mogę ukryć kształty na podstawie warunków innych niż tekst alternatywny?
Absolutnie! Możesz dostosować logikę ukrywania w oparciu o różne atrybuty, takie jak typ kształtu, kolor lub położenie.
### Gdzie mogę znaleźć dodatkową dokumentację Aspose.Slides?
 Zapoznaj się z dokumentacją[Tutaj](https://reference.aspose.com/slides/net/) szczegółowe informacje i przykłady.
### Czy dostępne są tymczasowe licencje dla Aspose.Slides?
 Tak, możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/) do celów testowych.
### Jak mogę uzyskać wsparcie społeczności dla Aspose.Slides?
 Dołącz do społeczności Aspose.Slides na stronie[forum](https://forum.aspose.com/c/slides/11) za dyskusję i pomoc.