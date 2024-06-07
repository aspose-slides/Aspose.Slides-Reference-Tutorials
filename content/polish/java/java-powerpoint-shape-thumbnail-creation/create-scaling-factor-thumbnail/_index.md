---
title: Utwórz miniaturę współczynnika skalowania
linktitle: Utwórz miniaturę współczynnika skalowania
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak tworzyć miniatury współczynników skalowania w Javie przy użyciu Aspose.Slides dla Java. Łatwy w obsłudze przewodnik z instrukcjami krok po kroku.
type: docs
weight: 12
url: /pl/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---
## Wstęp
W tym samouczku przeprowadzimy Cię przez proces tworzenia miniatury współczynnika skalowania przy użyciu Aspose.Slides dla Java. Postępuj zgodnie z poniższymi instrukcjami krok po kroku, aby osiągnąć pożądany rezultat.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
- Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w projekcie Java.
- Podstawowa znajomość języka programowania Java.

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety wymagane do pracy z Aspose.Slides w swoim kodzie Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Podzielmy teraz podany przykład na kilka kroków:
## Krok 1: Ustaw katalog dokumentów
Zdefiniuj ścieżkę do katalogu dokumentów, w którym znajduje się plik prezentacji programu PowerPoint.
```java
String dataDir = "Your Document Directory";
```
 Zastępować`"Your Document Directory"` ze ścieżką do aktualnego katalogu dokumentów.
## Krok 2: Utwórz instancję obiektu prezentacji
Utwórz instancję klasy Prezentacja, która będzie reprezentować plik prezentacji programu PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Pamiętaj o wymianie`"HelloWorld.pptx"` z nazwą pliku prezentacji programu PowerPoint.
## Krok 3: Utwórz obraz w pełnej skali
Wygeneruj pełnowymiarowy obraz żądanego slajdu z prezentacji.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Ten kod pobiera miniaturę pierwszego kształtu na pierwszym slajdzie prezentacji.
## Krok 4: Zapisz obraz
Zapisz wygenerowany obraz na dysku w formacie PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Pamiętaj o wymianie`"Scaling Factor Thumbnail_out.png"` z żądaną nazwą pliku wyjściowego.

## Wniosek
Podsumowując, pomyślnie utworzyłeś miniaturę współczynnika skalowania za pomocą Aspose.Slides dla Java. Wykonując podane kroki, możesz łatwo zintegrować tę funkcjonalność z aplikacjami Java.
## Często zadawane pytania
### Czy mogę używać Aspose.Slides for Java z dowolnym Java IDE?
Tak, Aspose.Slides for Java może być używany z dowolnym zintegrowanym środowiskiem programistycznym Java (IDE), takim jak Eclipse, IntelliJ IDEA lub NetBeans.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla Java?
 Tak, możesz skorzystać z bezpłatnej wersji próbnej Aspose.Slides dla Java, odwiedzając stronę[strona internetowa](https://releases.aspose.com/).
### Gdzie mogę znaleźć pomoc dotyczącą Aspose.Slides dla Java?
 Wsparcie dla Aspose.Slides dla Java znajdziesz na stronie[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Jak mogę kupić Aspose.Slides dla Java?
 Możesz kupić Aspose.Slides dla Java w sklepie[strona zakupu](https://purchase.aspose.com/buy).
### Czy potrzebuję tymczasowej licencji na korzystanie z Aspose.Slides dla Java?
 Tak, możesz uzyskać tymczasową licencję od[strona licencji tymczasowej](https://purchase.aspose.com/temporary-license/).