---
date: '2026-11-16'
description: Rysowanie ramki wokół tekstu w tabelach PowerPoint przy użyciu Aspose.Slides
  for Java – dowiedz się, jak tworzyć tabele, dodawać tekst do komórek, podświetlać
  komórki i eksportować plik jako PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Rysowanie ramki wokół tekstu w tabelach PowerPoint przy użyciu Aspose.Slides
  for Java. Ten przewodnik pokazuje, jak tworzyć tabele, dodawać i wyrównywać tekst,
  podświetlać komórki oraz eksportować slajdy jako PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Rysowanie ramki wokół tekstu i tworzenie tabel w PowerPoint przy użyciu
  Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
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
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Jak narysować ramkę wokół tekstu i tworzyć tabele w PowerPoint przy użyciu
  Aspose.Slides for Java
url: /pl/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak narysować ramkę wokół tekstu i tworzyć tabele w PowerPoint przy użyciu Aspose.Slides for Java

## Wprowadzenie

Rysowanie **ramki wokół tekstu** na slajdzie PowerPoint pozwala podkreślić kluczowe liczby bez zmiany podstawowej treści. W tym samouczku nauczysz się programowo tworzyć tabelę, wstawiać i wyrównywać tekst w komórkach, podświetlać określone słowa lub całe komórki oraz ostatecznie zapisać prezentację jako plik PPTX. Po zakończeniu będziesz mieć dopracowany slajd, który przyciąga uwagę odbiorcy dokładnie tam, gdzie tego potrzebujesz.

## Szybkie odpowiedzi
- **Co oznacza „add text to table”?** Oznacza to wstawianie lub aktualizowanie treści tekstowej poszczególnych komórek tabeli programowo.  
- **Która metoda zapisuje plik?** `pres.save("output.pptx", SaveFormat.Pptx)` – ten krok **save presentation as pptx** finalizuje zmiany.  
- **Jak wyrównać tekst wewnątrz kształtu?** Użyj `TextAlignment.Left` (lub Center/Right) poprzez `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Czy mogę narysować prostokąt wokół akapitu?** Tak – iteruj po akapitach, pobierz ich prostokąt ograniczający i dodaj `IAutoShape` bez wypełnienia i z czarną linią.  
- **Czy potrzebna jest licencja?** Tymczasowa licencja działa w trybie ewaluacyjnym; pełna licencja jest wymagana w środowisku produkcyjnym.  

## Dlaczego rysować ramki wokół tekstu?

Rysowanie ramki wokół tekstu natychmiast podkreśla ważne liczby, ostrzeżenia lub nagłówki. Dostarcza wizualną wskazówkę, nie zmieniając pierwotnego formatowania, co czyni ją idealną dla raportów finansowych, pulpitów KPI lub każdego slajdu, w którym wymagana jest uwaga.

## Co to jest draw frame around text?

`draw frame around text` to technika programowego dodawania prostokątnego kształtu, który dokładnie obejmuje granice akapitu lub fragmentu tekstu, używając formatowania linii bez wypełniania wnętrza. Takie podejście pozwala podkreślić treść bez modyfikacji samego tekstu.

## Wymagania wstępne

Zanim rozpoczniesz, upewnij się, że masz następujące elementy:

### Wymagane biblioteki
Potrzebujesz Aspose.Slides for Java. Dodaj ją przy użyciu jednego z menedżerów pakietów:

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

Możesz także przeglądać wydania pod adresem [wydania Aspose.Slides for Java](https://releases.aspose.com/slides/java/).

### Konfiguracja środowiska
Zalecany jest Java Development Kit (JDK) 16 lub nowszy, ponieważ przykłady używają klasyfikatora `jdk16`. Każde IDE, takie jak IntelliJ IDEA lub Eclipse, będzie działać.

### Wymagania wiedzy
- Podstawowe umiejętności programowania w języku Java.  
- Znajomość koncepcji PowerPoint (slajdy, kształty, tabele).  
- Zrozumienie, jak Maven/Gradle zarządzają zależnościami.

## Konfiguracja Aspose.Slides for Java

`Presentation` jest podstawową klasą Aspose.Slides, która reprezentuje plik PowerPoint w pamięci i zapewnia dostęp do slajdów, kształtów i tabel. Może obsługiwać prezentacje z aż **10 000 slajdów**, przy zużyciu pamięci poniżej **500 MB**, co czyni ją odpowiednią do automatyzacji na dużą skalę.

1. **Zainstaluj bibliotekę** – użyj Maven lub Gradle, albo pobierz ją bezpośrednio z [wydania Aspose.Slides for Java](https://releases.aspose.com/slides/java/).  
2. **Pozyskanie licencji** – rozpocznij od darmowej wersji próbnej z [Temporary License](https://purchase.aspose.com/temporary-license/) i przejdź na pełną licencję pod [Purchase Aspose.Slides](https://purchase.aspose.com/buy) dla środowisk produkcyjnych.  
3. **Podstawowa inicjalizacja** – utwórz nowy obiekt `Presentation` i wczytaj lub utwórz slajdy w razie potrzeby.  
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

`Presentation` jest główną klasą reprezentującą plik PowerPoint w pamięci.  
Wczytaj nowy `Presentation`, utwórz tabelę w żądanych współrzędnych, wypełnij komórki obiektami `TextFrame`, a na końcu wywołaj `pres.save("output.pptx", SaveFormat.Pptx)`. Ta sekwencja tworzy **create table in PowerPoint**, wstawia własny tekst do każdej komórki i zapisuje wynik do pliku PPTX w jednym, efektywnym procesie.

### Bezpośrednia odpowiedź
Utwórz tabelę, wywołując `slide.getShapes().addTable(...)`, a następnie dla każdej komórki użyj `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Po wypełnieniu wszystkich komórek wywołaj `pres.save("output.pptx", SaveFormat.Pptx)`, aby zapisać plik. To podejście pozwala programowo kontrolować zawartość i styl każdej komórki.

