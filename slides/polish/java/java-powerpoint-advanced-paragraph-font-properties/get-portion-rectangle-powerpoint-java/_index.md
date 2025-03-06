---
title: Uzyskaj prostokąt części w programie PowerPoint z Javą
linktitle: Uzyskaj prostokąt części w programie PowerPoint z Javą
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak uzyskać prostokąt części w programie PowerPoint przy użyciu Aspose.Slides dla języka Java, korzystając ze szczegółowego samouczka krok po kroku. Idealny dla programistów Java.
type: docs
weight: 12
url: /pl/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---
## Wstęp
Tworzenie dynamicznych prezentacji w Javie jest proste dzięki Aspose.Slides dla Java. W tym samouczku zagłębimy się w szczegóły tworzenia prostokąta części w programie PowerPoint za pomocą Aspose.Slides. Omówimy wszystko, od skonfigurowania środowiska po rozbicie kodu krok po kroku. Więc zacznijmy!
## Warunki wstępne
Zanim przejdziemy do kodu, upewnijmy się, że masz wszystko, czego potrzebujesz, aby płynnie działać:
1. Zestaw Java Development Kit (JDK): Upewnij się, że na komputerze jest zainstalowany pakiet JDK 8 lub nowszy.
2.  Aspose.Slides dla Java: Pobierz najnowszą wersję z[Tutaj](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Eclipse, IntelliJ IDEA lub dowolne inne wybrane środowisko Java IDE.
4. Podstawowa znajomość języka Java: Zrozumienie programowania w języku Java jest niezbędne.
## Importuj pakiety
Na początek zaimportujmy niezbędne pakiety. Będzie to obejmować Aspose.Slides i kilka innych, które pozwolą efektywnie wykonać nasze zadanie.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Krok 1: Konfiguracja prezentacji
Pierwszym krokiem jest utworzenie nowej prezentacji. To będzie nasze płótno, nad którym będziemy pracować.
```java
Presentation pres = new Presentation();
```
## Krok 2: Tworzenie tabeli
Dodajmy teraz tabelę do pierwszego slajdu naszej prezentacji. Ta tabela będzie zawierać komórki, w których dodamy nasz tekst.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Krok 3: Dodawanie akapitów do komórek
Następnie utworzymy akapity i dodamy je do określonej komórki w tabeli. Wiąże się to z usunięciem istniejącego tekstu i dodaniem nowych akapitów.
```java
// Utwórz akapity
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Dodaj tekst do komórki tabeli
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Krok 4: Dodawanie ramki tekstowej do autokształtu
Aby nasza prezentacja była bardziej dynamiczna, dodamy ramkę tekstową do Autokształtu i ustawimy jej wyrównanie.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Krok 5: Obliczanie współrzędnych
Musimy uzyskać współrzędne lewego górnego rogu komórki tabeli. Pomoże nam to w dokładnym umieszczeniu kształtów.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Krok 6: Dodawanie ramek do akapitów i fragmentów
 Używając`IParagraph.getRect()` I`IPortion.getRect()`metodami możemy dodawać ramki do naszych akapitów i fragmentów. Obejmuje to przeglądanie akapitów i fragmentów, tworzenie wokół nich kształtów i dostosowywanie ich wyglądu.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Krok 7: Dodawanie ramek do akapitów Autokształtu
Podobnie dodamy ramki do akapitów w naszym Autokształcie, zwiększając atrakcyjność wizualną prezentacji.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Krok 8: Zapisywanie prezentacji
Na koniec zapiszemy naszą prezentację w określonej ścieżce.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Krok 9: Sprzątanie
Dobrą praktyką jest pozbywanie się obiektu prezentacji w celu zwolnienia zasobów.
```java
if (pres != null) pres.dispose();
```
## Wniosek
Gratulacje! Pomyślnie nauczyłeś się, jak uzyskać prostokąt części w programie PowerPoint przy użyciu Aspose.Slides dla Java. Ta potężna biblioteka otwiera świat możliwości programowego tworzenia dynamicznych i atrakcyjnych wizualnie prezentacji. Zanurz się głębiej w Aspose.Slides i odkryj więcej funkcji, aby jeszcze bardziej ulepszyć swoje prezentacje.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides dla Java to potężna biblioteka, która umożliwia programistom programowe tworzenie, modyfikowanie i manipulowanie prezentacjami programu PowerPoint.
### Czy mogę używać Aspose.Slides for Java w projektach komercyjnych?
 Tak, Aspose.Slides for Java może być używany w projektach komercyjnych. Możesz kupić licencję od[Tutaj](https://purchase.aspose.com/buy).
### Czy dostępna jest bezpłatna wersja próbna Aspose.Slides dla Java?
 Tak, możesz pobrać bezpłatną wersję próbną ze strony[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
 Dokumentacja jest dostępna[Tutaj](https://reference.aspose.com/slides/java/).
### Jak mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Możesz uzyskać pomoc na forum Aspose[Tutaj](https://forum.aspose.com/c/slides/11).