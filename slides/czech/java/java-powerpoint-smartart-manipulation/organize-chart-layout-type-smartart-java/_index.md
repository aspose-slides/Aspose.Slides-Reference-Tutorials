---
title: Uspořádat rozložení grafu Typ v SmartArt pomocí Java
linktitle: Uspořádat rozložení grafu Typ v SmartArt pomocí Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Zvládněte uspořádání typů rozložení grafů v SmartArt pomocí Java s Aspose.Slides, bez námahy vylepšujte vizuály prezentace.
weight: 13
url: /cs/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
tomto tutoriálu projdeme procesem organizace typu rozložení grafu v SmartArt pomocí Java, konkrétně s využitím knihovny Aspose.Slides. SmartArt v prezentacích může výrazně zlepšit vizuální přitažlivost a jasnost vašich dat, takže je nezbytné zvládnout manipulaci s nimi.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Knihovna Aspose.Slides byla stažena a nastavena. Pokud jste to ještě neudělali, stáhněte si ji z[tady](https://releases.aspose.com/slides/java/).
3. Základní znalost programování v Javě.

## Importujte balíčky
Nejprve naimportujte potřebné balíčky:
```java
import com.aspose.slides.*;
```
Rozdělme uvedený příklad do několika kroků:
## Krok 1: Inicializujte objekt prezentace
```java
Presentation presentation = new Presentation();
```
Vytvořte nový objekt prezentace.
## Krok 2: Přidejte SmartArt do snímku
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Přidejte SmartArt na požadovaný snímek se zadanými rozměry a typem rozvržení.
## Krok 3: Nastavte rozvržení organizačního diagramu
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Nastavte typ rozložení organizačního diagramu. V tomto příkladu používáme rozložení vlevo zavěšené.
## Krok 4: Uložte prezentaci
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Uložte prezentaci s uspořádáním organizovaného grafu.

## Závěr
Zvládnutí organizace typů rozložení grafů v SmartArt pomocí Java vám umožňuje snadno vytvářet vizuálně poutavé prezentace. S Aspose.Slides se proces zjednoduší a zefektivní, což vám umožní soustředit se na vytváření působivého obsahu.
## FAQ
### Je Aspose.Slides kompatibilní s různými vývojovými prostředími Java?
Ano, Aspose.Slides je kompatibilní s různými vývojovými prostředími Java, což zajišťuje flexibilitu pro vývojáře.
### Mohu upravit vzhled prvků SmartArt pomocí Aspose.Slides?
Aspose.Slides rozhodně poskytuje rozsáhlé možnosti přizpůsobení prvků SmartArt, což vám umožňuje přizpůsobit je vašim konkrétním požadavkům.
### Nabízí Aspose.Slides komplexní dokumentaci pro vývojáře?
Ano, vývojáři mohou nahlédnout do podrobné dokumentace poskytnuté Aspose.Slides for Java, která nabízí pohled na její funkce a použití.
### Je k dispozici zkušební verze pro Aspose.Slides?
Ano, před rozhodnutím o koupi máte přístup k bezplatné zkušební verzi Aspose.Slides a prozkoumejte její funkce.
### Kde mohu hledat podporu pro dotazy související s Aspose.Slides?
 Pro jakoukoli pomoc nebo dotazy týkající se Aspose.Slides můžete navštívit fórum podpory[tady](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
