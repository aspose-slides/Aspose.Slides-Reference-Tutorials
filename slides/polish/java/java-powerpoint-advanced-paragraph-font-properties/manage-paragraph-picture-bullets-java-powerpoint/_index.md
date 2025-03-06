---
title: Zarządzaj punktorami obrazkowymi akapitów w programie Java PowerPoint
linktitle: Zarządzaj punktorami obrazkowymi akapitów w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak dodawać niestandardowe punktory obrazkowe do slajdów programu PowerPoint za pomocą Aspose.Slides dla Java. Postępuj zgodnie z tym szczegółowym przewodnikiem krok po kroku, aby zapewnić bezproblemową integrację.
weight: 11
url: /pl/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zarządzaj punktorami obrazkowymi akapitów w programie Java PowerPoint

## Wstęp
Tworzenie angażujących i atrakcyjnych wizualnie prezentacji to kluczowa umiejętność we współczesnym świecie biznesu. Programiści Java mogą wykorzystać Aspose.Slides do ulepszenia swoich prezentacji za pomocą niestandardowych punktorów obrazkowych na slajdach programu PowerPoint. Ten samouczek przeprowadzi Cię krok po kroku przez cały proces, dzięki czemu możesz śmiało dodawać punktory obrazkowe do swoich prezentacji.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że spełniasz następujące wymagania wstępne:
- Zainstalowany zestaw Java Development Kit (JDK).
- Zintegrowane środowisko programistyczne (IDE), takie jak Eclipse lub IntelliJ IDEA
- Aspose.Slides dla biblioteki Java
- Podstawowa znajomość programowania w języku Java
- Plik obrazu dla zdjęcia pocisku
 Aby pobrać bibliotekę Aspose.Slides for Java, odwiedź stronę[strona pobierania](https://releases.aspose.com/slides/java/) . Aby zapoznać się z dokumentacją, sprawdź[dokumentacja](https://reference.aspose.com/slides/java/).
## Importuj pakiety
Najpierw upewnij się, że zaimportowałeś niezbędne pakiety dla swojego projektu. Dodaj następujący import na początku pliku Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Podzielmy proces na łatwe do wykonania etapy.
## Krok 1: Skonfiguruj katalog projektu
Utwórz nowy katalog dla swojego projektu. Katalog ten będzie zawierał plik Java, bibliotekę Aspose.Slides i plik obrazu punktora.
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Zainicjuj prezentację
 Zainicjuj nową instancję`Presentation` klasa. Ten obiekt reprezentuje prezentację programu PowerPoint.
```java
Presentation presentation = new Presentation();
```
## Krok 3: Uzyskaj dostęp do pierwszego slajdu
Uzyskaj dostęp do pierwszego slajdu prezentacji. Slajdy mają indeks zerowy, więc pierwszy slajd ma indeks 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 4: Załaduj obraz pocisku
Załaduj obraz, którego chcesz użyć w punktorach. Obraz ten należy umieścić w katalogu projektu.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Krok 5: Dodaj autokształt do slajdu
Dodaj autokształt do slajdu. Kształt będzie zawierał tekst z niestandardowymi punktorami.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Krok 6: Uzyskaj dostęp do ramki tekstowej
Uzyskaj dostęp do ramki tekstowej Autokształtu, aby manipulować jej akapitami.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Krok 7: Usuń domyślny akapit
Usuń domyślny akapit, który jest automatycznie dodawany do ramki tekstowej.
```java
textFrame.getParagraphs().removeAt(0);
```
## Krok 8: Utwórz nowy akapit
Utwórz nowy akapit i ustaw jego tekst. Ten akapit będzie zawierał niestandardowe punktory obrazkowe.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Krok 9: Ustaw styl i obraz punktora
Ustaw styl punktora, aby używać niestandardowego obrazu wczytanego wcześniej.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Krok 10: Dostosuj wysokość pocisku
Ustaw wysokość pocisku, aby mieć pewność, że będzie dobrze wyglądał w prezentacji.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Krok 11: Dodaj akapit do ramki tekstowej
Dodaj nowo utworzony akapit do ramki tekstowej Autokształtu.
```java
textFrame.getParagraphs().add(paragraph);
```
## Krok 12: Zapisz prezentację
Na koniec zapisz prezentację jako plik PPTX i PPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Wniosek
 I masz to! Wykonując poniższe kroki, możesz łatwo dodawać niestandardowe punktory obrazkowe do prezentacji programu PowerPoint za pomocą Aspose.Slides dla Java. Ta potężna biblioteka oferuje szeroką gamę funkcji ułatwiających tworzenie profesjonalnych i atrakcyjnych wizualnie prezentacji. Nie zapomnij zbadać[dokumentacja](https://reference.aspose.com/slides/java/)aby uzyskać bardziej zaawansowane funkcje i opcje dostosowywania.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężna biblioteka, która umożliwia programistom Java programowe tworzenie, modyfikowanie i manipulowanie prezentacjami programu PowerPoint.
### Czy mogę użyć dowolnego obrazu w punktorach obrazkowych?
Tak, możesz użyć dowolnego obrazu w punktorach obrazkowych, o ile jest on dostępny z katalogu twojego projektu.
### Czy potrzebuję licencji, aby używać Aspose.Slides dla Java?
 Aspose.Slides dla Java wymaga licencji dla pełnej funkcjonalności. Licencję tymczasową można uzyskać od[Tutaj](https://purchase.aspose.com/temporary-license/) lub kup pełną licencję[Tutaj](https://purchase.aspose.com/buy).
### Czy mogę dodać wiele akapitów z różnymi stylami punktorów w jednym Autokształcie?
Tak, możesz dodać wiele akapitów z różnymi stylami punktorów do jednego autokształtu, tworząc i konfigurując każdy akapit indywidualnie.
### Gdzie mogę znaleźć więcej przykładów i wsparcia?
 Więcej przykładów znajdziesz w[dokumentacja](https://reference.aspose.com/slides/java/) i uzyskaj wsparcie od społeczności Aspose na stronie[fora](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
