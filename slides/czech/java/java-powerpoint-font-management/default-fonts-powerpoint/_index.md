---
"description": "Naučte se, jak nastavit výchozí písma v prezentacích PowerPointu pomocí Aspose.Slides pro Javu. Zajistěte konzistenci a vylepšete vizuální atraktivitu bez námahy."
"linktitle": "Výchozí písma v PowerPointu s Aspose.Slides pro Javu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Výchozí písma v PowerPointu s Aspose.Slides pro Javu"
"url": "/cs/java/java-powerpoint-font-management/default-fonts-powerpoint/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Výchozí písma v PowerPointu s Aspose.Slides pro Javu

## Zavedení
Vytváření prezentací v PowerPointu s vlastními fonty je běžným požadavkem v mnoha projektech. Aspose.Slides pro Javu poskytuje bezproblémové řešení pro správu výchozích fontů a zajišťuje konzistenci v různých prostředích. V tomto tutoriálu vás provedeme procesem nastavení výchozích fontů v prezentacích v PowerPointu pomocí Aspose.Slides pro Javu.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
1. Vývojová sada Java (JDK): Ujistěte se, že máte v systému nainstalovanou JDK.
2. Aspose.Slides pro Javu: Stáhněte a nainstalujte Aspose.Slides pro Javu z [stránka ke stažení](https://releases.aspose.com/slides/java/).
3. Základní znalost Javy: Znalost základů programovacího jazyka Java.

## Importovat balíčky
Začněte importem potřebných balíčků do vašeho projektu Java:
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
## Krok 1: Nastavení výchozích písem
Definujte cestu k adresáři dokumentů a vytvořte možnosti načítání pro určení výchozích běžných a asijských písem:
```java
String dataDir = "Your Document Directory";
LoadOptions loadOptions = new LoadOptions(LoadFormat.Auto);
loadOptions.setDefaultRegularFont("Wingdings");
loadOptions.setDefaultAsianFont("Wingdings");
```
## Krok 2: Načtení prezentace
Načtěte prezentaci PowerPointu pomocí definovaných možností načítání:
```java
Presentation pptx = new Presentation(dataDir + "DefaultFonts.pptx", loadOptions);
```
## Krok 3: Generování výstupů
Generování různých výstupů, jako jsou miniatury snímků, soubory PDF a XPS:
```java
try {
    // Generovat miniaturu snímku
    BufferedImage image = pptx.getSlides().get_Item(0).getThumbnail(1, 1);
    ImageIO.write(image, ".png", new File(dataDir + "output_out.png"));
    // Generovat PDF
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
Nastavení výchozích písem v prezentacích PowerPointu pomocí Aspose.Slides pro Javu je jednoduché a efektivní. Dodržováním kroků popsaných v tomto tutoriálu můžete zajistit konzistenci stylů písem napříč různými platformami a prostředími, čímž zvýšíte vizuální atraktivitu vašich prezentací.
## Často kladené otázky
### Mohu v Aspose.Slides pro Javu používat vlastní fonty?
Ano, v Aspose.Slides pro Javu můžete ve svých prezentacích zadat vlastní písma.
### Je Aspose.Slides pro Javu kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides pro Javu podporuje širokou škálu verzí PowerPointu, což zajišťuje kompatibilitu v různých prostředích.
### Jak mohu získat podporu pro Aspose.Slides pro Javu?
Podporu pro Aspose.Slides pro Javu můžete získat prostřednictvím [Fóra Aspose](https://forum.aspose.com/c/slides/11).
### Mohu si před zakoupením vyzkoušet Aspose.Slides pro Javu?
Ano, Aspose.Slides pro Javu si můžete vyzkoušet prostřednictvím bezplatné zkušební verze dostupné na adrese [releases.aspose.com](https://releases.aspose.com/).
### Kde mohu získat dočasnou licenci pro Aspose.Slides pro Javu?
Dočasnou licenci pro Aspose.Slides pro Javu můžete získat od [stránka nákupu](https://purchase.aspose.com/temporary-license/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}