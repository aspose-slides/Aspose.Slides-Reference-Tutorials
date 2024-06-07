---
title: Wypełnianie kształtów obrazami w programie PowerPoint
linktitle: Wypełnianie kształtów obrazami w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak wypełniać kształty obrazami w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Zwiększ atrakcyjność wizualną bez wysiłku.
type: docs
weight: 12
url: /pl/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---
## Wstęp
Prezentacje programu PowerPoint często wymagają elementów wizualnych, takich jak kształty wypełnione obrazami, aby zwiększyć ich atrakcyjność i skutecznie przekazywać informacje. Aspose.Slides dla Java zapewnia potężny zestaw narzędzi do bezproblemowego wykonania tego zadania. W tym samouczku nauczymy się krok po kroku wypełniać kształty obrazkami za pomocą Aspose.Slides for Java.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Pobrano bibliotekę Aspose.Slides dla Java. Możesz to dostać od[Tutaj](https://releases.aspose.com/slides/java/).
3. Podstawowa znajomość programowania w języku Java.
## Importuj pakiety
W swoim projekcie Java zaimportuj niezbędne pakiety:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Skonfiguruj katalog projektu
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
 Pamiętaj o wymianie`"Your Document Directory"` ze ścieżką do katalogu projektu.
## Krok 2: Utwórz prezentację
```java
Presentation pres = new Presentation();
```
 Utwórz instancję`Presentation` klasie, aby utworzyć nową prezentację programu PowerPoint.
## Krok 3: Dodaj slajd i kształt
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Dodaj slajd do prezentacji i utwórz na nim kształt prostokąta.
## Krok 4: Ustaw typ wypełnienia na Obraz
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Ustaw typ wypełnienia kształtu na obraz.
## Krok 5: Ustaw tryb wypełniania obrazem
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Ustaw tryb wypełniania obrazem kształtu.
## Krok 6: Ustaw obraz
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Załaduj obraz i ustaw go jako wypełnienie kształtu.
## Krok 7: Zapisz prezentację
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Zapisz zmodyfikowaną prezentację do pliku.

## Wniosek
Dzięki Aspose.Slides dla Java wypełnianie kształtów obrazami w prezentacjach programu PowerPoint staje się prostym procesem. Wykonując kroki opisane w tym samouczku, możesz łatwo wzbogacić swoje prezentacje o atrakcyjne wizualnie elementy.

## Często zadawane pytania
### Czy mogę wypełnić różne kształty obrazkami za pomocą Aspose.Slides dla Java?
Tak, Aspose.Slides for Java obsługuje wypełnianie różnych kształtów obrazami, zapewniając elastyczność w projektowaniu.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides for Java generuje prezentacje kompatybilne z programem PowerPoint 97 i nowszymi, zapewniając szeroką kompatybilność.
### Jak zmienić rozmiar obrazu w kształcie?
Możesz zmienić rozmiar obrazu w kształcie, dostosowując wymiary kształtu lub odpowiednio skalując obraz przed ustawieniem go jako wypełnienia.
### Czy istnieją jakieś ograniczenia dotyczące formatów obrazów obsługiwanych przy wypełnianiu kształtów?
Aspose.Slides for Java obsługuje szeroką gamę formatów obrazów, w tym między innymi JPEG, PNG, GIF, BMP i TIFF.
### Czy mogę zastosować efekty do wypełnionych kształtów?
Tak, Aspose.Slides dla Java zapewnia kompleksowe interfejsy API umożliwiające zastosowanie różnych efektów, takich jak cienie, odbicia i obroty 3D, do wypełnionych kształtów.