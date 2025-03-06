---
title: Přidejte text horního a dolního indexu v Java PowerPointu
linktitle: Přidejte text horního a dolního indexu v Java PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přidávat text horního a dolního indexu do prezentací Java PowerPoint pomocí Aspose.Slides for Java. Ideální pro vylepšení vašich snímků.
weight: 13
url: /cs/java/java-powerpoint-text-box-manipulation/add-superscript-subscript-text-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
Vytváření poutavých a informativních prezentací PowerPoint často vyžaduje použití funkcí formátování, jako je horní a dolní index textu. Tento tutoriál vás provede procesem začlenění textu horního a dolního indexu do vašich prezentací Java PowerPoint pomocí Aspose.Slides for Java.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
- Integrované vývojové prostředí (IDE), jako je IntelliJ IDEA nebo Eclipse, nastavené pro vývoj v Javě.
- Základní znalost programování v Javě a PowerPointových prezentací.

## Importujte balíčky
Nejprve naimportujte potřebné balíčky z Aspose.Slides for Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Nastavte prezentaci
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Krok 2: Otevřete snímek
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
## Krok 4: Přidejte text horního indexu
```java
// Vytvořte odstavec pro hlavní text
IParagraph mainParagraph = new Paragraph();
IPortion mainPortion = new Portion();
mainPortion.setText("SlideTitle");
mainParagraph.getPortions().add(mainPortion);
// Vytvořte část pro text horního indexu
IPortion superPortion = new Portion();
superPortion.getPortionFormat().setEscapement(30); // Nastavit escapement pro horní index
superPortion.setText("TM");
mainParagraph.getPortions().add(superPortion);
//Přidejte hlavní odstavec s horním indexem do textového pole
textFrame.getParagraphs().add(mainParagraph);
```
## Krok 5: Přidejte text dolního indexu
```java
// Vytvořte další odstavec pro text dolního indexu
IParagraph subscriptParagraph = new Paragraph();
IPortion subscriptPortion = new Portion();
subscriptPortion.setText("a");
subscriptParagraph.getPortions().add(subscriptPortion);
// Vytvořte část pro text dolního indexu
IPortion subPortion = new Portion();
subPortion.getPortionFormat().setEscapement(-25); // Nastavit escapement pro dolní index
subPortion.setText("i");
subscriptParagraph.getPortions().add(subPortion);
// Přidejte odstavec dolního indexu do textového pole
textFrame.getParagraphs().add(subscriptParagraph);
```
## Krok 6: Uložte prezentaci
```java
// Uložte prezentaci
presentation.save(dataDir + "TestOut.pptx", SaveFormat.Pptx);
```

## Závěr
V tomto tutoriálu jsme prozkoumali, jak vylepšit vaše prezentace Java PowerPoint pomocí horního a dolního indexu pomocí Aspose.Slides for Java. Podle těchto kroků můžete vytvořit vizuálně přitažlivější a informativnější snímky, které efektivně komunikují váš obsah.

## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je robustní knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět PowerPointové prezentace programově.
### Kde najdu další dokumentaci k Aspose.Slides for Java?
 Podrobnou dokumentaci lze nalézt[tady](https://reference.aspose.com/slides/java/).
### Jak mohu získat dočasnou licenci pro Aspose.Slides for Java?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Mohu vyzkoušet Aspose.Slides for Java zdarma?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Kde mohu získat podporu pro Aspose.Slides pro Java?
 Pro podporu a diskuze navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
