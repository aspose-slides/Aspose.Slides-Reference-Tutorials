---
"description": "Dowiedz się, jak ulepszyć prezentacje programu PowerPoint, dodając klatki wideo ze źródeł internetowych za pomocą Aspose.Slides dla Java."
"linktitle": "Dodaj klatkę wideo ze źródła internetowego w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Dodaj klatkę wideo ze źródła internetowego w programie PowerPoint"
"url": "/pl/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj klatkę wideo ze źródła internetowego w programie PowerPoint

## Wstęp
tym samouczku nauczymy się, jak dodać klatkę wideo ze źródła internetowego, takiego jak YouTube, do prezentacji PowerPoint przy użyciu Aspose.Slides dla Java. Postępując zgodnie z tymi instrukcjami krok po kroku, będziesz w stanie ulepszyć swoje prezentacje, włączając angażujące elementy multimedialne.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w Javie.
- JDK (Java Development Kit) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java została pobrana i dodana do Twojego projektu Java. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).
- Aktywne połączenie internetowe umożliwiające dostęp do źródła internetowego (np. YouTube).

## Importuj pakiety
Najpierw zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.IVideoFrame;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.VideoPlayModePreset;

import java.io.ByteArrayOutputStream;
import java.io.IOException;
import java.io.InputStream;
import java.net.URL;
import java.net.URLConnection;
```
## Krok 1: Utwórz obiekt prezentacji PowerPoint
Zainicjuj obiekt Presentation, który reprezentuje prezentację programu PowerPoint:
```java
Presentation pres = new Presentation();
```
## Krok 2: Dodaj klatkę wideo
Teraz dodajmy klatkę wideo do prezentacji. Ta klatka będzie zawierać wideo ze źródła internetowego. Użyjemy metody addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
Zastąp „VIDEO_ID” identyfikatorem filmu YouTube, który chcesz osadzić.
## Krok 3: Ustaw tryb odtwarzania wideo
Ustaw tryb odtwarzania dla klatki wideo. W tym przykładzie ustawimy go na Auto:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## Krok 4: Załaduj miniaturę
Aby poprawić atrakcyjność wizualną, załadujemy miniaturę wideo. Ten krok obejmuje pobranie obrazu miniatury ze źródła internetowego:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=ID_WIDEO";
URL url = new URL(thumbnailUri);
URLConnection connection = url.openConnection();
connection.setConnectTimeout(5000);
connection.setReadTimeout(10000);
try (InputStream input = connection.getInputStream();
     ByteArrayOutputStream output = new ByteArrayOutputStream()) {
    byte[] buffer = new byte[8192];
    for (int count; (count = input.read(buffer)) > 0;) {
        output.write(buffer, 0, count);
    }
    output.toByteArray();
    videoFrame.getPictureFormat().getPicture().setImage(pres.getImages().addImage(output.toByteArray()));
}
```
## Krok 5: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację:
```java
pres.save("YOUR_DIRECTORY/AddVideoFrameFromWebSource_out.pptx", SaveFormat.Pptx);
```
Zastąp „YOUR_DIRECTORY” katalogiem, w którym chcesz zapisać prezentację.

## Wniosek
Gratulacje! Udało Ci się nauczyć, jak dodać klatkę wideo ze źródła internetowego w programie PowerPoint przy użyciu Aspose.Slides dla Java. Włączenie elementów multimedialnych, takich jak filmy, może znacznie zwiększyć wpływ i zaangażowanie Twoich prezentacji.
## Najczęściej zadawane pytania
### Czy mogę dodać filmy ze źródeł innych niż YouTube?
Tak, możesz dodawać filmy z różnych źródeł internetowych, pod warunkiem, że zawierają one link umożliwiający osadzenie.
### Czy do odtworzenia osadzonego filmu potrzebuję połączenia z Internetem?
Tak, do strumieniowego przesyłania wideo ze źródła internetowego wymagane jest aktywne połączenie z Internetem.
### Czy mogę dostosować wygląd klatki wideo?
Oczywiście! Aspose.Slides zapewnia rozbudowane opcje dostosowywania wyglądu i zachowania klatek wideo.
### Czy Aspose.Slides jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides obsługuje szeroką gamę wersji programu PowerPoint, zapewniając kompatybilność na różnych platformach.
### Gdzie mogę znaleźć więcej materiałów i pomocy dla Aspose.Slides?
Możesz odwiedzić [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) w celu uzyskania pomocy, dokumentacji i wsparcia społeczności.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}