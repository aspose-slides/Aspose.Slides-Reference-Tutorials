---
date: '2025-12-10'
description: Dowiedz się, jak dodać tekst do tabeli i narysować ramki wokół tekstu
  w PowerPoint przy użyciu Aspose.Slides for Java. Ten przewodnik obejmuje tworzenie
  tabel, ustawianie wyrównania tekstu oraz otaczanie treści ramkami.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Aspose.Slides for Java – dodawanie tekstu do tabeli i manipulacja ramką
url: /pl/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Opanowanie manipulacji tabelami i ramkami w prezentacjach z Aspose.Slides dla Javy

## Introduction

Prezentowanie danych w sposób efektywny może być wyzwaniem w PowerPoint. Niezależnie od tego, czy jesteś programistą, czy projektantem prezentacji, **add text to table** komórki i rysowanie ramek wokół kluczowych akapitów sprawią, że Twoje slajdy będą przyciągać uwagę. W tym samouczku zobaczysz dokładnie, jak dodać tekst do tabeli, wyrównać go i narysować ramki wokół tekstu — wszystko przy użyciu Aspose.Slides dla Javy. Po zakończeniu będziesz w stanie tworzyć dopracowane prezentacje, które podkreślą właściwe informacje w odpowiednim momencie.

Gotowy, aby przekształcić swoje prezentacje? Zaczynajmy!

## Quick Answers
- **What does “add text to table” mean?** Oznacza to wstawianie lub aktualizowanie treści tekstowej poszczególnych komórek tabeli programowo.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – ten krok **save presentation as pptx** finalizuje Twoje zmiany.  
- **How can I align text inside a shape?** Użyj `TextAlignment.Left` (lub Center/Right) poprzez `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Tak – iteruj po akapitach, pobierz ich prostokąt ograniczający i dodaj `IAutoShape` bez wypełnienia oraz z czarną linią.  
- **Do I need a license?** Tymczasowa licencja działa w trybie ewaluacyjnym; pełna licencja jest wymagana w środowisku produkcyjnym.

## Prerequisites

Before diving into the code, ensure you have the following:

### Required Libraries
Będziesz potrzebować Aspose.Slides for Java. Oto jak go dodać używając Maven lub Gradle:

**Maven:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Environment Setup
Upewnij się, że masz zainstalowany Java Development Kit (JDK), najlepiej JDK 16 lub nowszy, ponieważ ten przykład używa klasyfikatora `jdk16`.

### Knowledge Prerequisites
- Podstawowa znajomość programowania w Javie.  
- Znajomość oprogramowania do prezentacji, takiego jak PowerPoint.  
- Doświadczenie w korzystaniu ze zintegrowanego środowiska programistycznego (IDE), takiego jak IntelliJ IDEA lub Eclipse.

## Setting Up Aspose.Slides for Java

Aby rozpocząć korzystanie z Aspose.Slides, wykonaj następujące kroki:

1. **Install the Library**: Użyj Maven lub Gradle do zarządzania zależnościami lub pobierz bibliotekę bezpośrednio z [Wydania Aspose.Slides dla Javy](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Rozpocznij od darmowej wersji próbnej, pobierając tymczasową licencję z [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Aby uzyskać pełny dostęp, rozważ zakup licencji pod adresem [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
Zainicjalizuj środowisko prezentacji przy użyciu poniższego fragmentu kodu:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Why add text to table and draw frames?

Dodawanie tekstu do tabeli pozwala jasno przedstawić dane strukturalne, a rysowanie ramek wokół akapitów lub konkretnych fragmentów (np. zawierających znak **'0'**) przyciąga uwagę widza do ważnych wartości. To połączenie jest idealne w raportach finansowych, dashboardach lub każdej prezentacji, w której trzeba wyróżnić kluczowe liczby bez zbędnego bałaganu.

## How to add text to table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
Ta funkcja demonstruje, jak **how to create table**, a następnie **add text to table** komórki i później **save presentation as pptx**.

#### Steps

**1. Create a Table**  
Najpierw zainicjalizuj prezentację i dodaj tabelę w pozycji (50, 50) o określonych szerokościach kolumn i wysokościach wierszy.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
Utwórz akapity z fragmentami tekstu i dodaj je do wybranej komórki.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 2: Add TextFrame to AutoShape and Set Alignment

#### Overview
Naucz się, jak dodać ramkę tekstową z określonym wyrównaniem do AutoShape — przykład **set text alignment java**.

#### Steps

**1. Add an AutoShape**  
Dodaj prostokąt jako AutoShape w pozycji (400, 100) o określonych wymiarach.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Ustaw tekst na „Text in shape” i wyrównaj go do lewej.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Feature 3: Draw Frames around Paragraphs and Portions in Table Cells

#### Overview
Ta funkcja koncentruje się na **draw frames around text** i nawet **draw rectangle around paragraph** dla fragmentów zawierających znak ‘0’.

#### Steps

**1. Create a Table**  
Ponownie użyj kodu z „Create Table and Add Text to Cells” do początkowej konfiguracji.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Ponownie użyj kodu tworzenia akapitów z poprzedniej funkcji.
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```

**3. Draw Frames**  
Iteruj po akapitach i fragmentach, aby narysować ramki wokół nich.
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Conclusion
Postępując zgodnie z tym przewodnikiem, możesz **add text to table**, wyrównać tekst wewnątrz kształtów oraz **draw frames around text**, aby podkreślić istotne informacje. Opanowanie tych technik pozwala tworzyć wysoce dopracowane, oparte na danych prezentacje z Aspose.Slides dla Javy. Aby dalej eksplorować możliwości, spróbuj połączyć te funkcje z wykresami, animacjami lub eksportem do PDF.

## Frequently Asked Questions

**Q: Can I use these APIs with older JDK versions?**  
A: Biblioteka obsługuje JDK 8 i nowsze, ale klasyfikator `jdk16` zapewnia najlepszą wydajność na nowszych środowiskach uruchomieniowych.

**Q: How do I change the frame color?**  
A: Zmodyfikuj kolor wypełnienia formatu linii, np. `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is it possible to export the final slide as an image?**  
A: Tak — użyj `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` i następnie zapisz tablicę bajtów.

**Q: What if I need to highlight only the word “Total” inside a cell?**  
A: Iteruj przez `cell.getTextFrame().getParagraphs()`, znajdź fragment zawierający „Total” i narysuj prostokąt wokół ramki ograniczającej tego fragmentu.

**Q: Does Aspose.Slides handle large presentations efficiently?**  
A: API strumieniuje dane i zwalnia zasoby po wywołaniu `pres.dispose()`, co pomaga w zarządzaniu pamięcią przy dużych plikach.

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2025-12-10  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}