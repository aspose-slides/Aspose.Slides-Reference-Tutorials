---
title: Render s záložním písmem v Java PowerPoint
linktitle: Render s záložním písmem v Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vykreslovat text pomocí záložních písem v prezentacích Java PowerPoint pomocí Aspose.Slides. Pro bezproblémovou implementaci postupujte podle tohoto podrobného průvodce.
type: docs
weight: 13
url: /cs/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---
## Úvod
Vytváření a manipulace s prezentacemi PowerPoint v Javě může být náročné, ale s Aspose.Slides to můžete udělat efektivně. Jednou z klíčových funkcí je schopnost vykreslovat text pomocí záložních písem. Tento článek poskytuje podrobného podrobného průvodce, jak implementovat záložní písma do snímků aplikace PowerPoint pomocí Aspose.Slides for Java.
## Předpoklady
Než se pustíte do implementace, ujistěte se, že máte vše, co potřebujete:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Slides for Java: Můžete si jej stáhnout z[Aspose.Slides for Java Download page](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): IDE jako IntelliJ IDEA nebo Eclipse vám usnadní vývojový proces.
4. Závislosti: Zahrňte Aspose.Slides do závislostí vašeho projektu.
## Importujte balíčky
Nejprve musíme naimportovat potřebné balíčky do našeho programu Java.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Pojďme si tento proces rozdělit na zvládnutelné kroky.
## Krok 1: Nastavte svůj projekt
 Před napsáním jakéhokoli kódu se ujistěte, že je váš projekt správně nastaven. To zahrnuje přidání knihovny Aspose.Slides do vašeho projektu. Můžete to udělat stažením knihovny z[Aspose.Slides pro Javu](https://releases.aspose.com/slides/java/) a přidejte jej do cesty sestavení.
## Krok 2: Inicializujte pravidla pro záložní písma
 Musíte vytvořit instanci`IFontFallBackRulesCollection` třídy a přidejte do ní pravidla. Tato pravidla definují záložní písma pro konkrétní rozsahy Unicode.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte novou instanci kolekce pravidel
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Vytvořte řadu pravidel
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Krok 3: Upravte záložní pravidla
V tomto kroku upravíme záložní pravidla odstraněním existujících záložních písem a aktualizací pravidel pro konkrétní rozsahy Unicode.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Pokus o odstranění FallBack fontu "Tahoma" z načtených pravidel
    fallBackRule.remove("Tahoma");
    // Aktualizujte pravidla pro zadaný rozsah
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//Odstraňte všechna existující pravidla ze seznamu
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Krok 4: Načtěte prezentaci
Načtěte prezentaci PowerPoint, kterou chcete upravit.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Krok 5: Přiřaďte k prezentaci záložní pravidla
Přiřaďte připravená záložní pravidla správci písem prezentace.
```java
try {
    // Přiřazení připraveného seznamu pravidel k použití
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Vykreslení miniatury pomocí inicializované kolekce pravidel a její uložení do PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Krok 6: Uložte a otestujte
Nakonec uložte svou práci a otestujte implementaci, abyste se ujistili, že vše funguje podle očekávání. Pokud narazíte na nějaké problémy, znovu zkontrolujte nastavení a ujistěte se, že jsou všechny závislosti správně přidány.
## Závěr
Podle této příručky můžete efektivně vykreslovat text pomocí záložních písem v prezentacích PowerPoint pomocí Aspose.Slides for Java. Tento proces zajišťuje, že si vaše prezentace zachovají konzistentní formátování, i když primární písma nejsou k dispozici. Šťastné kódování!
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je knihovna, která umožňuje vývojářům vytvářet, upravovat a vykreslovat prezentace PowerPoint v aplikacích Java.
### Jak přidám Aspose.Slides do svého projektu?
 Knihovnu si můžete stáhnout z[Stránka ke stažení Aspose.Slides](https://releases.aspose.com/slides/java/) a přidejte jej do cesty sestavení vašeho projektu.
### Co jsou záložní písma?
Záložní písma jsou alternativní písma používaná v případě, že zadané písmo není dostupné nebo nepodporuje určité znaky.
### Mohu použít více záložních pravidel?
Ano, můžete přidat více záložních pravidel pro práci s různými rozsahy Unicode a fonty.
### Kde mohu získat podporu pro Aspose.Slides?
 Můžete získat podporu od[Fórum podpory Aspose.Slides](https://forum.aspose.com/c/slides/11).