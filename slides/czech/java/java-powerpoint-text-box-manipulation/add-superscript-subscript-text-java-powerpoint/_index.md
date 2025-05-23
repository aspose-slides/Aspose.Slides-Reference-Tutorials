---
"description": "Naučte se, jak přidávat horní a dolní index textu do prezentací v PowerPointu v Javě pomocí Aspose.Slides pro Javu. Ideální pro vylepšení vašich slajdů."
"linktitle": "Přidání horního a dolního indexu v PowerPointu v Javě"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání horního a dolního indexu v PowerPointu v Javě"
"url": "/cs/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání horního a dolního indexu v PowerPointu v Javě

## Zavedení
Vytváření poutavých a informativních prezentací v PowerPointu často vyžaduje použití formátovacích funkcí, jako je horní a dolní index textu. Tento tutoriál vás provede procesem začlenění horního a dolního indexu textu do vašich prezentací v PowerPointu v Javě pomocí nástroje Aspose.Slides pro Javu.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
- Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
- Knihovna Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).
- Integrované vývojové prostředí (IDE), jako je IntelliJ IDEA nebo Eclipse, nastavené pro vývoj v Javě.
- Základní znalost programování v Javě a prezentací v PowerPointu.

## Importovat balíčky
Nejprve importujte potřebné balíčky z Aspose.Slides pro Javu:
```java
import com.aspose.slides.*;
```
## Krok 1: Příprava prezentace
```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Krok 2: Přístup ke snímku
```java
// Získejte první snímek
ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 3: Vytvořte textové pole
```java
// Vytvořte automatický tvar, který bude sloužit jako textové pole
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
ITextFrame textFrame = shape.getTextFrame();
textFrame.getParagraphs().clear();
```
## Krok 4: Přidání horního indexu
```java
// Vytvořte odstavec pro hlavní text
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Vytvořte část pro horní indexový text
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Nastavení escapementu pro horní index
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
// Přidejte hlavní odstavec s horním indexem do textového pole
textFrame.getParagraphs().add(mainParagraph);
```
## Krok 5: Přidání textu dolního indexu
```java
// Vytvořte další odstavec pro dolní indexový text
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Vytvořte část pro text dolního indexu
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Nastavení escapementu pro dolní index
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Přidání odstavce s dolním indexem do textového pole
textFrame.getParagraphs().add(subscriptParagraph);
```
## Krok 6: Uložte prezentaci
```java
// Uložit prezentaci
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Závěr
V tomto tutoriálu jsme se podívali na to, jak vylepšit vaše prezentace v PowerPointu v Javě pomocí horního a dolního indexu pomocí nástroje Aspose.Slides pro Javu. Dodržováním těchto kroků můžete vytvořit vizuálně přitažlivější a informativnější snímky, které efektivně sdělí váš obsah.

## Často kladené otázky
### Co je Aspose.Slides pro Javu?
Aspose.Slides pro Javu je robustní knihovna, která umožňuje vývojářům programově vytvářet, manipulovat a převádět prezentace v PowerPointu.
### Kde najdu další dokumentaci k Aspose.Slides pro Javu?
Podrobnou dokumentaci naleznete [zde](https://reference.aspose.com/slides/java/).
### Jak mohu získat dočasnou licenci pro Aspose.Slides pro Javu?
Můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).
### Mohu si Aspose.Slides pro Javu vyzkoušet zdarma?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).
### Kde mohu získat podporu pro Aspose.Slides pro Javu?
Pro podporu a diskuzi navštivte [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}