---
title: Dodaj przesunięcie rozciągania dla wypełnienia obrazem w programie PowerPoint
linktitle: Dodaj przesunięcie rozciągania dla wypełnienia obrazem w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodać przesunięcie rozciągania do wypełnienia obrazem w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla Java. W zestawie tutorial krok po kroku.
weight: 16
url: /pl/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj przesunięcie rozciągania dla wypełnienia obrazem w programie PowerPoint

## Wstęp
W tym samouczku dowiesz się, jak używać Aspose.Slides dla Java, aby dodać przesunięcie rozciągania przy wypełnianiu obrazu w prezentacjach programu PowerPoint. Ta funkcja umożliwia manipulowanie obrazami na slajdach, co daje większą kontrolę nad ich wyglądem.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2. Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w projekcie Java.
## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Skonfiguruj katalog dokumentów
Zdefiniuj katalog, w którym znajduje się dokument programu PowerPoint:
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Utwórz obiekt prezentacji
Utwórz instancję klasy Prezentacja reprezentującą plik programu PowerPoint:
```java
Presentation pres = new Presentation();
```
## Krok 3: Dodaj obraz do slajdu
Pobierz pierwszy slajd i dodaj do niego obraz:
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## Krok 4: Dodaj ramkę do zdjęć
Utwórz ramkę na zdjęcie o wymiarach odpowiadających obrazowi:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## Krok 5: Zapisz prezentację
Zapisz zmodyfikowany plik PowerPoint:
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak dodać przesunięcie rozciągania do wypełnienia obrazem w programie PowerPoint przy użyciu Aspose.Slides dla Java. Ta funkcja otwiera mnóstwo możliwości ulepszania prezentacji za pomocą niestandardowych obrazów.
## Często zadawane pytania
### Czy mogę użyć tej metody do dodania obrazów do określonych slajdów w prezentacji?
Tak, możesz określić indeks slajdu podczas pobierania obiektu slajdu w celu skierowania go do określonego slajdu.
### Czy Aspose.Slides for Java obsługuje inne formaty obrazów oprócz JPEG?
Tak, Aspose.Slides for Java obsługuje różne formaty obrazów, w tym między innymi PNG, GIF i BMP.
### Czy istnieje ograniczenie rozmiaru obrazów, które mogę dodać za pomocą tej metody?
Aspose.Slides for Java może obsługiwać obrazy o różnych rozmiarach, ale zaleca się optymalizację obrazów w celu uzyskania lepszej wydajności w prezentacjach.
### Czy mogę zastosować dodatkowe efekty lub przekształcenia do obrazów po dodaniu ich do slajdów?
Tak, możesz zastosować szeroką gamę efektów i transformacji do obrazów, korzystając z rozbudowanego API Aspose.Slides for Java.
### Gdzie mogę znaleźć więcej zasobów i wsparcia dla Aspose.Slides dla Java?
 Możesz odwiedzić[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) aby uzyskać szczegółowe przewodniki i poznać[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za wsparcie społeczności.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
