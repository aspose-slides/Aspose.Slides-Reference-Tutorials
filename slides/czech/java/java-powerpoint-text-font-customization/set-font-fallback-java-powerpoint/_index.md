---
title: Nastavte záložní písmo v Java PowerPointu
linktitle: Nastavte záložní písmo v Java PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit záložní písma v Java PowerPoint pomocí Aspose.Slides pro Java, abyste zajistili konzistentní zobrazení textu.
weight: 16
url: /cs/java/java-powerpoint-text-font-customization/set-font-fallback-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
V tomto tutoriálu se ponoříme do složitosti nastavení záložních písem v prezentacích Java PowerPoint pomocí Aspose.Slides for Java. Záložní písma jsou zásadní pro zajištění správného zobrazení textu ve vašich prezentacích na různých zařízeních a operačních systémech, i když požadovaná písma nejsou k dispozici.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
- Základní znalost programovacího jazyka Java.
- Integrované vývojové prostředí (IDE), jako je IntelliJ IDEA nebo Eclipse.

## Importujte balíčky
Nejprve do své třídy Java zahrňte potřebné balíčky Aspose.Slides for Java:
```java
import com.aspose.slides.FontFallBackRule;
import com.aspose.slides.IFontFallBackRule;
```
## Krok 1: Inicializujte pravidla pro záložní písma
Chcete-li nastavit záložní písma, musíte definovat pravidla, která určují rozsahy Unicode a odpovídající záložní písma. Tato pravidla můžete inicializovat takto:
```java
long startUnicodeIndex = 0x0B80;
long endUnicodeIndex = 0x0BFF;
IFontFallBackRule firstRule = new FontFallBackRule(startUnicodeIndex, endUnicodeIndex, "Vijaya");
IFontFallBackRule secondRule = new FontFallBackRule(0x3040, 0x309F, "MS Mincho, MS Gothic");
String[] fontNames = new String[]{"Segoe UI Emoji, Segoe UI Symbol", "Arial"};
IFontFallBackRule thirdRule = new FontFallBackRule(0x1F300, 0x1F64F, fontNames);
```
## Krok 2: Použijte pravidla pro záložní písmo
Dále tato pravidla použijete na prezentaci nebo snímek, kde je třeba nastavit záložní písma. Níže je uveden příklad použití těchto pravidel na snímek v prezentaci PowerPoint:
```java
// Za předpokladu, že snímek je váš objekt snímku
slide.getFontsManager().setFontFallBackRules(new IFontFallBackRule[]{firstRule, secondRule, thirdRule});
```

## Závěr
Nastavení záložních písem v prezentacích Java PowerPoint pomocí Aspose.Slides pro Java je zásadní pro zajištění konzistentního zobrazení textu v různých prostředích. Definováním záložních pravidel, jak je ukázáno v tomto kurzu, můžete zvládnout situace, kdy nejsou k dispozici konkrétní písma, a zachovat integritu vašich prezentací.

## FAQ
### Co jsou záložní písma v prezentacích PowerPoint?
Záložní písma zajišťují správné zobrazení textu tím, že nahrazují dostupná písma za ta, která nejsou nainstalována.
### Jak si mohu stáhnout Aspose.Slides pro Java?
 Aspose.Slides pro Java si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).
### Je Aspose.Slides for Java kompatibilní se všemi Java IDE?
Ano, Aspose.Slides for Java je kompatibilní s populárními Java IDE, jako jsou IntelliJ IDEA a Eclipse.
### Mohu získat dočasné licence pro produkty Aspose?
Ano, dočasné licence pro produkty Aspose lze získat od[tady](https://purchase.aspose.com/temporary-license/).
### Kde najdu podporu pro Aspose.Slides pro Java?
 Podporu související s Aspose.Slides for Java naleznete na[Aspose fórum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
