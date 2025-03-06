---
title: Zmień stan grafiki SmartArt w programie PowerPoint za pomocą języka Java
linktitle: Zmień stan grafiki SmartArt w programie PowerPoint za pomocą języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak zmieniać stany grafiki SmartArt w prezentacjach programu PowerPoint przy użyciu języka Java i Aspose.Slides. Zwiększ swoje umiejętności automatyzacji prezentacji.
type: docs
weight: 21
url: /pl/java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---
## Wstęp
W tym samouczku dowiesz się, jak manipulować obiektami SmartArt w prezentacjach programu PowerPoint przy użyciu języka Java i biblioteki Aspose.Slides. SmartArt to zaawansowana funkcja programu PowerPoint, która umożliwia tworzenie atrakcyjnych wizualnie diagramów i grafik.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że w systemie jest zainstalowana Java. Można go pobrać z[stronie internetowej Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides dla Java: Pobierz i zainstaluj bibliotekę Aspose.Slides dla Java z pliku[strona internetowa](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Aby rozpocząć pracę z Aspose.Slides w swoim projekcie Java, zaimportuj niezbędne pakiety:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;
```
Podzielmy teraz dostarczony przykładowy kod na kilka kroków:
## Krok 1: Zainicjuj obiekt prezentacji
```java
Presentation presentation = new Presentation();
```
 Tutaj tworzymy nowy`Presentation` obiekt, który reprezentuje prezentację programu PowerPoint.
## Krok 2: Dodaj obiekt SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);
```
 Ten krok dodaje obiekt SmartArt do pierwszego slajdu prezentacji. Określamy położenie i wymiary obiektu SmartArt, a także rodzaj układu (w tym przypadku`BasicProcess`).
## Krok 3: Ustaw stan grafiki SmartArt
```java
smart.setReversed(true);
```
Tutaj ustawiamy stan obiektu SmartArt. W tym przykładzie odwracamy kierunek grafiki SmartArt.
## Krok 4: Sprawdź stan grafiki SmartArt
```java
boolean flag = smart.isReversed();
```
 Możemy także sprawdzić aktualny stan obiektu SmartArt. Ta linia sprawdza, czy grafika SmartArt jest odwrócona, czy nie, i zapisuje ją w pliku`flag` zmienny.
## Krok 5: Zapisz prezentację
```java
presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
```
Na koniec zapisujemy zmodyfikowaną prezentację w określonej lokalizacji na dysku.

## Wniosek
W tym samouczku dowiedzieliśmy się, jak zmieniać stan obiektów SmartArt w prezentacjach programu PowerPoint przy użyciu języka Java i biblioteki Aspose.Slides. Dzięki tej wiedzy możesz programowo tworzyć dynamiczne i angażujące prezentacje.
## Często zadawane pytania
### Czy mogę modyfikować inne właściwości SmartArt przy użyciu Aspose.Slides dla Java?
Tak, możesz modyfikować różne aspekty obiektów SmartArt, takie jak kolory, style i układy, używając Aspose.Slides.
### Czy Aspose.Slides jest kompatybilny z różnymi wersjami programu PowerPoint?
Tak, Aspose.Slides obsługuje prezentacje PowerPoint w różnych wersjach, zapewniając kompatybilność i bezproblemową integrację.
### Czy mogę tworzyć niestandardowe układy SmartArt za pomocą Aspose.Slides?
Absolutnie! Aspose.Slides udostępnia interfejsy API do tworzenia niestandardowych układów SmartArt dostosowanych do Twoich konkretnych potrzeb.
### Czy Aspose.Slides oferuje obsługę innych formatów plików poza PowerPointem?
Tak, Aspose.Slides obsługuje szeroką gamę formatów plików, w tym PPTX, PPT, PDF i inne.
### Czy istnieje forum społeczności, na którym mogę uzyskać pomoc w przypadku pytań związanych z Aspose.Slides?
 Tak, możesz odwiedzić forum Aspose.Slides pod adresem[Tutaj](https://forum.aspose.com/c/slides/11) za pomoc i dyskusję.