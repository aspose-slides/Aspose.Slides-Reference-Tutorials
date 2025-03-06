---
title: Zastosuj efekty cienia zewnętrznego w programie Java PowerPoint
linktitle: Zastosuj efekty cienia zewnętrznego w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak łatwo zastosować efekty cienia zewnętrznego w prezentacjach Java PowerPoint przy użyciu Aspose.Slides, korzystając z naszego szczegółowego przewodnika krok po kroku.
weight: 11
url: /pl/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Tworzenie angażujących prezentacji często wymaga dodania różnych efektów poprawiających atrakcyjność wizualną slajdów. Jednym z takich efektów jest cień zewnętrzny, który może sprawić, że Twoje elementy wyblakną i dodadzą głębi treści. W tym samouczku omówimy proces stosowania efektów cienia zewnętrznego do kształtów w prezentacji programu PowerPoint przy użyciu Aspose.Slides dla Java.
## Warunki wstępne
Zanim przejdziemy do przewodnika krok po kroku, upewnijmy się, że masz wszystko, czego potrzebujesz:
1.  Zestaw Java Development Kit (JDK): Upewnij się, że masz zainstalowany pakiet JDK na swoim komputerze. Można go pobrać z[stronie internetowej Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides dla Java Library: Pobierz najnowszą wersję z[Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Użyj IDE, takiego jak IntelliJ IDEA lub Eclipse, do pisania i wykonywania kodu Java.
4.  Ważna licencja Załóż: Możesz kupić licencję od[Aspose](https://purchase.aspose.com/buy) lub zdobądź[licencja tymczasowa](https://purchase.aspose.com/temporary-license/) dla ewolucji.
## Importuj pakiety
Najpierw musisz zaimportować niezbędne pakiety dla Aspose.Slides. To przygotowuje grunt pod wykorzystanie potężnych funkcjonalności udostępnianych przez bibliotekę.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Podzielmy proces stosowania efektów cienia zewnętrznego na łatwe do wykonania etapy:
## Krok 1: Skonfiguruj katalog projektu
Zanim zaczniesz pisać kod, musisz skonfigurować katalog projektu, w którym będą przechowywane i udostępniane pliki programu PowerPoint.
Upewnij się, że katalog projektu istnieje. Jeśli nie, utwórz go, używając następującego kodu:
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Krok 2: Zainicjuj prezentację
Teraz musimy zainicjować prezentację, w której dodamy nasze kształty i efekty.

 Utwórz nową instancję`Presentation` klasę, aby rozpocząć pracę z nowym plikiem programu PowerPoint.
```java
// Utwórz instancję klasy PPTX
Presentation pres = new Presentation();
```
## Krok 3: Dodaj slajd i kształt
Następnie dodaj slajd do swojej prezentacji, a następnie dodaj kształt, do którego zastosujesz efekt cienia.
### Pobierz odniesienie do slajdu
Pobierz odniesienie do pierwszego slajdu w prezentacji.
```java
// Uzyskaj odniesienie do slajdu
ISlide sld = pres.getSlides().get_Item(0);
```
### Dodaj autokształt
Dodaj prostokątny autokształt do slajdu o określonych współrzędnych.
```java
// Dodaj typ Autokształtu prostokąta
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Krok 4: Dostosuj kształt
Dodaj tekst do swojego kształtu i dostosuj jego ustawienia wypełnienia, aby efekt cienia był bardziej widoczny.
### Dodaj ramkę tekstową do kształtu
Wstaw tekst w kształcie prostokąta.
```java
// Dodaj ramkę tekstową do prostokąta
aShp.addTextFrame("Aspose TextBox");
```
### Wyłącz wypełnianie kształtu
Wyłącz wypełnienie kształtu, aby podkreślić cień tekstu.
```java
// Wyłącz wypełnianie kształtu w przypadku, gdy chcemy uzyskać cień tekstu
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Krok 5: Zastosuj efekt zewnętrznego cienia
Teraz nadszedł czas, aby zastosować efekt zewnętrznego cienia do kształtu.
### Włącz efekt cienia zewnętrznego
Włącz efekt cienia zewnętrznego dla kształtu.
```java
// Dodaj cień zewnętrzny i ustaw wszystkie niezbędne parametry
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Skonfiguruj parametry cienia
Ustaw różne właściwości cienia, takie jak promień rozmycia, kierunek, odległość, wyrównanie i kolor.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Krok 6: Zapisz prezentację
Na koniec zapisz prezentację na dysku.
```java
//Zapisz prezentację na dysku
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Krok 7: Pozbądź się zasobów
Upewnij się, że zwolnisz zasoby, pozbywając się obiektu prezentacji.
```java
// Oczyść zasoby
if (pres != null) pres.dispose();
```
## Wniosek
I masz to! Pomyślnie zastosowałeś efekt cienia zewnętrznego do kształtu w prezentacji programu PowerPoint przy użyciu Aspose.Slides for Java. Efekt ten może znacznie poprawić atrakcyjność wizualną slajdów, dzięki czemu zawartość będzie się wyróżniać.
 Jeśli napotkasz jakiekolwiek problemy lub potrzebujesz dalszej pomocy, nie wahaj się sprawdzić[Dokumentacja Aspose.Slides](https://reference.aspose.com/slides/java/) lub odwiedź[forum wsparcia](https://forum.aspose.com/c/slides/11). Miłego kodowania!
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężna biblioteka, która umożliwia tworzenie, manipulowanie i konwertowanie prezentacji programu PowerPoint w aplikacjach Java.
### Jak mogę uzyskać bezpłatną wersję próbną Aspose.Slides dla Java?
 Możesz pobrać bezpłatną wersję próbną ze strony[Strona Aspose](https://releases.aspose.com/).
### Czy mogę używać Aspose.Slides dla Java z dowolnym IDE?
Tak, możesz używać Aspose.Slides for Java z dowolnym IDE Java, takim jak IntelliJ IDEA, Eclipse lub NetBeans.
### Jak uzyskać tymczasową licencję na Aspose.Slides?
 Możesz uzyskać tymczasową licencję od[Strona Aspose](https://purchase.aspose.com/temporary-license/).
### Gdzie mogę znaleźć więcej przykładów i dokumentacji dla Aspose.Slides?
 Więcej przykładów i szczegółową dokumentację można znaleźć na stronie[Strona dokumentacji Aspose.Slides](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
