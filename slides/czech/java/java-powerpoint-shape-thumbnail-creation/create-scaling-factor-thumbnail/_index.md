---
"description": "Naučte se, jak v Javě vytvářet miniatury s faktory škálování pomocí Aspose.Slides pro Javu. Snadno srozumitelný návod s podrobnými pokyny."
"linktitle": "Vytvořit miniaturu faktoru škálování"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vytvořit miniaturu faktoru škálování"
"url": "/cs/java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit miniaturu faktoru škálování

## Zavedení
V tomto tutoriálu vás provedeme procesem vytvoření miniatury s faktorem škálování pomocí Aspose.Slides pro Javu. Postupujte podle těchto podrobných pokynů k dosažení požadovaného výsledku.
## Předpoklady
Než začnete, ujistěte se, že máte následující předpoklady:
- Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
- Stažení a nastavení knihovny Aspose.Slides pro Java ve vašem projektu Java.
- Základní znalost programovacího jazyka Java.

## Importovat balíčky
Nejprve importujte potřebné balíčky pro práci s Aspose.Slides do kódu Java. 
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```

Nyní si rozdělme uvedený příklad do několika kroků:
## Krok 1: Nastavení adresáře dokumentů
Definujte cestu k adresáři dokumentů, kde se nachází soubor s prezentací PowerPoint.
```java
String dataDir = "Your Document Directory";
```
Nahradit `"Your Document Directory"` s cestou k vašemu skutečnému adresáři dokumentů.
## Krok 2: Vytvoření instance objektu Presentation
Vytvořte instanci třídy Presentation, která bude reprezentovat soubor prezentace aplikace PowerPoint.
```java
Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
```
Ujistěte se, že vyměníte `"HelloWorld.pptx"` s názvem souboru vaší prezentace v PowerPointu.
## Krok 3: Vytvořte obrázek v plném měřítku
Vygenerujte z prezentace obrázek požadovaného snímku v plné velikosti.
```java
BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);
```
Tento kód načte miniaturu prvního tvaru na prvním snímku prezentace.
## Krok 4: Uložte obrázek
Uložte vygenerovaný obrázek na disk ve formátu PNG.
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
```
Ujistěte se, že vyměníte `"Scaling Factor Thumbnail_out.png"` s požadovaným názvem výstupního souboru.

## Závěr
Závěrem lze říci, že jste úspěšně vytvořili miniaturu s faktorem škálování pomocí Aspose.Slides pro Javu. Dodržením uvedených kroků můžete tuto funkci snadno integrovat do svých aplikací v Javě.
## Často kladené otázky
### Mohu použít Aspose.Slides pro Javu s jakýmkoli Java IDE?
Ano, Aspose.Slides pro Javu lze použít s jakýmkoli integrovaným vývojovým prostředím (IDE) pro Javu, jako je Eclipse, IntelliJ IDEA nebo NetBeans.
### Je k dispozici bezplatná zkušební verze Aspose.Slides pro Javu?
Ano, můžete využít bezplatnou zkušební verzi Aspose.Slides pro Javu na adrese [webové stránky](https://releases.aspose.com/).
### Kde najdu podporu pro Aspose.Slides pro Javu?
Podporu pro Aspose.Slides pro Javu naleznete na [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
### Jak si mohu zakoupit Aspose.Slides pro Javu?
Aspose.Slides pro Javu si můžete zakoupit od [stránka nákupu](https://purchase.aspose.com/buy).
### Potřebuji dočasnou licenci pro používání Aspose.Slides pro Javu?
Ano, můžete získat dočasnou licenci od [stránka s dočasnou licencí](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}