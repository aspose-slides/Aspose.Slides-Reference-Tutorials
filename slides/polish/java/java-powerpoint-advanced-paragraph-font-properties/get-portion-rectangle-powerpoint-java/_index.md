---
"description": "Dowiedz się, jak uzyskać prostokąt porcji w programie PowerPoint za pomocą Aspose.Slides dla Java dzięki temu szczegółowemu samouczkowi krok po kroku. Idealne dla programistów Java."
"linktitle": "Uzyskaj część prostokąta w programie PowerPoint za pomocą języka Java"
"second_title": "Aspose.Slides Java PowerPoint Processing API"
"title": "Uzyskaj część prostokąta w programie PowerPoint za pomocą języka Java"
"url": "/pl/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Uzyskaj część prostokąta w programie PowerPoint za pomocą języka Java

## Wstęp
Tworzenie dynamicznych prezentacji w Javie jest dziecinnie proste dzięki Aspose.Slides for Java. W tym samouczku zagłębimy się w szczegóły uzyskiwania prostokąta porcji w programie PowerPoint za pomocą Aspose.Slides. Omówimy wszystko, od konfiguracji środowiska po rozbicie kodu krok po kroku. Więc zaczynajmy!
## Wymagania wstępne
Zanim przejdziemy do kodu, upewnijmy się, że masz wszystko, czego potrzebujesz, aby płynnie kontynuować pracę:
1. Java Development Kit (JDK): Upewnij się, że na Twoim komputerze zainstalowany jest JDK w wersji 8 lub nowszej.
2. Aspose.Slides dla Java: Pobierz najnowszą wersję z [Tutaj](https://releases.aspose.com/slides/java/).
3. Zintegrowane środowisko programistyczne (IDE): Eclipse, IntelliJ IDEA lub dowolne inne środowisko IDE Java według własnego wyboru.
4. Podstawowa znajomość języka Java: Znajomość programowania w języku Java jest niezbędna.
## Importuj pakiety
Po pierwsze, zaimportujmy niezbędne pakiety. Będą to Aspose.Slides i kilka innych, aby sprawnie obsłużyć nasze zadanie.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Krok 1: Konfigurowanie prezentacji
Pierwszym krokiem jest stworzenie nowej prezentacji. To będzie nasze płótno do pracy.
```java
Presentation pres = new Presentation();
```
## Krok 2: Tworzenie tabeli
Teraz dodajmy tabelę do pierwszego slajdu naszej prezentacji. Ta tabela będzie zawierać komórki, w których dodamy nasz tekst.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Krok 3: Dodawanie akapitów do komórek
Następnie utworzymy akapity i dodamy je do konkretnej komórki w tabeli. Wiąże się to z wyczyszczeniem istniejącego tekstu, a następnie dodaniem nowych akapitów.
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
Aby nadać naszej prezentacji więcej dynamiki, dodamy ramkę tekstową do autokształtu i ustawimy jej wyrównanie.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Krok 5: Obliczanie współrzędnych
Musimy uzyskać współrzędne lewego górnego rogu komórki tabeli. Pomoże nam to dokładnie umieścić kształty.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Krok 6: Dodawanie ramek do akapitów i części
Korzystanie z `IParagraph.getRect()` I `IPortion.getRect()` metod, możemy dodawać ramki do naszych akapitów i fragmentów. Wiąże się to z iterowaniem po akapitach i fragmentach, tworzeniem wokół nich kształtów i dostosowywaniem ich wyglądu.
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
## Krok 7: Dodawanie ramek do akapitów Autokształt
Podobnie dodamy ramki do akapitów w naszym Autokształcie, zwiększając w ten sposób atrakcyjność wizualną prezentacji.
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
## Krok 9: Czyszczenie
Dobrą praktyką jest usuwanie obiektu prezentacji w celu zwolnienia zasobów.
```java
if (pres != null) pres.dispose();
```
## Wniosek
Gratulacje! Udało Ci się nauczyć, jak uzyskać prostokąt porcji w programie PowerPoint za pomocą Aspose.Slides dla Javy. Ta potężna biblioteka otwiera świat możliwości tworzenia dynamicznych i atrakcyjnych wizualnie prezentacji programowo. Zanurz się głębiej w Aspose.Slides i odkryj więcej funkcji, aby jeszcze bardziej ulepszyć swoje prezentacje.
## Najczęściej zadawane pytania
### Czym jest Aspose.Slides dla Java?
Aspose.Slides for Java to zaawansowana biblioteka umożliwiająca programistom programistyczne tworzenie, modyfikowanie i manipulowanie prezentacjami PowerPoint.
### Czy mogę używać Aspose.Slides for Java w projektach komercyjnych?
Tak, Aspose.Slides for Java może być używany w projektach komercyjnych. Możesz kupić licencję od [Tutaj](https://purchase.aspose.com/buy).
### Czy jest dostępna bezpłatna wersja próbna Aspose.Slides for Java?
Tak, możesz pobrać bezpłatną wersję próbną z [Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
Dokumentacja jest dostępna [Tutaj](https://reference.aspose.com/slides/java/).
### Gdzie mogę uzyskać pomoc techniczną dotyczącą Aspose.Slides dla Java?
Możesz uzyskać wsparcie na forum Aspose [Tutaj](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}