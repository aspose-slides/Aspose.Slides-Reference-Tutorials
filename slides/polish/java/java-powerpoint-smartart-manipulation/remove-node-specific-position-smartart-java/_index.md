---
"description": "Dowiedz się, jak usunąć węzeł w określonej pozycji w SmartArt przy użyciu Aspose.Slides dla Java. Ulepsz dostosowywanie prezentacji bez wysiłku."
"linktitle": "Usuń węzeł w określonej pozycji w SmartArt"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Usuń węzeł w określonej pozycji w SmartArt"
"url": "/pl/java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Usuń węzeł w określonej pozycji w SmartArt

## Wstęp
dziedzinie rozwoju Java, Aspose.Slides wyłania się jako potężne narzędzie do programowego manipulowania prezentacjami. Niezależnie od tego, czy chodzi o tworzenie, modyfikowanie czy zarządzanie slajdami, Aspose.Slides dla Java zapewnia solidny zestaw funkcji, aby usprawnić te zadania. Jedną z takich typowych operacji jest usuwanie węzła w określonej pozycji w obiekcie SmartArt. Ten samouczek zagłębia się w proces krok po kroku, aby osiągnąć to za pomocą Aspose.Slides dla Java.
## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
1. Java Development Kit (JDK): Upewnij się, że masz zainstalowany JDK w swoim systemie. Możesz go pobrać z [Tutaj](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2. Aspose.Slides dla Java: Pobierz bibliotekę Aspose.Slides dla Java. Możesz ją pobrać z [ten link](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Zainstalowanie środowiska IDE, np. IntelliJ IDEA lub Eclipse, umożliwi bezproblemowe pisanie i wykonywanie kodu Java.

## Importuj pakiety
swoim projekcie Java uwzględnij niezbędne pakiety, aby wykorzystać funkcjonalności Aspose.Slides:
```java
import com.aspose.slides.*;
```
## Krok 1: Załaduj prezentację
Zacznij od załadowania pliku prezentacji, w którym znajduje się obiekt SmartArt:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## Krok 2: Przechodzenie przez kształty SmartArt
Przejrzyj każdy kształt w prezentacji, aby zidentyfikować obiekty SmartArt:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## Krok 3: Uzyskaj dostęp do węzła SmartArt
Uzyskaj dostęp do węzła SmartArt w żądanym położeniu:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Krok 4: Usuń węzeł podrzędny
Usuń węzeł podrzędny w określonej pozycji:
```java
((ISmartArtNodeCollection) node.getChildNodes()).removeNode(1);
```
## Krok 5: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację:
```java
pres.save(dataDir + "RemoveSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Dzięki Aspose.Slides for Java manipulowanie obiektami SmartArt w prezentacjach staje się prostym zadaniem. Postępując zgodnie z opisanymi krokami, możesz bezproblemowo usuwać węzły w określonych pozycjach, zwiększając możliwości dostosowywania prezentacji.
## Najczęściej zadawane pytania
### Czy Aspose.Slides for Java jest darmowy?
Aspose.Slides for Java to komercyjna biblioteka, ale możesz zapoznać się z jej funkcjonalnościami dzięki bezpłatnej wersji próbnej. Odwiedź [ten link](https://releases.aspose.com/) aby zacząć.
### Gdzie mogę znaleźć pomoc dotyczącą zapytań związanych z Aspose.Slides?
W razie pytań lub potrzeby uzyskania pomocy możesz odwiedzić forum Aspose.Slides [Tutaj](https://forum.aspose.com/c/slides/11).
### Czy mogę uzyskać tymczasową licencję na Aspose.Slides?
Tak, możesz uzyskać tymczasową licencję od [Tutaj](https://purchase.aspose.com/temporary-license/) w celach ewaluacyjnych.
### Jak mogę zakupić Aspose.Slides dla Java?
Aby zakupić Aspose.Slides dla Java, odwiedź stronę zakupu [Tutaj](https://purchase.aspose.com/buy).
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Slides dla Java?
Możesz uzyskać dostęp do pełnej dokumentacji [Tutaj](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}