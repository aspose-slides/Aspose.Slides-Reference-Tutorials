---
title: Změňte pořadí tvarů v PowerPointu
linktitle: Změňte pořadí tvarů v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: V tomto podrobném návodu se dozvíte, jak změnit pořadí tvarů v PowerPointu pomocí Aspose.Slides for Java. Vylepšete své prezentační dovednosti bez námahy.
weight: 15
url: /cs/java/java-powerpoint-animation-shape-manipulation/change-shape-order-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
Vytváření vizuálně přitažlivých a dobře strukturovaných prezentací může být náročný úkol. Se správnými nástroji a technikami si to však můžete výrazně usnadnit. Aspose.Slides for Java je výkonná knihovna, která vám pomůže programově manipulovat a spravovat prezentace PowerPoint. V tomto tutoriálu vás provedeme kroky ke změně pořadí tvarů na snímku aplikace PowerPoint pomocí Aspose.Slides for Java.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1.  Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný JDK. Můžete si jej stáhnout z[Web společnosti Oracle](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java Library: Stáhněte si nejnovější verzi z[Aspose.Slides for Java download page](https://releases.aspose.com/slides/java/).
3. Integrované vývojové prostředí (IDE): Pro kódování použijte IDE jako IntelliJ IDEA nebo Eclipse.
4. Soubor prezentace: Připravte si soubor PowerPoint, se kterým chcete manipulovat.
## Importujte balíčky
Chcete-li začít, musíte importovat potřebné balíčky z knihovny Aspose.Slides. Tyto importy vám umožní pracovat s prezentacemi, snímky a tvary.
```java
import com.aspose.slides.*;

```
této příručce rozdělíme proces změny pořadí tvaru do několika kroků pro lepší pochopení a snadnější implementaci.
## Krok 1: Načtěte prezentaci
 Nejprve musíte načíst soubor prezentace PowerPoint, se kterým chcete pracovat. Tento krok zahrnuje inicializaci`Presentation` třídy s cestou k souboru PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation1 = new Presentation(dataDir + "HelloWorld.pptx");
```
## Krok 2: Otevřete požadovaný snímek
Po načtení prezentace přejděte na snímek, kde chcete změnit pořadí tvarů. Snímky jsou indexovány od 0, takže pro přístup k prvnímu snímku použijte index 0.
```java
ISlide slide = presentation1.getSlides().get_Item(0);
```
## Krok 3: Přidejte na snímek tvary
Dále přidejte tvary na snímek. Pro demonstraci přidáme na snímek tvar obdélníku a trojúhelníku.
```java
IAutoShape shp3 = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 365, 400, 150);
shp3.getFillFormat().setFillType(FillType.NoFill);
shp3.addTextFrame(" ");
ITextFrame txtFrame = shp3.getTextFrame();
IParagraph para = txtFrame.getParagraphs().get_Item(0);
IPortion portion = para.getPortions().get_Item(0);
portion.setText("Watermark Text Watermark Text Watermark Text");
shp3 = slide.getShapes().addAutoShape(ShapeType.Triangle, 200, 365, 400, 150);
```
## Krok 4: Změňte pořadí tvarů
 Nyní změňte pořadí tvarů na snímku. The`reorder` umožňuje určit novou polohu tvaru v rámci kolekce obrazců snímku.
```java
slide.getShapes().reorder(2, shp3);
```
## Krok 5: Uložte upravenou prezentaci
Po změně pořadí obrazců uložte upravenou prezentaci do nového souboru. Tím zajistíte, že váš původní soubor zůstane nezměněn.
```java
presentation1.save(dataDir + "Reshape_out.pptx", SaveFormat.Pptx);
```
## Krok 6: Vyčistěte zdroje
Nakonec zlikvidujte objekt prezentace, abyste uvolnili zdroje.
```java
if (presentation1 != null) presentation1.dispose();
```
## Závěr
Pomocí těchto kroků můžete snadno změnit pořadí tvarů na snímku aplikace PowerPoint pomocí Aspose.Slides for Java. Tato výkonná knihovna zjednodušuje mnoho úkolů spojených s prezentacemi PowerPoint a umožňuje vám vytvářet snímky a manipulovat s nimi programově. Ať už automatizujete tvorbu prezentací nebo jen potřebujete provádět hromadné změny, Aspose.Slides pro Java je neocenitelný nástroj.
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je Java API pro vytváření a manipulaci s prezentacemi PowerPoint bez použití aplikace Microsoft PowerPoint.
### Mohu používat Aspose.Slides for Java s jinými Java IDE?
Ano, můžete jej použít s jakýmkoli Java IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.
### Je Aspose.Slides for Java kompatibilní se všemi formáty PowerPoint?
Ano, Aspose.Slides for Java podporuje formáty PPT, PPTX a další PowerPoint.
### Jak získám bezplatnou zkušební verzi Aspose.Slides for Java?
 Můžete si stáhnout bezplatnou zkušební verzi z[Aspose.Slides for Java download page](https://releases.aspose.com/).
### Kde najdu další dokumentaci k Aspose.Slides for Java?
 Podrobnou dokumentaci najdete na[Dokumentační stránka Aspose.Slides pro Java](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
