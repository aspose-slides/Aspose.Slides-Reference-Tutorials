---
title: Scal komórki w tabeli programu PowerPoint za pomocą języka Java
linktitle: Scal komórki w tabeli programu PowerPoint za pomocą języka Java
second_title: Aspose.Slides API przetwarzania Java PowerPoint
description: Dowiedz się, jak łączyć komórki w tabelach programu PowerPoint przy użyciu Aspose.Slides dla Java. Ulepsz układ swojej prezentacji, korzystając z tego przewodnika krok po kroku.
weight: 17
url: /pl/java/java-powerpoint-table-manipulation/merge-cells-powerpoint-table-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Wstęp
W tym samouczku dowiesz się, jak skutecznie scalać komórki w tabeli programu PowerPoint za pomocą Aspose.Slides dla Java. Aspose.Slides to potężna biblioteka, która umożliwia programistom programowe tworzenie, manipulowanie i konwertowanie prezentacji programu PowerPoint. Łącząc komórki w tabeli, możesz dostosować układ i strukturę slajdów prezentacji, zwiększając przejrzystość i atrakcyjność wizualną.
## Warunki wstępne
Zanim zagłębisz się w ten samouczek, upewnij się, że spełniasz następujące wymagania wstępne:
- Podstawowa znajomość języka programowania Java.
- JDK (Java Development Kit) zainstalowany na twoim komputerze.
- IDE (Zintegrowane środowisko programistyczne), takie jak IntelliJ IDEA lub Eclipse.
-  Aspose.Slides dla biblioteki Java. Można go pobrać z[Tutaj](https://releases.aspose.com/slides/java/).

## Importuj pakiety
Na początek upewnij się, że zaimportowałeś pakiety niezbędne do pracy z Aspose.Slides:
```java
import com.aspose.slides.*;
import java.awt.*;
```
## Krok 1: Skonfiguruj swój projekt
Najpierw utwórz nowy projekt Java w preferowanym IDE i dodaj bibliotekę Aspose.Slides for Java do zależności projektu.
## Krok 2: Utwórz instancję obiektu prezentacji
 Utwórz instancję`Presentation` klasa reprezentująca plik PPTX, z którym pracujesz:
```java
Presentation presentation = new Presentation();
```
## Krok 3: Uzyskaj dostęp do slajdu
Przejdź do slajdu, do którego chcesz dodać tabelę. Na przykład, aby uzyskać dostęp do pierwszego slajdu:
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 4: Zdefiniuj wymiary tabeli
 Zdefiniuj kolumny i wiersze tabeli. Określ szerokości kolumn i wysokości wierszy jako tablice`double`:
```java
double[] dblCols = {70, 70, 70, 70};
double[] dblRows = {70, 70, 70, 70};
```
## Krok 5: Dodaj kształt tabeli do slajdu
Dodaj kształt tabeli do slajdu, korzystając ze zdefiniowanych wymiarów:
```java
ITable table = slide.getShapes().addTable(100, 50, dblCols, dblRows);
```
## Krok 6: Dostosuj obramowanie komórek
Ustaw format obramowania dla każdej komórki w tabeli. W tym przykładzie ustawiana jest czerwona, ciągła ramka o szerokości 5 dla każdej komórki:
```java
for (IRow row : table.getRows()) {
    for (ICell cell : (Iterable<ICell>) row) {
        // Ustaw format obramowania dla każdej strony komórki
        cell.getCellFormat().getBorderTop().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderTop().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderTop().setWidth(5);
        cell.getCellFormat().getBorderBottom().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderBottom().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderBottom().setWidth(5);
        cell.getCellFormat().getBorderLeft().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderLeft().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderLeft().setWidth(5);
        cell.getCellFormat().getBorderRight().getFillFormat().setFillType(FillType.Solid);
        cell.getCellFormat().getBorderRight().getFillFormat().getSolidFillColor().setColor(Color.RED);
        cell.getCellFormat().getBorderRight().setWidth(5);
    }
}
```
## Krok 7: Połącz komórki w tabeli
 Aby scalić komórki w tabeli, użyj opcji`mergeCells` metoda. Ten przykład łączy komórki od (1, 1) do (2, 1) i od (1, 2) do (2, 2):
```java
table.mergeCells(table.get_Item(1, 1), table.get_Item(2, 1), false);
table.mergeCells(table.get_Item(1, 2), table.get_Item(2, 2), false);
```
## Krok 8: Zapisz prezentację
Na koniec zapisz zmodyfikowaną prezentację w pliku PPTX na swoim dysku:
```java
String dataDir = "Your_Document_Directory_Path/";
presentation.save(dataDir + "MergeCells1_out.pptx", SaveFormat.Pptx);
```

## Wniosek
Wykonując poniższe kroki, z powodzeniem nauczyłeś się łączyć komórki w tabeli programu PowerPoint za pomocą Aspose.Slides dla Java. Technika ta umożliwia programowe tworzenie bardziej złożonych i atrakcyjnych wizualnie prezentacji, zwiększając produktywność i możliwości dostosowywania.
## Często zadawane pytania
### Co to jest Aspose.Slides dla Java?
Aspose.Slides for Java to interfejs API języka Java służący do programowego tworzenia, manipulowania i konwertowania prezentacji programu PowerPoint.
### Jak pobrać Aspose.Slides dla Java?
 Możesz pobrać Aspose.Slides dla Java z[Tutaj](https://releases.aspose.com/slides/java/).
### Czy mogę wypróbować Aspose.Slides dla Java przed zakupem?
 Tak, możesz uzyskać bezpłatną wersję próbną Aspose.Slides dla Java od[Tutaj](https://releases.aspose.com/).
### Gdzie mogę znaleźć dokumentację Aspose.Slides dla Java?
 Można znaleźć dokumentację[Tutaj](https://reference.aspose.com/slides/java/).
### Jak mogę uzyskać pomoc dotyczącą Aspose.Slides dla Java?
 Możesz uzyskać pomoc na forum społeczności Aspose.Slides[Tutaj](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
