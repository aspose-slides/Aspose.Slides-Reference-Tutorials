---
title: Dodaj prostą linię do slajdu
linktitle: Dodaj prostą linię do slajdu
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak programowo dodać prostą linię do slajdu programu PowerPoint przy użyciu Aspose.Slides dla Java. Zwiększ swoją produktywność dzięki temu przewodnikowi krok po kroku.
weight: 14
url: /pl/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
Aspose.Slides for Java to potężna biblioteka, która umożliwia programistom Java programową pracę z prezentacjami programu PowerPoint. Dzięki Aspose.Slides możesz z łatwością tworzyć, modyfikować i konwertować pliki programu PowerPoint, oszczędzając czas i wysiłek. W tym samouczku przeprowadzimy Cię przez proces dodawania zwykłej linii do slajdu w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java.
## Warunki wstępne
Zanim zaczniemy, upewnij się, że masz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie
- Biblioteka Aspose.Slides for Java pobrana i dodana do projektu Java
- Podstawowa znajomość języka programowania Java

## Importuj pakiety
Aby rozpocząć, musisz zaimportować niezbędne pakiety do swojego kodu Java. Oto jak możesz to zrobić:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## Krok 1: Skonfiguruj środowisko
 Najpierw utwórz nowy projekt Java i dodaj bibliotekę Aspose.Slides for Java do ścieżki klas swojego projektu. Bibliotekę możesz pobrać ze strony[Tutaj](https://releases.aspose.com/slides/java/).
## Krok 2: Utwórz nową prezentację
 Następnie utwórz instancję`Presentation` klasie, aby utworzyć nową prezentację programu PowerPoint.
```java
Presentation pres = new Presentation();
```
## Krok 3: Dodaj slajd
Pobierz pierwszy slajd prezentacji i zapisz go w zmiennej.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 4: Dodaj kształt linii
Teraz dodaj do slajdu autokształt linii tekstu.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Krok 5: Zapisz prezentację
Na koniec zapisz prezentację na dysku.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Gratulacje! Pomyślnie dodałeś prostą linię do slajdu w prezentacji PowerPoint przy użyciu Aspose.Slides for Java. Dzięki Aspose.Slides możesz łatwo programowo manipulować plikami PowerPoint, otwierając świat możliwości dla aplikacji Java.

## Często zadawane pytania
### Czy mogę dostosować właściwości kształtu linii?
Tak, możesz dostosować różne właściwości, takie jak kolor linii, szerokość, styl i inne, korzystając z interfejsu API Aspose.Slides.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami programu PowerPoint?
Tak, Aspose.Slides obsługuje różne formaty programu PowerPoint, w tym PPT, PPTX i inne, zapewniając kompatybilność w różnych wersjach.
### Czy Aspose.Slides zapewnia obsługę dodawania innych kształtów oprócz linii?
Absolutnie! Aspose.Slides oferuje szeroką gamę typów kształtów, w tym prostokąty, okręgi, strzałki i inne.
### Czy mogę dodać tekst do slajdu wraz z kształtem linii?
Tak, możesz dodawać tekst, obrazy i inną zawartość do slajdu za pomocą interfejsu API Aspose.Slides.
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides?
 Tak, możesz pobrać bezpłatną wersję próbną Aspose.Slides z[Tutaj](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
