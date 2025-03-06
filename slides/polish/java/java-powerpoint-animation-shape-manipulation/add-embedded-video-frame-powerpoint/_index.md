---
title: Dodaj osadzoną ramkę wideo w programie PowerPoint
linktitle: Dodaj osadzoną ramkę wideo w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak osadzać klatki wideo w programie PowerPoint przy użyciu Aspose.Slides dla Java, korzystając z tego samouczka krok po kroku. Z łatwością ulepszaj swoje prezentacje.
weight: 21
url: /pl/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Dodawanie filmów do prezentacji programu PowerPoint może uczynić je bardziej wciągającymi i pouczającymi. Używając Aspose.Slides dla Java, możesz łatwo osadzać filmy bezpośrednio w swoich slajdach. W tym samouczku przeprowadzimy Cię przez proces krok po kroku, upewniając się, że rozumiesz każdą część kodu i jego działanie. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik pomoże Ci ulepszyć swoje prezentacje za pomocą osadzonych filmów.
## Warunki wstępne
Zanim zagłębisz się w kod, upewnij się, że spełnione są następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK na swoim komputerze.
2. Aspose.Slides dla Java: Pobierz i zainstaluj bibliotekę Aspose.Slides dla Java.
3. Zintegrowane środowisko programistyczne (IDE): Użyj IDE, takiego jak IntelliJ IDEA lub Eclipse, aby uzyskać lepsze doświadczenia programistyczne.
4. Plik wideo: Przygotuj plik wideo, który chcesz osadzić w prezentacji programu PowerPoint.
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do pracy z Aspose.Slides. Importy te pomogą Ci zarządzać slajdami, filmami i plikami prezentacji.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Krok 1: Skonfiguruj swoje środowisko
Zanim zaczniesz kodować, upewnij się, że środowisko jest poprawnie skonfigurowane. Wiąże się to z utworzeniem niezbędnych katalogów i przygotowaniem pliku wideo.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Krok 2: Utwórz instancję klasy prezentacji
 Utwórz instancję`Presentation` klasa. Ta klasa reprezentuje plik programu PowerPoint.
```java
// Klasa prezentacji natychmiastowej reprezentująca PPTX
Presentation pres = new Presentation();
```
## Krok 3: Zdobądź pierwszy slajd
Uzyskaj dostęp do pierwszego slajdu prezentacji, w którym osadzisz wideo.
```java
// Zdobądź pierwszy slajd
ISlide sld = pres.getSlides().get_Item(0);
```
## Krok 4: Dodaj wideo do prezentacji
Osadź plik wideo w prezentacji. Upewnij się, że ścieżka wideo została poprawnie określona.
```java
// Osadź wideo w prezentacji
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Krok 5: Dodaj klatkę wideo do slajdu
Utwórz klatkę wideo na slajdzie i ustaw jej wymiary oraz położenie.
```java
// Dodaj klatkę wideo
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Krok 6: Skonfiguruj właściwości ramki wideo
Ustaw wideo w klatce wideo i skonfiguruj jego ustawienia odtwarzania, takie jak tryb odtwarzania i głośność.
```java
// Ustaw wideo na klatkę wideo
vf.setEmbeddedVideo(vid);
// Ustaw tryb odtwarzania i głośność wideo
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Krok 7: Zapisz prezentację
Zapisz prezentację z osadzonym wideo w określonym katalogu.
```java
// Zapisz plik PPTX na dysku
pres.save(resultPath, SaveFormat.Pptx);
```
## Krok 8: Oczyść zasoby
Na koniec pozbądź się obiektu prezentacji, aby zwolnić zasoby.
```java
// Pozbądź się przedmiotu prezentacji
if (pres != null) pres.dispose();
```
## Wniosek
Osadzanie wideo w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla Java jest prostym procesem. Wykonując czynności opisane w tym przewodniku, możesz wzbogacić swoje prezentacje o angażującą treść wideo. Pamiętaj, że praktyka czyni mistrza, więc spróbuj osadzać różne filmy i dostosowywać ich właściwości, aby zobaczyć, co najlepiej odpowiada Twoim potrzebom.
## Często zadawane pytania
### Czy mogę osadzić wiele filmów na jednym slajdzie?
Tak, możesz osadzić wiele filmów na jednym slajdzie, dodając wiele klatek wideo.
### Jak mogę sterować odtwarzaniem wideo?
 Odtwarzaniem można sterować za pomocą przycisku`setPlayMode` I`setVolume` metody`IVideoFrame` klasa.
### Jakie formaty wideo są obsługiwane przez Aspose.Slides?
Aspose.Slides obsługuje różne formaty wideo, w tym MP4, AVI i WMV.
### Czy potrzebuję licencji, aby korzystać z Aspose.Slides?
Tak, potrzebujesz ważnej licencji, aby korzystać z Aspose.Slides. Możesz uzyskać tymczasową licencję do oceny.
### Czy mogę dostosować rozmiar i położenie klatki wideo?
Tak, możesz dostosować rozmiar i położenie, ustawiając odpowiednie parametry podczas dodawania klatki wideo.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
