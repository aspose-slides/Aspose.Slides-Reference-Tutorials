---
title: Vkládání písem do HTML pomocí Aspose.Slides for Java
linktitle: Vkládání písem do HTML pomocí Aspose.Slides for Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vkládat písma do HTML pomocí Aspose.Slides for Java, abyste zajistili konzistentní typografii na různých platformách a zařízeních.
weight: 13
url: /cs/java/java-powerpoint-font-management/embed-fonts-in-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vkládání písem do HTML pomocí Aspose.Slides for Java

## Úvod
Aspose.Slides for Java je výkonný nástroj pro vývojáře v jazyce Java, kteří chtějí programově manipulovat s prezentacemi v PowerPointu. V tomto tutoriálu se ponoříme do procesu vkládání písem do HTML pomocí Aspose.Slides for Java. Vložením písem zajistíte, že si vaše prezentace zachovají svůj zamýšlený vzhled na různých platformách a zařízeních, i když požadovaná písma nejsou nainstalována lokálně.
## Předpoklady
Než začneme, ujistěte se, že máte splněny následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Slides for Java: Stáhněte a nainstalujte Aspose.Slides for Java z[stránka ke stažení](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Vyberte si preferované IDE pro vývoj v Javě, jako je IntelliJ IDEA nebo Eclipse.

## Importujte balíčky
Nejprve musíte importovat potřebné balíčky, abyste mohli začít vkládat fonty do HTML pomocí Aspose.Slides for Java.
```java
import com.aspose.slides.*;
```
## Krok 1: Definujte dokument a výstupní adresáře
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
```
 Ujistěte se, že vyměníte`"Your Document Directory"` a`"Your Output Directory"` s cestami k vaší vstupní prezentaci PowerPoint a požadovaným výstupním adresářem.
## Krok 2: Načtěte prezentaci
```java
Presentation pres = new Presentation(dataDir + "Presentation.pptx");
```
Tento krok načte prezentaci PowerPoint do paměti a umožní vám s ní provádět různé operace.
## Krok 3: Vyloučení výchozích písem
```java
String[] fontNameExcludeList = { "Arial" };
```
Zadejte písma, která chcete vyloučit z vkládání. V tomto příkladu vyloučíme Arial.
## Krok 4: Vložení písem do HTML
```java
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
HtmlOptions htmlOptionsEmbed = new HtmlOptions();
htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
pres.save(outPath + "pres.html", SaveFormat.Html, htmlOptionsEmbed);
```
 V tomto kroku vytvoříme instanci`EmbedAllFontsHtmlController` pro vložení všech písem kromě těch, která jsou uvedena v seznamu výjimek. Poté definujeme`HtmlOptions` nastavte vlastní formátovač HTML pro vkládání písem. Nakonec prezentaci uložíme jako HTML s vloženými fonty.

## Závěr
V tomto tutoriálu jsme prozkoumali, jak vložit fonty do HTML pomocí Aspose.Slides pro Javu. Dodržením uvedených kroků můžete zajistit, že si vaše prezentace udrží konzistentní typografii na různých platformách a zařízeních, což zlepší celkový zážitek ze sledování.
## FAQ
### Mohu vložit konkrétní písma namísto jejich vyloučení?
 Ano, můžete určit písma, která chcete vložit úpravou`fontNameExcludeList` pole podle toho.
### Podporuje Aspose.Slides for Java vkládání písem v jiných formátech kromě HTML?
Ano, Aspose.Slides podporuje vkládání písem v různých výstupních formátech, včetně PDF a obrázků.
### Je k dispozici zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Kde najdu další podporu nebo pomoc s Aspose.Slides for Java?
 Můžete navštívit[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) pro podporu komunity nebo se obraťte na podporu Aspose pro odbornou pomoc.
### Mohu si zakoupit dočasnou licenci pro Aspose.Slides for Java?
Ano, můžete získat dočasnou licenci od[nákupní stránku](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
