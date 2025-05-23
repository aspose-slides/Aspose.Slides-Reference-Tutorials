---
"description": "Dowiedz się, jak łączyć kształty za pomocą łączników w prezentacjach PowerPoint z Aspose.Slides dla Java. Samouczek krok po kroku dla początkujących."
"linktitle": "Łączenie kształtów za pomocą łączników w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Łączenie kształtów za pomocą łączników w programie PowerPoint"
"url": "/pl/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Łączenie kształtów za pomocą łączników w programie PowerPoint

## Wstęp
W tym samouczku pokażemy, jak łączyć kształty za pomocą łączników w prezentacjach PowerPoint za pomocą Aspose.Slides for Java. Postępuj zgodnie z tymi instrukcjami krok po kroku, aby skutecznie łączyć kształty i tworzyć atrakcyjne wizualnie slajdy.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania Java.
- Zainstalowano Java Development Kit (JDK) w systemie.
- Pobrano i skonfigurowano Aspose.Slides dla Java. Jeśli jeszcze go nie zainstalowałeś, możesz go pobrać z [Tutaj](https://releases.aspose.com/slides/java/).
- Edytor kodu, np. Eclipse lub IntelliJ IDEA.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do pracy z Aspose.Slides w swoim projekcie Java.
```java
import com.aspose.slides.*;

```
## Krok 1: Utwórz klasę prezentacji
Utwórz instancję `Presentation` Klasa, która reprezentuje plik PPTX, nad którym pracujesz.
```java
// Ścieżka do katalogu dokumentów.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Krok 2: Uzyskaj dostęp do kolekcji kształtów
Uzyskaj dostęp do kolekcji kształtów dla wybranego slajdu, do którego chcesz dodać kształty i łączniki.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Krok 3: Dodaj kształty
Dodaj wymagane kształty do slajdu. W tym przykładzie dodamy elipsę i prostokąt.
```java
// Dodaj autokształt Ellipse
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Dodaj kształt automatyczny Prostokąt
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Krok 4: Dodaj złącze
Dodaj kształt łącznika do kolekcji kształtów slajdów.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Krok 5: Połącz kształty z łącznikami
Połącz kształty z łącznikiem.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Krok 6: Przekieruj łącznik
Wywołaj przekierowanie, aby ustawić automatyczną najkrótszą ścieżkę między kształtami.
```java
connector.reroute();
```
## Krok 7: Zapisz prezentację
Po połączeniu kształtów za pomocą łączników zapisz prezentację.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Na koniec nie zapomnij usunąć obiektu Presentation.
```java
if (input != null) input.dispose();
```
Udało Ci się połączyć kształty za pomocą łączników w programie PowerPoint przy użyciu Aspose.Slides dla Java.

## Wniosek
W tym samouczku nauczyliśmy się, jak łączyć kształty za pomocą łączników w prezentacjach PowerPoint z Aspose.Slides dla Java. Postępując zgodnie z tymi prostymi krokami, możesz ulepszyć swoje prezentacje za pomocą atrakcyjnych wizualnie diagramów i schematów blokowych.
## Najczęściej zadawane pytania
### Czy mogę dostosować wygląd łączników w Aspose.Slides dla Java?
Tak, możesz dostosować różne właściwości łączników, takie jak kolor, styl linii i grubość, aby dopasować je do potrzeb swojej prezentacji.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides for Java obsługuje różne formaty PowerPoint, w tym PPTX, PPT i ODP.
### Czy mogę połączyć więcej niż dwa kształty za pomocą jednego łącznika?
Tak, możesz łączyć wiele kształtów za pomocą złożonych łączników udostępnianych przez Aspose.Slides dla Java.
### Czy Aspose.Slides dla Java umożliwia dodawanie tekstu do kształtów?
Oczywiście, możesz łatwo dodawać tekst do kształtów i łączników programowo, korzystając z Aspose.Slides dla Java.
### Czy istnieje forum społecznościowe lub kanał wsparcia dla użytkowników Aspose.Slides for Java?
Tak, na forum Aspose.Slides możesz znaleźć przydatne zasoby, zadawać pytania i nawiązywać kontakty z innymi użytkownikami [Tutaj](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}