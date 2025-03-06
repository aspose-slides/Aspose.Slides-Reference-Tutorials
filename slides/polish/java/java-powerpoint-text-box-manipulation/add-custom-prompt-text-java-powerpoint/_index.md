---
title: Dodaj niestandardowy tekst podpowiedzi w programie Java PowerPoint
linktitle: Dodaj niestandardowy tekst podpowiedzi w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodać niestandardowy tekst podpowiedzi w programie Java PowerPoint przy użyciu Aspose.Slides. Dzięki temu samouczkowi możesz bez wysiłku usprawnić interakcję z użytkownikiem.
weight: 12
url: /pl/java/java-powerpoint-text-box-manipulation/add-custom-prompt-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Dodaj niestandardowy tekst podpowiedzi w programie Java PowerPoint

## Wstęp
dzisiejszej erze cyfrowej tworzenie dynamicznych i angażujących prezentacji ma kluczowe znaczenie dla skutecznej komunikacji. Aspose.Slides for Java umożliwia programistom programowe manipulowanie prezentacjami programu PowerPoint, oferując rozbudowane funkcje dostosowywania slajdów, kształtów, tekstu i nie tylko. Ten samouczek poprowadzi Cię przez proces dodawania niestandardowego tekstu podpowiedzi do elementów zastępczych w prezentacjach Java PowerPoint przy użyciu Aspose.Slides.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że posiadasz następujące elementy:
- Podstawowa znajomość programowania w języku Java.
- JDK (Java Development Kit) zainstalowany w twoim systemie.
-  Zainstalowano Aspose.Slides dla Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
- Konfiguracja zintegrowanego środowiska programistycznego (IDE), takiego jak IntelliJ IDEA lub Eclipse.

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne klasy Aspose.Slides do pliku Java:
```java
import com.aspose.slides.*;
```

## Krok 1: Załaduj prezentację
Najpierw załaduj prezentację programu PowerPoint, do której chcesz dodać niestandardowy tekst podpowiedzi do symboli zastępczych.
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Presentation2.pptx");
```
## Krok 2: Iteruj po kształtach slajdów
Uzyskaj dostęp do slajdu i przeglądaj jego kształty, aby znaleźć elementy zastępcze.
```java
try {
    ISlide slide = pres.getSlides().get_Item(0);
    for (IShape shape : slide.getShapes()) {
        if (shape.getPlaceholder() != null && shape instanceof AutoShape) {
            // Przetwarzaj tylko symbole zastępcze Autokształtu
            String text = "";
            if (shape.getPlaceholder().getType() == PlaceholderType.CenteredTitle) {
                text = "Click to add custom title";
            } else if (shape.getPlaceholder().getType() == PlaceholderType.Subtitle) {
                text = "Click to add custom subtitle";
            }
            
            // Ustaw niestandardowy tekst monitu
            ((IAutoShape) shape).getTextFrame().setText(text);
            
            // Wydrukuj tekst zastępczy w celu weryfikacji
            System.out.println(String.format("Placeholder with text: %s", text));
        }
    }
    
    //Zapisz zmodyfikowaną prezentację
    pres.save(dataDir + "Placeholders_PromptText.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Wniosek
Podsumowując, Aspose.Slides for Java upraszcza zadanie programowego dostosowywania prezentacji PowerPoint. Postępując zgodnie z tym samouczkiem, możesz usprawnić interakcję z użytkownikiem, bez wysiłku dodając zrozumiały tekst podpowiedzi do symboli zastępczych.
## Często zadawane pytania
### Czy mogę dodać tekst podpowiedzi do dowolnego elementu zastępczego na slajdzie programu PowerPoint przy użyciu Aspose.Slides for Java?
Tak, możesz programowo ustawić niestandardowy tekst podpowiedzi dla różnych typów symboli zastępczych.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides obsługuje szeroką gamę wersji programu PowerPoint, zapewniając kompatybilność i niezawodność.
### Gdzie mogę znaleźć więcej przykładów i dokumentacji dla Aspose.Slides dla Java?
 Odwiedzić[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/) obszerne przewodniki i przykłady.
### Jak mogę uzyskać tymczasową licencję na Aspose.Slides dla Java?
 Możesz dostać[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) aby ocenić pełne funkcje Aspose.Slides.
### Czy Aspose.Slides for Java obsługuje dodawanie niestandardowych animacji do slajdów?
Tak, Aspose.Slides udostępnia interfejsy API umożliwiające programowe zarządzanie animacjami slajdów.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