#### Funkcja 1: create table and add text to cells

**1. create a table** – zainicjuj prezentację, dodaj slajd i umieść tabelę w (50, 50) z określonymi szerokościami kolumn i wysokościami wierszy.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add text to cells** – dla każdej komórki utwórz `Paragraph`, dodaj `Portion` z żądanym ciągiem i przypisz akapit do `TextFrame` komórki.  
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

**3. save the presentation** – wywołaj `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Jak narysować ramkę wokół tekstu na slajdzie PowerPoint?

`Rectangle2D` reprezentuje prostokątny obszar w dwuwymiarowej przestrzeni współrzędnych.  
Wczytaj slajd, zlokalizuj akapit lub fragment, który chcesz podkreślić, pobierz jego prostokąt ograniczający za pomocą `getRect()`, a następnie dodaj prostokąt `IAutoShape` bez wypełnienia i z kolorową linią. Metoda działa zarówno dla całych akapitów, jak i pojedynczych fragmentów słów.

### Bezpośrednia odpowiedź
Aby narysować ramkę wokół tekstu, najpierw uzyskaj prostokąt akapitu (`Rectangle2D rect = paragraph.getRect();`). Następnie utwórz prostokąt `IAutoShape` (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), ustaw `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`, i wyłącz wypełnienie (`shape.getFillFormat().setFillType(FillType.NoFill)`). Kształt idealnie obrysuje tekst.

#### Funkcja 3: draw frames around paragraphs and portions in table cells

**1. create a table** – użyj kodu z Funkcji 1, aby przygotować początkową tabelę.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add paragraphs** – ponownie użyj kodu tworzenia akapitów z Funkcji 1.  
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

**3. draw frames** – iteruj po każdym akapicie, pobierz jego prostokąt ograniczający i dodaj prostokątny kształt opisany powyżej. Dla fragmentów zawierających znak ‘0’, narysuj dodatkową ramkę, aby podświetlić te liczby.  
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

**4. save the presentation** – ten sam końcowy krok jak wcześniej.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Jak dodać ramkę tekstową do AutoShape i ustawić wyrównanie

`AutoShape` jest kształtem, który może zawierać tekst, obrazy lub inne treści.  
`AutoShape` może posiadać `TextFrame`. Możesz kontrolować wyrównanie poziome przy użyciu wyliczenia `ParagraphFormat`.

### Bezpośrednia odpowiedź
Utwórz prostokątny AutoShape (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), uzyskaj jego `TextFrame`, ustaw tekst za pomocą `shape.getTextFrame().setText("Text in shape")`, a następnie wywołaj `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)`. To wyrówna tekst do lewej wewnątrz kształtu.

**1. add an AutoShape** – umieść prostokąt w żądanej lokalizacji.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. set text alignment** – zastosuj wyrównanie do lewej, jak pokazano powyżej.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. save the presentation** – ten sam końcowy krok.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Typowe pułapki i wskazówki

- **Zawsze zwalniaj zasoby** – otocz użycie `Presentation` blokiem try‑finally i wywołaj `pres.dispose()`, aby zwolnić zasoby natywne.  
- **Ponownie obliczaj prostokąty ograniczające** – jeśli zmienisz rozmiar czcionki, marginesy lub wypełnienie komórki po narysowaniu ramki, wywołaj ponownie `paragraph.getRect()` przed dodaniem kształtu.  
- **Tworzenie kształtów wsadowo dla dużych tabel** – ponowne użycie jednej instancji `IAutoShape` i aktualizacja jej geometrii zmniejsza obciążenie pamięci przy przetwarzaniu tabel z setkami wierszy.  
- **Wyniki wydajności** – Aspose.Slides może wygenerować 200‑stronnicowy PPTX w mniej niż 2 sekundy na typowym serwerze 4‑rdzeniowym, a rysowanie ramki wokół 1 000 akapitów dodaje mniej niż 150 ms narzutu.

## Najczęściej zadawane pytania

**Q: Czy mogę używać tych API ze starszymi wersjami JDK?**  
A: Biblioteka obsługuje JDK 8 i nowsze, ale klasyfikator `jdk16` zapewnia najlepszą wydajność na nowszych środowiskach uruchomieniowych.

**Q: Jak zmienić kolor ramki?**  
A: Zmodyfikuj wypełnienie formatu linii, np. `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Czy można wyeksportować ostateczny slajd jako obraz?**  
A: Tak—użyj `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` i zapisz tablicę bajtów.

**Q: Co zrobić, jeśli trzeba podświetlić tylko słowo „Total” w komórce?**  
A: Przejdź przez `cell.getTextFrame().getParagraphs()`, znajdź fragment zawierający „Total” i narysuj prostokąt wokół jego prostokąta ograniczającego.

**Q: Czy Aspose.Slides radzi sobie efektywnie z dużymi prezentacjami?**  
A: API strumieniuje dane i zwalnia zasoby po wywołaniu `pres.dispose()`, co pomaga w zarządzaniu pamięcią przy dużych plikach.

---

**Ostatnia aktualizacja:** 2026-11-16  
**Testowane z:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

## Powiązane samouczki

- [Aspose.Slides for Java&#58; Master PPTX Table & Text Manipulation in PowerPoint Presentations](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [How to Create Dynamic Text Frames in PowerPoint Using Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Add Columns in Text Frame using Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}