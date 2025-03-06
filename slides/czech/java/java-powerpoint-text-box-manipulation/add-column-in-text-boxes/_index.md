---
title: Přidejte sloupec do textových polí pomocí Aspose.Slides pro Java
linktitle: Přidejte sloupec do textových polí pomocí Aspose.Slides pro Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přidávat sloupce do textových polí v PowerPointu pomocí Aspose.Slides for Java. Vylepšete své prezentace pomocí tohoto podrobného průvodce.
weight: 10
url: /cs/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
tomto tutoriálu prozkoumáme, jak vylepšit textová pole přidáním sloupců pomocí Aspose.Slides pro Java. Aspose.Slides je výkonná Java knihovna, která umožňuje vývojářům vytvářet, manipulovat a převádět PowerPointové prezentace programově bez nutnosti Microsoft Office. Přidání sloupců do textových polí může výrazně zlepšit čitelnost a organizaci obsahu snímků, díky čemuž budou vaše prezentace poutavější a profesionálnější.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.
- JDK (Java Development Kit) nainstalovaný na vašem počítači.
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Chcete-li začít, musíte do souboru Java importovat potřebné třídy Aspose.Slides. Můžete to udělat takto:
```java
import com.aspose.slides.*;
```
## Krok 1: Inicializujte prezentaci a snímek
Nejprve vytvořte novou prezentaci PowerPoint a inicializujte první snímek.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Získejte první snímek prezentace
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 2: Přidejte automatický tvar (obdélník)
Dále přidejte na snímek automatický tvar typu obdélník.
```java
    // Přidejte automatický tvar typu Obdélník
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Krok 3: Přidejte TextFrame do obdélníku
Nyní přidejte TextFrame do automatického tvaru obdélníku a nastavte jeho počáteční text.
```java
    // Přidejte TextFrame do obdélníku
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Krok 4: Nastavte počet sloupců
Zadejte počet sloupců v rámci TextFrame.
```java
    // Získejte textový formát TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Zadejte počet sloupců v TextFrame
    format.setColumnCount(3);
```
## Krok 5: Upravte rozestup sloupců
Nastavte mezery mezi sloupci v TextFrame.
```java
    // Určete mezery mezi sloupci
    format.setColumnSpacing(10);
```
## Krok 6: Uložte prezentaci
Nakonec upravenou prezentaci uložte do souboru PowerPoint.
```java
    // Uložit vytvořenou prezentaci
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Závěr
Pomocí těchto kroků můžete snadno přidávat sloupce do textových polí v prezentacích PowerPoint pomocí Aspose.Slides for Java. Tato funkce vám umožňuje zlepšit strukturu a čitelnost vašich snímků, díky čemuž jsou vizuálně přitažlivější a profesionálnější.
## FAQ
### Mohu do textového pole přidat více než tři sloupce?
Ano, můžete zadat libovolný počet sloupců programově pomocí Aspose.Slides.
### Je Aspose.Slides kompatibilní s Java 11?
Ano, Aspose.Slides podporuje Java 11 a vyšší verze.
### Jak mohu získat dočasnou licenci pro Aspose.Slides?
 Můžete získat dočasnou licenci[tady](https://purchase.aspose.com/temporary-license/).
### Vyžaduje Aspose.Slides nainstalovaný Microsoft Office?
Ne, Aspose.Slides nevyžaduje instalaci sady Microsoft Office na počítači.
### Kde najdu další dokumentaci o Aspose.Slides pro Java?
 K dispozici je podrobná dokumentace[tady](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
