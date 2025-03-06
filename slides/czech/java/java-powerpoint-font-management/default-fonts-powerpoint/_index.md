---
title: Výchozí písma v PowerPointu s Aspose.Slides pro Javu
linktitle: Výchozí písma v PowerPointu s Aspose.Slides pro Javu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit výchozí písma v prezentacích PowerPoint pomocí Aspose.Slides for Java. Zajistěte konzistenci a bez námahy vylepšete vizuální přitažlivost.
weight: 11
url: /cs/java/java-powerpoint-font-management/default-fonts-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
Vytváření prezentací PowerPoint pomocí vlastních písem je běžným požadavkem v mnoha projektech. Aspose.Slides for Java poskytuje bezproblémové řešení pro správu výchozích písem a zajišťuje konzistenci v různých prostředích. V tomto tutoriálu vás provedeme procesem nastavení výchozích písem v prezentacích PowerPoint pomocí Aspose.Slides for Java.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Java Development Kit (JDK): Ujistěte se, že máte v systému nainstalovaný JDK.
2.  Aspose.Slides for Java: Stáhněte a nainstalujte Aspose.Slides for Java z[stránka ke stažení](https://releases.aspose.com/slides/java/).
3. Základní znalost jazyka Java: Znalost základů programovacího jazyka Java.

## Importujte balíčky
Začněte importováním potřebných balíčků do vašeho projektu Java:
```java
import com.aspose.slides.LoadFormat;
import com.aspose.slides.LoadOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Nastavte výchozí písma
Definujte cestu k adresáři dokumentů a vytvořte možnosti načtení pro určení výchozích běžných a asijských písem:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## Krok 2: Načtěte prezentaci
Načtěte prezentaci PowerPoint pomocí definovaných možností načtení:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## Krok 3: Generování výstupů
Generujte různé výstupy, jako jsou miniatury snímků, soubory PDF a XPS:
```java
try {
    // Vygenerovat miniaturu snímku
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // Vygenerovat PDF
    pptx.save(dataDir + "output_out.pdf", SaveFormat.Pdf);
    // Generovat XPS
    pptx.save(dataDir + "output_out.xps", SaveFormat.Xps);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pptx != null) pptx.dispose();
}
```

## Závěr
Nastavení výchozích písem v prezentacích PowerPoint pomocí Aspose.Slides pro Java je jednoduché a efektivní. Dodržováním kroků uvedených v tomto kurzu můžete zajistit konzistenci stylů písem napříč různými platformami a prostředími, čímž zvýšíte vizuální přitažlivost vašich prezentací.
## FAQ
### Mohu používat vlastní písma s Aspose.Slides for Java?
Ano, pomocí Aspose.Slides for Java můžete ve svých prezentacích zadat vlastní písma.
### Je Aspose.Slides for Java kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides for Java podporuje širokou škálu verzí aplikace PowerPoint, což zajišťuje kompatibilitu v různých prostředích.
### Jak mohu získat podporu pro Aspose.Slides pro Java?
 Podporu pro Aspose.Slides pro Java můžete získat prostřednictvím[Aspose fóra](https://forum.aspose.com/c/slides/11).
### Mohu si Aspose.Slides for Java před nákupem vyzkoušet?
 Ano, Aspose.Slides pro Java můžete prozkoumat prostřednictvím bezplatné zkušební verze dostupné na adrese[releases.aspose.com](https://releases.aspose.com/).
### Kde mohu získat dočasnou licenci pro Aspose.Slides for Java?
 Můžete získat dočasnou licenci pro Aspose.Slides for Java z[nákupní stránku](https://purchase.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
