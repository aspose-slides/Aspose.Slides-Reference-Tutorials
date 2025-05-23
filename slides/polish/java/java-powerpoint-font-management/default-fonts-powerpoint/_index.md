---
"description": "Dowiedz się, jak ustawić domyślne czcionki w prezentacjach PowerPoint za pomocą Aspose.Slides dla Java. Zapewnij spójność i popraw atrakcyjność wizualną bez wysiłku."
"linktitle": "Domyślne czcionki w programie PowerPoint z Aspose.Slides dla Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Domyślne czcionki w programie PowerPoint z Aspose.Slides dla Java"
"url": "/pl/java/java-powerpoint-font-management/default-fonts-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Domyślne czcionki w programie PowerPoint z Aspose.Slides dla Java

## Wstęp
Tworzenie prezentacji PowerPoint z niestandardowymi czcionkami jest powszechnym wymogiem w wielu projektach. Aspose.Slides for Java zapewnia bezproblemowe rozwiązanie do zarządzania domyślnymi czcionkami, zapewniając spójność w różnych środowiskach. W tym samouczku przeprowadzimy Cię przez proces ustawiania domyślnych czcionek w prezentacjach PowerPoint przy użyciu Aspose.Slides for Java.
## Wymagania wstępne
Zanim zaczniemy, upewnij się, że spełniasz następujące wymagania wstępne:
1. Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany JDK.
2. Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java ze strony [strona do pobrania](https://releases.aspose.com/slides/java/).
3. Podstawowa wiedza o języku Java: Znajomość podstaw języka programowania Java.

## Importuj pakiety
Zacznij od zaimportowania niezbędnych pakietów do swojego projektu Java:
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Ustaw domyślne czcionki
Zdefiniuj ścieżkę do katalogu dokumentów i utwórz opcje ładowania, aby określić domyślne czcionki zwykłe i azjatyckie:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## Krok 2: Załaduj prezentację
Załaduj prezentację PowerPoint, korzystając ze zdefiniowanych opcji ładowania:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## Krok 3: Generowanie wyników
Generuj różne dane wyjściowe, takie jak miniatury slajdów, pliki PDF i XPS:
```java
try {
    // Generuj miniaturę slajdu
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // Wygeneruj PDF
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // Generuj XPS
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## Wniosek
Ustawianie domyślnych czcionek w prezentacjach PowerPoint przy użyciu Aspose.Slides for Java jest proste i wydajne. Postępując zgodnie z krokami opisanymi w tym samouczku, możesz zapewnić spójność stylów czcionek na różnych platformach i w różnych środowiskach, zwiększając atrakcyjność wizualną swoich prezentacji.
## Najczęściej zadawane pytania
### Czy mogę używać niestandardowych czcionek w Aspose.Slides dla Java?
Tak, możesz określić niestandardowe czcionki w swoich prezentacjach, korzystając z Aspose.Slides for Java.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides for Java obsługuje szeroką gamę wersji programu PowerPoint, zapewniając kompatybilność w różnych środowiskach.
### Gdzie mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides dla Java?
Wsparcie dla Aspose.Slides dla Java można uzyskać za pośrednictwem [Fora Aspose](https://forum.aspose.com/c/slides/11).
### Czy mogę wypróbować Aspose.Slides dla Java przed zakupem?
Tak, możesz wypróbować Aspose.Slides dla Java za pośrednictwem bezpłatnej wersji próbnej dostępnej pod adresem [wydania.aspose.com](https://releases.aspose.com/).
### Gdzie mogę uzyskać tymczasową licencję na Aspose.Slides dla Java?
Tymczasową licencję na Aspose.Slides dla Java można uzyskać na stronie [strona zakupu](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}