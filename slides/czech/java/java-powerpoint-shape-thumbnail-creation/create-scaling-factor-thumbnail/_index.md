---
title: Vytvořte miniaturu faktoru měřítka
linktitle: Vytvořte miniaturu faktoru měřítka
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet miniatury měřítka v Javě pomocí Aspose.Slides for Java. Snadno srozumitelný průvodce s pokyny krok za krokem.
weight: 12
url: /cs/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
V tomto tutoriálu vás provedeme procesem vytvoření miniatury měřítka pomocí Aspose.Slides for Java. Postupujte podle těchto pokynů krok za krokem, abyste dosáhli požadovaného výsledku.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
- Knihovna Aspose.Slides for Java byla stažena a nastavena ve vašem projektu Java.
- Základní znalost programovacího jazyka Java.

## Importujte balíčky
Nejprve importujte potřebné balíčky potřebné pro práci s Aspose.Slides ve vašem kódu Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Nyní si uvedený příklad rozdělíme do několika kroků:
## Krok 1: Nastavte adresář dokumentů
Definujte cestu k adresáři vašeho dokumentu, kde je umístěn soubor prezentace PowerPoint.
```java
String dataDir = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` s cestou k vašemu skutečnému adresáři dokumentů.
## Krok 2: Vytvořte instanci objektu prezentace
Vytvořte instanci třídy Presentation, která bude reprezentovat soubor prezentace PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
 Zajistěte výměnu`"HelloWorld.pptx"` s názvem souboru vaší prezentace PowerPoint.
## Krok 3: Vytvořte obrázek v plném měřítku
Vygenerujte z prezentace obrázek požadovaného snímku v plném měřítku.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Tento kód načte miniaturu prvního obrazce na prvním snímku prezentace.
## Krok 4: Uložte obrázek
Uložte vygenerovaný obrázek na disk ve formátu PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
 Zajistěte výměnu`"Scaling Factor Thumbnail_out.png"` s požadovaným názvem výstupního souboru.

## Závěr
Závěrem lze říci, že jste úspěšně vytvořili miniaturu měřítka pomocí Aspose.Slides for Java. Podle uvedených kroků můžete tuto funkci snadno integrovat do svých aplikací Java.
## FAQ
### Mohu použít Aspose.Slides for Java s jakýmkoli Java IDE?
Ano, Aspose.Slides for Java lze použít s jakýmkoli Java Integrated Development Environment (IDE), jako je Eclipse, IntelliJ IDEA nebo NetBeans.
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete využít bezplatnou zkušební verzi Aspose.Slides for Java návštěvou webu[webová stránka](https://releases.aspose.com/).
### Kde najdu podporu pro Aspose.Slides pro Java?
 Podporu pro Aspose.Slides pro Javu najdete na[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Jak si mohu zakoupit Aspose.Slides pro Java?
 Aspose.Slides pro Java si můžete zakoupit od[nákupní stránku](https://purchase.aspose.com/buy).
### Potřebuji dočasnou licenci pro používání Aspose.Slides for Java?
 Ano, můžete získat dočasnou licenci od[dočasná licenční stránka](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
