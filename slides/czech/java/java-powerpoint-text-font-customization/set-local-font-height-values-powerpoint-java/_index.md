---
"description": "Naučte se, jak upravit výšku písma v prezentacích PowerPointu pomocí Javy s Aspose.Slides. Bez námahy vylepšete formátování textu ve slidech."
"linktitle": "Nastavení lokálních hodnot výšky písma v PowerPointu pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení lokálních hodnot výšky písma v PowerPointu pomocí Javy"
"url": "/cs/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení lokálních hodnot výšky písma v PowerPointu pomocí Javy

## Zavedení
V tomto tutoriálu se naučíte, jak manipulovat s výškou písma na různých úrovních v prezentacích v PowerPointu pomocí Aspose.Slides pro Javu. Ovládání velikosti písma je klíčové pro vytváření vizuálně přitažlivých a strukturovaných prezentací. Projdeme si podrobné příklady, které ilustrují, jak nastavit výšku písma pro různé textové prvky.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
- Sada pro vývoj Java (JDK) nainstalovaná ve vašem systému
- Knihovna Aspose.Slides pro Javu. Můžete si ji stáhnout. [zde](https://releases.aspose.com/slides/java/).
- Základní znalost programování v Javě a prezentací v PowerPointu
## Importovat balíčky
Nezapomeňte do souboru Java zahrnout potřebné balíčky Aspose.Slides:
```java
import com.aspose.slides.*;
```
## Krok 1: Inicializace prezentačního objektu
Nejprve vytvořte nový objekt prezentace v PowerPointu:
```java
Presentation pres = new Presentation();
```
## Krok 2: Přidání tvaru a textového rámečku
Přidejte automatický tvar s textovým rámečkem na první snímek:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Krok 3: Vytvořte textové části
Definujte části textu s různou výškou písma:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Krok 4: Nastavení výšky písma
Nastavení výšky písma na různých úrovních:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Krok 5: Uložte prezentaci
Uložte upravenou prezentaci do souboru:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Závěr
Tento tutoriál ukázal, jak programově upravit výšku písma v PowerPointových slidech pomocí Aspose.Slides pro Javu. Manipulací s velikostmi písma na různých úrovních (v celé prezentaci, v odstavci a v části) můžete dosáhnout přesné kontroly nad formátováním textu ve vašich prezentacích.
## Často kladené otázky
### Co je Aspose.Slides pro Javu?
Aspose.Slides pro Javu je výkonné API pro programovou manipulaci s prezentacemi v PowerPointu.
### Kde najdu dokumentaci k Aspose.Slides pro Javu?
Dokumentaci najdete [zde](https://reference.aspose.com/slides/java/).
### Mohu si před zakoupením vyzkoušet Aspose.Slides pro Javu?
Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.Slides pro Javu?
Pro podporu navštivte [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Kde si mohu zakoupit licenci pro Aspose.Slides pro Javu?
Můžete si zakoupit licenci [zde](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}