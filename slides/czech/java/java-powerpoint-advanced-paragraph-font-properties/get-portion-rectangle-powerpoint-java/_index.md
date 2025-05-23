---
"description": "Naučte se, jak získat obdélník porce v PowerPointu pomocí Aspose.Slides pro Javu v tomto podrobném návodu krok za krokem. Ideální pro vývojáře v Javě."
"linktitle": "Získejte obdélník porce v PowerPointu pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Získejte obdélník porce v PowerPointu pomocí Javy"
"url": "/cs/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Získejte obdélník porce v PowerPointu pomocí Javy

## Zavedení
Vytváření dynamických prezentací v Javě je s Aspose.Slides pro Javu hračka. V tomto tutoriálu se ponoříme do detailů získání výřezového obdélníku v PowerPointu pomocí Aspose.Slides. Probereme vše od nastavení prostředí až po podrobný rozbor kódu. Tak pojďme na to!
## Předpoklady
Než se pustíme do samotného kódu, ujistěte se, že máte vše potřebné k bezproblémovému sledování:
1. Vývojová sada pro Javu (JDK): Ujistěte se, že máte na počítači nainstalovanou verzi JDK 8 nebo vyšší.
2. Aspose.Slides pro Javu: Stáhněte si nejnovější verzi z [zde](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Eclipse, IntelliJ IDEA nebo jakékoli jiné Java IDE dle vašeho výběru.
4. Základní znalost Javy: Znalost programování v Javě je nezbytná.
## Importovat balíčky
Nejdříve si importujme potřebné balíčky. Patří sem Aspose.Slides a několik dalších pro efektivní zvládnutí našeho úkolu.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Krok 1: Příprava prezentace
Prvním krokem je vytvoření nové prezentace. To bude naše plátno, na kterém budeme pracovat.
```java
Presentation pres = new Presentation();
```
## Krok 2: Vytvoření tabulky
Nyní přidejme tabulku na první snímek naší prezentace. Tato tabulka bude obsahovat buňky, kam přidáme náš text.
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
// Přidání textu do buňky tabulky
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Krok 4: Přidání textového rámečku do automatického tvaru
Aby byla naše prezentace dynamičtější, přidáme k automatickému tvaru textový rámeček a nastavíme jeho zarovnání.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Krok 5: Výpočet souřadnic
Potřebujeme zjistit souřadnice levého horního rohu buňky tabulky. To nám pomůže přesně umístit tvary.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Krok 6: Přidání rámců k odstavcům a částem
Použití `IParagraph.getRect()` a `IPortion.getRect()` metody, můžeme přidávat rámečky k našim odstavcům a částem. To zahrnuje iteraci odstavci a částmi, vytváření tvarů kolem nich a úpravu jejich vzhledu.
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
## Krok 7: Přidání rámců k odstavcům automatických tvarů
Podobně přidáme rámečky k odstavcům v našem automatickém tvaru, čímž vylepšíme vizuální atraktivitu prezentace.
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
Nakonec uložíme naši prezentaci do zadané cesty.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Krok 9: Úklid
Je dobrým zvykem zbavit se prezentačního objektu, aby se uvolnily prostředky.
```java
if (pres != null) pres.dispose();
```
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak v PowerPointu získat obdélník porce pomocí knihovny Aspose.Slides pro Javu. Tato výkonná knihovna otevírá svět možností pro programovou tvorbu dynamických a vizuálně atraktivních prezentací. Ponořte se hlouběji do knihovny Aspose.Slides a prozkoumejte další funkce, které vaše prezentace ještě více vylepší.
## Často kladené otázky
### Co je Aspose.Slides pro Javu?
Aspose.Slides pro Javu je výkonná knihovna, která umožňuje vývojářům programově vytvářet, upravovat a manipulovat s prezentacemi v PowerPointu.
### Mohu použít Aspose.Slides pro Javu v komerčních projektech?
Ano, Aspose.Slides pro Javu lze použít v komerčních projektech. Licenci si můžete zakoupit od [zde](https://purchase.aspose.com/buy).
### Je k dispozici bezplatná zkušební verze Aspose.Slides pro Javu?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Slides pro Javu?
Dokumentace je k dispozici [zde](https://reference.aspose.com/slides/java/).
### Jak mohu získat podporu pro Aspose.Slides pro Javu?
Podporu můžete získat na fóru Aspose [zde](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}