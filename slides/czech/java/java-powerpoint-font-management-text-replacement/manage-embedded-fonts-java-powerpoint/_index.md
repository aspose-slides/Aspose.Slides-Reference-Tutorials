---
title: Správa vložených písem v Java PowerPoint
linktitle: Správa vložených písem v Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Bez námahy spravujte vložená písma v prezentacích Java PowerPoint pomocí Aspose.Slides. Podrobný průvodce optimalizací snímků pro konzistenci.
weight: 11
url: /cs/java/java-powerpoint-font-management-text-replacement/manage-embedded-fonts-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
neustále se vyvíjejícím světě prezentací může efektivní správa písem znamenat obrovský rozdíl v kvalitě a kompatibilitě vašich souborů PowerPoint. Aspose.Slides for Java nabízí komplexní řešení pro správu vložených písem a zajišťuje, že vaše prezentace budou vypadat perfektně na jakémkoli zařízení. Ať už se zabýváte staršími prezentacemi nebo vytváříte nové, tato příručka vás provede procesem správy vložených písem ve vašich prezentacích Java PowerPoint pomocí Aspose.Slides. Pojďme se ponořit!
## Předpoklady
Než začneme, ujistěte se, že máte následující nastavení:
- Java Development Kit (JDK): Ujistěte se, že máte na svém počítači nainstalovaný JDK 8 nebo novější.
-  Aspose.Slides pro Javu: Stáhněte si knihovnu z[Aspose.Slides for Java](https://releases.aspose.com/slides/java/).
- IDE: Integrované vývojové prostředí jako IntelliJ IDEA nebo Eclipse.
- Prezentační soubor: Ukázkový soubor PowerPoint s vloženými fonty. Pro tento výukový program můžete použít "EmbeddedFonts.pptx".
- Závislosti: Přidejte Aspose.Slides pro Javu do svých projektových závislostí.
## Importujte balíčky
Nejprve musíte do svého projektu Java importovat potřebné balíčky:
```java
import com.aspose.slides.IFontData;
import com.aspose.slides.IFontsManager;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import javax.imageio.ImageIO;
import java.awt.*;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Pojďme si příklad rozebrat do podrobného průvodce krok za krokem.
## Krok 1: Nastavte adresář projektu
Než začnete, nastavte adresář projektu, kam budete ukládat soubory PowerPoint a výstupní obrázky.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
```
## Krok 2: Načtěte prezentaci
 Instantovat a`Presentation` objekt, který bude reprezentovat váš soubor PowerPoint.
```java
Presentation presentation = new Presentation(dataDir + "EmbeddedFonts.pptx");
```
## Krok 3: Vykreslení snímku pomocí vložených písem
Vykreslete snímek, který obsahuje textový rámeček, pomocí vloženého písma a uložte jej jako obrázek.
```java
try {
    // Vykreslete první snímek na obrázek
    BufferedImage image1 = presentation.getSlides().get_Item(0).getThumbnail(new Dimension(960, 720));
    ImageIO.write(image1, ".png", new File(dataDir + "picture1_out.png"));
```
## Krok 4: Otevřete Správce písem
 Dostaň`IFontsManager` instance z prezentace pro správu písem.
```java
    IFontsManager fontsManager = presentation.getFontsManager();
```
## Krok 5: Načtěte vložená písma
Načtěte všechna vložená písma v prezentaci.
```java
    // Získejte všechna vložená písma
    IFontData[] embeddedFonts = fontsManager.getEmbeddedFonts();
```
## Krok 6: Najděte a odstraňte konkrétní vložené písmo
Identifikujte a odstraňte konkrétní vložené písmo (např. „Calibri“) z prezentace.
```java
    //Najděte písmo "Calibri".
    IFontData funSizedEmbeddedFont = null;
    for (IFontData embeddedFont : embeddedFonts) {
        if ("Calibri".equals(embeddedFont.getFontName())) {
            funSizedEmbeddedFont = embeddedFont;
            break;
        }
    }
    // Odstraňte písmo "Calibri".
    if (funSizedEmbeddedFont != null) fontsManager.removeEmbeddedFont(funSizedEmbeddedFont);
```
## Krok 7: Znovu vykreslete snímek
Znovu vykreslete snímek, abyste ověřili změny po odebrání vloženého písma.
```java
    // Chcete-li vidět změny, znovu vykreslete první snímek
    BufferedImage image2 = presentation.getSlides().get_Item(0).getThumbnail(new Dimension(960, 720));
    ImageIO.write(image2, ".png", new File(dataDir + "picture2_out.png"));
```
## Krok 8: Uložte aktualizovanou prezentaci
Uložte upravený soubor prezentace bez vloženého písma.
```java
    // Uložte prezentaci bez vloženého písma "Calibri".
    presentation.save(dataDir + "WithoutManageEmbeddedFonts_out.ppt", SaveFormat.Ppt);
}
finally {
    if (presentation != null) presentation.dispose();
}
```
## Závěr
Správa vložených písem v prezentacích PowerPoint je zásadní pro zachování konzistence a kompatibility napříč různými zařízeními a platformami. S Aspose.Slides pro Java se tento proces stává přímočarým a efektivním. Podle kroků uvedených v této příručce můžete snadno odstranit nebo spravovat vložená písma ve svých prezentacích a zajistit, aby vypadaly přesně tak, jak chcete, bez ohledu na to, kde jsou zobrazeny.
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonná knihovna pro práci s PowerPoint prezentacemi v Javě. Umožňuje vytvářet, upravovat a spravovat prezentace programově.
### Jak přidám Aspose.Slides do svého projektu?
 Aspose.Slides můžete přidat do svého projektu stažením z[webová stránka](https://releases.aspose.com/slides/java/) a zahrnout jej do závislostí projektu.
### Mohu použít Aspose.Slides pro Javu s jakoukoli verzí Javy?
Aspose.Slides for Java je kompatibilní s JDK 8 a novějšími verzemi.
### Jaké jsou výhody správy vložených písem v prezentacích?
Správa vložených písem zajistí, že vaše prezentace budou vypadat konzistentně na různých zařízeních a platformách, a pomůže snížit velikost souboru odstraněním nepotřebných písem.
### Kde mohu získat podporu pro Aspose.Slides pro Java?
 Můžete získat podporu od[Fórum podpory Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
