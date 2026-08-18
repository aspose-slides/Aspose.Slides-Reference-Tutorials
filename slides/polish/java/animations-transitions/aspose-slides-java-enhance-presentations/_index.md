---
date: '2026-06-23'
description: Dowiedz się, jak utworzyć tabelę w PowerPoint, dodać tekst do komórek
  tabeli, narysować ramki wokół tekstu oraz zapisać prezentację jako pptx przy użyciu
  Aspose.Slides for Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
title: Jak utworzyć tabelę w PowerPoint i narysować ramki za pomocą Aspose.Slides
  for Java
url: /pl/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak utworzyć tabelę w PowerPoint i rysować ramki za pomocą Aspose.Slides for Java

## Wprowadzenie

Tworzenie **create table in PowerPoint** programowo może zaoszczędzić godziny ręcznego formatowania, szczególnie gdy musisz wyróżnić kluczowe liczby lub dodać notatki wyjaśniające. W tym samouczku dowiesz się, jak dodać tekst do komórek tabeli, rysować ramki wokół konkretnych akapitów, ustawić precyzyjne wyrównanie tekstu oraz ostatecznie **save presentation as pptx** – wszystko przy użyciu potężnego API Aspose.Slides for Java. Po zakończeniu będziesz mieć slajd, który wygląda profesjonalnie, jest łatwy do odczytania i natychmiast przyciąga uwagę odbiorców do najważniejszych danych.

## Szybkie odpowiedzi
- **What does “add text to table” mean?** Oznacza to wstawianie lub aktualizowanie treści tekstowej poszczególnych komórek tabeli programowo.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – ten **save presentation as pptx** krok finalizuje twoje zmiany.  
- **How can I align text inside a shape?** Use `TextAlignment.Left` (or Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Yes – iterate over paragraphs, get their bounding rectangle, and add an `IAutoShape` with no fill and a black line.  
- **Do I need a license?** Tymczasowa licencja działa w trybie ewaluacji; pełna licencja jest wymagana w środowisku produkcyjnym.  

## Dlaczego rysować ramki wokół tekstu?

Rysowanie ramki (lub prostokąta) wokół akapitu lub konkretnego fragmentu — takiego jak dowolny tekst zawierający znak **'0'** — natychmiast przyciąga uwagę odbiorców do tej treści. Zapewnia wyraźny wizualny sygnał bez zmiany podstawowego tekstu, co czyni go idealnym do wyróżniania kluczowych liczb, ostrzeżeń lub oddzielania sekcji na slajdzie.

## Wymagania wstępne

Zanim zanurzysz się w kod, upewnij się, że masz następujące elementy:

### Wymagane biblioteki
Będziesz potrzebować Aspose.Slides for Java. Oto jak dodać go przy użyciu Maven lub Gradle:

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

### Konfiguracja środowiska
Upewnij się, że masz zainstalowany Java Development Kit (JDK), najlepiej JDK 16 lub nowszy, ponieważ ten przykład używa klasyfikatora `jdk16`.

### Wymagania wiedzy
- Podstawowa znajomość programowania w języku Java.  
- Znajomość oprogramowania do prezentacji, takiego jak PowerPoint.  
- Doświadczenie w korzystaniu ze zintegrowanego środowiska programistycznego (IDE), takiego jak IntelliJ IDEA lub Eclipse.

## Konfigurowanie Aspose.Slides dla Java

`Presentation` jest podstawową klasą Aspose.Slides, która reprezentuje plik PowerPoint w pamięci i zapewnia dostęp do slajdów, kształtów i tabel. Aby rozpocząć korzystanie z Aspose.Slides, wykonaj następujące kroki:

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

## Jak dodać tekst do tabeli w Aspose.Slides for Java?

Załaduj nową `Presentation`, utwórz tabelę w żądanych współrzędnych, wypełnij komórki obiektami `TextFrame`, a na końcu wywołaj `pres.save("output.pptx", SaveFormat.Pptx)`. Ta sekwencja tworzy **create table in PowerPoint**, wstawia niestandardowy tekst do każdej komórki i zapisuje wynik do pliku PPTX w jednym, efektywnym procesie.

### Funkcja 1: Utwórz tabelę i dodaj tekst do komórek

#### Przegląd
Ta funkcja demonstruje, jak **create table**, następnie **add text to table** w komórkach i później **save presentation as pptx**.

#### Kroki

**1. Create a Table**  
Najpierw zainicjuj prezentację i dodaj tabelę w pozycji (50, 50) z określonymi szerokościami kolumn i wysokościami wierszy.  
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

### Funkcja 2: Dodaj TextFrame do AutoShape i ustaw wyrównanie

#### Przegląd
Dowiedz się, jak dodać ramkę tekstową z określonym wyrównaniem do auto‑kształtu — przykład **set text alignment java**.

#### Kroki

AutoShape jest kształtem, który może zawierać tekst i grafikę.

**1. Add an AutoShape**  
Dodaj prostokąt jako AutoShape w pozycji (400, 100) o określonych wymiarach.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum defines horizontal alignment options for text within a shape.

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

### Funkcja 3: Rysuj ramki wokół akapitów i fragmentów w komórkach tabeli

#### Przegląd
Ta funkcja koncentruje się na **draw frames around text** oraz **draw rectangle around paragraph** dla fragmentów zawierających znak ‘0’.

#### Kroki

`IAutoShape` represents a shape object that can be drawn on a slide, such as rectangles used for frames.

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

## Typowe pułapki i wskazówki

- **Null checks** – Always wrap your `Presentation` usage in a try‑finally block to ensure `pres.dispose()` runs and frees native resources.  
- **Bounding rectangle accuracy** – The rectangle returned by `para.getRect()` reflects the current layout; if you change font size or margins, recompute the rectangle before drawing the frame.  
- **Performance** – When working with very large tables, consider batching shape additions or reusing a single `IAutoShape` instance with updated geometry to reduce memory overhead.  

## Najczęściej zadawane pytania

**Q: Czy mogę używać tych API z starszymi wersjami JDK?**  
A: Biblioteka obsługuje JDK 8 i nowsze, ale klasyfikator `jdk16` zapewnia najlepszą wydajność na nowszych środowiskach uruchomieniowych.

**Q: Jak zmienić kolor ramki?**  
A: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Czy można wyeksportować ostateczny slajd jako obraz?**  
A: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` and then save the byte array.

**Q: Co zrobić, jeśli muszę wyróżnić tylko słowo „Total” w komórce?**  
A: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion containing “Total”, and draw a rectangle around that portion’s bounding box.

**Q: Czy Aspose.Slides radzi sobie efektywnie z dużymi prezentacjami?**  
A: The API streams data and releases resources when `pres.dispose()` is called, which helps with memory management for large files.

---

**Last Updated:** 2026-06-23  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Powiązane samouczki

- [Aspose.Slides for Java&#58; Mistrzowska manipulacja tabelami i tekstem PPTX w prezentacjach PowerPoint](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Jak tworzyć dynamiczne ramki tekstowe w PowerPoint przy użyciu Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Dodaj kolumny w ramce tekstowej przy użyciu Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}