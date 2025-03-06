---
title: Vyplňte tvary vzorem v PowerPointu
linktitle: Vyplňte tvary vzorem v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vyplňovat tvary vzory v PowerPointu pomocí Aspose.Slides for Java. Postupujte podle našeho jednoduchého průvodce krok za krokem, abyste své prezentace vizuálně vylepšili.
weight: 11
url: /cs/java/java-powerpoint-shape-formatting-geometry/fill-shapes-pattern-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vyplňte tvary vzorem v PowerPointu

## Úvod
Vytváření vizuálně přitažlivých prezentací je nezbytné pro zapojení publika. Jedním ze způsobů, jak vylepšit snímky aplikace PowerPoint, je vyplnit tvary vzory. V tomto tutoriálu si projdeme kroky k vyplnění tvarů vzory pomocí Aspose.Slides for Java. Tato příručka je přizpůsobena vývojářům, kteří chtějí využít výkonné funkce Aspose.Slides k vytváření úžasných prezentací programově.
## Předpoklady
Než se ponoříte do kódu, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný na vašem počítači.
- Integrované vývojové prostředí (IDE), jako je IntelliJ IDEA nebo Eclipse.
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).
- Základní znalost programování v Javě.
## Importujte balíčky
Nejprve importujme potřebné balíčky požadované pro náš příklad.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Krok 1: Nastavte svůj projekt
Před napsáním kódu se ujistěte, že je váš projekt správně nastaven. Vytvořte nový projekt Java ve svém IDE a přidejte knihovnu Aspose.Slides for Java do svých závislostí projektu.
## Krok 2: Vytvořte adresář dokumentů
Chcete-li efektivně spravovat své soubory, vytvořte si adresář, kam budeme ukládat naši PowerPoint prezentaci.
```java
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    new File(dataDir).mkdirs();
}
```
Tento úryvek zkontroluje, zda adresář existuje, a pokud ne, vytvoří jej.
## Krok 3: Vytvořte prezentační třídu
 Dále musíme vytvořit instanci`Presentation` class, která představuje náš soubor PowerPoint.
```java
Presentation pres = new Presentation();
```
Tím se inicializuje nový objekt prezentace, který použijeme k přidání snímků a tvarů.
## Krok 4: Otevřete první snímek
Pro začátek potřebujeme zpřístupnit první snímek naší prezentace. Zde přidáme naše tvary.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 5: Přidejte tvar obdélníku
Přidejme k našemu snímku obdélníkový tvar. Tento obdélník bude vyplněn vzorem.
```java
IShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Tento fragment kódu přidá na snímek obdélník na zadané pozici a velikosti.
## Krok 6: Nastavte Typ výplně na Vzor
Nyní musíme nastavit typ výplně našeho obdélníku na vzorovou výplň.
```java
shape.getFillFormat().setFillType(FillType.Pattern);
```
## Krok 7: Vyberte styl vzoru
Aspose.Slides nabízí různé styly vzorů. V tomto příkladu použijeme vzor "Trellis".
```java
shape.getFillFormat().getPatternFormat().setPatternStyle(PatternStyle.Trellis);
```
## Krok 8: Nastavte barvy vzoru
Můžeme přizpůsobit barvy našeho vzoru. Nastavíme barvu pozadí na světle šedou a barvu popředí na žlutou.
```java
shape.getFillFormat().getPatternFormat().getBackColor().setColor(Color.LIGHT_GRAY);
shape.getFillFormat().getPatternFormat().getForeColor().setColor(Color.YELLOW);
```
## Krok 9: Uložte prezentaci
Po nastavení našeho tvaru s požadovaným vzorem musíme prezentaci uložit do souboru.
```java
pres.save(dataDir + "RectShpPatt_out.pptx", SaveFormat.Pptx);
```
Tím se prezentace uloží do zadaného adresáře s názvem "RectShpPatt_out.pptx".
## Krok 10: Vyčistěte zdroje
Je dobrým zvykem zlikvidovat objekt prezentace, abyste uvolnili zdroje.
```java
if (pres != null) pres.dispose();
```
## Závěr
Gratulujeme! Úspěšně jste vyplnili obrazec vzorem na snímku aplikace PowerPoint pomocí Aspose.Slides for Java. Tato výkonná knihovna vám umožňuje snadno vytvářet a manipulovat s prezentacemi a dodat vašim projektům profesionální vzhled.
 Podle tohoto podrobného průvodce můžete své prezentace vylepšit různými vzory, aby byly poutavější a vizuálně přitažlivější. Pro pokročilejší funkce a možnosti přizpůsobení se nezapomeňte podívat na[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonné API, které umožňuje vývojářům vytvářet, manipulovat a převádět PowerPointové prezentace v aplikacích Java.
### Jak mohu získat Aspose.Slides pro Java?
 Aspose.Slides pro Java si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete získat bezplatnou zkušební verzi od[tady](https://releases.aspose.com/).
### Mohu použít Aspose.Slides for Java k manipulaci se stávajícími prezentacemi?
Ano, Aspose.Slides for Java vám umožňuje otevírat, upravovat a ukládat existující PowerPoint prezentace.
### Kde mohu získat podporu pro Aspose.Slides pro Java?
 Můžete získat podporu od[Fórum podpory Aspose.Slides](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
