---
"description": "Dowiedz się, jak tworzyć miniatury współczynnika skalowania w Javie przy użyciu Aspose.Slides dla Javy. Łatwy do naśladowania przewodnik z instrukcjami krok po kroku."
"linktitle": "Utwórz miniaturę współczynnika skalowania"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Utwórz miniaturę współczynnika skalowania"
"url": "/pl/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz miniaturę współczynnika skalowania

## Wstęp
W tym samouczku przeprowadzimy Cię przez proces tworzenia miniatury współczynnika skalowania przy użyciu Aspose.Slides dla Java. Postępuj zgodnie z tymi instrukcjami krok po kroku, aby uzyskać pożądany rezultat.
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że spełniasz następujące wymagania wstępne:
- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java została pobrana i skonfigurowana w projekcie Java.
- Podstawowa znajomość języka programowania Java.

## Importuj pakiety
Najpierw zaimportuj do kodu Java niezbędne pakiety potrzebne do pracy z Aspose.Slides. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Teraz rozłóżmy podany przykład na kilka kroków:
## Krok 1: Ustaw katalog dokumentów
Zdefiniuj ścieżkę do katalogu dokumentów, w którym znajduje się plik prezentacji PowerPoint.
```java
String dataDir = "Your Document Directory";
```
Zastępować `"Your Document Directory"` ze ścieżką do aktualnego katalogu dokumentów.
## Krok 2: Utwórz obiekt prezentacji
Utwórz instancję klasy Presentation, aby reprezentować plik prezentacji programu PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Upewnij się, że wymienisz `"HelloWorld.pptx"` z nazwą pliku prezentacji PowerPoint.
## Krok 3: Utwórz obraz w pełnej skali
Wygeneruj pełnowymiarowy obraz wybranego slajdu z prezentacji.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Ten kod pobiera miniaturę pierwszego kształtu na pierwszym slajdzie prezentacji.
## Krok 4: Zapisz obraz
Zapisz wygenerowany obraz na dysku w formacie PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Upewnij się, że wymienisz `"Scaling Factor Thumbnail_out.png"` z żądaną nazwą pliku wyjściowego.

## Wniosek
Podsumowując, udało Ci się utworzyć miniaturę współczynnika skalowania przy użyciu Aspose.Slides dla Java. Postępując zgodnie z podanymi krokami, możesz łatwo zintegrować tę funkcjonalność ze swoimi aplikacjami Java.
## Najczęściej zadawane pytania
### Czy mogę używać Aspose.Slides for Java z dowolnym środowiskiem IDE Java?
Tak, Aspose.Slides for Java można używać z dowolnym zintegrowanym środowiskiem programistycznym (IDE) Java, takim jak Eclipse, IntelliJ IDEA czy NetBeans.
### Czy jest dostępna bezpłatna wersja próbna Aspose.Slides for Java?
Tak, możesz skorzystać z bezpłatnej wersji próbnej Aspose.Slides dla Java, odwiedzając stronę [strona internetowa](https://releases.aspose.com/).
### Gdzie mogę znaleźć pomoc techniczną dotyczącą Aspose.Slides dla Java?
Pomoc dotyczącą Aspose.Slides dla języka Java można znaleźć na stronie [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Jak mogę zakupić Aspose.Slides dla Java?
Aspose.Slides dla Javy można zakupić w sklepie [strona zakupu](https://purchase.aspose.com/buy).
### Czy potrzebuję tymczasowej licencji, aby korzystać z Aspose.Slides dla Java?
Tak, możesz uzyskać tymczasową licencję od [tymczasowa strona licencji](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}