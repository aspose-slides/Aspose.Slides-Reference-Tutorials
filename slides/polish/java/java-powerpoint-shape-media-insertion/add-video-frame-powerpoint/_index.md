---
title: Dodaj klatkę wideo w programie PowerPoint
linktitle: Dodaj klatkę wideo w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak bezproblemowo integrować zawartość wideo z prezentacjami programu PowerPoint za pomocą Aspose.Slides dla Java. Twoje slajdy z elementami multimedialnymi, które zaangażują odbiorców.
weight: 17
url: /pl/java/java-powerpoint-shape-media-insertion/add-video-frame-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
W tym samouczku przeprowadzimy Cię przez proces dodawania klatki wideo do prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java. Postępując zgodnie z tymi szczegółowymi instrukcjami, będziesz w stanie z łatwością bezproblemowo zintegrować treści wideo ze swoimi prezentacjami.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie
- Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w projekcie Java
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety, aby móc korzystać z funkcjonalności Aspose.Slides w swoim kodzie Java. 
```java
import com.aspose.slides.*;

import java.io.File;
```
## Krok 1: Skonfiguruj katalog dokumentów
Upewnij się, że masz skonfigurowany katalog do przechowywania plików programu PowerPoint.
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Utwórz obiekt prezentacji
 Utwórz instancję`Presentation` klasa reprezentująca plik programu PowerPoint.
```java
Presentation pres = new Presentation();
```
## Krok 3: Dodaj klatkę wideo do slajdu
Pobierz pierwszy slajd i dodaj do niego klatkę wideo.
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
Gratulacje! Pomyślnie nauczyłeś się, jak dodać klatkę wideo do prezentacji programu PowerPoint za pomocą Aspose.Slides for Java. Ulepsz swoje prezentacje, włączając elementy multimedialne, aby skutecznie zaangażować odbiorców.
## Często zadawane pytania
### Czy mogę dodać filmy w dowolnym formacie do prezentacji PowerPoint?
Aspose.Slides obsługuje różne formaty wideo, takie jak AVI, WMV, MP4 i inne. Upewnij się, że format jest zgodny z programem PowerPoint.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami Java?
Tak, Aspose.Slides dla Java jest kompatybilny z wersją JDK 6 i nowszą.
### Jak mogę dostosować rozmiar i położenie klatki wideo?
 Możesz dostosować wymiary i współrzędne klatki wideo, modyfikując parametry w pliku`addVideoFrame` metoda.
### Czy mogę kontrolować ustawienia odtwarzania wideo?
Tak, możesz ustawić tryb odtwarzania i głośność klatki wideo zgodnie ze swoimi preferencjami.
### Gdzie mogę znaleźć więcej wsparcia i zasobów dla Aspose.Slides?
 Odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za pomoc, dokumentację i wsparcie społeczności.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
