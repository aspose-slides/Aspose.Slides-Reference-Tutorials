---
title: Vytvořte formátovaný obdélník v PowerPointu
linktitle: Vytvořte formátovaný obdélník v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak vytvořit a formátovat obdélník v PowerPointu pomocí Aspose.Slides for Java, pomocí tohoto podrobného průvodce.
weight: 18
url: /cs/java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
V tomto tutoriálu vás provedeme procesem vytváření formátovaného obdélníku na snímku aplikace PowerPoint pomocí Aspose.Slides for Java. Každý krok rozebereme a zajistíme, že jej budete moci sledovat a implementovat do svých vlastních projektů.
## Předpoklady
Než se ponoříme do kódu, pokryjeme předpoklady. Budete potřebovat následující:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2. Knihovna Aspose.Slides for Java: Stáhněte si a zahrňte knihovnu Aspose.Slides for Java do svého projektu.
3. Integrované vývojové prostředí (IDE): IDE jako IntelliJ IDEA nebo Eclipse vám usnadní práci s kódováním.
4. Základní znalost Javy: Znalost programování v Javě vám pomůže postupovat podle tohoto návodu.
## Importujte balíčky
Chcete-li začít, budete muset importovat potřebné balíčky z knihovny Aspose.Slides. Můžete to udělat takto:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
Tyto importy jsou klíčové, protože přinášejí třídy potřebné k vytváření a formátování tvarů v prezentaci PowerPoint.
## Krok 1: Nastavení adresáře projektu
Nejprve musíte vytvořit adresář pro váš projekt. Tento adresář bude ukládat vaše PowerPoint soubory.
```java
String dataDir = "Your Document Directory";
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Tento kód zkontroluje, zda adresář existuje, a pokud ne, vytvoří jej. Je dobrým zvykem udržovat soubory projektu organizované.
## Krok 2: Vytvořte prezentační třídu
 Dále vytvoříte instanci`Presentation` class, která představuje váš soubor PowerPoint.
```java
Presentation pres = new Presentation();
```
Tento řádek kódu vytvoří novou prázdnou prezentaci, do které můžete začít přidávat obsah.
## Krok 3: Přidejte do prezentace snímek
Nyní do vaší prezentace přidáme snímek. Ve výchozím nastavení obsahuje nová prezentace jeden snímek, takže s tím budeme pracovat.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
Tento fragment kódu získá první snímek z prezentace.
## Krok 4: Přidejte tvar obdélníku
Nyní přidáme na snímek obdélník.
```java
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);
```
Zde přidáváme na snímek obdélník se zadanými rozměry (šířka, výška) a pozicí (x, y).
## Krok 5: Naformátujte obdélník
Aplikujme nějaké formátování, aby byl obdélník vizuálně přitažlivý.
```java
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
Tento kód nastavuje typ náplně na plnou a barvu náplně na čokoládu.
## Naformátujte ohraničení obdélníku
Dále naformátujeme ohraničení obdélníku.
```java
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
Tento kód nastaví barvu ohraničení na černou a šířku ohraničení na 5.
## Krok 6: Uložte prezentaci
Nakonec uložme prezentaci do vašeho projektového adresáře.
```java
pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
```
Tento řádek kódu uloží prezentaci jako soubor PPTX do zadaného adresáře.
## Krok 7: Vyčistěte zdroje
 Dobrou praxí je zlikvidovat`Presentation` protestovat proti uvolnění zdrojů.
```java
if (pres != null) pres.dispose();
```
Tím je zajištěno správné uvolnění všech zdrojů.
## Závěr
Vytváření a formátování tvarů v prezentaci PowerPoint pomocí Aspose.Slides pro Java je jednoduchý proces. Podle kroků uvedených v tomto kurzu můžete snadno automatizovat vytváření vizuálně přitažlivých snímků. Ať už vyvíjíte aplikace pro obchodní výkaznictví, vzdělávací obsah nebo dynamické prezentace, Aspose.Slides for Java nabízí nástroje, které potřebujete k úspěchu.
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je knihovna, která umožňuje vývojářům programově vytvářet, upravovat a převádět prezentace PowerPoint.
### Mohu použít Aspose.Slides pro Javu s jakýmkoli IDE?
Ano, Aspose.Slides pro Javu můžete použít s jakýmkoli Java kompatibilním IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.
### Jak mohu získat bezplatnou zkušební verzi Aspose.Slides for Java?
 Můžete si stáhnout bezplatnou zkušební verzi Aspose.Slides for Java z[tady](https://releases.aspose.com/).
###  Je nutné likvidovat`Presentation` object?
 Ano, likvidace`Presentation` objekt pomáhá uvolnit zdroje a vyhnout se únikům paměti.
### Kde najdu dokumentaci k Aspose.Slides for Java?
 Dokumentace je k dispozici[tady](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
