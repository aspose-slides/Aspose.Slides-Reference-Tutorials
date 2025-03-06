---
title: Utwórz miniaturę kształtu w programie PowerPoint
linktitle: Utwórz miniaturę kształtu w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak generować miniatury kształtów w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Dostarczono przewodnik krok po kroku.
weight: 14
url: /pl/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
tym samouczku zajmiemy się tworzeniem miniatur kształtów w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Aspose.Slides to potężna biblioteka, która umożliwia programistom programową pracę z plikami PowerPoint, umożliwiając automatyzację różnych zadań, w tym generowanie miniatur kształtów.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
- Zestaw Java Development Kit (JDK) zainstalowany w systemie.
-  Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w Twoim projekcie. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Po pierwsze, musisz zaimportować niezbędne pakiety do swojego kodu Java, aby móc korzystać z funkcjonalności Aspose.Slides. Dołącz następujące instrukcje importu na początku pliku Java:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Zdefiniuj katalog dokumentów
```java
String dataDir = "Your Document Directory";
```
 Zastępować`"Your Document Directory"` ze ścieżką do katalogu zawierającego plik PowerPoint.
## Krok 2: Utwórz instancję obiektu prezentacji
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 Utwórz nową instancję`Presentation` class, przekazując jako parametr ścieżkę do pliku programu PowerPoint.
## Krok 3: Wygeneruj miniaturę kształtu
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Pobierz miniaturę żądanego kształtu z pierwszego slajdu prezentacji.
## Krok 4: Zapisz obraz miniatury
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Zapisz wygenerowaną miniaturę na dysku w formacie PNG z określoną nazwą pliku.

## Wniosek
Podsumowując, w tym samouczku pokazano, jak tworzyć miniatury kształtów w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Postępując zgodnie ze szczegółowym przewodnikiem i korzystając z dostarczonych fragmentów kodu, możesz efektywnie programowo generować miniatury kształtów.

## Często zadawane pytania
### Czy mogę tworzyć miniatury kształtów na dowolnym slajdzie prezentacji?
Tak, możesz zmodyfikować kod, aby kierować kształty na dowolnym slajdzie, odpowiednio dostosowując indeks slajdu.
### Czy Aspose.Slides obsługuje inne formaty obrazów do zapisywania miniatur?
Tak, oprócz PNG, Aspose.Slides obsługuje zapisywanie miniatur w różnych formatach obrazów, takich jak JPEG, GIF i BMP.
### Czy Aspose.Slides nadaje się do użytku komercyjnego?
 Tak, Aspose.Slides oferuje licencje komercyjne dla firm i organizacji. Możesz kupić licencję od[Tutaj](https://purchase.aspose.com/buy).
### Czy mogę wypróbować Aspose.Slides przed zakupem?
 Absolutnie! Możesz pobrać bezpłatną wersję próbną Aspose.Slides z[Tutaj](https://releases.aspose.com/) ocenić jego cechy i możliwości.
### Gdzie mogę znaleźć wsparcie dla Aspose.Slides?
 Jeśli masz jakieś pytania lub potrzebujesz pomocy z Aspose.Slides, możesz odwiedzić stronę[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) dla wsparcia.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
