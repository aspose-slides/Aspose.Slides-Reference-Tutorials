---
title: Połącz kształty za pomocą witryn połączeń w programie PowerPoint
linktitle: Połącz kształty za pomocą witryn połączeń w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak łączyć kształty w programie PowerPoint przy użyciu Aspose.Slides dla języka Java. Zautomatyzuj swoje prezentacje bez wysiłku.
weight: 19
url: /pl/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W tym samouczku omówimy, jak łączyć kształty za pomocą witryn połączeń w programie PowerPoint przy użyciu Aspose.Slides dla Java. Ta potężna biblioteka pozwala nam programowo manipulować prezentacjami programu PowerPoint, dzięki czemu zadania takie jak łączenie kształtów są płynne i wydajne.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java. Można go pobrać i zainstalować ze strony[strona internetowa](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java z[strona pobierania](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): wybierz środowisko IDE do programowania w języku Java, takie jak IntelliJ IDEA, Eclipse lub NetBeans.

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
// Klasa prezentacji instancji reprezentująca plik PPTX
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Krok 2: Dodawanie kształtu złącza
Dodaj kształt łącznika do kolekcji kształtów slajdu:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Krok 3: Dodawanie Autokształtów
Dodaj automatyczne kształty, takie jak elipsa i prostokąt:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Krok 4: Łączenie kształtów w łączniki
Połącz kształty ze złączem:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Krok 5: Ustawianie indeksu witryny połączenia
Ustaw żądany indeks miejsca połączenia dla kształtów:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Wniosek
tym samouczku nauczyliśmy się łączyć kształty za pomocą witryn połączeń w programie PowerPoint przy użyciu Aspose.Slides dla Java. Dzięki tej wiedzy możesz teraz z łatwością automatyzować i dostosowywać prezentacje programu PowerPoint.
## Często zadawane pytania
### Czy Aspose.Slides for Java może być używany do innych zadań związanych z manipulacją programem PowerPoint?
Tak, Aspose.Slides for Java zapewnia szeroką gamę funkcjonalności do tworzenia, edytowania i konwertowania prezentacji PowerPoint.
### Czy korzystanie z Aspose.Slides dla Java jest bezpłatne?
 Aspose.Slides for Java jest biblioteką komercyjną, ale możesz poznać jej funkcje w ramach bezpłatnej wersji próbnej. Odwiedzać[Tutaj](https://releases.aspose.com/) rozpocząć.
### Czy mogę uzyskać pomoc, jeśli napotkam jakiekolwiek problemy podczas korzystania z Aspose.Slides dla Java?
 Tak, możesz uzyskać wsparcie na forach społeczności Aspose[Tutaj](https://forum.aspose.com/c/slides/11).
### Czy dostępne są tymczasowe licencje dla Aspose.Slides dla Java?
 Tak, dostępne są licencje tymczasowe do celów testowania i oceny. Możesz taki otrzymać[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę kupić licencję na Aspose.Slides dla Java?
Możesz kupić licencję na stronie internetowej Aspose[Tutaj](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
