---
title: Ustaw format wypełnienia punktorem w SmartArt przy użyciu języka Java
linktitle: Ustaw format wypełnienia punktorem w SmartArt przy użyciu języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić format wypełnienia punktorem w SmartArt przy użyciu języka Java z Aspose.Slides. Przewodnik krok po kroku dotyczący skutecznej manipulacji prezentacją.
type: docs
weight: 18
url: /pl/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---
## Wstęp
dziedzinie programowania w języku Java sprawna manipulacja prezentacjami jest powszechnym wymogiem, szczególnie w przypadku elementów SmartArt. Aspose.Slides for Java okazuje się potężnym narzędziem do takich zadań, oferującym szereg funkcji do programowej obsługi prezentacji. W tym samouczku szczegółowo omówimy proces ustawiania formatu wypełnienia punktorem w SmartArt przy użyciu języka Java z Aspose.Slides.
## Warunki wstępne
Zanim przejdziemy do tego samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
### Zestaw programistyczny Java (JDK)
 Musisz mieć zainstalowany JDK w swoim systemie. Można go pobrać z[strona internetowa](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) i postępuj zgodnie z instrukcją instalacji.
### Aspose.Slides dla Java
 Pobierz i zainstaluj Aspose.Slides dla Java z[link do pobrania](https://releases.aspose.com/slides/java/). Postępuj zgodnie z instrukcjami instalacji zawartymi w dokumentacji konkretnego systemu operacyjnego.

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Podzielmy podany przykład na wiele kroków, aby lepiej zrozumieć, jak ustawić format wypełnienia punktorem w SmartArt przy użyciu języka Java i Aspose.Slides.
## Krok 1: Utwórz obiekt prezentacji
```java
Presentation presentation = new Presentation();
```
Najpierw utwórz nową instancję klasy Prezentacja, która reprezentuje prezentację programu PowerPoint.
## Krok 2: Dodaj grafikę SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Następnie dodaj kształt SmartArt do slajdu. Ten wiersz kodu inicjuje nowy kształt SmartArt z określonymi wymiarami i układem.
## Krok 3: Uzyskaj dostęp do węzła SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Teraz uzyskaj dostęp do pierwszego węzła (lub dowolnego żądanego węzła) w kształcie grafiki SmartArt, aby zmodyfikować jego właściwości.
## Krok 4: Ustaw format wypełnienia punktorem
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Tutaj sprawdzamy, czy format wypełnienia punktorem jest obsługiwany. Jeśli tak, ładujemy plik obrazu i ustawiamy go jako wypełnienie punktora dla węzła SmartArt.
## Krok 5: Zapisz prezentację
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Na koniec zapisz zmodyfikowaną prezentację w określonej lokalizacji.

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się ustawiać format wypełnienia punktorem w SmartArt przy użyciu języka Java z Aspose.Slides. Ta funkcja otwiera świat możliwości dynamicznych i atrakcyjnych wizualnie prezentacji w aplikacjach Java.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides for Java do tworzenia prezentacji od podstaw?
Absolutnie! Aspose.Slides zapewnia kompleksowe interfejsy API do tworzenia, modyfikowania i manipulowania prezentacjami całkowicie za pomocą kodu.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami programu PowerPoint?
Tak, Aspose.Slides zapewnia kompatybilność z różnymi wersjami programu Microsoft PowerPoint, umożliwiając bezproblemową integrację z przepływem pracy.
### Czy mogę dostosować elementy SmartArt poza formatem punktorów?
Rzeczywiście, Aspose.Slides umożliwia dostosowanie każdego aspektu kształtów SmartArt, w tym układu, stylu, zawartości i innych.
### Czy dostępna jest wersja próbna Aspose.Slides dla Java?
 Tak, możesz poznać funkcje Aspose.Slides w ramach bezpłatnej wersji próbnej. Po prostu pobierz go z[strona internetowa](https://releases.aspose.com/slides/java/) i zacznij odkrywać.
### Gdzie mogę znaleźć pomoc dotyczącą Aspose.Slides dla Java?
 W przypadku jakichkolwiek pytań lub pomocy możesz odwiedzić forum Aspose.Slides pod adresem[ten link](https://forum.aspose.com/c/slides/11).