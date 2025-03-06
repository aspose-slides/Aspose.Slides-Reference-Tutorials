---
title: Użyj narzędzia ShapeUtil do określenia kształtu geometrii w programie PowerPoint
linktitle: Użyj narzędzia ShapeUtil do określenia kształtu geometrii w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Twórz niestandardowe kształty w programie PowerPoint za pomocą Aspose.Slides dla Java. Postępuj zgodnie z tym przewodnikiem krok po kroku, aby ulepszyć swoje prezentacje.
weight: 23
url: /pl/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji programu PowerPoint często wymaga czegoś więcej niż tylko użycia standardowych kształtów i tekstu. Wyobraź sobie, że możesz dodawać niestandardowe kształty i ścieżki tekstowe bezpośrednio do slajdów, zwiększając wizualny efekt prezentacji. Używając Aspose.Slides dla Java, możesz to osiągnąć z łatwością. Ten samouczek przeprowadzi Cię przez proces korzystania z narzędzia`ShapeUtil` zajęcia do tworzenia kształtów geometrycznych w prezentacjach programu PowerPoint. Niezależnie od tego, czy jesteś doświadczonym programistą, czy dopiero zaczynasz, ten przewodnik krok po kroku pomoże Ci wykorzystać moc Aspose.Slides dla Java do tworzenia oszałamiających treści o niestandardowym kształcie.
## Warunki wstępne
Zanim przejdziemy do samouczka, będziesz potrzebować kilku rzeczy:
1. Zestaw Java Development Kit (JDK): Upewnij się, że na komputerze jest zainstalowany pakiet JDK 8 lub nowszy.
2.  Aspose.Slides dla Java: Pobierz najnowszą wersję z[strona pobierania](https://releases.aspose.com/slides/java/).
3. Środowisko programistyczne: użyj dowolnego środowiska Java IDE, takiego jak IntelliJ IDEA, Eclipse lub NetBeans.
4.  Licencja tymczasowa: Uzyskaj bezpłatną licencję tymczasową od[Strona tymczasowej licencji Aspose](https://purchase.aspose.com/temporary-license/) aby odblokować pełną funkcjonalność Aspose.Slides dla Java.
## Importuj pakiety
Aby rozpocząć, musisz zaimportować pakiety niezbędne do pracy z Aspose.Slides i Java AWT (Abstract Window Toolkit):
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## Krok 1: Konfiguracja projektu
Najpierw skonfiguruj projekt Java i dodaj Aspose.Slides for Java do zależności swojego projektu. Możesz to zrobić, dodając pliki JAR bezpośrednio lub używając narzędzia do kompilacji, takiego jak Maven lub Gradle.
## Krok 2: Utwórz nową prezentację
Zacznij od utworzenia nowego obiektu prezentacji programu PowerPoint. Ten obiekt będzie płótnem, na którym będziesz dodawać własne kształty.
```java
Presentation pres = new Presentation();
```
## Krok 3: Dodaj kształt prostokąta
Następnie dodaj podstawowy kształt prostokąta do pierwszego slajdu prezentacji. Kształt ten zostanie później zmodyfikowany w celu uwzględnienia niestandardowej ścieżki geometrii.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## Krok 4: Pobierz i zmodyfikuj ścieżkę geometrii
 Pobierz ścieżkę geometrii kształtu prostokąta i zmodyfikuj jego tryb wypełnienia`None`. Ten krok jest kluczowy, ponieważ umożliwia połączenie tej ścieżki z inną niestandardową ścieżką geometrii.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## Krok 5: Utwórz niestandardową ścieżkę geometrii z tekstu
Teraz utwórz niestandardową ścieżkę geometrii na podstawie tekstu. Obejmuje to konwersję ciągu tekstowego na ścieżkę graficzną, a następnie konwersję tej ścieżki na ścieżkę geometryczną.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## Krok 6: Połącz ścieżki geometrii
Połącz oryginalną ścieżkę geometrii z nową ścieżką geometrii opartą na tekście i ustaw tę kombinację dla kształtu.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## Krok 7: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację do pliku. Spowoduje to wygenerowanie pliku programu PowerPoint z niestandardowymi kształtami.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## Wniosek
Gratulacje! Właśnie utworzyłeś niestandardowy kształt geometryczny w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java. Ten samouczek przeprowadził Cię przez każdy krok, od skonfigurowania projektu po wygenerowanie i połączenie ścieżek geometrycznych. Opanowując te techniki, możesz dodać do swoich prezentacji unikalne i przyciągające wzrok elementy, dzięki czemu będą się wyróżniać.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężny interfejs API do pracy z plikami programu PowerPoint w języku Java. Umożliwia programowe tworzenie, modyfikowanie i konwertowanie prezentacji.
### Jak zainstalować Aspose.Slides dla Java?
 Najnowszą wersję można pobrać ze strony[strona pobierania](https://releases.aspose.com/slides/java/) i dodaj pliki JAR do swojego projektu.
### Czy mogę korzystać z Aspose.Slides za darmo?
Aspose.Slides oferuje bezpłatną wersję próbną, z której możesz pobrać[Tutaj](https://releases.aspose.com/)Aby uzyskać pełną funkcjonalność, należy zakupić licencję.
### Jaki jest pożytek z klasy ShapeUtil?
 The`ShapeUtil` class w Aspose.Slides udostępnia metody użytkowe do pracy z kształtami, takie jak konwertowanie ścieżek graficznych na ścieżki geometryczne.
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides?
 Możesz uzyskać wsparcie od[Forum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
