---
title: Wyodrębnij dane z osadzonego pliku z obiektu OLE w programie PowerPoint
linktitle: Wyodrębnij dane z osadzonego pliku z obiektu OLE w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak wyodrębnić osadzone dane plików z prezentacji programu PowerPoint za pomocą Aspose.Slides dla Java, zwiększając możliwości zarządzania dokumentami.
weight: 22
url: /pl/java/java-powerpoint-animation-shape-manipulation/extract-embedded-file-data-ole-object-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Wstęp
W dziedzinie programowania w języku Java wyodrębnianie osadzonych danych plików z obiektów OLE (Object Linking and Embedding) w prezentacjach programu PowerPoint jest zadaniem, które często się pojawia, szczególnie w aplikacjach do zarządzania dokumentami lub ekstrakcji danych. Aspose.Slides for Java oferuje solidne rozwiązanie do programowej obsługi prezentacji PowerPoint. W tym samouczku przyjrzymy się, jak wyodrębnić dane z osadzonych plików z obiektów OLE za pomocą Aspose.Slides dla Java.
## Warunki wstępne
Zanim przejdziemy do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość programowania w języku Java.
- JDK (Java Development Kit) zainstalowany w twoim systemie.
- Biblioteka Aspose.Slides for Java pobrana i do której odwołuje się Twój projekt.

## Importuj pakiety
Po pierwsze, upewnij się, że zaimportowałeś niezbędne pakiety do swojego projektu Java, aby móc korzystać z funkcjonalności zapewnianych przez Aspose.Slides dla Java.
```java
import com.aspose.slides.IShape;
import com.aspose.slides.ISlide;
import com.aspose.slides.OleObjectFrame;
import com.aspose.slides.Presentation;

import java.io.FileOutputStream;
import java.io.IOException;
```

Podzielmy teraz proces na kilka etapów:
## Krok 1: Podaj ścieżkę do katalogu dokumentów
```java
String dataDir = "Your Document Directory";
```
 Zastępować`"Your Document Directory"` ze ścieżką do katalogu zawierającego prezentację programu PowerPoint.
## Krok 2: Określ nazwę pliku programu PowerPoint
```java
String pptxFileName = dataDir + "TestOlePresentation.pptx";
```
 Pamiętaj o wymianie`"TestOlePresentation.pptx"` z nazwą pliku prezentacji programu PowerPoint.
## Krok 3: Załaduj prezentację
```java
Presentation pres = new Presentation(pptxFileName);
```
 Ta linia inicjuje nową instancję klasy`Presentation` class, ładując określony plik prezentacji programu PowerPoint.
## Krok 4: Iteruj po slajdach i kształtach
```java
for (ISlide sld : pres.getSlides()) {
    for (IShape shape : sld.getShapes()) {
```
Tutaj przeglądamy każdy slajd i kształt w prezentacji.
## Krok 5: Sprawdź obiekt OLE
```java
if (shape instanceof OleObjectFrame) {
```
Ten warunek sprawdza, czy kształt jest obiektem OLE.
## Krok 6: Wyodrębnij dane z osadzonego pliku
```java
OleObjectFrame oleFrame = (OleObjectFrame) shape;
byte[] data = oleFrame.getEmbeddedData().getEmbeddedFileData();
```
Jeśli kształt jest obiektem OLE, wyodrębniamy osadzone w nim dane pliku.
## Krok 7: Określ rozszerzenie pliku
```java
String fileExtention = oleFrame.getEmbeddedData().getEmbeddedFileExtension();
```
Ta linia pobiera rozszerzenie wyodrębnionego osadzonego pliku.
## Krok 8: Zapisz wyodrębniony plik
```java
String extractedPath = dataDir + "ExtractedObject_out" + objectnum + fileExtention;
FileOutputStream fs = new FileOutputStream(extractedPath);
fs.write(data, 0, data.length);
```
Na koniec zapisujemy wyodrębnione dane pliku w określonym katalogu.

## Wniosek
W tym samouczku nauczyliśmy się, jak używać Aspose.Slides dla języka Java do wyodrębniania danych osadzonych plików z obiektów OLE w prezentacjach programu PowerPoint. Wykonując podane kroki, możesz bezproblemowo zintegrować tę funkcjonalność z aplikacjami Java, zwiększając możliwości zarządzania dokumentami.
## Często zadawane pytania
### Czy Aspose.Slides może wyodrębniać dane ze wszystkich typów osadzonych obiektów?
Aspose.Slides zapewnia rozbudowaną obsługę wyodrębniania danych z różnych osadzonych obiektów, w tym obiektów OLE, wykresów i innych.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami programu PowerPoint?
Tak, Aspose.Slides zapewnia zgodność z prezentacjami programu PowerPoint w różnych wersjach, zapewniając bezproblemową ekstrakcję osadzonych danych.
### Czy Aspose.Slides wymaga licencji do użytku komercyjnego?
 Tak, do komercyjnego wykorzystania Aspose.Slides wymagana jest ważna licencja. Licencję można uzyskać od firmy Aspose[strona internetowa](https://purchase.aspose.com/temporary-license/).
### Czy mogę zautomatyzować proces ekstrakcji za pomocą Aspose.Slides?
Absolutnie Aspose.Slides zapewnia kompleksowe interfejsy API do automatyzacji zadań, takich jak wyodrębnianie osadzonych danych z plików, umożliwiając wydajne i usprawnione przetwarzanie dokumentów.
### Gdzie mogę znaleźć dalszą pomoc lub wsparcie dla Aspose.Slides?
 W przypadku jakichkolwiek pytań, pomocy technicznej lub wsparcia społeczności możesz odwiedzić forum Aspose.Slajdy lub zapoznać się z dokumentacją[Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
