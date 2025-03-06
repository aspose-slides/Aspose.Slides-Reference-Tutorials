---
title: Domyślne czcionki w programie PowerPoint z Aspose.Slides dla Java
linktitle: Domyślne czcionki w programie PowerPoint z Aspose.Slides dla Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić domyślne czcionki w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Zapewniaj spójność i bez wysiłku poprawiaj atrakcyjność wizualną.
weight: 11
url: /pl/java/java-powerpoint-font-management/default-fonts-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Domyślne czcionki w programie PowerPoint z Aspose.Slides dla Java

## Wstęp
Tworzenie prezentacji PowerPoint przy użyciu niestandardowych czcionek jest powszechnym wymogiem w wielu projektach. Aspose.Slides dla Java zapewnia płynne rozwiązanie do zarządzania domyślnymi czcionkami, zapewniając spójność w różnych środowiskach. W tym samouczku przeprowadzimy Cię przez proces ustawiania domyślnych czcionek w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK.
2.  Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java z[strona pobierania](https://releases.aspose.com/slides/java/).
3. Podstawowa znajomość języka Java: Znajomość podstaw języka programowania Java.

## Importuj pakiety
Zacznij od zaimportowania niezbędnych pakietów do projektu Java:
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
## Krok 3: Wygeneruj wyniki
Generuj różne wyniki, takie jak miniatury slajdów, pliki PDF i XPS:
```java
try {
    // Wygeneruj miniaturę slajdu
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // Wygeneruj plik PDF
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // Wygeneruj XPS-a
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## Wniosek
Ustawianie domyślnych czcionek w prezentacjach programu PowerPoint za pomocą Aspose.Slides dla Java jest proste i wydajne. Wykonując kroki opisane w tym samouczku, możesz zapewnić spójność stylów czcionek na różnych platformach i środowiskach, poprawiając atrakcyjność wizualną swoich prezentacji.
## Często zadawane pytania
### Czy mogę używać niestandardowych czcionek w Aspose.Slides dla Java?
Tak, możesz określić niestandardowe czcionki w swoich prezentacjach za pomocą Aspose.Slides for Java.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides for Java obsługuje szeroką gamę wersji programu PowerPoint, zapewniając kompatybilność w różnych środowiskach.
### Jak mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Możesz uzyskać wsparcie dla Aspose.Slides dla Java poprzez[Fora Aspose](https://forum.aspose.com/c/slides/11).
### Czy mogę wypróbować Aspose.Slides dla Java przed zakupem?
 Tak, możesz poznać Aspose.Slides for Java w ramach bezpłatnej wersji próbnej dostępnej pod adresem[releases.aspose.com](https://releases.aspose.com/).
### Gdzie mogę uzyskać tymczasową licencję na Aspose.Slides dla Java?
 Tymczasową licencję na Aspose.Slides dla Java można uzyskać z witryny[strona zakupu](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
