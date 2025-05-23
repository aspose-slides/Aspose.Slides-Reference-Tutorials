---
"description": "Naučte se, jak vykreslit text s náhradními fonty v prezentacích v PowerPointu v Javě pomocí Aspose.Slides. Pro bezproblémovou implementaci postupujte podle tohoto podrobného návodu."
"linktitle": "Vykreslení s náhradním písmem v PowerPointu v Javě"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vykreslení s náhradním písmem v PowerPointu v Javě"
"url": "/cs/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vykreslení s náhradním písmem v PowerPointu v Javě

## Zavedení
Vytváření a manipulace s prezentacemi v PowerPointu v Javě může být náročná, ale s Aspose.Slides to zvládnete efektivně. Jednou z klíčových funkcí je možnost vykreslování textu s použitím záložních fontů. Tento článek poskytuje podrobný návod krok za krokem, jak implementovat záložní fonty do snímků v PowerPointu pomocí Aspose.Slides pro Javu.
## Předpoklady
Než se pustíme do implementace, ujistěte se, že máte vše, co potřebujete:
1. Vývojová sada Java (JDK): Ujistěte se, že máte v systému nainstalovanou JDK.
2. Aspose.Slides pro Javu: Můžete si jej stáhnout z [Stránka ke stažení Aspose.Slides pro Javu](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): IDE jako IntelliJ IDEA nebo Eclipse vám usnadní proces vývoje.
4. Závislosti: Zahrňte Aspose.Slides do závislostí vašeho projektu.
## Importovat balíčky
Nejprve musíme importovat potřebné balíčky do našeho programu v Javě.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Rozdělme si proces na zvládnutelné kroky.
## Krok 1: Nastavení projektu
Před napsáním jakéhokoli kódu se ujistěte, že je váš projekt správně nastaven. To zahrnuje i přidání knihovny Aspose.Slides do vašeho projektu. Můžete to provést stažením knihovny z [Aspose.Slides pro Javu](https://releases.aspose.com/slides/java/) a jeho přidání do cesty sestavení.
## Krok 2: Inicializace pravidel pro záložní písma
Musíte vytvořit instanci `IFontFallBackRulesCollection` třídu a přidat do ní pravidla. Tato pravidla definují záložní písma pro konkrétní rozsahy Unicode.
```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření nové instance kolekce pravidel
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Vytvořte řadu pravidel
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## Krok 3: Úprava záložních pravidel
V tomto kroku upravíme záložní pravidla odstraněním stávajících záložních písem a aktualizací pravidel pro konkrétní rozsahy Unicode.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Snažím se odstranit záložní písmo „Tahoma“ z načtených pravidel
    fallBackRule.remove("Tahoma");
    // Aktualizovat pravidla pro zadaný rozsah
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
// Odeberte všechna existující pravidla ze seznamu
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## Krok 4: Načtení prezentace
Načtěte prezentaci PowerPointu, kterou chcete upravit.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## Krok 5: Přiřaďte záložní pravidla k prezentaci
Přiřaďte připravená záložní pravidla správci písem prezentace.
```java
try {
    // Přiřazení připraveného seznamu pravidel k použití
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Vykreslení miniatury pomocí inicializované kolekce pravidel a její uložení do formátu PNG
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Krok 6: Uložení a otestování
Nakonec si uložte práci a otestujte implementaci, abyste se ujistili, že vše funguje podle očekávání. Pokud narazíte na nějaké problémy, znovu zkontrolujte nastavení a ujistěte se, že jsou všechny závislosti správně přidány.
## Závěr
Dodržováním tohoto návodu můžete efektivně vykreslit text s náhradními fonty ve vašich prezentacích v PowerPointu pomocí Aspose.Slides pro Javu. Tento proces zajišťuje, že vaše prezentace si zachovají konzistentní formátování, i když primární fonty nejsou k dispozici. Hodně štěstí s programováním!
## Často kladené otázky
### Co je Aspose.Slides pro Javu?
Aspose.Slides pro Javu je knihovna, která umožňuje vývojářům vytvářet, upravovat a vykreslovat prezentace v PowerPointu v aplikacích Java.
### Jak přidám Aspose.Slides do svého projektu?
Knihovnu si můžete stáhnout z [Stránka pro stažení Aspose.Slides](https://releases.aspose.com/slides/java/) a přidejte jej do cesty sestavení vašeho projektu.
### Co jsou záložní fonty?
Záložní písma jsou alternativní písma používaná, když zadané písmo není k dispozici nebo nepodporuje určité znaky.
### Mohu použít více záložních pravidel?
Ano, můžete přidat více záložních pravidel pro zpracování různých rozsahů a písem Unicode.
### Kde mohu získat podporu pro Aspose.Slides?
Podporu můžete získat od [Fórum podpory Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}