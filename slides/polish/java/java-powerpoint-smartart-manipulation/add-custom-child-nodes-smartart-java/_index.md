---
title: Dodaj niestandardowe węzły podrzędne w SmartArt przy użyciu języka Java
linktitle: Dodaj niestandardowe węzły podrzędne w SmartArt przy użyciu języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać niestandardowe węzły podrzędne do grafiki SmartArt w prezentacjach programu PowerPoint przy użyciu języka Java z Aspose.Slides. Bez wysiłku wzbogacaj swoje slajdy profesjonalną grafiką.
weight: 11
url: /pl/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
SmartArt to zaawansowana funkcja programu PowerPoint, która umożliwia użytkownikom szybkie i łatwe tworzenie profesjonalnie wyglądającej grafiki. W tym samouczku dowiemy się, jak dodawać niestandardowe węzły podrzędne do grafiki SmartArt przy użyciu języka Java i Aspose.Slides.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java.
2.  Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Załaduj prezentację
Załaduj prezentację programu PowerPoint, do której chcesz dodać niestandardowe węzły podrzędne do grafiki SmartArt:
```java
String dataDir = "Your Document Directory";
// Załaduj żądaną prezentację
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Krok 2: Dodaj grafikę SmartArt do slajdu
Teraz dodajmy grafikę SmartArt do slajdu:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Krok 3: Przesuń kształt grafiki SmartArt
Przenieś kształt SmartArt do nowej pozycji:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(1);
ISmartArtShape shape = node.getShapes().get_Item(1);
shape.setX(shape.getX() + (shape.getWidth() * 2));
shape.setY(shape.getY() - (shape.getHeight() / 2));
```
## Krok 4: Zmień szerokość kształtu
Zmień szerokość kształtu SmartArt:
```java
node = smart.getAllNodes().get_Item(2);
shape = node.getShapes().get_Item(1);
shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));
```
## Krok 5: Zmień wysokość kształtu
Zmień wysokość kształtu SmartArt:
```java
node = smart.getAllNodes().get_Item(3);
shape = node.getShapes().get_Item(1);
shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));
```
## Krok 6: Obróć kształt
Obróć kształt SmartArt:
```java
node = smart.getAllNodes().get_Item(4);
shape = node.getShapes().get_Item(1);
shape.setRotation(90);
```
## Krok 7: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację:
```java
pres.save(dataDir + "ModifiedPresentation.pptx", SaveFormat.Pptx);
```

## Wniosek
W tym samouczku dowiedzieliśmy się, jak dodawać niestandardowe węzły podrzędne do grafiki SmartArt przy użyciu języka Java i Aspose.Slides. Wykonując poniższe kroki, możesz wzbogacić swoje prezentacje o niestandardową grafikę, dzięki czemu będą bardziej wciągające i profesjonalne.
## Często zadawane pytania
### Czy mogę dodawać różne typy układów SmartArt za pomocą Aspose.Slides dla Java?
Tak, Aspose.Slides for Java obsługuje różne układy SmartArt, dzięki czemu możesz wybrać ten, który najlepiej odpowiada Twoim potrzebom w zakresie prezentacji.
### Czy Aspose.Slides for Java jest kompatybilny z różnymi wersjami programu PowerPoint?
Aspose.Slides for Java został zaprojektowany tak, aby bezproblemowo współpracować z różnymi wersjami programu PowerPoint, zapewniając kompatybilność i spójność na różnych platformach.
### Czy mogę programowo dostosować wygląd kształtów SmartArt?
Absolutnie! Dzięki Aspose.Slides for Java możesz programowo dostosować wygląd, rozmiar, kolor i układ kształtów SmartArt do własnych preferencji projektowych.
### Czy Aspose.Slides for Java zapewnia dokumentację i wsparcie?
Tak, możesz znaleźć obszerną dokumentację i dostęp do forów wsparcia społeczności na stronie internetowej Aspose.
### Czy dostępna jest wersja próbna Aspose.Slides dla Java?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Slides dla Java ze strony internetowej, aby zapoznać się z jej funkcjami i możliwościami przed dokonaniem zakupu[Tutaj](https://releases.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
