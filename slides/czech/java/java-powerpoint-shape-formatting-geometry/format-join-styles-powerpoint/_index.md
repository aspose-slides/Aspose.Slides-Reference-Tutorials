---
title: Formátovat styly spojení v PowerPointu
linktitle: Formátovat styly spojení v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak vylepšit své powerpointové prezentace nastavením různých stylů spojování čar pro tvary pomocí Aspose.Slides for Java. Postupujte podle našeho podrobného průvodce.
weight: 15
url: /cs/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
Vytváření vizuálně přitažlivých prezentací v PowerPointu může být náročný úkol, zvláště když chcete, aby každý detail byl dokonalý. Zde se hodí Aspose.Slides for Java. Je to výkonné API, které vám umožňuje vytvářet, manipulovat a spravovat prezentace programově. Jednou z funkcí, které můžete využít, je nastavení různých stylů spojení čar pro tvary, což může výrazně zlepšit estetiku vašich snímků. V tomto tutoriálu se ponoříme do toho, jak můžete použít Aspose.Slides pro Java k nastavení stylů spojení pro tvary v prezentacích PowerPoint. 
## Předpoklady
Než začneme, je potřeba splnit několik předpokladů:
1.  Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný JDK. Můžete si jej stáhnout z[Web společnosti Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java Library: Musíte si stáhnout a zahrnout Aspose.Slides for Java do svého projektu. Můžete to získat od[tady](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Použijte IDE jako IntelliJ IDEA, Eclipse nebo NetBeans k zápisu a spouštění kódu Java.
4. Základní znalost Javy: Základní znalost programování v Javě vám pomůže postupovat spolu s výukovým programem.
## Importujte balíčky
Nejprve musíte naimportovat potřebné balíčky pro Aspose.Slides. To je nezbytné pro přístup ke třídám a metodám požadovaným pro naše prezentační manipulace.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Krok 1: Nastavení adresáře projektu
Začněme vytvořením adresáře pro uložení našich prezentačních souborů. To zajišťuje, že všechny naše soubory jsou uspořádány a snadno dostupné.
```java
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
V tomto kroku definujeme cestu k adresáři a zkontrolujeme, zda existuje. Pokud ne, vytvoříme adresář. Jedná se o jednoduchý, ale účinný způsob, jak mít soubory pořádané.
## Krok 2: Inicializujte prezentaci
 Dále vytvoříme instanci`Presentation` třídy, která představuje náš soubor PowerPoint. To je základ, na kterém budeme stavět naše diapozitivy a tvary.
```java
Presentation pres = new Presentation();
```
Tento řádek kódu vytvoří novou prezentaci. Představte si to jako otevření prázdného souboru PowerPoint, kam přidáte veškerý svůj obsah.
## Krok 3: Přidejte na snímek tvary
### Získejte první snímek
Před přidáním tvarů musíme získat odkaz na první snímek v naší prezentaci. Ve výchozím nastavení obsahuje nová prezentace jeden prázdný snímek.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### Přidejte tvary obdélníku
Nyní do snímku přidáme tři obdélníkové tvary. Tyto tvary budou demonstrovat různé styly spojení čar.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
V tomto kroku přidáme tři obdélníky na určené pozice na snímku. Každý obdélník bude později stylizován jinak, aby se předvedly různé styly spojení.
## Krok 4: Upravte tvary
### Nastavte barvu výplně
Chceme, aby naše obdélníky byly vyplněny plnou barvou. Zde zvolíme jako barvu výplně černou.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### Nastavte šířku a barvu čáry
Dále definujeme šířku a barvu čáry pro každý obdélník. To pomáhá při vizuálním rozlišení stylů spojení.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## Krok 5: Použijte styly spojení
Vrcholem tohoto tutoriálu je nastavení stylů spojení čar. Použijeme tři různé styly: pokos, zkosení a zaoblení.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
Každý styl spojení čar dává tvarům jedinečný vzhled v rozích, kde se čáry setkávají. To může být užitečné zejména pro vytváření vizuálně odlišných diagramů nebo ilustrací.
## Krok 6: Přidejte text do tvarů
Aby bylo jasné, co jednotlivé tvary představují, přidáváme do každého obdélníku text popisující použitý styl spojení.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
Přidání textu pomáhá při identifikaci různých stylů při prezentaci nebo sdílení snímku.
## Krok 7: Uložte prezentaci
Nakonec naši prezentaci uložíme do zadaného adresáře.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
Tento příkaz zapíše prezentaci do souboru PPTX, který můžete otevřít pomocí aplikace Microsoft PowerPoint nebo jiného kompatibilního softwaru.
## Závěr
A tady to máte! Právě jste vytvořili snímek aplikace PowerPoint se třemi obdélníky, z nichž každý představuje jiný styl spojení čar pomocí Aspose.Slides for Java. Tento výukový program vám nejen pomůže porozumět základům Aspose.Slides, ale také vám ukáže, jak vylepšit vaše prezentace jedinečnými styly. Šťastnou prezentaci!
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonné API pro vytváření, manipulaci a správu prezentací v PowerPointu programově.
### Mohu použít Aspose.Slides pro Javu v jakémkoli IDE?
Ano, Aspose.Slides pro Javu můžete použít v jakémkoli IDE s podporou Java, jako je IntelliJ IDEA, Eclipse nebo NetBeans.
### Existuje bezplatná zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete získat bezplatnou zkušební verzi od[tady](https://releases.aspose.com/).
### Co jsou styly spojování čar v PowerPointu?
Styly spojení čar odkazují na tvar rohů, kde se dvě čáry setkávají. Mezi běžné styly patří pokos, zkosení a zaoblení.
### Kde najdu další dokumentaci k Aspose.Slides for Java?
 Můžete najít podrobnou dokumentaci[tady](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
