---
title: Ustaw automatyczne dopasowanie ramki tekstowej w programie Java PowerPoint
linktitle: Ustaw automatyczne dopasowanie ramki tekstowej w programie Java PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak ustawić automatyczne dopasowanie ramek tekstowych w programie Java PowerPoint przy użyciu programu Aspose.Slides dla języka Java. Twórz dynamiczne prezentacje bez wysiłku.
weight: 14
url: /pl/java/java-powerpoint-text-font-customization/set-autofit-text-frame-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Wstęp
Podczas tworzenia aplikacji w języku Java powszechnym wymogiem jest programowe tworzenie dynamicznych i atrakcyjnych wizualnie prezentacji programu PowerPoint. Aspose.Slides for Java zapewnia potężny zestaw interfejsów API, które pozwalają to osiągnąć bez wysiłku. Jedną z istotnych funkcji jest ustawienie automatycznego dopasowania ramek tekstowych, co zapewnia dokładne dopasowanie tekstu w kształtach bez konieczności ręcznego dopasowywania. Ten samouczek poprowadzi Cię krok po kroku przez proces, wykorzystując Aspose.Slides for Java do automatyzacji dopasowywania tekstu na slajdach programu PowerPoint.
## Warunki wstępne
Zanim przejdziesz do samouczka, upewnij się, że masz skonfigurowane następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany w systemie
- Biblioteka Aspose.Slides for Java pobrana i przywoływana w projekcie Java
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse
### Importuj pakiety
Po pierwsze, pamiętaj o zaimportowaniu niezbędnych klas Aspose.Slides do swojego projektu Java:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Krok 1: Utwórz nową prezentację
Rozpocznij od utworzenia nowej instancji prezentacji programu PowerPoint, w której dodasz slajdy i kształty.
```java
// Ścieżka do katalogu dokumentów.
String dataDir = "Your Document Directory";
// Utwórz instancję klasy Prezentacja
Presentation presentation = new Presentation();
```
## Krok 2: Uzyskaj dostęp do slajdu, aby dodać kształty
Uzyskaj dostęp do pierwszego slajdu prezentacji, do którego chcesz dodać kształt z tekstem autodopasowanym.
```java
// Uzyskaj dostęp do pierwszego slajdu
ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 3: Dodaj autokształt (prostokąt)
Dodaj autokształt (prostokąt) do slajdu o określonych współrzędnych i wymiarach.
```java
// Dodaj typ Autokształtu prostokąta
IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 350, 350);
```
## Krok 4: Dodaj ramkę tekstową do prostokąta
Dodaj ramkę tekstową do kształtu prostokąta.
```java
// Dodaj ramkę tekstową do prostokąta
ashp.addTextFrame(" ");
ashp.getFillFormat().setFillType(FillType.NoFill);
```
## Krok 5: Ustaw automatyczne dopasowanie ramki tekstowej
Ustaw właściwości automatycznego dopasowania ramki tekstowej, aby dostosować tekst na podstawie rozmiaru kształtu.
```java
// Dostęp do ramki tekstowej
ITextFrame txtFrame = ashp.getTextFrame();
txtFrame.getTextFrameFormat().setAutofitType(TextAutofitType.Shape);
```
## Krok 6: Dodaj tekst do ramki tekstowej
Dodaj treść tekstową do ramki tekstowej w kształcie.
```java
// Utwórz obiekt Akapit dla ramki tekstowej
IParagraph para = txtFrame.getParagraphs().get_Item(0);
// Utwórz obiekt Porcja dla akapitu
IPortion portion = para.getPortions().get_Item(0);
portion.setText("A quick brown fox jumps over the lazy dog. A quick brown fox jumps over the lazy dog.");
portion.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
portion.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
## Krok 7: Zapisz prezentację
Zapisz zmodyfikowaną prezentację z ramką tekstową automatycznego dopasowania.
```java
// Zapisz prezentację
presentation.save(dataDir + "formatText_out.pptx", SaveFormat.Pptx);
```

## Wniosek
W tym samouczku nauczyłeś się, jak ustawić automatyczne dopasowanie ramek tekstowych w prezentacjach Java PowerPoint przy użyciu Aspose.Slides dla Java. Wykonując poniższe kroki, możesz zautomatyzować dopasowywanie tekstu w kształtach, programowo poprawiając czytelność i estetykę prezentacji.

## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to solidny interfejs API Java, który pozwala programistom tworzyć, czytać, manipulować i konwertować prezentacje programu PowerPoint.
### Jak pobrać Aspose.Slides dla Java?
 Możesz pobrać Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/).
### Czy mogę bezpłatnie wypróbować Aspose.Slides dla Java?
 Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Slides dla Java od[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
 Możesz znaleźć szczegółową dokumentację Aspose.Slides dla Java[Tutaj](https://reference.aspose.com/slides/java/).
### Jak mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Możesz uzyskać wsparcie społeczności i profesjonalne wsparcie dla Aspose.Slides for Java od[Tutaj](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
