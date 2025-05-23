---
"description": "Dowiedz się, jak dodawać niestandardowe punkty obrazkowe do slajdów programu PowerPoint za pomocą Aspose.Slides for Java. Postępuj zgodnie z tym szczegółowym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację."
"linktitle": "Zarządzanie punktami akapitów w programie Java PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Zarządzanie punktami akapitów w programie Java PowerPoint"
"url": "/pl/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzanie punktami akapitów w programie Java PowerPoint

## Wstęp
Tworzenie angażujących i atrakcyjnych wizualnie prezentacji to kluczowa umiejętność w nowoczesnym świecie biznesu. Programiści Java mogą wykorzystać Aspose.Slides, aby ulepszyć swoje prezentacje za pomocą niestandardowych wypunktowań obrazkowych w slajdach programu PowerPoint. Ten samouczek przeprowadzi Cię przez proces krok po kroku, zapewniając, że możesz pewnie dodawać wypunktowania obrazkowe do swoich prezentacji.
## Wymagania wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełnione są następujące wymagania wstępne:
- Zainstalowano Java Development Kit (JDK)
- Zintegrowane środowisko programistyczne (IDE), takie jak Eclipse lub IntelliJ IDEA
- Biblioteka Aspose.Slides dla Java
- Podstawowa znajomość programowania w Javie
- Plik obrazu dla zdjęcia pocisku
Aby pobrać bibliotekę Aspose.Slides dla języka Java, odwiedź stronę [strona do pobrania](https://releases.aspose.com/slides/java/). Aby uzyskać dokumentację, sprawdź [dokumentacja](https://reference.aspose.com/slides/java/).
## Importuj pakiety
Najpierw upewnij się, że zaimportowałeś niezbędne pakiety dla swojego projektu. Dodaj następujące importy na początku swojego pliku Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Podzielmy ten proces na łatwiejsze do opanowania kroki.
## Krok 1: Skonfiguruj katalog swojego projektu
Utwórz nowy katalog dla swojego projektu. Ten katalog będzie zawierał Twój plik Java, bibliotekę Aspose.Slides i plik obrazu dla punktu.
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Zainicjuj prezentację
Zainicjuj nową instancję `Presentation` Klasa. Ten obiekt reprezentuje Twoją prezentację PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Krok 3: Dostęp do pierwszego slajdu
Uzyskaj dostęp do pierwszego slajdu prezentacji. Slajdy są indeksowane od zera, więc pierwszy slajd ma indeks 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 4: Załaduj obraz pocisku
Załaduj obraz, którego chcesz użyć do wypunktowania. Ten obraz powinien zostać umieszczony w katalogu Twojego projektu.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Krok 5: Dodaj Autokształt do slajdu
Dodaj Autokształt do slajdu. Kształt będzie zawierał tekst z niestandardowymi punktami wypunktowania.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Krok 6: Uzyskaj dostęp do ramki tekstowej
Uzyskaj dostęp do ramki tekstowej Autokształtu w celu manipulowania jego akapitami.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Krok 7: Usuń domyślny akapit
Usuń domyślny akapit, który jest automatycznie dodawany do ramki tekstowej.
```java
textFrame.getParagraphs().removeAt(0);
```
## Krok 8: Utwórz nowy akapit
Utwórz nowy akapit i ustaw jego tekst. Ten akapit będzie zawierał niestandardowe punkty obrazkowe.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Krok 9: Ustaw styl i obraz punktu
Ustaw styl punktu tak, aby używał wcześniej załadowanego obrazu niestandardowego.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Krok 10: Dostosuj wysokość pocisku
Ustaw wysokość punktu, aby mieć pewność, że będzie dobrze wyglądał w prezentacji.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Krok 11: Dodaj akapit do ramki tekstowej
Dodaj nowo utworzony akapit do ramki tekstowej Autokształtu.
```java
textFrame.getParagraphs().add(paragraph);
```
## Krok 12: Zapisz prezentację
Na koniec zapisz prezentację zarówno jako plik PPTX, jak i PPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Wniosek
I masz to! Wykonując te kroki, możesz łatwo dodać niestandardowe punkty obrazkowe do swoich prezentacji PowerPoint za pomocą Aspose.Slides dla Java. Ta potężna biblioteka oferuje szeroki zakres funkcji, które pomogą Ci tworzyć profesjonalne i atrakcyjne wizualnie prezentacje. Nie zapomnij zapoznać się z [dokumentacja](https://reference.aspose.com/slides/java/) aby uzyskać dostęp do bardziej zaawansowanych funkcji i opcji personalizacji.
## Najczęściej zadawane pytania
### Czym jest Aspose.Slides dla Java?
Aspose.Slides for Java to zaawansowana biblioteka umożliwiająca programistom Java programowe tworzenie, modyfikowanie i manipulowanie prezentacjami PowerPoint.
### Czy mogę użyć dowolnego obrazu w punktorach obrazkowych?
Tak, możesz użyć dowolnego obrazu w formie punktorów, pod warunkiem, że jest on dostępny w katalogu Twojego projektu.
### Czy potrzebuję licencji, aby używać Aspose.Slides dla Java?
Aspose.Slides dla Java wymaga licencji dla pełnej funkcjonalności. Możesz uzyskać tymczasową licencję od [Tutaj](https://purchase.aspose.com/temporary-license/) lub kup pełną licencję [Tutaj](https://purchase.aspose.com/buy).
### Czy mogę dodać wiele akapitów z różnymi stylami punktowania w jednym Autokształcie?
Tak, możesz dodać wiele akapitów z różnymi stylami punktowania do jednego Autokształtu, tworząc i konfigurując każdy akapit osobno.
### Gdzie mogę znaleźć więcej przykładów i pomoc?
Więcej przykładów znajdziesz w [dokumentacja](https://reference.aspose.com/slides/java/) i uzyskaj wsparcie od społeczności Aspose na [fora](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}