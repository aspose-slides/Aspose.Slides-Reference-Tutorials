---
title: Zadejte výchozí jazyk textu v Java PowerPoint
linktitle: Zadejte výchozí jazyk textu v Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak určit výchozí jazyk textu v Java PowerPoint pomocí Aspose.Slides for Java. Ideální pro vývojáře, kteří chtějí lokalizovat text programově.
weight: 21
url: /cs/java/java-powerpoint-text-font-customization/specify-default-text-language-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
V oblasti vývoje aplikací Java je programová správa a manipulace s prezentacemi v PowerPointu běžným požadavkem. Aspose.Slides for Java nabízí robustní sadu funkcí, které umožňují vývojářům vytvářet, upravovat a vylepšovat prezentace v PowerPointu pomocí kódu Java. Tento výukový program vás provede základními kroky určení výchozího jazyka textu v prezentaci Java PowerPoint pomocí Aspose.Slides.
## Předpoklady
Než se pustíte do tohoto tutoriálu, ujistěte se, že máte následující předpoklady:
- Základní znalost programovacího jazyka Java.
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
- Nastavení integrovaného vývojového prostředí (IDE), jako je IntelliJ IDEA nebo Eclipse.
-  Nainstalovaná knihovna Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
-  Přístup k dokumentaci Aspose.Slides for Java, kterou lze nalézt[tady](https://reference.aspose.com/slides/java/).

## Importujte balíčky
Než začnete kódovat, nezapomeňte importovat potřebné třídy Aspose.Slides do souboru Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Nastavte možnosti načítání
Nejprve nakonfigurujte možnosti načtení prezentace a určete výchozí jazyk textu (`en-US` v tomto případě).
```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setDefaultTextLanguage("en-US");
```
## Krok 2: Načtěte prezentaci
 Instantovat a`Presentation` objekt pomocí nakonfigurovaných možností načtení k načtení existující prezentace PowerPoint nebo vytvoření nové.
```java
Presentation pres = new Presentation(loadOptions);
```
## Krok 3: Přidejte tvar s textem
Přidejte obdélníkový tvar na první snímek prezentace a nastavte jeho textový obsah.
```java
IAutoShape shp = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 150, 50);
shp.getTextFrame().setText("New Text");
```
## Krok 4: Zkontrolujte jazyk částí textu
Načtěte a ověřte nastavení jazyka textových částí v přidaném tvaru.
```java
PortionFormat portionFormat = shp.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat();
System.out.println(portionFormat.getLanguageId());
```
## Krok 5: Zlikvidujte objekt prezentace
 Zajistěte správnou likvidaci`Presentation` protest proti uvolnění zdrojů po použití.
```java
finally {
    if (pres != null) pres.dispose();
}
```

## Závěr
V tomto tutoriálu jste se naučili, jak využít Aspose.Slides pro Java k programovému určení výchozího jazyka textu v prezentaci PowerPoint. Tato schopnost je zásadní pro zajištění konzistentního jazykového nastavení napříč textovými prvky ve vašich prezentacích, zlepšuje čitelnost a úsilí o lokalizaci.
## FAQ
### Mohu změnit výchozí jazyk textu na jiný jazyk, například francouzštinu nebo španělštinu?
Ano, při nastavování výchozího jazyka textu pomocí Aspose.Slides for Java můžete zadat libovolný podporovaný kód jazyka.
### Je Aspose.Slides for Java vhodný pro aplikace na podnikové úrovni?
Absolutně. Aspose.Slides for Java je navržen pro škálovatelnost a výkon, takže je ideální pro podniková prostředí.
### Kde najdu další příklady a zdroje pro Aspose.Slides pro Java?
 Obsáhlou dokumentaci a další příklady můžete prozkoumat na[Dokumentační stránka Aspose.Slides pro Java](https://reference.aspose.com/slides/java/).
### Podporuje Aspose.Slides for Java integraci s cloudovými službami?
Ano, Aspose.Slides for Java poskytuje rozhraní API, která podporují integraci s oblíbenými cloudovými platformami.
### Mohu vyhodnotit Aspose.Slides pro Java před nákupem?
 Ano, můžete získat bezplatnou zkušební verzi Aspose.Slides for Java od[tady](https://releases.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
