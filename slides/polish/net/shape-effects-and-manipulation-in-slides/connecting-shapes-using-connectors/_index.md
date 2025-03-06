---
title: Aspose.Slides — płynnie łącz kształty w platformie .NET
linktitle: Łączenie kształtów za pomocą łączników w prezentacji
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Odkryj moc Aspose.Slides dla .NET, bez wysiłku łącząc kształty w swoich prezentacjach. Podnieś poziom swoich slajdów dzięki dynamicznym łącznikom.
weight: 29
url: /pl/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides — płynnie łącz kształty w platformie .NET

## Wstęp
W dynamicznym świecie prezentacji możliwość łączenia kształtów za pomocą łączników dodaje slajdom warstwy wyrafinowania. Aspose.Slides dla .NET umożliwia programistom bezproblemowe osiągnięcie tego celu. Ten samouczek poprowadzi Cię przez cały proces, dzieląc każdy krok w celu zapewnienia jasnego zrozumienia.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:
- Podstawowa znajomość C# i frameworku .NET.
-  Zainstalowano Aspose.Slides dla .NET. Jeśli nie, pobierz go[Tutaj](https://releases.aspose.com/slides/net/).
- Skonfigurowano środowisko programistyczne.
## Importuj przestrzenie nazw
W kodzie C# zacznij od zaimportowania niezbędnych przestrzeni nazw:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Skonfiguruj katalog dokumentów
Rozpocznij od zdefiniowania katalogu dla swojego dokumentu:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Natychmiastowa klasa prezentacji
Utwórz instancję klasy Prezentacja reprezentującą plik PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Dostęp do kolekcji kształtów dla wybranego slajdu
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Dodaj kształty do slajdu
Dodaj do slajdu niezbędne kształty, takie jak elipsa i prostokąt:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Dodaj kształt złącza
Dołącz kształt łącznika do kolekcji kształtów slajdu:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Połącz kształty za pomocą łącznika
Określ kształty, które mają być połączone łącznikiem:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Przekieruj złącze
Wywołaj metodę reroute, aby ustawić automatyczną najkrótszą ścieżkę pomiędzy kształtami:
```csharp
connector.Reroute();
```
## 7. Zapisz prezentację
Zapisz prezentację, aby wyświetlić połączone kształty:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Wniosek
Gratulacje! Pomyślnie połączyłeś kształty za pomocą łączników na slajdach prezentacji przy użyciu Aspose.Slides dla .NET. Ulepsz swoje prezentacje dzięki tej zaawansowanej funkcji i zachwyć odbiorców.
## Często zadawane pytania
### Czy Aspose.Slides for .NET jest kompatybilny z najnowszym frameworkiem .NET?
Tak, Aspose.Slides dla .NET jest regularnie aktualizowany, aby zapewnić kompatybilność z najnowszymi wersjami platformy .NET.
### Czy mogę połączyć więcej niż dwa kształty za pomocą jednego złącza?
Oczywiście możesz połączyć wiele kształtów, rozszerzając logikę łącznika w swoim kodzie.
### Czy są jakieś ograniczenia dotyczące kształtów, które mogę połączyć?
Aspose.Slides dla .NET obsługuje łączenie różnych kształtów, w tym kształtów podstawowych, grafiki inteligentnej i kształtów niestandardowych.
### Jak mogę dostosować wygląd złącza?
Zapoznaj się z dokumentacją Aspose.Slides, aby poznać metody dostosowywania wyglądu złącza, takie jak styl i kolor linii.
### Czy istnieje forum społecznościowe dotyczące wsparcia Aspose.Slides?
 Tak, możesz znaleźć pomoc i podzielić się swoimi doświadczeniami w[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
