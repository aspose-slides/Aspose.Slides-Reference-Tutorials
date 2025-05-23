---
"description": "Naučte se, jak spravovat pravidla pro záložní písma v prezentacích PowerPointu pomocí Aspose.Slides pro Javu. Bez námahy vylepšete kompatibilitu napříč zařízeními."
"linktitle": "Kolekce záložních pravidel v PowerPointu v Javě"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Kolekce záložních pravidel v PowerPointu v Javě"
"url": "/cs/java/java-powerpoint-text-highlighting-fallback-rules/fallback-rules-collection-java-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Kolekce záložních pravidel v PowerPointu v Javě

## Zavedení
tomto tutoriálu se ponoříme do správy pravidel pro záložní fonty pomocí Aspose.Slides pro Javu. Záložní fonty jsou klíčové pro zajištění správného zobrazení vašich prezentací v různých prostředích, zejména pokud nejsou k dispozici konkrétní fonty. Provedeme vás krok za krokem importem potřebných balíčků, nastavením prostředí a implementací záložních pravidel.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
- Základní znalost programování v Javě.
- JDK (Java Development Kit) nainstalovaný ve vašem systému.
- Knihovna Aspose.Slides pro Javu byla stažena a nainstalována. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).
- Nainstalované IDE (integrované vývojové prostředí), jako je IntelliJ IDEA nebo Eclipse.
## Importovat balíčky
Začněte importem potřebných balíčků do vašeho projektu v Javě:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.FontFallBackRulesCollection;
import com.aspose.slides.IFontFallBackRulesCollection;
import com.aspose.slides.Presentation;
```
## Nastavení prezentačního objektu
Nejprve inicializujte objekt Presentation, kde definujete pravidla pro záložní písma.
```java
Presentation presentation = new Presentation();
```
## Vytváření kolekce pravidel pro záložní písma
Dále vytvořte objekt FontFallBackRulesCollection pro správu vlastních pravidel pro záložní písma.
```java
IFontFallBackRulesCollection userRulesList = new FontFallBackRulesCollection();
```
## Přidání pravidel pro záložní písma
Nyní přidejte specifická pravidla pro záložní písma pomocí rozsahů Unicode a názvů záložních písem.
### Krok 1: Definování rozsahu a písma Unicode
```java
userRulesList.add(new FontFallBackRule(0x0B80, 0x0BFF, "Vijaya"));
```
Tento řádek nastavuje záložní pravidlo pro rozsah Unicode 0x0B80 až 0x0BFF pro použití písma „Vijaya“, pokud primární písmo není k dispozici.
### Krok 2: Definujte další rozsah a písmo Unicode
```java
userRulesList.add(new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic"));
```
Zde pravidlo určuje, že rozsah Unicode 0x3040 až 0x309F by měl být nahrazen fonty „MS Mincho“ nebo „MS Gothic“.
## Použití pravidel pro záložní písma v prezentaci
Použijte vytvořenou kolekci pravidel pro záložní písma na FontsManager prezentace.
```java
presentation.getFontsManager().setFontFallBackRulesCollection(userRulesList);
```
## Odstranit prezentační objekt
Nakonec zajistěte správnou správu zdrojů odstraněním objektu Presentation v bloku try-finally.
```java
try {
    // Použijte prezentační objekt podle potřeby
} finally {
    if (presentation != null) presentation.dispose();
}
```
## Závěr
tomto tutoriálu jsme prozkoumali, jak spravovat pravidla pro záložní fonty pomocí Aspose.Slides pro Javu. Pochopení a implementace záložních fontů zajišťuje konzistentní a spolehlivé vykreslování fontů napříč různými platformami a prostředími. Dodržením těchto kroků můžete přizpůsobit chování záložních fontů tak, aby bezproblémově splňovalo specifické požadavky na prezentaci.

## Často kladené otázky
### Jaká jsou pravidla pro záložní fonty?
Pravidla pro záložní písma definují alternativní písma, která se použijí, když zadané písmo není k dispozici, a tím je zajištěno konzistentní zobrazení textu.
### Jak si stáhnu Aspose.Slides pro Javu?
Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/).
### Mohu si před zakoupením vyzkoušet Aspose.Slides pro Javu?
Ano, můžete získat bezplatnou zkušební verzi [zde](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Slides pro Javu?
Podrobná dokumentace je k dispozici [zde](https://reference.aspose.com/slides/java/).
### Jak získám podporu pro Aspose.Slides pro Javu?
Pro podporu navštivte fórum Aspose.Slides [zde](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}