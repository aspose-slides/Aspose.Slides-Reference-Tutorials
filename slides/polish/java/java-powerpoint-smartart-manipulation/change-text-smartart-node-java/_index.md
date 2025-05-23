---
"description": "Dowiedz się, jak aktualizować tekst węzła SmartArt w programie PowerPoint za pomocą języka Java z programem Aspose.Slides, co pozwala na lepsze dostosowywanie prezentacji."
"linktitle": "Zmiana tekstu w węźle SmartArt za pomocą Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Zmiana tekstu w węźle SmartArt za pomocą Java"
"url": "/pl/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zmiana tekstu w węźle SmartArt za pomocą Java

## Wstęp
SmartArt w programie PowerPoint to potężna funkcja do tworzenia atrakcyjnych wizualnie diagramów. Aspose.Slides for Java zapewnia kompleksowe wsparcie w celu programowego manipulowania elementami SmartArt. W tym samouczku przeprowadzimy Cię przez proces zmiany tekstu w węźle SmartArt przy użyciu języka Java.
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:
- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java została pobrana i wykorzystana w projekcie Java.
- Podstawowa znajomość programowania w Javie.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety, aby uzyskać dostęp do funkcjonalności Aspose.Slides w kodzie Java.
```java
import com.aspose.slides.*;
```
Podzielmy przykład na kilka kroków:
## Krok 1: Zainicjuj obiekt prezentacji
```java
Presentation presentation = new Presentation();
```
Utwórz nową instancję `Presentation` klasa pracująca z prezentacją PowerPoint.
## Krok 2: Dodaj SmartArt do slajdu
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
Dodaj SmartArt do pierwszego slajdu. W tym przykładzie używamy `BasicCycle` układ.
## Krok 3: Uzyskaj dostęp do węzła SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Pobierz odwołanie do drugiego węzła głównego obiektu SmartArt.
## Krok 4: Ustaw tekst na węźle
```java
node.getTextFrame().setText("Second root node");
```
Ustaw tekst dla wybranego węzła SmartArt.
## Krok 5: Zapisz prezentację
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Zapisz zmodyfikowaną prezentację w określonej lokalizacji.

## Wniosek
tym samouczku pokazaliśmy, jak zmienić tekst w węźle SmartArt za pomocą Java i Aspose.Slides. Dzięki tej wiedzy możesz dynamicznie manipulować elementami SmartArt w prezentacjach PowerPoint, zwiększając ich atrakcyjność wizualną i przejrzystość.
## Najczęściej zadawane pytania
### Czy mogę zmienić układ obiektu SmartArt po dodaniu go do slajdu?
Tak, możesz zmienić układ, uzyskując dostęp do `SmartArt.setAllNodes(LayoutType)` metoda.
### Czy Aspose.Slides jest kompatybilny z Java 11?
Tak, Aspose.Slides for Java jest kompatybilny z Java 11 i nowszymi wersjami.
### Czy mogę programowo dostosować wygląd węzłów SmartArt?
Oczywiście, możesz modyfikować różne właściwości, takie jak kolor, rozmiar i kształt, korzystając z interfejsu API Aspose.Slides.
### Czy Aspose.Slides obsługuje inne typy układów SmartArt?
Tak, Aspose.Slides obsługuje szeroką gamę układów SmartArt, dzięki czemu możesz wybrać taki, który najlepiej odpowiada potrzebom Twojej prezentacji.
### Gdzie mogę znaleźć więcej materiałów i pomocy dla Aspose.Slides?
Możesz odwiedzić [Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/) aby uzyskać szczegółowe odniesienia do API i samouczki. Dodatkowo możesz zwrócić się o pomoc do [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) lub rozważ zakup [licencja tymczasowa](https://purchase.aspose.com/temporary-license/) Aby uzyskać profesjonalne wsparcie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}