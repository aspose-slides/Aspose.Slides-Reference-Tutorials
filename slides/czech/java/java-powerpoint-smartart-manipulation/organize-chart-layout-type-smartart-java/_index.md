---
"description": "Zvládněte organizaci typů rozvržení grafů ve SmartArt pomocí Javy s Aspose.Slides a bez námahy vylepšete vizuální prvky prezentací."
"linktitle": "Uspořádání typu rozvržení grafu v SmartArt pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Uspořádání typu rozvržení grafu v SmartArt pomocí Javy"
"url": "/cs/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Uspořádání typu rozvržení grafu v SmartArt pomocí Javy

## Zavedení
V tomto tutoriálu si projdeme procesem organizace typů rozvržení grafu ve SmartArt pomocí Javy, konkrétně s využitím knihovny Aspose.Slides. SmartArt v prezentacích může výrazně zlepšit vizuální atraktivitu a přehlednost vašich dat, takže je nezbytné zvládnout jeho manipulaci.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
2. Knihovna Aspose.Slides byla stažena a nastavena. Pokud jste tak ještě neučinili, stáhněte si ji z [zde](https://releases.aspose.com/slides/java/).
3. Základní znalost programování v Javě.

## Importovat balíčky
Nejprve importujte potřebné balíčky:
```java
import com.aspose.slides.*;
```
Rozdělme si uvedený příklad do několika kroků:
## Krok 1: Inicializace prezentačního objektu
```java
Presentation presentation = new Presentation();
```
Vytvořte nový objekt prezentace.
## Krok 2: Přidání prvku SmartArt do snímku
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Přidejte na požadovaný snímek prvek SmartArt se zadanými rozměry a typem rozvržení.
## Krok 3: Nastavení rozvržení organizačního diagramu
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Nastavte typ rozvržení organizačního diagramu. V tomto příkladu používáme rozvržení Levý visící graf.
## Krok 4: Uložení prezentace
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Uložte prezentaci s uspořádaným rozvržením grafu.

## Závěr
Zvládnutí organizace typů rozvržení grafů ve SmartArt pomocí Javy vám umožní snadno vytvářet vizuálně poutavé prezentace. S Aspose.Slides se proces zjednoduší a zefektivní, což vám umožní soustředit se na tvorbu působivého obsahu.
## Často kladené otázky
### Je Aspose.Slides kompatibilní s různými vývojovými prostředími Java?
Ano, Aspose.Slides je kompatibilní s různými vývojovými prostředími Java, což vývojářům zajišťuje flexibilitu.
### Mohu si přizpůsobit vzhled prvků SmartArt pomocí Aspose.Slides?
Aspose.Slides samozřejmě nabízí rozsáhlé možnosti přizpůsobení prvků SmartArt, což vám umožňuje přizpůsobit je vašim specifickým požadavkům.
### Nabízí Aspose.Slides komplexní dokumentaci pro vývojáře?
Ano, vývojáři se mohou podívat na podrobnou dokumentaci k Aspose.Slides pro Javu, která nabízí vhled do jeho funkcí a použití.
### Je k dispozici zkušební verze pro Aspose.Slides?
Ano, před rozhodnutím o koupi si můžete stáhnout bezplatnou zkušební verzi Aspose.Slides a prozkoumat její funkce.
### Kde mohu hledat podporu s dotazy týkajícími se Aspose.Slides?
Pro jakoukoli pomoc nebo dotazy týkající se Aspose.Slides můžete navštívit fórum podpory. [zde](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}