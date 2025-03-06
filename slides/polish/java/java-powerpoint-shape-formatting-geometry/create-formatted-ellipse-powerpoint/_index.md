---
title: Utwórz sformatowaną elipsę w programie PowerPoint
linktitle: Utwórz sformatowaną elipsę w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak utworzyć sformatowaną elipsę w programie PowerPoint przy użyciu Aspose.Slides dla Java, korzystając z naszego szczegółowego przewodnika krok po kroku.
weight: 17
url: /pl/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Utwórz sformatowaną elipsę w programie PowerPoint

## Wstęp
Witamy w tym obszernym samouczku dotyczącym tworzenia sformatowanej elipsy w programie PowerPoint przy użyciu Aspose.Slides dla Java. Aspose.Slides to potężna biblioteka, która umożliwia programistom programowe manipulowanie plikami programu PowerPoint. Niezależnie od tego, czy automatyzujesz generowanie slajdów, czy ulepszasz prezentacje za pomocą niestandardowych kształtów, ten przewodnik przeprowadzi Cię przez każdy krok, zapewniając, że możesz z łatwością dodać idealnie sformatowaną elipsę do swoich slajdów. Zagłębmy się w szczegóły i zobaczmy, jak możemy to osiągnąć!
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
1. Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK 1.6 lub nowszy.
2.  Aspose.Slides dla Java: Pobierz najnowszą wersję z[Aspose.Slides dla Java](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Użyj IDE, takiego jak IntelliJ IDEA lub Eclipse.
4. Podstawowa znajomość języka Java: Wymagana jest znajomość programowania w języku Java.
## Importuj pakiety
Aby rozpocząć korzystanie z Aspose.Slides, musisz zaimportować niezbędne pakiety. Oto jak możesz to zrobić:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Krok 1: Skonfiguruj katalog projektu
Po pierwsze, potrzebujesz katalogu do przechowywania plików programu PowerPoint.
### Utworzyć katalog
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Upewnij się, że wymieniłeś`"Your Document Directory"` z rzeczywistą ścieżką, w której chcesz przechowywać swoje pliki.
## Krok 2: Zainicjuj prezentację
Teraz utwórz instancję klasy Prezentacja, która reprezentuje plik programu PowerPoint.
```java
// Klasa prezentacji natychmiastowej reprezentująca PPTX
Presentation pres = new Presentation();
```
## Krok 3: Zdobądź pierwszy slajd
Następnie pobierz pierwszy slajd z prezentacji, w którym dodasz elipsę.
```java
// Zdobądź pierwszy slajd
ISlide sld = pres.getSlides().get_Item(0);
```
## Krok 4: Dodaj kształt elipsy
Dodaj do slajdu automatyczny kształt elipsy.
```java
// Dodaj autokształt typu elipsy
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Tutaj,`50, 150, 150, 50` są współrzędnymi i rozmiarem elipsy (pozycja x, pozycja y, szerokość, wysokość).
## Krok 5: Zastosuj formatowanie do elipsy
Teraz zastosuj formatowanie elipsy. Ustawimy jednolity kolor wypełnienia i kolor linii.
### Ustaw kolor wypełnienia
```java
// Zastosuj formatowanie do kształtu elipsy
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Ustaw kolor i szerokość linii
```java
// Zastosuj formatowanie do linii elipsy
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Krok 6: Zapisz prezentację
Na koniec zapisz prezentację w określonym katalogu.
```java
// Zapisz plik PPTX na dysku
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Krok 7: Pozbądź się przedmiotu prezentacji
Pozbądź się obiektu prezentacji, aby zwolnić zasoby.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Wniosek
Gratulacje! Pomyślnie utworzyłeś sformatowaną elipsę w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java. Ten samouczek przeprowadził Cię przez proces konfigurowania projektu, dodawania elipsy, stosowania formatowania i zapisywania prezentacji. Dzięki tym umiejętnościom możesz teraz programowo ulepszać slajdy programu PowerPoint, czyniąc prezentacje bardziej dynamicznymi i atrakcyjnymi wizualnie.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides dla Java to potężna biblioteka, która umożliwia programistom programowe tworzenie, modyfikowanie i zarządzanie prezentacjami programu PowerPoint.
### Czy mogę używać Aspose.Slides dla Java z dowolnym IDE?
Tak, możesz używać Aspose.Slides for Java z dowolnym IDE Java, takim jak IntelliJ IDEA, Eclipse lub NetBeans.
### Czy potrzebuję licencji na Aspose.Slides?
Tak, Aspose.Slides jest produktem komercyjnym i do pełnej funkcjonalności potrzebujesz licencji. Możesz uzyskać licencję tymczasową[Tutaj](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Slides dla Java?
 Możesz znaleźć szczegółową dokumentację dotyczącą Aspose.Slides dla Java[strona z dokumentacją](https://reference.aspose.com/slides/java/).
### Czy dostępna jest obsługa Aspose.Slides?
 Tak, Aspose oferuje wsparcie za pośrednictwem swoich[forum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
