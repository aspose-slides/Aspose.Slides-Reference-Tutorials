---
title: Získejte částečný obdélník v PowerPointu s Javou
linktitle: Získejte částečný obdélník v PowerPointu s Javou
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak získat obdélník části v PowerPointu pomocí Aspose.Slides pro Java, pomocí tohoto podrobného, podrobného návodu. Ideální pro vývojáře v Javě.
type: docs
weight: 12
url: /cs/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---
## Úvod
Vytváření dynamických prezentací v Javě je s Aspose.Slides pro Javu hračkou. V tomto tutoriálu se ponoříme do toho nejnutnějšího získání obdélníku části v PowerPointu pomocí Aspose.Slides. Pokryjeme vše od nastavení vašeho prostředí až po rozebrání kódu krok za krokem. Takže, pojďme začít!
## Předpoklady
Než se pustíme do kódu, ujistěte se, že máte vše, co potřebujete, abyste mohli hladce postupovat:
1. Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný JDK 8 nebo vyšší.
2.  Aspose.Slides for Java: Stáhněte si nejnovější verzi z[tady](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Eclipse, IntelliJ IDEA nebo jakékoli jiné Java IDE dle vašeho výběru.
4. Základní znalost Javy: Pochopení programování v Javě je nezbytné.
## Importujte balíčky
Nejprve naimportujme potřebné balíčky. To bude zahrnovat Aspose.Slides a několik dalších pro efektivní zvládnutí našeho úkolu.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Krok 1: Nastavení prezentace
Prvním krokem je vytvoření nové prezentace. Toto bude naše plátno, na kterém budeme pracovat.
```java
Presentation pres = new Presentation();
```
## Krok 2: Vytvoření tabulky
Nyní přidáme tabulku na první snímek naší prezentace. Tato tabulka bude obsahovat buňky, do kterých přidáme náš text.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Krok 3: Přidání odstavců do buněk
Dále vytvoříme odstavce a přidáme je do konkrétní buňky v tabulce. To zahrnuje vymazání veškerého existujícího textu a následné přidání nových odstavců.
```java
// Vytvářejte odstavce
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Přidejte text do buňky tabulky
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Krok 4: Přidání textového rámečku do automatického tvaru
Aby byla naše prezentace dynamičtější, přidáme do automatického tvaru textový rámeček a nastavíme jeho zarovnání.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Krok 5: Výpočet souřadnic
Potřebujeme získat souřadnice levého horního rohu buňky tabulky. To nám pomůže umístit tvary přesně.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Krok 6: Přidání rámců do odstavců a částí
 Za použití`IParagraph.getRect()` a`IPortion.getRect()`můžeme do našich odstavců a částí přidat rámce. To zahrnuje opakování odstavců a částí, vytváření tvarů kolem nich a přizpůsobení jejich vzhledu.
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
## Krok 7: Přidání rámců do odstavců automatického tvaru
Podobně přidáme rámce k odstavcům v našem automatickém tvaru, čímž zvýšíme vizuální přitažlivost prezentace.
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
## Krok 8: Uložení prezentace
Nakonec naši prezentaci uložíme do zadané cesty.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Krok 9: Čištění
Je dobrým zvykem zlikvidovat objekt prezentace, abyste uvolnili zdroje.
```java
if (pres != null) pres.dispose();
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak získat obdélník části v PowerPointu pomocí Aspose.Slides for Java. Tato výkonná knihovna otevírá svět možností pro programové vytváření dynamických a vizuálně přitažlivých prezentací. Ponořte se hlouběji do Aspose.Slides a prozkoumejte další funkce pro další vylepšení vašich prezentací.
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonná knihovna, která umožňuje vývojářům programově vytvářet, upravovat a manipulovat s prezentacemi PowerPoint.
### Mohu používat Aspose.Slides pro Javu v komerčních projektech?
 Ano, Aspose.Slides for Java lze použít v komerčních projektech. Licenci si můžete zakoupit od[tady](https://purchase.aspose.com/buy).
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Slides for Java?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/slides/java/).
### Jak mohu získat podporu pro Aspose.Slides pro Java?
 Podporu můžete získat na fóru Aspose[tady](https://forum.aspose.com/c/slides/11).