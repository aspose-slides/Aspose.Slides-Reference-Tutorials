---
"description": "Dowiedz się, jak płynnie integrować treści wideo z prezentacjami PowerPoint za pomocą Aspose.Slides for Java. Twoje slajdy z elementami multimedialnymi, które angażują odbiorców."
"linktitle": "Dodaj klatkę wideo w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodaj klatkę wideo w programie PowerPoint"
"url": "/pl/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj klatkę wideo w programie PowerPoint

## Wstęp
W tym samouczku przeprowadzimy Cię przez proces dodawania klatki wideo do prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Postępując zgodnie z tymi instrukcjami krok po kroku, będziesz w stanie bezproblemowo zintegrować zawartość wideo ze swoimi prezentacjami.
## Wymagania wstępne
Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w Twoim systemie
- Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w projekcie Java
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety, aby móc korzystać z funkcjonalności Aspose.Slides w kodzie Java. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## Krok 1: Skonfiguruj katalog dokumentów
Upewnij się, że utworzono katalog, w którym będziesz przechowywać pliki programu PowerPoint.
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Utwórz obiekt prezentacji
Utwórz instancję `Presentation` Klasa reprezentująca plik programu PowerPoint.
```java
Presentation pres = new Presentation();
```
## Krok 3: Dodaj klatkę wideo do slajdu
Wybierz pierwszy slajd i dodaj do niego klatkę wideo.
```java
ISlide sld = pres.getSlides().get_Item(0);
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 150, dataDir + "video1.avi");
```
## Krok 4: Ustaw tryb odtwarzania i głośność
Ustaw tryb odtwarzania i głośność klatki wideo.
```java
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Krok 5: Zapisz prezentację
Zapisz zmodyfikowany plik programu PowerPoint na dysku.
```java
pres.save(dataDir + "VideoFrame_out.pptx", SaveFormat.Pptx);
```
## Wniosek
Gratulacje! Udało Ci się nauczyć, jak dodać klatkę wideo do prezentacji PowerPoint za pomocą Aspose.Slides dla Java. Ulepsz swoje prezentacje, włączając elementy multimedialne, aby skutecznie zaangażować odbiorców.
## Najczęściej zadawane pytania
### Czy do prezentacji PowerPoint mogę dodać filmy w dowolnym formacie?
Aspose.Slides obsługuje różne formaty wideo, takie jak AVI, WMV, MP4 i inne. Upewnij się, że format jest zgodny z programem PowerPoint.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami Java?
Tak, Aspose.Slides for Java jest kompatybilny z JDK w wersji 6 i nowszych.
### Jak mogę dostosować rozmiar i położenie klatki wideo?
Możesz dostosować wymiary i współrzędne klatki wideo, modyfikując parametry w `addVideoFrame` metoda.
### Czy mogę kontrolować ustawienia odtwarzania wideo?
Tak, możesz ustawić tryb odtwarzania i głośność klatki wideo według własnych preferencji.
### Gdzie mogę znaleźć więcej pomocy i zasobów dotyczących Aspose.Slides?
Odwiedź [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) w celu uzyskania pomocy, dokumentacji i wsparcia społeczności.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}