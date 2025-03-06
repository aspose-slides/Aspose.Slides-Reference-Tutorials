---
title: Usuń węzeł w określonej pozycji w SmartArt
linktitle: Usuń węzeł w określonej pozycji w SmartArt
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak usunąć węzeł w określonej pozycji w SmartArt za pomocą Aspose.Slides dla Java. Zwiększ możliwości dostosowywania prezentacji bez wysiłku.
weight: 15
url: /pl/java/java-powerpoint-smartart-manipulation/remove-node-specific-position-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
dziedzinie programowania w języku Java Aspose.Slides jawi się jako potężne narzędzie do programowego manipulowania prezentacjami. Niezależnie od tego, czy tworzysz, modyfikujesz czy zarządzasz slajdami, Aspose.Slides dla Java zapewnia solidny zestaw funkcji efektywnie usprawniających te zadania. Jedną z takich typowych operacji jest usuwanie węzła w określonym miejscu obiektu SmartArt. W tym samouczku opisano krok po kroku proces realizacji tego za pomocą Aspose.Slides dla Java.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK w swoim systemie. Można go pobrać z[Tutaj](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides dla Java: Uzyskaj bibliotekę Aspose.Slides dla Java. Można go pobrać z[ten link](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Zainstaluj środowisko IDE, takie jak IntelliJ IDEA lub Eclipse, aby bezproblemowo pisać i wykonywać kod Java.

## Importuj pakiety
W swoim projekcie Java dołącz niezbędne pakiety, aby móc korzystać z funkcjonalności Aspose.Slides:
```java
import com.aspose.slides.*;
```
## Krok 1: Załaduj prezentację
Rozpocznij od załadowania pliku prezentacji, w którym istnieje obiekt SmartArt:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "RemoveNodeSpecificPosition.pptx");
```
## Krok 2: Przejdź przez kształty SmartArt
Przeglądaj każdy kształt w prezentacji, aby zidentyfikować obiekty SmartArt:
```java
for (IShape shape : pres.getSlides().get_Item(0).getShapes()) {
    if (shape instanceof ISmartArt) {
        ISmartArt smart = (ISmartArt) shape;
```
## Krok 3: Uzyskaj dostęp do węzła SmartArt
Uzyskaj dostęp do węzła SmartArt w żądanej pozycji:
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
Dzięki Aspose.Slides dla Java manipulowanie obiektami SmartArt w prezentacjach staje się prostym zadaniem. Wykonując opisane kroki, możesz bezproblemowo usuwać węzły w określonych pozycjach, zwiększając możliwości dostosowywania prezentacji.
## Często zadawane pytania
### Czy korzystanie z Aspose.Slides dla Java jest bezpłatne?
 Aspose.Slides for Java jest biblioteką komercyjną, ale możesz poznać jej funkcjonalności w ramach bezpłatnej wersji próbnej. Odwiedzać[ten link](https://releases.aspose.com/) rozpocząć.
### Gdzie mogę znaleźć pomoc dotyczącą zapytań związanych z Aspose.Slides?
 Aby uzyskać pomoc lub pytania, możesz odwiedzić forum Aspose.Slides[Tutaj](https://forum.aspose.com/c/slides/11).
### Czy mogę uzyskać tymczasową licencję na Aspose.Slides?
 Tak, możesz uzyskać licencję tymczasową od[Tutaj](https://purchase.aspose.com/temporary-license/) w celach ewaluacyjnych.
### Jak mogę kupić Aspose.Slides dla Java?
 Aby kupić Aspose.Slides dla Java, odwiedź stronę zakupu[Tutaj](https://purchase.aspose.com/buy).
### Gdzie mogę znaleźć szczegółową dokumentację Aspose.Slides dla Java?
 Możesz uzyskać dostęp do obszernej dokumentacji[Tutaj](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
