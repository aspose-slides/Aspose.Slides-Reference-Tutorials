---
title: Zmień układ grafiki SmartArt w programie PowerPoint za pomocą języka Java
linktitle: Zmień układ grafiki SmartArt w programie PowerPoint za pomocą języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak manipulować układami SmartArt w prezentacjach programu PowerPoint przy użyciu języka Java z Aspose.Slides dla języka Java.
weight: 19
url: /pl/java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zmień układ grafiki SmartArt w programie PowerPoint za pomocą języka Java

## Wstęp
W tym samouczku dowiemy się, jak manipulować układami SmartArt w prezentacjach programu PowerPoint przy użyciu języka Java. SmartArt to zaawansowana funkcja programu PowerPoint, która umożliwia użytkownikom tworzenie atrakcyjnych wizualnie grafik do różnych celów, takich jak ilustrowanie procesów, hierarchii, relacji i nie tylko.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że posiadasz następujące elementy:
1. Środowisko programistyczne Java: Upewnij się, że w systemie jest zainstalowany zestaw Java Development Kit (JDK).
2.  Biblioteka Aspose.Slides: Pobierz i zainstaluj bibliotekę Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/).
3. Podstawowa znajomość języka Java: Pomocna będzie znajomość podstaw języka programowania Java.
4. Zintegrowane środowisko programistyczne (IDE): wybierz preferowane środowisko IDE, takie jak Eclipse lub IntelliJ IDEA.

## Importuj pakiety
Aby rozpocząć, zaimportuj niezbędne pakiety do swojego projektu Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
## Krok 1: Skonfiguruj środowisko projektu Java
Upewnij się, że projekt Java jest poprawnie skonfigurowany w wybranym IDE. Utwórz nowy projekt Java i dołącz bibliotekę Aspose.Slides do zależności swojego projektu.
## Krok 2: Utwórz nową prezentację
Utwórz wystąpienie nowego obiektu prezentacji, aby utworzyć nową prezentację programu PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Krok 3: Dodaj grafikę SmartArt
Dodaj grafikę SmartArt do swojej prezentacji. Określ położenie i wymiary grafiki SmartArt na slajdzie.
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);
```
## Krok 4: Zmień układ grafiki SmartArt
Zmień układ grafiki SmartArt na żądany typ układu.
```java
smart.setLayout(SmartArtLayoutType.BasicProcess);
```
## Krok 5: Zapisz prezentację
Zapisz zmodyfikowaną prezentację w określonym katalogu w systemie.
```java
presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Manipulowanie układami SmartArt w prezentacjach programu PowerPoint przy użyciu języka Java jest prostym procesem dzięki Aspose.Slides dla języka Java. Postępując zgodnie z tym samouczkiem, możesz łatwo modyfikować grafikę SmartArt, aby dostosować ją do potrzeb prezentacji.
## Często zadawane pytania
### Czy mogę dostosować wygląd grafiki SmartArt za pomocą Aspose.Slides dla Java?
Tak, możesz dostosować różne aspekty grafiki SmartArt, takie jak kolory, style i efekty.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami programu PowerPoint?
Aspose.Slides obsługuje prezentacje PowerPoint utworzone w różnych wersjach programu PowerPoint, zapewniając kompatybilność na różnych platformach.
### Czy Aspose.Slides oferuje obsługę innych języków programowania?
Tak, Aspose.Slides jest dostępny dla wielu języków programowania, w tym .NET, Python i JavaScript.
### Czy mogę tworzyć grafikę SmartArt od podstaw za pomocą Aspose.Slides?
Absolutnie możesz programowo tworzyć grafiki SmartArt lub modyfikować istniejące, aby spełniały Twoje wymagania.
### Czy istnieje forum społeczności, na którym mogę szukać pomocy dotyczącej Aspose.Slides?
 Tak, możesz odwiedzić forum Aspose.Slides[Tutaj](https://forum.aspose.com/c/slides/11) do zadawania pytań i nawiązywania kontaktu ze społecznością.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
