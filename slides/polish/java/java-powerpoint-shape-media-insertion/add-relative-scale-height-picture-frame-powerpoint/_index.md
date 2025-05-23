---
"description": "Dowiedz się, jak dodawać ramki obrazów o względnej skali wysokości w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla Java, wzbogacając w ten sposób swoją zawartość wizualną."
"linktitle": "Dodaj ramkę obrazu o względnej skali wysokości w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodaj ramkę obrazu o względnej skali wysokości w programie PowerPoint"
"url": "/pl/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj ramkę obrazu o względnej skali wysokości w programie PowerPoint

## Wstęp
W tym samouczku dowiesz się, jak dodać ramkę obrazu z uwzględnieniem względnej skali wysokości do prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java.
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że masz następujące rzeczy:
1. Java Development Kit (JDK) zainstalowany w Twoim systemie.
2. Biblioteka Aspose.Slides for Java została pobrana i dodana do projektu Java.

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
Najpierw upewnij się, że masz utworzony katalog dla swojego projektu i że środowisko Java jest prawidłowo skonfigurowane.
## Krok 2: Utwórz obiekt prezentacji
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
Dodaj ramkę obrazu do slajdu prezentacji:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Krok 5: Ustaw względną szerokość i wysokość skali
Ustaw względną skalę szerokości i wysokości ramki obrazu:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Krok 6: Zapisz prezentację
Zapisz prezentację z dodaną ramką obrazu:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Wykonując te kroki, możesz łatwo dodać ramkę obrazu z względną wysokością skali w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Eksperymentuj z różnymi wartościami skali, aby uzyskać pożądany wygląd obrazów.

## Najczęściej zadawane pytania
### Czy mogę dodać wiele ramek zdjęć do jednego slajdu, używając tej metody?
Tak, możesz dodać wiele ramek do slajdu, powtarzając ten proces dla każdego obrazu.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides for Java jest kompatybilny z różnymi wersjami programu PowerPoint, co zapewnia elastyczność podczas tworzenia prezentacji.
### Czy mogę dostosować położenie i rozmiar ramki na zdjęcie?
Oczywiście, możesz dostosować parametry położenia i rozmiaru w `addPictureFrame` metodę dostosowaną do Twoich potrzeb.
### Czy Aspose.Slides dla Java obsługuje inne formaty obrazów oprócz JPEG?
Tak, Aspose.Slides for Java obsługuje różne formaty obrazów, w tym PNG, GIF, BMP i inne.
### Czy istnieje forum społecznościowe lub kanał wsparcia dostępny dla użytkowników Aspose.Slides?
Tak, możesz odwiedzić forum Aspose.Slides, aby zadać pytania, porozmawiać lub uzyskać pomoc dotyczącą biblioteki.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}