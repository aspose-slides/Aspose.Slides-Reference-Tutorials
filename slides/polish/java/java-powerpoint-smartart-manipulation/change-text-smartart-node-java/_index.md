---
title: Zmień tekst w węźle SmartArt za pomocą języka Java
linktitle: Zmień tekst w węźle SmartArt za pomocą języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak zaktualizować tekst węzła SmartArt w programie PowerPoint przy użyciu języka Java z Aspose.Slides, usprawniając dostosowywanie prezentacji.
type: docs
weight: 22
url: /pl/java/java-powerpoint-smartart-manipulation/change-text-smartart-node-java/
---
## Wstęp
SmartArt w programie PowerPoint to zaawansowana funkcja umożliwiająca tworzenie atrakcyjnych wizualnie diagramów. Aspose.Slides for Java zapewnia kompleksową obsługę programowego manipulowania elementami SmartArt. W tym samouczku przeprowadzimy Cię przez proces zmiany tekstu w węźle SmartArt przy użyciu języka Java.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
- Biblioteka Aspose.Slides for Java pobrana i przywoływana w projekcie Java.
- Podstawowa znajomość programowania w języku Java.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety, aby uzyskać dostęp do funkcjonalności Aspose.Slides w kodzie Java.
```java
import com.aspose.slides.*;
```
Podzielmy przykład na wiele kroków:
## Krok 1: Zainicjuj obiekt prezentacji
```java
Presentation presentation = new Presentation();
```
 Utwórz nową instancję`Presentation` klasie do pracy z prezentacją w programie PowerPoint.
## Krok 2: Dodaj grafikę SmartArt do slajdu
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
 Dodaj grafikę SmartArt do pierwszego slajdu. W tym przykładzie używamy`BasicCycle` układ.
## Krok 3: Uzyskaj dostęp do węzła SmartArt
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
Uzyskaj odwołanie do drugiego węzła głównego grafiki SmartArt.
## Krok 4: Ustaw tekst w węźle
```java
node.getTextFrame().setText("Second root node");
```
Ustaw tekst dla wybranego węzła grafiki SmartArt.
## Krok 5: Zapisz prezentację
```java
presentation.save(dataDir + "ChangeText_On_SmartArt_Node_out.pptx", SaveFormat.Pptx);
```
Zapisz zmodyfikowaną prezentację w określonej lokalizacji.

## Wniosek
W tym samouczku pokazaliśmy, jak zmienić tekst w węźle SmartArt przy użyciu języka Java i Aspose.Slides. Dzięki tej wiedzy możesz dynamicznie manipulować elementami SmartArt w prezentacjach programu PowerPoint, poprawiając ich atrakcyjność wizualną i przejrzystość.
## Często zadawane pytania
### Czy mogę zmienić układ grafiki SmartArt po dodaniu jej do slajdu?
 Tak, możesz zmienić układ, uzyskując dostęp do`SmartArt.setAllNodes(LayoutType)` metoda.
### Czy Aspose.Slides jest kompatybilny z Java 11?
Tak, Aspose.Slides for Java jest kompatybilny z Java 11 i nowszymi wersjami.
### Czy mogę programowo dostosować wygląd węzłów SmartArt?
Z pewnością możesz modyfikować różne właściwości, takie jak kolor, rozmiar i kształt, za pomocą interfejsu API Aspose.Slides.
### Czy Aspose.Slides obsługuje inne typy układów SmartArt?
Tak, Aspose.Slides obsługuje szeroką gamę układów SmartArt, dzięki czemu możesz wybrać ten, który najlepiej odpowiada Twoim potrzebom w zakresie prezentacji.
### Gdzie mogę znaleźć więcej zasobów i wsparcia dla Aspose.Slides?
 Możesz odwiedzić[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/) szczegółowe odniesienia do API i samouczki. Dodatkowo możesz zwrócić się o pomoc do[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) lub rozważ zakup[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) za profesjonalne wsparcie.