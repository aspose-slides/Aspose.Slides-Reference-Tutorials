---
"description": "Odkryj moc Aspose.Slides dla .NET, łącząc kształty bez wysiłku w swoich prezentacjach. Ulepsz swoje slajdy dzięki dynamicznym łącznikom."
"linktitle": "Łączenie kształtów za pomocą łączników w prezentacji"
"second_title": "Aspose.Slides .NET API przetwarzania programu PowerPoint"
"title": "Aspose.Slides — bezproblemowe łączenie kształtów w .NET"
"url": "/pl/net/shape-effects-and-manipulation-in-slides/connecting-shapes-using-connectors/"
"weight": 29
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Slides — bezproblemowe łączenie kształtów w .NET

## Wstęp
W dynamicznym świecie prezentacji możliwość łączenia kształtów za pomocą łączników dodaje warstwę wyrafinowania do slajdów. Aspose.Slides dla .NET umożliwia programistom osiągnięcie tego bezproblemowo. Ten samouczek przeprowadzi Cię przez proces, rozbijając każdy krok, aby zapewnić jasne zrozumienie.
## Wymagania wstępne
Zanim przejdziemy do samouczka, upewnij się, że masz następujące rzeczy:
- Podstawowa znajomość języka C# i .NET Framework.
- Aspose.Slides dla .NET zainstalowany. Jeśli nie, pobierz go [Tutaj](https://releases.aspose.com/slides/net/).
- Utworzono środowisko programistyczne.
## Importuj przestrzenie nazw
W kodzie C# zacznij od zaimportowania niezbędnych przestrzeni nazw:
```csharp
using Aspose.Slides.Export;
using Aspose.Slides;
                input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## 1. Skonfiguruj katalog dokumentów
Zacznij od zdefiniowania katalogu dla swojego dokumentu:
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
```
## 2. Utwórz klasę prezentacji
Utwórz instancję klasy Presentation, aby reprezentować plik PPTX:
```csharp
using (Presentation input = new Presentation())
{
    // Uzyskiwanie dostępu do kolekcji kształtów dla wybranego slajdu
    IShapeCollection shapes = input.Slides[0].Shapes;
```
## 3. Dodaj kształty do slajdu
Dodaj do slajdu potrzebne kształty, takie jak elipsa i prostokąt:
```csharp
IAutoShape ellipse = shapes.AddAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.AddAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. Dodaj kształt łącznika
Dodaj kształt łącznika do kolekcji kształtów slajdu:
```csharp
IConnector connector = shapes.AddConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. Połącz kształty za pomocą łącznika
Określ kształty, które mają zostać połączone za pomocą łącznika:
```csharp
connector.StartShapeConnectedTo = ellipse;
connector.EndShapeConnectedTo = rectangle;
```
## 6. Przekieruj łącznik
Wywołaj metodę reroute, aby ustawić automatyczną najkrótszą ścieżkę między kształtami:
```csharp
connector.Reroute();
```
## 7. Zapisz prezentację
Zapisz prezentację, aby wyświetlić połączone kształty:
```csharp
input.Save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
## Wniosek
Gratulacje! Udało Ci się połączyć kształty za pomocą łączników w slajdach prezentacji przy użyciu Aspose.Slides dla .NET. Ulepsz swoje prezentacje za pomocą tej zaawansowanej funkcji i oczaruj publiczność.
## Często zadawane pytania
### Czy Aspose.Slides dla .NET jest kompatybilny z najnowszą wersją .NET Framework?
Tak, Aspose.Slides dla .NET jest regularnie aktualizowany w celu zapewnienia zgodności z najnowszymi wersjami .NET Framework.
### Czy mogę połączyć więcej niż dwa kształty za pomocą jednego łącznika?
Oczywiście, możesz połączyć wiele kształtów poprzez rozszerzenie logiki łącznika w kodzie.
### Czy istnieją jakieś ograniczenia co do kształtów, jakie mogę łączyć?
Aspose.Slides dla platformy .NET obsługuje łączenie różnych kształtów, w tym kształtów podstawowych, obiektów Smart Art i kształtów niestandardowych.
### Jak mogę dostosować wygląd łącznika?
Zapoznaj się z dokumentacją Aspose.Slides, aby poznać metody dostosowywania wyglądu łącznika, np. styl linii i kolor.
### Czy istnieje forum społecznościowe poświęcone pomocy technicznej Aspose.Slides?
Tak, możesz znaleźć pomoc i podzielić się swoimi doświadczeniami w [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}