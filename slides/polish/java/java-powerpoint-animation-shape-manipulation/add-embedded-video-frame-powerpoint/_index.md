---
"description": "Dowiedz się, jak osadzać klatki wideo w programie PowerPoint za pomocą Aspose.Slides dla Java dzięki temu samouczkowi krok po kroku. Ulepsz swoje prezentacje w prosty sposób."
"linktitle": "Dodaj osadzoną klatkę wideo w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodaj osadzoną klatkę wideo w programie PowerPoint"
"url": "/pl/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj osadzoną klatkę wideo w programie PowerPoint

## Wstęp
Dodawanie filmów do prezentacji PowerPoint może sprawić, że będą bardziej angażujące i pouczające. Używając Aspose.Slides for Java, możesz łatwo osadzać filmy bezpośrednio w slajdach. W tym samouczku przeprowadzimy Cię przez proces krok po kroku, upewniając się, że rozumiesz każdą część kodu i sposób jego działania. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik pomoże Ci ulepszyć prezentacje za pomocą osadzonych filmów.
## Wymagania wstępne
Zanim zaczniesz pisać kod, upewnij się, że spełnione są następujące wymagania wstępne:
1. Java Development Kit (JDK): Upewnij się, że na Twoim komputerze jest zainstalowany JDK.
2. Aspose.Slides dla Java: Pobierz i zainstaluj bibliotekę Aspose.Slides dla Java.
3. Zintegrowane środowisko programistyczne (IDE): Użyj środowiska IDE, takiego jak IntelliJ IDEA lub Eclipse, aby zapewnić sobie lepsze warunki do tworzenia oprogramowania.
4. Plik wideo: Posiadasz plik wideo, który chcesz osadzić w prezentacji programu PowerPoint.
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety, aby pracować z Aspose.Slides. Te importy pomogą Ci zarządzać slajdami, filmami i plikami prezentacji.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Krok 1: Skonfiguruj swoje środowisko
Zanim zaczniesz kodować, upewnij się, że Twoje środowisko jest poprawnie skonfigurowane. Obejmuje to utworzenie niezbędnych katalogów i przygotowanie pliku wideo.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Utwórz katalog, jeśli jeszcze go nie ma.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Krok 2: Utwórz klasę prezentacji
Utwórz instancję `Presentation` klasa. Ta klasa reprezentuje Twój plik PowerPoint.
```java
// Utwórz klasę prezentacji reprezentującą PPTX
Presentation pres = new Presentation();
```
## Krok 3: Pobierz pierwszy slajd
Przejdź do pierwszego slajdu prezentacji, w którym chcesz osadzić wideo.
```java
// Zobacz pierwszy slajd
ISlide sld = pres.getSlides().get_Item(0);
```
## Krok 4: Dodaj wideo do prezentacji
Osadź plik wideo w prezentacji. Upewnij się, że ścieżka wideo jest poprawnie określona.
```java
// Osadź wideo w prezentacji
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Krok 5: Dodaj klatkę wideo do slajdu
Utwórz klatkę wideo na slajdzie i ustaw jej wymiary oraz pozycję.
```java
// Dodaj klatkę wideo
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Krok 6: Skonfiguruj właściwości klatki wideo
Wskaż klatkę wideo i skonfiguruj ustawienia odtwarzania, takie jak tryb odtwarzania i głośność.
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
Na koniec usuń obiekt prezentacji, aby zwolnić zasoby.
```java
// Usuń obiekt prezentacji
if (pres != null) pres.dispose();
```
## Wniosek
Osadzanie wideo w prezentacjach PowerPoint przy użyciu Aspose.Slides for Java to prosty proces. Postępując zgodnie z krokami opisanymi w tym przewodniku, możesz wzbogacić swoje prezentacje o angażującą zawartość wideo. Pamiętaj, że praktyka czyni mistrza, więc spróbuj osadzić różne filmy i dostosować ich właściwości, aby zobaczyć, co najlepiej odpowiada Twoim potrzebom.
## Najczęściej zadawane pytania
### Czy mogę osadzić wiele filmów na jednym slajdzie?
Tak, możesz osadzić wiele filmów na jednym slajdzie, dodając wiele klatek wideo.
### Jak mogę sterować odtwarzaniem filmu?
Odtwarzaniem można sterować za pomocą `setPlayMode` I `setVolume` metody `IVideoFrame` klasa.
### Jakie formaty wideo obsługuje Aspose.Slides?
Aspose.Slides obsługuje różne formaty wideo, w tym MP4, AVI i WMV.
### Czy potrzebuję licencji, aby korzystać z Aspose.Slides?
Tak, potrzebujesz ważnej licencji, aby używać Aspose.Slides. Możesz uzyskać tymczasową licencję do oceny.
### Czy mogę dostosować rozmiar i położenie klatki wideo?
Tak, możesz dostosować rozmiar i położenie, ustawiając odpowiednie parametry podczas dodawania klatki wideo.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}