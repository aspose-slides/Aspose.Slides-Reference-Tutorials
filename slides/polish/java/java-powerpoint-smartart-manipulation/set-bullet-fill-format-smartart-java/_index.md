---
"description": "Dowiedz się, jak ustawić format wypełniania punktorów w SmartArt przy użyciu Java z Aspose.Slides. Przewodnik krok po kroku do wydajnej manipulacji prezentacją."
"linktitle": "Ustaw format wypełnienia punktora w SmartArt za pomocą Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Ustaw format wypełnienia punktora w SmartArt za pomocą Java"
"url": "/pl/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Ustaw format wypełnienia punktora w SmartArt za pomocą Java

## Wstęp
W dziedzinie programowania Java, wydajna manipulacja prezentacjami jest powszechnym wymogiem, szczególnie w przypadku elementów SmartArt. Aspose.Slides dla Java wyłania się jako potężne narzędzie do takich zadań, oferując szereg funkcjonalności do obsługi prezentacji programowo. W tym samouczku zagłębimy się w proces ustawiania formatu wypełniania wypunktowania w SmartArt przy użyciu Java z Aspose.Slides, krok po kroku.
## Wymagania wstępne
Zanim rozpoczniesz ten samouczek, upewnij się, że spełnione są następujące wymagania wstępne:
### Zestaw narzędzi programistycznych Java (JDK)
Musisz mieć zainstalowany JDK w swoim systemie. Możesz go pobrać ze strony [strona internetowa](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) i postępuj zgodnie z instrukcją instalacji.
### Aspose.Slides dla Java
Pobierz i zainstaluj Aspose.Slides dla Java ze strony [link do pobrania](https://releases.aspose.com/slides/java/). Postępuj zgodnie z instrukcjami instalacji podanymi w dokumentacji dla Twojego konkretnego systemu operacyjnego.

## Importuj pakiety
Na początek zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Rozłóżmy podany przykład na kilka kroków, aby lepiej zrozumieć, jak ustawić format wypełnienia punktora w SmartArt za pomocą Java i Aspose.Slides.
## Krok 1: Utwórz obiekt prezentacji
```java
Presentation presentation = new Presentation();
```
Najpierw utwórz nową instancję klasy Presentation, która reprezentuje prezentację programu PowerPoint.
## Krok 2: Dodaj SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Następnie dodaj kształt SmartArt do slajdu. Ta linia kodu inicjuje nowy kształt SmartArt o określonych wymiarach i układzie.
## Krok 3: Uzyskaj dostęp do węzła SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Teraz uzyskaj dostęp do pierwszego węzła (lub dowolnego innego węzła) w kształcie SmartArt, aby zmodyfikować jego właściwości.
## Krok 4: Ustaw format wypełnienia punktora
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Tutaj sprawdzamy, czy format wypełnienia punktora jest obsługiwany. Jeśli tak, ładujemy plik obrazu i ustawiamy go jako wypełnienie punktora dla węzła SmartArt.
## Krok 5: Zapisz prezentację
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Na koniec zapisz zmodyfikowaną prezentację w określonej lokalizacji.

## Wniosek
Gratulacje! Udało Ci się nauczyć, jak ustawić format wypełniania punktorów w SmartArt przy użyciu Java z Aspose.Slides. Ta możliwość otwiera świat możliwości dla dynamicznych i wizualnie atrakcyjnych prezentacji w aplikacjach Java.
## Najczęściej zadawane pytania
### Czy mogę używać Aspose.Slides for Java do tworzenia prezentacji od podstaw?
Oczywiście! Aspose.Slides zapewnia kompleksowe API do tworzenia, modyfikowania i manipulowania prezentacjami całkowicie za pomocą kodu.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami programu PowerPoint?
Tak, Aspose.Slides gwarantuje zgodność z różnymi wersjami programu Microsoft PowerPoint, umożliwiając bezproblemową integrację z Twoim procesem pracy.
### Czy mogę dostosować elementy SmartArt poza formatem wypełnienia punktorem?
Dzięki Aspose.Slides możesz dostosować każdy aspekt kształtów SmartArt, w tym układ, styl, zawartość i nie tylko.
### Czy jest dostępna wersja próbna Aspose.Slides dla Java?
Tak, możesz zapoznać się z funkcjami Aspose.Slides dzięki bezpłatnej wersji próbnej. Wystarczy pobrać ją ze strony [strona internetowa](https://releases.aspose.com/slides/java/) i zacznij odkrywać.
### Gdzie mogę znaleźć pomoc techniczną dotyczącą Aspose.Slides dla Java?
W razie pytań lub potrzeby pomocy możesz odwiedzić forum Aspose.Slides pod adresem [ten link](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}