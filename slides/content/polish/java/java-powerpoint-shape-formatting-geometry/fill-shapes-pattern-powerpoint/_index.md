---
title: Wypełnianie kształtów wzorkiem w programie PowerPoint
linktitle: Wypełnianie kształtów wzorkiem w programie PowerPoint
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak wypełniać kształty wzorami w programie PowerPoint przy użyciu aplikacji Aspose.Slides dla języka Java. Postępuj zgodnie z naszym prostym przewodnikiem krok po kroku, aby wizualnie ulepszyć swoje prezentacje.
type: docs
weight: 11
url: /pl/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/
---
## Wstęp
Tworzenie atrakcyjnych wizualnie prezentacji jest niezbędne, aby zaangażować odbiorców. Jednym ze sposobów ulepszenia slajdów programu PowerPoint jest wypełnianie kształtów wzorami. W tym samouczku omówimy etapy wypełniania kształtów wzorami przy użyciu Aspose.Slides dla Java. Ten przewodnik jest przeznaczony dla programistów, którzy chcą wykorzystać zaawansowane funkcje Aspose.Slides do programowego tworzenia wspaniałych prezentacji.
## Warunki wstępne
Zanim zagłębisz się w kod, upewnij się, że spełniasz następujące wymagania wstępne:
- Zestaw Java Development Kit (JDK) zainstalowany na komputerze.
- Zintegrowane środowisko programistyczne (IDE), takie jak IntelliJ IDEA lub Eclipse.
-  Aspose.Slides dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).
- Podstawowa znajomość programowania w języku Java.
## Importuj pakiety
Najpierw zaimportujmy niezbędne pakiety wymagane w naszym przykładzie.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Krok 1: Skonfiguruj swój projekt
Przed napisaniem kodu upewnij się, że projekt jest poprawnie skonfigurowany. Utwórz nowy projekt Java w swoim IDE i dodaj bibliotekę Aspose.Slides for Java do zależności projektu.
## Krok 2: Utwórz katalog dokumentów
Aby efektywnie zarządzać Twoimi plikami, utwórzmy katalog, w którym będziemy zapisywać naszą prezentację PowerPoint.
```java
String dataDir = "Your Document Directory";
// Utwórz katalog, jeśli jeszcze nie istnieje.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
Ten fragment sprawdza, czy katalog istnieje i tworzy go, jeśli nie.
## Krok 3: Utwórz instancję klasy prezentacji
 Następnie musimy utworzyć instancję`Presentation` class, która reprezentuje nasz plik PowerPoint.
```java
Presentation pres = new Presentation();
```
Spowoduje to inicjowanie nowego obiektu prezentacji, którego będziemy używać do dodawania slajdów i kształtów.
## Krok 4: Uzyskaj dostęp do pierwszego slajdu
Na początek musimy uzyskać dostęp do pierwszego slajdu naszej prezentacji. Tutaj będziemy dodawać nasze kształty.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 5: Dodaj kształt prostokąta
Dodajmy do naszego slajdu prostokątny kształt. Prostokąt ten zostanie wypełniony wzorem.
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Ten fragment kodu dodaje prostokąt do slajdu w określonym położeniu i rozmiarze.
## Krok 6: Ustaw typ wypełnienia na wzór
Teraz musimy ustawić typ wypełnienia naszego prostokąta na wypełnienie wzorem.
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## Krok 7: Wybierz styl wzoru
Aspose.Slides zapewnia różne style wzorów. W tym przykładzie użyjemy wzoru „Trellis”.
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## Krok 8: Ustaw kolory wzoru
Możemy dostosować kolorystykę naszego wzoru. Ustawmy kolor tła na jasnoszary, a kolor pierwszego planu na żółty.
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## Krok 9: Zapisz prezentację
Po ustawieniu naszego kształtu z pożądanym wzorem musimy zapisać prezentację do pliku.
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
Spowoduje to zapisanie prezentacji w określonym katalogu pod nazwą pliku „RectShpPatt_out.pptx”.
## Krok 10: Oczyść zasoby
Dobrą praktyką jest pozbywanie się obiektu prezentacji w celu zwolnienia zasobów.
```java
if (pres != null) pres.dispose();
```
## Wniosek
Gratulacje! Pomyślnie wypełniłeś kształt wzorkiem na slajdzie programu PowerPoint przy użyciu Aspose.Slides for Java. Ta potężna biblioteka umożliwia łatwe tworzenie prezentacji i manipulowanie nimi, dodając profesjonalny charakter do Twoich projektów.
 Postępując zgodnie z tym przewodnikiem krok po kroku, możesz wzbogacić swoje prezentacje różnymi wzorami, dzięki czemu będą bardziej wciągające i atrakcyjne wizualnie. Aby uzyskać bardziej zaawansowane funkcje i opcje dostosowywania, zapoznaj się z sekcją[Aspose.Slides dla dokumentacji Java](https://reference.aspose.com/slides/java/).
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to potężny interfejs API, który umożliwia programistom tworzenie, manipulowanie i konwertowanie prezentacji programu PowerPoint w aplikacjach Java.
### Jak mogę pobrać Aspose.Slides dla Java?
 Możesz pobrać Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/).
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla Java?
 Tak, możesz uzyskać bezpłatną wersję próbną od[Tutaj](https://releases.aspose.com/).
### Czy mogę używać Aspose.Slides for Java do manipulowania istniejącymi prezentacjami?
Tak, Aspose.Slides for Java umożliwia otwieranie, edytowanie i zapisywanie istniejących prezentacji programu PowerPoint.
### Gdzie mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Możesz uzyskać wsparcie od[Forum wsparcia Aspose.Slides](https://forum.aspose.com/c/slides/11).