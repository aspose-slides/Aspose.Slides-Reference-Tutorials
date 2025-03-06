---
title: Utwórz sformatowany prostokąt w programie PowerPoint
linktitle: Utwórz sformatowany prostokąt w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak utworzyć i sformatować prostokąt w programie PowerPoint przy użyciu Aspose.Slides dla Java, korzystając z tego przewodnika krok po kroku.
weight: 18
url: /pl/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
W tym samouczku przeprowadzimy Cię przez proces tworzenia sformatowanego prostokąta na slajdzie programu PowerPoint przy użyciu Aspose.Slides dla Java. Omówimy każdy krok, abyś mógł go śledzić i wdrożyć we własnych projektach.
## Warunki wstępne
Zanim zagłębimy się w kod, omówmy wymagania wstępne. Będziesz potrzebować:
1. Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowany pakiet JDK.
2. Biblioteka Aspose.Slides for Java: Pobierz i dołącz bibliotekę Aspose.Slides for Java do swojego projektu.
3. Zintegrowane środowisko programistyczne (IDE): IDE, takie jak IntelliJ IDEA lub Eclipse, sprawi, że kodowanie stanie się płynniejsze.
4. Podstawowa znajomość języka Java: Znajomość programowania w języku Java pomoże Ci w wykonaniu tego samouczka.
## Importuj pakiety
Aby rozpocząć, musisz zaimportować niezbędne pakiety z biblioteki Aspose.Slides. Oto jak możesz to zrobić:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
Importy te są kluczowe, ponieważ wprowadzają zajęcia wymagane do tworzenia i formatowania kształtów w prezentacji programu PowerPoint.
## Krok 1: Konfiguracja katalogu projektu
Najpierw musisz utworzyć katalog dla swojego projektu. W tym katalogu będą przechowywane Twoje pliki programu PowerPoint.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Ten kod sprawdza, czy katalog istnieje i tworzy go, jeśli nie. Dobrą praktyką jest utrzymywanie porządku w plikach projektu.
## Krok 2: Utwórz instancję klasy prezentacji
 Następnie utworzysz instancję`Presentation` class, która reprezentuje plik programu PowerPoint.
```java
Presentation pres = new Presentation();
```
Ta linia kodu tworzy nową, pustą prezentację, do której możesz rozpocząć dodawanie treści.
## Krok 3: Dodaj slajd do prezentacji
Teraz dodajmy slajd do Twojej prezentacji. Domyślnie nowa prezentacja zawiera jeden slajd, więc będziemy nad tym pracować.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
Ten fragment kodu pobiera pierwszy slajd z prezentacji.
## Krok 4: Dodaj kształt prostokąta
Teraz dodamy prostokąt do slajdu.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Tutaj dodajemy do slajdu prostokąt o określonych wymiarach (szerokość, wysokość) i położeniu (x, y).
## Krok 5: Sformatuj prostokąt
Zastosujmy pewne formatowanie, aby prostokąt był atrakcyjny wizualnie.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
Ten kod ustawia typ wypełnienia na pełne, a kolor wypełnienia na czekoladowy.
## Sformatuj granicę prostokąta
Następnie sformatujmy krawędź prostokąta.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
Ten kod ustawia kolor obramowania na czarny i szerokość obramowania na 5.
## Krok 6: Zapisz prezentację
Na koniec zapiszmy prezentację w katalogu Twojego projektu.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Ta linia kodu zapisuje prezentację jako plik PPTX w określonym katalogu.
## Krok 7: Oczyść zasoby
 Dobrą praktyką jest pozbywanie się`Presentation` sprzeciwiać się zwolnieniu zasobów.
```java
if (pres != null) pres.dispose();
```
Dzięki temu wszystkie zasoby zostaną prawidłowo zwolnione.
## Wniosek
Tworzenie i formatowanie kształtów w prezentacji programu PowerPoint za pomocą Aspose.Slides dla Java jest prostym procesem. Wykonując kroki opisane w tym samouczku, możesz z łatwością zautomatyzować tworzenie atrakcyjnych wizualnie slajdów. Niezależnie od tego, czy tworzysz aplikacje do tworzenia raportów biznesowych, treści edukacyjnych czy prezentacji dynamicznych, Aspose.Slides for Java oferuje narzędzia potrzebne do osiągnięcia sukcesu.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides dla Java to biblioteka, która umożliwia programistom programowe tworzenie, modyfikowanie i konwertowanie prezentacji programu PowerPoint.
### Czy mogę używać Aspose.Slides dla Java z dowolnym IDE?
Tak, możesz używać Aspose.Slides for Java z dowolnym IDE zgodnym z Javą, takim jak IntelliJ IDEA, Eclipse lub NetBeans.
### Jak mogę uzyskać bezpłatną wersję próbną Aspose.Slides dla Java?
 Możesz pobrać bezpłatną wersję próbną Aspose.Slides dla Java ze strony[Tutaj](https://releases.aspose.com/).
###  Czy konieczne jest utylizowanie`Presentation` object?
 Tak, utylizacja`Presentation` Obiekt pomaga zwolnić zasoby i uniknąć wycieków pamięci.
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
