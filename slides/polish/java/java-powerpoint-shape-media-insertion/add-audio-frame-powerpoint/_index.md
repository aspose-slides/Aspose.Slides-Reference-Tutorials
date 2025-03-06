---
title: Dodaj ramkę audio w programie PowerPoint
linktitle: Dodaj ramkę audio w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać ramki audio do prezentacji programu PowerPoint za pomocą Aspose.Slides dla Java. Ulepsz swoje prezentacje dzięki wciągającym elementom audio bez wysiłku.
weight: 12
url: /pl/java/java-powerpoint-shape-media-insertion/add-audio-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Wzbogacanie prezentacji elementami audio może znacznie zwiększyć ich wpływ i zaangażowanie. Dzięki Aspose.Slides dla Java integracja klatek audio z prezentacjami programu PowerPoint staje się płynnym procesem. Ten samouczek poprowadzi Cię krok po kroku przez proces dodawania klatek audio do prezentacji przy użyciu Aspose.Slides dla Java.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że spełnione są następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java.
2.  Biblioteka Aspose.Slides dla Java: Pobierz i zainstaluj bibliotekę Aspose.Slides dla Java. Można go pobrać z[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).
3. Plik audio: Przygotuj plik audio (np. w formacie WAV), który chcesz dodać do swojej prezentacji.
## Importuj pakiety
Zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Krok 1: Skonfiguruj katalog projektu
Upewnij się, że masz skonfigurowaną strukturę katalogów dla swojego projektu. Jeśli nie, utwórz taki, aby efektywnie porządkować pliki.
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
## Krok 2: Utwórz instancję klasy prezentacji
 Utwórz instancję`Presentation` klasa reprezentująca prezentację programu PowerPoint.
```java
Presentation pres = new Presentation();
```
## Krok 3: Pobierz slajd i załaduj plik audio
Pobierz pierwszy slajd i załaduj plik audio ze swojego katalogu.
```java
ISlide sld = pres.getSlides().get_Item(0);
FileInputStream fstr = new FileInputStream(dataDir + "sampleaudio.wav");
```
## Krok 4: Dodaj ramkę audio
Dodaj ramkę audio do slajdu.
```java
IAudioFrame audioFrame = sld.getShapes().addAudioFrameEmbedded(50, 150, 100, 100, fstr);
```
## Krok 5: Ustaw właściwości audio
Ustaw właściwości, takie jak odtwarzanie między slajdami, przewijanie dźwięku do tyłu, tryb odtwarzania i głośność.
```java
audioFrame.setPlayAcrossSlides(true);
audioFrame.setRewindAudio(true);
audioFrame.setPlayMode(AudioPlayModePreset.Auto);
audioFrame.setVolume(AudioVolumeMode.Loud);
```
## Krok 6: Zapisz prezentację
Zapisz zmodyfikowaną prezentację z dodaną ramką audio.
```java
pres.save(dataDir + "AudioFrameEmbed_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Włączenie elementów audio do prezentacji programu PowerPoint może zwiększyć ich skuteczność i przyciągnąć uwagę odbiorców. Dzięki Aspose.Slides for Java proces dodawania klatek audio staje się łatwy, co pozwala na łatwe tworzenie dynamicznych i wciągających prezentacji.

## Często zadawane pytania
### Czy do mojej prezentacji mogę dodać pliki audio w różnych formatach?
Tak, Aspose.Slides for Java obsługuje różne formaty audio, w tym WAV, MP3 i inne.
### Czy można dostosować czas odtwarzania dźwięku na slajdach?
Absolutnie. Możesz zsynchronizować odtwarzanie dźwięku z określonymi przejściami slajdów za pomocą Aspose.Slides for Java.
### Czy Aspose.Slides dla Java zapewnia obsługę kompatybilności między platformami?
Tak, możesz tworzyć prezentacje programu PowerPoint z osadzonymi ramkami audio, które są kompatybilne na różnych platformach.
### Czy mogę dostosować wygląd odtwarzacza audio w prezentacji?
Aspose.Slides for Java oferuje szerokie możliwości dostosowywania, umożliwiając dostosowanie wyglądu odtwarzacza audio do własnych preferencji.
### Czy dostępna jest wersja próbna Aspose.Slides dla Java?
 Tak, możesz uzyskać dostęp do bezpłatnej wersji próbnej Aspose.Slides dla Java z ich strony[strona internetowa](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
