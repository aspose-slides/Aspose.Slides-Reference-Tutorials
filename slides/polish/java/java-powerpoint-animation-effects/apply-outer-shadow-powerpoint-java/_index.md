---
"description": "Dowiedz się, jak zastosować efekt cienia zewnętrznego w programie PowerPoint za pomocą języka Java z Aspose.Slides. Ulepsz swoje prezentacje dzięki głębi i atrakcyjności wizualnej."
"linktitle": "Zastosuj cień zewnętrzny w programie PowerPoint za pomocą języka Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Zastosuj cień zewnętrzny w programie PowerPoint za pomocą języka Java"
"url": "/pl/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zastosuj cień zewnętrzny w programie PowerPoint za pomocą języka Java

## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji PowerPoint często wiąże się z dodawaniem różnych efektów do kształtów i tekstu. Jednym z takich efektów jest cień zewnętrzny, który może sprawić, że elementy będą się wyróżniać i doda głębi Twoim slajdom. W tym samouczku dowiesz się, jak zastosować efekt cienia zewnętrznego do kształtu w programie PowerPoint przy użyciu języka Java z Aspose.Slides.
## Wymagania wstępne

Zanim rozpoczniesz ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:

1. Java Development Kit (JDK): Upewnij się, że masz zainstalowaną Javę w swoim systemie. Możesz pobrać i zainstalować najnowszą wersję JDK ze strony internetowej Oracle.

2. Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java ze strony [strona do pobrania](https://releases.aspose.com/slides/java/).

3. Zintegrowane środowisko programistyczne (IDE): Wybierz preferowane środowisko IDE dla języka Java, np. Eclipse, IntelliJ IDEA lub NetBeans, do kodowania i uruchamiania aplikacji Java.

4. Podstawowa wiedza o języku Java: Znajomość podstaw języka programowania Java oraz koncepcji obiektowych będzie korzystna dla zrozumienia przykładów kodu.

## Importuj pakiety

Najpierw zaimportuj niezbędne pakiety do pracy z Aspose.Slides i powiązanymi funkcjonalnościami w swoim projekcie Java:

```java
import com.aspose.slides.*;
```

Teraz podzielimy przykładowy kod na kilka kroków, aby zastosować efekt zewnętrznego cienia do kształtu w programie PowerPoint za pomocą języka Java i pakietu Aspose.Slides:

## Krok 1: Skonfiguruj środowisko projektu

Utwórz nowy projekt Java w preferowanym środowisku IDE i dodaj bibliotekę Aspose.Slides for Java do ścieżki kompilacji projektu.

## Krok 2: Zainicjuj obiekt prezentacji

Utwórz instancję `Presentation` Klasa, która reprezentuje plik prezentacji programu PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Krok 3: Dodaj slajd i kształt

Uzyskaj odwołanie do slajdu, do którego chcesz dodać kształt, a następnie dodaj autokształt (np. prostokąt) do slajdu.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Krok 4: Dostosuj kształt

Ustaw typ wypełnienia kształtu na „NoFill” i dodaj tekst do kształtu.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Krok 5: Dostosuj tekst

Uzyskaj dostęp do właściwości tekstu kształtu i dostosuj rozmiar czcionki.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Krok 6: Włącz efekt Cienia zewnętrznego

Włącz efekt zewnętrznego cienia dla części tekstowej.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Krok 7: Ustaw parametry cienia

Zdefiniuj parametry efektu zewnętrznego cienia, takie jak promień rozmycia, kierunek, odległość i kolor cienia.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Krok 8: Zapisz prezentację

Zapisz zmodyfikowaną prezentację z zastosowanym do kształtu efektem cienia zewnętrznego.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Wniosek

Gratulacje! Udało Ci się zastosować efekt cienia zewnętrznego do kształtu w programie PowerPoint przy użyciu języka Java z Aspose.Slides. Eksperymentuj z różnymi parametrami, aby uzyskać pożądane efekty wizualne w swoich prezentacjach.

## Najczęściej zadawane pytania

### Czy efekt cienia zewnętrznego mogę zastosować do innych kształtów niż prostokąty?
Tak, możesz zastosować efekt zewnętrznego cienia do różnych kształtów obsługiwanych przez Aspose.Slides, takich jak okręgi, trójkąty i kształty niestandardowe.

### Czy można dostosować kolor i intensywność cienia?
Oczywiście! Masz pełną kontrolę nad parametrami cienia, w tym kolorem, promieniem rozmycia, kierunkiem i odległością.

### Czy mogę zastosować wiele efektów do tego samego kształtu?
Tak, możesz łączyć wiele efektów, takich jak cień zewnętrzny, cień wewnętrzny, blask i odbicie, aby zwiększyć atrakcyjność wizualną kształtów i tekstu w prezentacjach.

### Czy Aspose.Slides obsługuje stosowanie efektów do elementów tekstowych?
Tak, efekty można stosować nie tylko do kształtów, ale także do poszczególnych fragmentów tekstu w ich obrębie. Daje to dużą elastyczność podczas projektowania slajdów.

### Gdzie mogę znaleźć więcej materiałów i pomocy dla Aspose.Slides?
Możesz zapoznać się z [dokumentacja](https://reference.aspose.com/slides/java/) aby uzyskać szczegółowe informacje na temat interfejsu API i zapoznać się z [Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) w celu uzyskania wsparcia społeczności i dyskusji.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}