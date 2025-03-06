---
title: Dodaj węzły w określonej pozycji w SmartArt przy użyciu języka Java
linktitle: Dodaj węzły w określonej pozycji w SmartArt przy użyciu języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać węzły w określonych pozycjach w SmartArt przy użyciu Java z Aspose.Slides. Twórz dynamiczne prezentacje bez wysiłku.
type: docs
weight: 16
url: /pl/java/java-powerpoint-smartart-manipulation/add-nodes-specific-position-smartart-java/
---
## Wstęp
W tym samouczku przeprowadzimy Cię przez proces dodawania węzłów w określonych pozycjach w SmartArt przy użyciu języka Java z Aspose.Slides. SmartArt to funkcja programu PowerPoint umożliwiająca tworzenie atrakcyjnych wizualnie diagramów i wykresów.
## Warunki wstępne
Zanim zaczniesz, upewnij się, że masz następujące elementy:
1. Zestaw Java Development Kit (JDK) zainstalowany w systemie.
2.  Pobrano bibliotekę Aspose.Slides dla Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
3. Podstawowa znajomość języka programowania Java.

## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety do naszego kodu Java:
```java
import com.aspose.slides.*;
import java.io.File;
```
## Krok 1: Utwórz instancję prezentacji
Zacznij od utworzenia instancji klasy Prezentacja:
```java
Presentation pres = new Presentation();
```
## Krok 2: Uzyskaj dostęp do slajdu prezentacji
Przejdź do slajdu, do którego chcesz dodać grafikę SmartArt:
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 3: Dodaj kształt SmartArt
Dodaj kształt SmartArt do slajdu:
```java
ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.StackedList);
```
## Krok 4: Uzyskaj dostęp do węzła SmartArt
Uzyskaj dostęp do węzła SmartArt pod żądanym indeksem:
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
## Krok 5: Dodaj węzeł podrzędny w określonej pozycji
Dodaj nowy węzeł podrzędny w określonym miejscu węzła nadrzędnego:
```java
SmartArtNode chNode = (SmartArtNode) ((SmartArtNodeCollection) node.getChildNodes()).addNodeByPosition(2);
```
## Krok 6: Dodaj tekst do węzła
Ustaw tekst dla nowo dodanego węzła:
```java
chNode.getTextFrame().setText("Sample Text Added");
```
## Krok 7: Zapisz prezentację
Zapisz zmodyfikowaną prezentację:
```java
pres.save(dataDir + "AddSmartArtNodeByPosition_out.pptx", SaveFormat.Pptx);
```

## Wniosek
W tym samouczku nauczyłeś się dodawać węzły w określonych pozycjach w SmartArt przy użyciu języka Java i Aspose.Slides. Wykonując poniższe kroki, możesz programowo manipulować kształtami SmartArt w celu tworzenia dynamicznych prezentacji.
## Często zadawane pytania
### Czy mogę dodać wiele węzłów jednocześnie?
Tak, możesz programowo dodać wiele węzłów, iterując po żądanych pozycjach.
### Czy Aspose.Slides jest kompatybilny ze wszystkimi wersjami programu PowerPoint?
Aspose.Slides obsługuje różne formaty programu PowerPoint, zapewniając kompatybilność z większością wersji.
### Czy mogę dostosować wygląd węzłów SmartArt?
Tak, możesz dostosować wygląd węzłów, w tym ich rozmiar, kolor i styl.
### Czy Aspose.Slides oferuje obsługę innych języków programowania?
Tak, Aspose.Slides udostępnia biblioteki dla wielu języków programowania, w tym .NET i Python.
### Czy dostępna jest wersja próbna Aspose.Slides?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).