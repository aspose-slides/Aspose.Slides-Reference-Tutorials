---
title: Zastosuj cień wewnętrzny w prezentacjach Java PowerPoint
linktitle: Zastosuj cień wewnętrzny w prezentacjach Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak zastosować efekty cienia wewnętrznego do kształtów w prezentacjach Java PowerPoint przy użyciu Aspose.Slides. Ulepsz swoje slajdy, korzystając z tego przewodnika krok po kroku.
weight: 12
url: /pl/java/java-powerpoint-animation-effects/apply-inner-shadow-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zastosuj cień wewnętrzny w prezentacjach Java PowerPoint

## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji ma kluczowe znaczenie dla skutecznego komunikowania swoich pomysłów. Jednym z narzędzi, które może znacznie ulepszyć Twoje prezentacje, jest wykorzystanie cieni wewnętrznych. Ten samouczek poprowadzi Cię przez proces stosowania cieni wewnętrznych do kształtów w prezentacjach programu PowerPoint przy użyciu Aspose.Slides dla Java. Pod koniec tego samouczka będziesz mieć pełną wiedzę na temat manipulowania elementami slajdu w celu uzyskania oszałamiających efektów.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że na komputerze jest zainstalowany pakiet JDK. Można go pobrać z[witryna internetowa Java](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides dla Java: Pobierz najnowszą wersję z[Strona pobierania Aspose.Slides](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): IDE, takie jak IntelliJ IDEA lub Eclipse, pomoże Ci efektywniej zarządzać projektem.
4.  Licencja Aspose.Slides: Aby uzyskać licencję tymczasową, odwiedź stronę[Przydziel licencję tymczasową](https://purchase.aspose.com/temporary-license/) . Aby zapoznać się z opcjami zakupu, sprawdź[Strona zakupu Aspose](https://purchase.aspose.com/buy).
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety. Umożliwią one korzystanie z klas i metod dostarczonych przez Aspose.Slides.
```java
import com.aspose.slides.*;
import java.io.File;
```
## Krok 1: Skonfiguruj katalog projektu
Najpierw skonfiguruj katalog projektu. Będzie to miejsce, w którym będą znajdować się Twoje pliki programu PowerPoint i zajęcia z języka Java.
```java
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Na tym etapie upewniamy się, że istnieje katalog plików projektu. Jeżeli nie, to my to tworzymy.
## Krok 2: Zainicjuj prezentację
 Następnie musisz utworzyć instancję`Presentation` klasa. Obiekt ten będzie głównym interfejsem do manipulowania prezentacją programu PowerPoint.
```java
Presentation pres = new Presentation();
```
## Krok 3: Uzyskaj dostęp do pierwszego slajdu
Teraz przejdź do pierwszego slajdu swojej prezentacji. Slajdy są przechowywane w kolekcji, a pierwszy z nich możesz pobrać za pomocą jego indeksu.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
## Krok 4: Dodaj kształt do slajdu
Do slajdu dodamy kształt prostokąta. Do tego kształtu zostanie później zastosowany tekst i cień wewnętrzny.
```java
IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Krok 5: Dodaj tekst do kształtu
### Utwórz ramkę tekstową i uzyskaj do niej dostęp
 Aby dodać tekst do kształtu, musisz utworzyć plik i uzyskać do niego dostęp`TextFrame`.
```java
ashp.addTextFrame(" ");
ITextFrame txtFrame = ashp.getTextFrame();
```
### Ustaw tekst
Dodaj tekst do kształtu prostokąta, uzyskując dostęp do`Paragraph` I`Portion` obiekty.
```java
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Aspose TextBox");
```
## Krok 6: Zastosuj cień wewnętrzny
Ten krok polega na stworzeniu efektu wewnętrznego cienia i nałożeniu go na kształt.
```java
IEffectFormat effectFormat = ashp.getEffectFormat();
effectFormat.enableInnerShadowEffect();
IInnerShadowEffect innerShadow = effectFormat.getInnerShadowEffect();
innerShadow.setBlurRadius(5.0);
innerShadow.setDirection(45.0);
innerShadow.setDistance(4.0);
innerShadow.getShadowColor().setColor(java.awt.Color.BLACK);
```
## Krok 7: Zapisz prezentację
Na koniec zapisz prezentację we wskazanym katalogu. Ten krok gwarantuje, że zmiany zostaną zapisane w pliku.
```java
pres.save(dataDir + "ApplyInnerShadow_out.pptx", SaveFormat.Pptx);
```
## Krok 8: Oczyść zasoby
 Aby uniknąć wycieków pamięci, zawsze usuwaj plik`Presentation` obiekt, gdy już z nim skończysz.
```java
if (pres != null) pres.dispose();
```
## Wniosek
Gratulacje! Pomyślnie zastosowałeś cień wewnętrzny do kształtu w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java. W tym samouczku omówiono podstawowe kroki od skonfigurowania projektu do zapisania ostatecznej prezentacji. Dzięki tym umiejętnościom możesz teraz wzbogacać swoje prezentacje różnymi efektami, aby uczynić je bardziej wciągającymi i atrakcyjnymi wizualnie.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężny interfejs API do programowego tworzenia i manipulowania prezentacjami programu PowerPoint. Umożliwia programistom pracę z prezentacjami bez konieczności korzystania z programu Microsoft PowerPoint.
### Czy mogę używać Aspose.Slides bez licencji?
 Aspose.Slides oferuje bezpłatną wersję próbną, którą można pobrać ze strony[Aspose bezpłatna strona próbna](https://releases.aspose.com/). Jednak do pełnej funkcjonalności wymagana jest licencja.
### Jak dodać różne kształty do slajdu?
 Możesz dodawać różne kształty za pomocą`addAutoShape` metody i określenie typu kształtu, np`ShapeType.Rectangle`, `ShapeType.Ellipse`itp.
### Czy mogę bardziej dostosować efekty cieni?
Tak, możesz dostosować różne parametry efektu cienia, takie jak promień rozmycia, kierunek, odległość i kolor, do swoich potrzeb.
### Gdzie mogę znaleźć bardziej szczegółową dokumentację?
 Możesz zapoznać się z[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/) szczegółowe informacje i przykłady.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
