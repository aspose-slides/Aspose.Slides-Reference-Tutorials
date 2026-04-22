---
date: '2026-02-09'
description: Dowiedz się, jak rysować ramki wokół tekstu i dodawać tekst do komórek
  tabeli w programie PowerPoint przy użyciu Aspose.Slides for Java. Ten samouczek
  obejmuje tworzenie tabel, ustawianie wyrównania tekstu oraz zapisywanie prezentacji
  jako plik pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Jak rysować ramki i dodawać tekst do tabeli przy użyciu Aspose.Slides dla Javy
url: /pl/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak rysować ramki i dodawać tekst do tabeli w prezentacjach przy użyciu Aspose.Slides for Java

## Introduction

Prezentowanie danych w PowerPoint może być prawdziwą przeszkodą, szczególnie gdy trzeba **dodać tekst do komórek tabeli** i podkreślić ważne wartości za pomocą wskazówek wizualnych. W tym przewodniku nauczysz się **jak rysować ramki** wokół konkretnych akapitów, ustawiać wyrównanie tekstu wewnątrz kształtów oraz w końcu **zapisać prezentację jako pptx** — wszystko przy użyciu Aspose.Slides for Java. Po zakończeniu będziesz mieć dopracowaną prezentację, która przyciąga uwagę odbiorców dokładnie tam, gdzie chcesz.

Gotowy, aby Twoje slajdy wyróżniały się? Przejdźmy krok po kroku przez proces.

## Quick Answers
- **Co oznacza „add text to table”?** Oznacza to wstawianie lub aktualizowanie treści tekstowej poszczególnych komórek tabeli programowo.  
- **Która metoda zapisuje plik?** `pres.save("output.pptx", SaveFormat.Pptx)` – ten krok **save presentation as pptx** finalizuje Twoje zmiany.  
- **Jak mogę wyrównać tekst wewnątrz kształtu?** Użyj `TextAlignment.Left` (lub Center/Right) poprzez `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Czy mogę narysować prostokąt wokół akapitu?** Tak – iteruj po akapitach, pobierz ich prostokąt ograniczający i dodaj `IAutoShape` bez wypełnienia i z czarną linią.  
- **Czy potrzebuję licencji?** Tymczasowa licencja działa w trybie ewaluacji; pełna licencja jest wymagana w środowisku produkcyjnym.  

## Why draw frames around text?

Rysowanie ramki (lub prostokąta) wokół akapitu lub konkretnej części (na przykład dowolnego tekstu zawierającego znak **'0'**) natychmiast przyciąga uwagę. Ta technika jest idealna do:

- Podkreślania kluczowych danych finansowych w tabeli.  
- Wyróżniania ostrzeżeń lub ważnych notatek na slajdzie.  
- Tworzenia wizualnych separatorów bez ręcznego dodawania dodatkowych kształtów.

## Prerequisites

Zanim zagłębisz się w kod, upewnij się, że masz następujące:

### Required Libraries
Będziesz potrzebować Aspose.Slides for Java. Oto jak go dodać przy użyciu Maven lub Gradle:

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
- Podstawowa znajomość programowania w języku Java.  
- Znajomość oprogramowania do prezentacji, takiego jak PowerPoint.  
- Doświadczenie w korzystaniu ze zintegrowanego środowiska programistycznego (IDE), takiego jak IntelliJ IDEA lub Eclipse.

## Setting Up Aspose.Slides for Java

Aby rozpocząć korzystanie z Aspose.Slides, wykonaj następujące kroki:

1. **Install the Library**: Use Maven or Gradle to manage dependencies, or download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Start with a free trial by downloading a temporary license from [Temporary License](https://purchase.aspose.com/temporary-license/).
   - For full access, consider purchasing a license at [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
Initialize your presentation environment with the following code snippet:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## How to Add Text to Table in Aspose.Slides for Java

### Feature 1: Create Table and Add Text to Cells

#### Overview
This feature demonstrates how to **create table**, then **add text to table** cells and later **save presentation as pptx**.

#### Steps

**1. Create a Table**  
First, initialize your presentation and add a table at position (50, 50) with specified column widths and row heights.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Text to Cells**  
Create paragraphs with portions of text and add them to a specific cell.
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
Learn how to add a text frame with specific alignment to an auto shape—an example of **set text alignment java**.

#### Steps

**1. Add an AutoShape**  
Add a rectangle as an AutoShape at position (400, 100) with specified dimensions.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Set the text to “Text in shape” and align it to the left.
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
This feature focuses on **draw frames around text** and even **draw rectangle around paragraph** for portions containing the character ‘0’.

#### Steps

**1. Create a Table**  
Reuse the code from “Create Table and Add Text to Cells” for initial setup.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Reuse the paragraph creation code from the previous feature.
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
Iterate over paragraphs and portions to draw frames around them.
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

## Common Pitfalls & Tips

- **Null checks** – Always wrap your `Presentation` usage in a try‑finally block to ensure `pres.dispose()` runs and frees native resources.  
- **Bounding rectangle accuracy** – The rectangle returned by `para.getRect()` reflects the current layout; if you change font size or margins, recompute the rectangle before drawing the frame.  
- **Performance** – When working with very large tables, consider batching shape additions or reusing a single `IAutoShape` instance with updated geometry to reduce memory overhead.

## Frequently Asked Questions

**P: Czy mogę używać tych API ze starszymi wersjami JDK?**  
O: Biblioteka obsługuje JDK 8 i nowsze, ale klasyfikator `jdk16` zapewnia najlepszą wydajność na nowszych środowiskach uruchomieniowych.

**P: Jak zmienić kolor ramki?**  
O: Zmodyfikuj kolor wypełnienia formatu linii, np. `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**P: Czy można wyeksportować końcowy slajd jako obraz?**  
O: Tak – użyj `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` i następnie zapisz tablicę bajtów.

**P: Co zrobić, jeśli muszę podświetlić tylko słowo „Total” wewnątrz komórki?**  
O: Iteruj przez `cell.getTextFrame().getParagraphs()`, znajdź część zawierającą „Total” i narysuj prostokąt wokół prostokąta ograniczającego tę część.

**P: Czy Aspose.Slides radzi sobie efektywnie z dużymi prezentacjami?**  
O: API strumieniuje dane i zwalnia zasoby po wywołaniu `pres.dispose()`, co pomaga w zarządzaniu pamięcią przy dużych plikach.

---

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
