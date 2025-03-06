---
title: Zmień kolejność kształtów w programie PowerPoint
linktitle: Zmień kolejność kształtów w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Z tego samouczka krok po kroku dowiesz się, jak zmienić kolejność kształtów w programie PowerPoint przy użyciu Aspose.Slides dla języka Java. Zwiększ swoje umiejętności prezentacji bez wysiłku.
weight: 15
url: /pl/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Tworzenie atrakcyjnych wizualnie i dobrze zorganizowanych prezentacji może być trudnym zadaniem. Jednak dzięki odpowiednim narzędziom i technikom możesz znacznie ułatwić to zadanie. Aspose.Slides dla Java to potężna biblioteka, która pomaga programowo manipulować prezentacjami programu PowerPoint i zarządzać nimi. W tym samouczku przeprowadzimy Cię przez kolejne etapy zmiany kolejności kształtów na slajdzie programu PowerPoint przy użyciu programu Aspose.Slides dla języka Java.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK na swoim komputerze. Można go pobrać z[stronie internetowej Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java Library: Pobierz najnowszą wersję z[Strona pobierania Aspose.Slides dla Java](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Do kodowania używaj środowiska IDE, takiego jak IntelliJ IDEA lub Eclipse.
4. Plik prezentacji: Przygotuj plik programu PowerPoint, którym chcesz manipulować.
## Importuj pakiety
Aby rozpocząć, musisz zaimportować niezbędne pakiety z biblioteki Aspose.Slides. Importy te umożliwią pracę z prezentacjami, slajdami i kształtami.
```java
import com.aspose.slides.*;

```
tym przewodniku podzielimy proces zmiany kolejności kształtów na kilka kroków, aby lepiej zrozumieć i ułatwić wdrożenie.
## Krok 1: Załaduj prezentację
 Najpierw musisz załadować plik prezentacji PowerPoint, z którym chcesz pracować. Ten krok obejmuje inicjalizację pliku`Presentation` class ze ścieżką do pliku programu PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## Krok 2: Uzyskaj dostęp do żądanego slajdu
Po załadowaniu prezentacji przejdź do slajdu, na którym chcesz zmienić kolejność kształtów. Slajdy są indeksowane począwszy od 0, więc aby uzyskać dostęp do pierwszego slajdu, użyj indeksu 0.
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## Krok 3: Dodaj kształty do slajdu
Następnie dodaj kształty do slajdu. W celach demonstracyjnych dodamy do slajdu kształt prostokąta i trójkąta.
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Krok 4: Zmień kolejność kształtów
 Teraz zmień kolejność kształtów na slajdzie. The`reorder` Metoda pozwala określić nową pozycję kształtu w kolekcji kształtów slajdu.
```java
slide.getShapes().reorder(2, shp3);
```
## Krok 5: Zapisz zmodyfikowaną prezentację
Po zmianie kolejności kształtów zapisz zmodyfikowaną prezentację w nowym pliku. Dzięki temu oryginalny plik pozostanie niezmieniony.
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## Krok 6: Oczyść zasoby
Na koniec pozbądź się obiektu prezentacji, aby zwolnić zasoby.
```java
if (presentation1 != null) presentation1.dispose();
```
## Wniosek
Wykonując poniższe kroki, możesz łatwo zmienić kolejność kształtów na slajdzie programu PowerPoint za pomocą Aspose.Slides for Java. Ta potężna biblioteka upraszcza wiele zadań związanych z prezentacjami programu PowerPoint, umożliwiając programowe tworzenie slajdów i manipulowanie nimi. Niezależnie od tego, czy automatyzujesz tworzenie prezentacji, czy po prostu chcesz wprowadzić zbiorcze zmiany, Aspose.Slides dla Java jest nieocenionym narzędziem.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to interfejs API języka Java umożliwiający tworzenie i manipulowanie prezentacjami programu PowerPoint bez korzystania z programu Microsoft PowerPoint.
### Czy mogę używać Aspose.Slides for Java z innymi środowiskami IDE Java?
Tak, możesz go używać z dowolnym Java IDE, takim jak IntelliJ IDEA, Eclipse lub NetBeans.
### Czy Aspose.Slides for Java jest kompatybilny ze wszystkimi formatami programu PowerPoint?
Tak, Aspose.Slides for Java obsługuje PPT, PPTX i inne formaty PowerPoint.
### Jak uzyskać bezpłatną wersję próbną Aspose.Slides dla Java?
 Możesz pobrać bezpłatną wersję próbną ze strony[Strona pobierania Aspose.Slides dla Java](https://releases.aspose.com/).
### Gdzie mogę znaleźć więcej dokumentacji na temat Aspose.Slides dla Java?
 Szczegółową dokumentację można znaleźć na stronie[Strona dokumentacji Aspose.Slides for Java](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
