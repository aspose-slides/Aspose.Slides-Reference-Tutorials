---
title: Dodaj ramkę obrazu o względnej wysokości w programie PowerPoint
linktitle: Dodaj ramkę obrazu o względnej wysokości w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać ramki obrazów o względnej wysokości w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java, poprawiając zawartość wizualną.
weight: 15
url: /pl/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W tym samouczku dowiesz się, jak dodać ramkę obrazu ze względną wysokością w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2. Biblioteka Aspose.Slides for Java pobrana i dodana do projektu Java.

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Skonfiguruj swój projekt
Najpierw upewnij się, że masz skonfigurowany katalog dla swojego projektu i że środowisko Java jest prawidłowo skonfigurowane.
## Krok 2: Utwórz instancję obiektu prezentacji
Utwórz nowy obiekt prezentacji za pomocą Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Krok 3: Załaduj obraz, który chcesz dodać
Załaduj obraz, który chcesz dodać do prezentacji:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Krok 4: Dodaj ramkę obrazu do slajdu
Dodaj ramkę obrazu do slajdu w prezentacji:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Krok 5: Ustaw względną szerokość i wysokość skali
Ustaw względną szerokość i wysokość skali dla ramki obrazu:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Krok 6: Zapisz prezentację
Zapisz prezentację z dodaną ramką na zdjęcie:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Wykonując poniższe kroki, możesz łatwo dodać ramkę obrazu o względnej wysokości w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Eksperymentuj z różnymi wartościami skali, aby uzyskać pożądany wygląd obrazów.

## Często zadawane pytania
### Czy przy użyciu tej metody mogę dodać wiele ramek do jednego slajdu?
Tak, możesz dodać wiele ramek obrazów do slajdu, powtarzając proces dla każdego obrazu.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides for Java jest kompatybilny z różnymi wersjami programu PowerPoint, zapewniając elastyczność w tworzeniu prezentacji.
### Czy mogę dostosować położenie i rozmiar ramki na zdjęcia?
 Oczywiście możesz dostosować parametry pozycji i rozmiaru w pliku`addPictureFrame` metodę dostosowaną do Twoich wymagań.
### Czy Aspose.Slides for Java obsługuje inne formaty obrazów oprócz JPEG?
Tak, Aspose.Slides for Java obsługuje różne formaty obrazów, w tym PNG, GIF, BMP i inne.
### Czy dla użytkowników Aspose.Slides dostępne jest forum społecznościowe lub kanał wsparcia?
Tak, możesz odwiedzić forum Aspose.Slides w przypadku jakichkolwiek pytań, dyskusji lub pomocy dotyczącej biblioteki.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
