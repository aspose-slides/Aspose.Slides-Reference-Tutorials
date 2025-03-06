---
title: Dodaj klatkę wideo ze źródła internetowego w programie PowerPoint
linktitle: Dodaj klatkę wideo ze źródła internetowego w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ulepszyć prezentacje programu PowerPoint, dodając klatki wideo ze źródeł internetowych za pomocą Aspose.Slides dla Java.
weight: 18
url: /pl/java/java-powerpoint-shape-media-insertion/add-video-frame-web-source-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj klatkę wideo ze źródła internetowego w programie PowerPoint

## Wstęp
tym samouczku dowiemy się, jak dodać klatkę wideo ze źródła internetowego, takiego jak YouTube, do prezentacji programu PowerPoint za pomocą Aspose.Slides for Java. Postępując zgodnie z tymi szczegółowymi instrukcjami, będziesz w stanie ulepszyć swoje prezentacje poprzez dodanie angażujących elementów multimedialnych.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
- JDK (Java Development Kit) zainstalowany w twoim systemie.
-  Biblioteka Aspose.Slides for Java pobrana i dodana do projektu Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
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
## Krok 1: Utwórz obiekt prezentacji programu PowerPoint
Zainicjuj obiekt Prezentacja, który reprezentuje prezentację programu PowerPoint:
```java
Presentation pres = new Presentation();
```
## Krok 2: Dodaj klatkę wideo
Dodajmy teraz do prezentacji klatkę wideo. Ta ramka będzie zawierać wideo ze źródła internetowego. Użyjemy metody addVideoFrame:
```java
IVideoFrame videoFrame = pres.getSlides().get_Item(0).getShapes().addVideoFrame(10, 10, 427, 240, "https://www.youtube.com/embed/VIDEO_ID");
```
Zastąp „VIDEO_ID” identyfikatorem filmu z YouTube, który chcesz osadzić.
## Krok 3: Ustaw tryb odtwarzania wideo
Ustaw tryb odtwarzania klatki wideo. W tym przykładzie ustawimy to na Auto:
```java
videoFrame.setPlayMode(VideoPlayModePreset.Auto);
```
## Krok 4: Załaduj miniaturę
Aby poprawić atrakcyjność wizualną, załadujemy miniaturę filmu. Ten krok obejmuje pobranie obrazu miniatury ze źródła internetowego:
```java
String thumbnailUri = "https://www.youtube.com/watch?v=VIDEO_ID";
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
Zastąp „TWÓJ_KATALOG” katalogiem, w którym chcesz zapisać prezentację.

## Wniosek
Gratulacje! Pomyślnie nauczyłeś się dodawać klatkę wideo ze źródła internetowego w programie PowerPoint przy użyciu Aspose.Slides dla Java. Włączenie elementów multimedialnych, takich jak filmy, może znacznie zwiększyć wpływ i zaangażowanie prezentacji.
## Często zadawane pytania
### Czy mogę dodawać filmy z innych źródeł niż YouTube?
Tak, możesz dodawać filmy z różnych źródeł internetowych, pod warunkiem, że zawierają one link, który można umieścić na stronie.
### Czy do odtwarzania osadzonego wideo potrzebne jest połączenie internetowe?
Tak, do strumieniowego przesyłania wideo ze źródła internetowego wymagane jest aktywne połączenie internetowe.
### Czy mogę dostosować wygląd klatki wideo?
Absolutnie! Aspose.Slides zapewnia rozbudowane opcje dostosowywania wyglądu i zachowania klatek wideo.
### Czy Aspose.Slides jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides obsługuje szeroką gamę wersji programu PowerPoint, zapewniając kompatybilność na różnych platformach.
### Gdzie mogę znaleźć więcej zasobów i wsparcia dla Aspose.Slides?
 Możesz odwiedzić[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za pomoc, dokumentację i wsparcie społeczności.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
