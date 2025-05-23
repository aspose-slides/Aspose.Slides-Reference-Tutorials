---
"description": "Dowiedz się, jak generować miniatury kształtów w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Dostarczono przewodnik krok po kroku."
"linktitle": "Utwórz miniaturę kształtu w programie PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Utwórz miniaturę kształtu w programie PowerPoint"
"url": "/pl/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz miniaturę kształtu w programie PowerPoint

## Wstęp
tym samouczku zagłębimy się w tworzenie miniatur kształtów w prezentacjach PowerPoint przy użyciu Aspose.Slides dla Java. Aspose.Slides to potężna biblioteka, która umożliwia programistom programową pracę z plikami PowerPoint, umożliwiając automatyzację różnych zadań, w tym generowanie miniatur kształtów.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w Javie.
- Java Development Kit (JDK) zainstalowany w Twoim systemie.
- Biblioteka Aspose.Slides for Java pobrana i skonfigurowana w Twoim projekcie. Możesz ją pobrać z [Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety do swojego kodu Java, aby wykorzystać funkcjonalności Aspose.Slides. Dołącz następujące polecenia importu na początku swojego pliku Java:
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
Zastępować `"Your Document Directory"` ze ścieżką do katalogu zawierającego plik PowerPoint.
## Krok 2: Utwórz obiekt prezentacji
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
Utwórz nową instancję `Presentation` klasę, przekazując ścieżkę do pliku PowerPoint jako parametr.
## Krok 3: Generowanie miniatury kształtu
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Pobierz miniaturę wybranego kształtu z pierwszego slajdu prezentacji.
## Krok 4: Zapisz obraz miniatury
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Zapisz wygenerowany obraz miniatury na dysku w formacie PNG pod określoną nazwą pliku.

## Wniosek
Podsumowując, ten samouczek pokazał, jak tworzyć miniatury kształtów w prezentacjach PowerPoint przy użyciu Aspose.Slides for Java. Postępując zgodnie z przewodnikiem krok po kroku i wykorzystując dostarczone fragmenty kodu, możesz wydajnie generować miniatury kształtów programowo.

## Najczęściej zadawane pytania
### Czy mogę tworzyć miniatury kształtów na dowolnym slajdzie prezentacji?
Tak, możesz zmodyfikować kod, aby kierować kształty na dowolnym slajdzie, odpowiednio dostosowując indeks slajdu.
### Czy Aspose.Slides obsługuje inne formaty obrazów do zapisywania miniatur?
Tak, oprócz formatu PNG, Aspose.Slides obsługuje zapisywanie miniatur w różnych formatach obrazu, takich jak JPEG, GIF i BMP.
### Czy Aspose.Slides nadaje się do użytku komercyjnego?
Tak, Aspose.Slides oferuje licencje komercyjne dla firm i organizacji. Możesz kupić licencję od [Tutaj](https://purchase.aspose.com/buy).
### Czy mogę wypróbować Aspose.Slides przed zakupem?
Oczywiście! Możesz pobrać bezpłatną wersję próbną Aspose.Slides z [Tutaj](https://releases.aspose.com/) aby ocenić jego funkcje i możliwości.
### Gdzie mogę znaleźć pomoc dotyczącą Aspose.Slides?
Jeśli masz jakiekolwiek pytania lub potrzebujesz pomocy w zakresie Aspose.Slides, możesz odwiedzić stronę [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) o wsparcie.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}