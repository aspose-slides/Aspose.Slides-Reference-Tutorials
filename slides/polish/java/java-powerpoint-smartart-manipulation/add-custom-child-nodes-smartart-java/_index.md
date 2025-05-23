---
"description": "Dowiedz się, jak dodawać niestandardowe węzły podrzędne do SmartArt w prezentacjach PowerPoint przy użyciu Java z Aspose.Slides. Ulepszaj swoje slajdy za pomocą profesjonalnych grafik bez wysiłku."
"linktitle": "Dodawanie niestandardowych węzłów podrzędnych w SmartArt przy użyciu Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodawanie niestandardowych węzłów podrzędnych w SmartArt przy użyciu Java"
"url": "/pl/java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodawanie niestandardowych węzłów podrzędnych w SmartArt przy użyciu Java

## Wstęp
SmartArt to potężna funkcja w programie PowerPoint, która umożliwia użytkownikom szybkie i łatwe tworzenie profesjonalnie wyglądających grafik. W tym samouczku nauczymy się, jak dodawać niestandardowe węzły podrzędne do SmartArt przy użyciu języka Java z Aspose.Slides.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że masz następujące rzeczy:
1. Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java.
2. Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java ze strony [Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Załaduj prezentację
Załaduj prezentację programu PowerPoint, do której chcesz dodać niestandardowe węzły podrzędne do obiektu SmartArt:
```java
String dataDir = "Your Document Directory";
// Załaduj wybraną prezentację
Presentation pres = new Presentation(dataDir + "YourPresentation.pptx");
```
## Krok 2: Dodaj SmartArt do slajdu
Teraz dodajmy SmartArt do slajdu:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);
```
## Krok 3: Przesuń kształt SmartArt
Przesuń kształt SmartArt do nowej pozycji:
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
tym samouczku nauczyliśmy się, jak dodawać niestandardowe węzły podrzędne do SmartArt za pomocą Java z Aspose.Slides. Wykonując te kroki, możesz ulepszyć swoje prezentacje za pomocą niestandardowych grafik, czyniąc je bardziej angażującymi i profesjonalnymi.
## Najczęściej zadawane pytania
### Czy mogę dodać różne typy układów SmartArt za pomocą Aspose.Slides dla Java?
Tak, Aspose.Slides for Java obsługuje różne układy SmartArt, umożliwiając wybór takiego, który najlepiej odpowiada potrzebom danej prezentacji.
### Czy Aspose.Slides for Java jest kompatybilny z różnymi wersjami programu PowerPoint?
Aspose.Slides for Java został zaprojektowany tak, aby bezproblemowo współpracować z różnymi wersjami programu PowerPoint, zapewniając kompatybilność i spójność na różnych platformach.
### Czy mogę programowo dostosować wygląd kształtów SmartArt?
Oczywiście! Dzięki Aspose.Slides for Java możesz programowo dostosować wygląd, rozmiar, kolor i układ kształtów SmartArt do swoich preferencji projektowych.
### Czy Aspose.Slides for Java udostępnia dokumentację i pomoc techniczną?
Tak, na stronie internetowej Aspose można znaleźć kompleksową dokumentację i uzyskać dostęp do forów wsparcia społeczności.
### Czy jest dostępna wersja próbna Aspose.Slides dla Java?
Tak, możesz pobrać bezpłatną wersję próbną Aspose.Slides dla Java ze strony internetowej, aby zapoznać się z jej funkcjami i możliwościami przed dokonaniem zakupu [Tutaj](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}