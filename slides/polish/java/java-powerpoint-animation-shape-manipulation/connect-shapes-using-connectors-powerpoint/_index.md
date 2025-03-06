---
title: Łącz kształty za pomocą łączników w programie PowerPoint
linktitle: Łącz kształty za pomocą łączników w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak łączyć kształty za pomocą łączników w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla Java. Samouczek krok po kroku dla początkujących.
weight: 18
url: /pl/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W tym samouczku dowiemy się, jak łączyć kształty za pomocą łączników w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla języka Java. Postępuj zgodnie z tymi instrukcjami krok po kroku, aby skutecznie łączyć kształty i tworzyć atrakcyjne wizualnie slajdy.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania Java.
- Zainstalowano zestaw Java Development Kit (JDK) w systemie.
-  Pobrano i skonfigurowano Aspose.Slides dla Java. Jeśli jeszcze go nie zainstalowałeś, możesz go pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/).
- Edytor kodu taki jak Eclipse lub IntelliJ IDEA.

## Importuj pakiety
Najpierw zaimportuj pakiety niezbędne do pracy z Aspose.Slides w swoim projekcie Java.
```java
import com.aspose.slides.*;

```
## Krok 1: Utwórz instancję klasy prezentacji
 Utwórz instancję`Presentation`class, która reprezentuje plik PPTX, nad którym pracujesz.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Krok 2: Uzyskaj dostęp do kolekcji kształtów
Uzyskaj dostęp do kolekcji kształtów dla wybranego slajdu, do której chcesz dodać kształty i łączniki.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Krok 3: Dodaj kształty
Dodaj wymagane kształty do slajdu. W tym przykładzie dodamy elipsę i prostokąt.
```java
// Dodaj elipsę automatycznego kształtowania
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Dodaj prostokąt automatycznego kształtowania
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Krok 4: Dodaj złącze
Dodaj kształt łącznika do kolekcji kształtów slajdu.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Krok 5: Połącz kształty ze złączami
Połącz kształty ze złączem.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Krok 6: Przekieruj złącze
Wywołaj przekierowanie, aby ustawić automatyczną najkrótszą ścieżkę między kształtami.
```java
connector.reroute();
```
## Krok 7: Zapisz prezentację
Zapisz prezentację po połączeniu kształtów za pomocą łączników.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Na koniec nie zapomnij pozbyć się obiektu Prezentacja.
```java
if (input != null) input.dispose();
```
Teraz udało Ci się połączyć kształty za pomocą łączników w programie PowerPoint przy użyciu Aspose.Slides dla Java.

## Wniosek
tym samouczku nauczyliśmy się łączyć kształty za pomocą łączników w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla Java. Wykonując te proste kroki, możesz ulepszyć swoje prezentacje za pomocą atrakcyjnych wizualnie diagramów i schematów blokowych.
## Często zadawane pytania
### Czy mogę dostosować wygląd złączy w Aspose.Slides dla Java?
Tak, możesz dostosować różne właściwości złączy, takie jak kolor, styl linii i grubość, aby dopasować je do potrzeb prezentacji.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides for Java obsługuje różne formaty programu PowerPoint, w tym PPTX, PPT i ODP.
### Czy mogę połączyć więcej niż dwa kształty za pomocą jednego złącza?
Tak, możesz łączyć wiele kształtów za pomocą złożonych łączników dostarczonych przez Aspose.Slides dla Java.
### Czy Aspose.Slides dla Java oferuje obsługę dodawania tekstu do kształtów?
Absolutnie możesz łatwo programowo dodawać tekst do kształtów i złączy, używając Aspose.Slides dla Java.
### Czy dostępne jest forum społecznościowe lub kanał wsparcia dla użytkowników Aspose.Slides for Java?
 Tak, na forum Aspose.Slides możesz znaleźć pomocne zasoby, zadawać pytania i kontaktować się z innymi użytkownikami[Tutaj](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
