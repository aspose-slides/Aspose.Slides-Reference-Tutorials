---
title: Zastosuj cień zewnętrzny w programie PowerPoint przy użyciu języka Java
linktitle: Zastosuj cień zewnętrzny w programie PowerPoint przy użyciu języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak zastosować efekt cienia zewnętrznego w programie PowerPoint przy użyciu języka Java z Aspose.Slides. Wzbogać swoje prezentacje głębią i atrakcyjnością wizualną.
weight: 13
url: /pl/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji programu PowerPoint często wiąże się z dodawaniem różnych efektów do kształtów i tekstu. Jednym z takich efektów jest cień zewnętrzny, który może wyróżnić elementy i dodać głębi slajdom. W tym samouczku dowiesz się, jak zastosować efekt cienia zewnętrznego do kształtu w programie PowerPoint przy użyciu języka Java i Aspose.Slides.
## Warunki wstępne

Przed rozpoczęciem tego samouczka upewnij się, że spełnione są następujące wymagania wstępne:

1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java. Możesz pobrać i zainstalować najnowszą wersję JDK ze strony internetowej Oracle.

2.  Aspose.Slides dla Java: Pobierz i zainstaluj Aspose.Slides dla Java z[strona pobierania](https://releases.aspose.com/slides/java/).

3. Zintegrowane środowisko programistyczne (IDE): Wybierz preferowane środowisko Java IDE, takie jak Eclipse, IntelliJ IDEA lub NetBeans, do kodowania i uruchamiania aplikacji Java.

4. Podstawowa znajomość języka Java: Znajomość podstaw języka programowania Java i koncepcji obiektowych będzie korzystna dla zrozumienia przykładów kodu.

## Importuj pakiety

Najpierw zaimportuj pakiety niezbędne do pracy z Aspose.Slides i powiązanymi funkcjami w swoim projekcie Java:

```java
import com.aspose.slides.*;
```

Podzielmy teraz przykładowy kod na wiele kroków, aby zastosować efekt cienia zewnętrznego do kształtu w programie PowerPoint przy użyciu języka Java i Aspose.Slides:

## Krok 1: Skonfiguruj środowisko projektu

Utwórz nowy projekt Java w preferowanym środowisku IDE i dodaj bibliotekę Aspose.Slides for Java do ścieżki kompilacji projektu.

## Krok 2: Zainicjuj obiekt prezentacji

 Utwórz instancję`Presentation` class, która reprezentuje plik prezentacji programu PowerPoint.

```java
Presentation presentation = new Presentation();
```

## Krok 3: Dodaj slajd i kształt

Uzyskaj odwołanie do slajdu, do którego chcesz dodać kształt, a następnie dodaj do slajdu autokształt (np. prostokąt).

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

## Krok 6: Włącz efekt zewnętrznego cienia

Włącz efekt cienia zewnętrznego dla części tekstowej.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Krok 7: Ustaw parametry cienia

Zdefiniuj parametry efektu cienia zewnętrznego, takie jak promień rozmycia, kierunek, odległość i kolor cienia.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Krok 8: Zapisz prezentację

Zapisz zmodyfikowaną prezentację z efektem cienia zewnętrznego zastosowanym do kształtu.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Wniosek

Gratulacje! Pomyślnie zastosowałeś efekt cienia zewnętrznego do kształtu w programie PowerPoint przy użyciu języka Java z Aspose.Slides. Eksperymentuj z różnymi parametrami, aby uzyskać pożądane efekty wizualne w swoich prezentacjach.

## Często zadawane pytania

### Czy mogę zastosować efekt cienia zewnętrznego do innych kształtów oprócz prostokątów?
Tak, możesz zastosować efekt cienia zewnętrznego do różnych kształtów obsługiwanych przez Aspose.Slides, takich jak koła, trójkąty i kształty niestandardowe.

### Czy można dostosować kolor i intensywność cienia?
Absolutnie! Masz pełną kontrolę nad parametrami cienia, w tym kolorem, promieniem rozmycia, kierunkiem i odległością.

### Czy mogę zastosować wiele efektów do tego samego kształtu?
Tak, możesz łączyć wiele efektów, takich jak cień zewnętrzny, cień wewnętrzny, poświata i odbicia, aby poprawić atrakcyjność wizualną kształtów i tekstu w prezentacjach.

### Czy Aspose.Slides obsługuje stosowanie efektów do elementów tekstowych?
Tak, możesz stosować efekty nie tylko do kształtów, ale także do poszczególnych fragmentów tekstu w kształtach, co zapewnia dużą elastyczność w projektowaniu slajdów.

### Gdzie mogę znaleźć więcej zasobów i wsparcia dla Aspose.Slides?
 Możesz zapoznać się z[dokumentacja](https://reference.aspose.com/slides/java/) aby uzyskać szczegółowe odniesienia do API i zapoznać się z[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11) za wsparcie społeczności i dyskusje.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
