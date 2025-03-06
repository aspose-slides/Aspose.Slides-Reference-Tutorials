---
title: Utwórz miniaturę kształtu obwiedni
linktitle: Utwórz miniaturę kształtu obwiedni
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak tworzyć miniatury kształtów z granicami za pomocą Aspose.Slides dla Java. Ten samouczek krok po kroku przeprowadzi Cię przez cały proces.
weight: 10
url: /pl/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Aspose.Slides for Java to potężna biblioteka, która umożliwia programistom Java programowe tworzenie, manipulowanie i konwertowanie prezentacji programu PowerPoint. W tym samouczku dowiemy się, jak utworzyć miniaturę kształtu z granicami za pomocą Aspose.Slides dla Java.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Biblioteka Aspose.Slides for Java pobrana i dodana do Twojego projektu. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Upewnij się, że zaimportowałeś niezbędne pakiety w kodzie Java:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Skonfiguruj swój projekt
Utwórz nowy projekt Java w preferowanym środowisku IDE i dodaj bibliotekę Aspose.Slides for Java do zależności swojego projektu.
## Krok 2: Utwórz instancję obiektu prezentacji
 Utwórz instancję a`Presentation` obiekt, podając ścieżkę do pliku prezentacji programu PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Krok 3: Utwórz miniaturę kształtu granic
Utwórzmy teraz miniaturę kształtu z granicami z prezentacji.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Wniosek
W tym samouczku nauczyliśmy się, jak utworzyć miniaturę kształtu z granicami za pomocą Aspose.Slides dla Java. Wykonując poniższe kroki, możesz łatwo programowo generować miniatury kształtów w prezentacjach programu PowerPoint.
## Często zadawane pytania
### Czy mogę tworzyć miniatury określonych kształtów na slajdzie?
Tak, możesz uzyskiwać dostęp do poszczególnych kształtów na slajdzie i generować dla nich miniatury za pomocą Aspose.Slides for Java.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami plików PowerPoint?
Aspose.Slides for Java obsługuje różne formaty plików PowerPoint, w tym PPT, PPTX, PPS, PPSX i inne.
### Czy mogę dostosować wygląd generowanych miniatur?
Tak, możesz dostosować właściwości miniatur, takie jak rozmiar i jakość, zgodnie ze swoimi wymaganiami.
### Czy Aspose.Slides for Java obsługuje inne funkcje poza generowaniem miniatur?
Tak, Aspose.Slides for Java zapewnia rozbudowaną funkcjonalność do pracy z prezentacjami programu PowerPoint, w tym manipulowanie slajdami, wyodrębnianie tekstu i generowanie wykresów.
### Czy dostępna jest wersja próbna Aspose.Slides dla Java?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
