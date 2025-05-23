---
"description": "Naučte se, jak přidávat sloupce do textových polí v PowerPointu pomocí Aspose.Slides pro Javu. Vylepšete své prezentace pomocí tohoto podrobného návodu."
"linktitle": "Přidání sloupce do textových polí pomocí Aspose.Slides pro Javu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání sloupce do textových polí pomocí Aspose.Slides pro Javu"
"url": "/cs/java/java-powerpoint-text-box-manipulation/add-column-in-text-boxes/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání sloupce do textových polí pomocí Aspose.Slides pro Javu

## Zavedení
tomto tutoriálu se podíváme na to, jak vylepšit textová pole přidáním sloupců pomocí knihovny Aspose.Slides pro Javu. Aspose.Slides je výkonná knihovna Java, která umožňuje vývojářům programově vytvářet, manipulovat a převádět prezentace v PowerPointu bez nutnosti použití Microsoft Office. Přidání sloupců do textových polí může výrazně zlepšit čitelnost a organizaci obsahu v rámci snímků, díky čemuž budou vaše prezentace poutavější a profesionálnější.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.
- JDK (Java Development Kit) nainstalovaný na vašem počítači.
- Knihovna Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Importovat balíčky
Chcete-li začít, musíte importovat potřebné třídy Aspose.Slides do souboru Java. Zde je návod, jak to udělat:
```java
import com.aspose.slides.*;
```
## Krok 1: Inicializace prezentace a snímku
Nejprve vytvořte novou prezentaci v PowerPointu a inicializujte první snímek.
```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try {
    // Získejte první snímek prezentace
    ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 2: Přidání automatického tvaru (obdélník)
Dále přidejte na snímek automatický tvar typu Obdélník.
```java
    // Přidat automatický tvar typu Obdélník
    IAutoShape aShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Krok 3: Přidání textového rámečku do obdélníku
Nyní přidejte textový rámec TextFrame do automatického tvaru Obdélník a nastavte jeho počáteční text.
```java
    // Přidat textový rámec do obdélníku
    aShape.addTextFrame("All these columns are limited to be within a single text container -- " +
            "you can add or delete text and the new or remaining text automatically adjusts " +
            "itself to flow within the container. You cannot have text flow from one container " +
            "to other though -- we told you PowerPoint's column options for text are limited!");
```
## Krok 4: Nastavení počtu sloupců
Zadejte počet sloupců v rámci TextFrame.
```java
    // Získání textového formátu TextFrame
    ITextFrameFormat format = aShape.getTextFrame().getTextFrameFormat();
    // Zadejte počet sloupců v TextFrame
    format.setColumnCount(3);
```
## Krok 5: Úprava rozteče sloupců
Nastavte mezery mezi sloupci v TextFrame.
```java
    // Určete rozteč mezi sloupci
    format.setColumnSpacing(10);
```
## Krok 6: Uložte prezentaci
Nakonec upravenou prezentaci uložte do souboru PowerPointu.
```java
    // Uložit vytvořenou prezentaci
    presentation.save(dataDir + "ColumnCount.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Závěr
Pomocí těchto kroků můžete snadno přidávat sloupce do textových polí v prezentacích PowerPointu pomocí nástroje Aspose.Slides pro Javu. Tato funkce vám umožňuje vylepšit strukturu a čitelnost vašich snímků, čímž je učiní vizuálně přitažlivějšími a profesionálnějšími.
## Často kladené otázky
### Mohu do textového pole přidat více než tři sloupce?
Ano, můžete programově zadat libovolný počet sloupců pomocí Aspose.Slides.
### Je Aspose.Slides kompatibilní s Javou 11?
Ano, Aspose.Slides podporuje Javu 11 a vyšší verze.
### Jak mohu získat dočasnou licenci pro Aspose.Slides?
Můžete získat dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).
### Vyžaduje Aspose.Slides nainstalovaný Microsoft Office?
Ne, Aspose.Slides nevyžaduje instalaci Microsoft Office na počítači.
### Kde najdu další dokumentaci o Aspose.Slides pro Javu?
Podrobná dokumentace je k dispozici [zde](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}