---
title: Kolekce záložních pravidel v Java PowerPointu
linktitle: Kolekce záložních pravidel v Java PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak spravovat záložní pravidla písem v prezentacích PowerPoint pomocí Aspose.Slides pro Java. Vylepšete kompatibilitu mezi zařízeními bez námahy.
weight: 11
url: /cs/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
tomto tutoriálu se ponoříme do toho, jak spravovat záložní pravidla písem pomocí Aspose.Slides pro Java. Záložní písma jsou zásadní pro zajištění správného zobrazení vašich prezentací v různých prostředích, zvláště když nejsou k dispozici konkrétní písma. Krok za krokem vás provedeme importem potřebných balíčků, nastavením prostředí a implementací záložních pravidel.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
- Základní znalost programování v Javě.
- JDK (Java Development Kit) nainstalovaný ve vašem systému.
-  Knihovna Aspose.Slides pro Java byla stažena a nastavena. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
- Nainstalované IDE (Integrated Development Environment), jako je IntelliJ IDEA nebo Eclipse.
## Importujte balíčky
Začněte importem potřebných balíčků do vašeho projektu Java:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## Nastavení objektu prezentace
Nejprve inicializujte objekt Presentation, kde definujete pravidla pro záložní písmo.
```java
Presentation presentation = new Presentation();
```
## Vytváření kolekce záložních pravidel písem
Dále vytvořte objekt FontFallBackRulesCollection pro správu vlastních pravidel záložních písem.
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## Přidání pravidel pro záložní písmo
Nyní přidejte konkrétní pravidla pro záložní písma pomocí rozsahů Unicode a názvů záložních písem.
### Krok 1: Definujte rozsah Unicode a písmo
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
Tento řádek nastavuje záložní pravidlo pro rozsah Unicode 0x0B80 až 0x0BFF pro použití písma „Vijaya“, pokud primární písmo není k dispozici.
### Krok 2: Definujte jiný rozsah Unicode a písmo
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
Zde pravidlo určuje, že rozsah Unicode 0x3040 až 0x309F by se měl vrátit k fontům „MS Mincho“ nebo „MS Gothic“.
## Použití pravidel pro záložní písma na prezentaci
Aplikujte vytvořenou kolekci záložních pravidel písem na FontsManager prezentace.
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## Zlikvidujte předmět prezentace
Nakonec zajistěte řádnou správu zdrojů tím, že zlikvidujete objekt prezentace v bloku try-finally.
```java
try {
    // Podle potřeby použijte objekt prezentace
} finally {
    if (presentation != null) presentation.dispose();
}
```
## Závěr
tomto tutoriálu jsme prozkoumali, jak spravovat záložní pravidla písem pomocí Aspose.Slides pro Java. Pochopení a implementace záložních písem zajišťuje konzistentní a spolehlivé vykreslování písem napříč různými platformami a prostředími. Pomocí těchto kroků můžete přizpůsobit chování záložních písem tak, aby hladce splňovaly specifické požadavky na prezentaci.

## FAQ
### Co jsou pravidla pro záložní písma?
Záložní pravidla písem definují alternativní písma, která se mají použít, když zadané písmo není k dispozici, a zajišťují konzistentní zobrazení textu.
### Jak si stáhnu Aspose.Slides for Java?
 Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).
### Mohu si Aspose.Slides for Java před nákupem vyzkoušet?
 Ano, můžete získat bezplatnou zkušební verzi[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Slides pro Javu?
 K dispozici je podrobná dokumentace[tady](https://reference.aspose.com/slides/java/).
### Jak získám podporu pro Aspose.Slides pro Java?
Podporu získáte na fóru Aspose.Slides[tady](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
