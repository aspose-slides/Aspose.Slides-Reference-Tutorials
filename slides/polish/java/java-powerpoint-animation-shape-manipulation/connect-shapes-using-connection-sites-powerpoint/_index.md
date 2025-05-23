---
"description": "Dowiedz się, jak łączyć kształty w programie PowerPoint za pomocą Aspose.Slides dla Java. Automatyzuj swoje prezentacje bez wysiłku."
"linktitle": "Łączenie kształtów za pomocą miejsc połączeń w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Łączenie kształtów za pomocą miejsc połączeń w programie PowerPoint"
"url": "/pl/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Łączenie kształtów za pomocą miejsc połączeń w programie PowerPoint

## Wstęp
W tym samouczku pokażemy, jak łączyć kształty za pomocą witryn połączeń w programie PowerPoint przy użyciu Aspose.Slides dla języka Java. Ta potężna biblioteka pozwala nam programowo manipulować prezentacjami programu PowerPoint, dzięki czemu zadania takie jak łączenie kształtów są płynne i wydajne.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowaną Javę w swoim systemie. Możesz ją pobrać i zainstalować z [strona internetowa](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java ze strony [strona do pobrania](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Wybierz środowisko IDE do programowania w języku Java, np. IntelliJ IDEA, Eclipse lub NetBeans.

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.*;

```
## Krok 1: Dostęp do kolekcji kształtów
Uzyskaj dostęp do kolekcji kształtów dla wybranego slajdu:
```java
// Ścieżka do katalogu dokumentów.                    
String dataDir = "Your Document Directory";
// Utwórz klasę prezentacji reprezentującą plik PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Krok 2: Dodawanie kształtu łącznika
Dodaj kształt łącznika do kolekcji kształtów slajdów:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Krok 3: Dodawanie Autokształtów
Dodaj automatyczne kształty, takie jak elipsa i prostokąt:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Krok 4: Łączenie kształtów z łącznikami
Połącz kształty z łącznikiem:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Krok 5: Ustawienie indeksu witryny połączenia
Ustaw żądany indeks miejsca połączenia dla kształtów:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Wniosek
W tym samouczku nauczyliśmy się, jak łączyć kształty za pomocą witryn połączeń w programie PowerPoint przy użyciu Aspose.Slides dla języka Java. Dzięki tej wiedzy możesz teraz z łatwością automatyzować i dostosowywać swoje prezentacje programu PowerPoint.
## Najczęściej zadawane pytania
### Czy Aspose.Slides for Java można używać do innych zadań związanych z obsługą programu PowerPoint?
Tak, Aspose.Slides for Java oferuje szeroką gamę funkcji do tworzenia, edytowania i konwertowania prezentacji PowerPoint.
### Czy Aspose.Slides for Java jest darmowy?
Aspose.Slides for Java to komercyjna biblioteka, ale możesz zapoznać się z jej funkcjami dzięki bezpłatnej wersji próbnej. Odwiedź [Tutaj](https://releases.aspose.com/) aby zacząć.
### Czy mogę uzyskać pomoc, jeśli napotkam jakiekolwiek problemy podczas korzystania z Aspose.Slides dla Java?
Tak, możesz uzyskać wsparcie na forach społeczności Aspose [Tutaj](https://forum.aspose.com/c/slides/11).
### Czy dostępne są licencje tymczasowe na Aspose.Slides dla Java?
Tak, tymczasowe licencje są dostępne do celów testowych i ewaluacyjnych. Możesz uzyskać jedną [Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę nabyć licencję na Aspose.Slides dla Java?
Licencję można zakupić na stronie internetowej Aspose [Tutaj](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}