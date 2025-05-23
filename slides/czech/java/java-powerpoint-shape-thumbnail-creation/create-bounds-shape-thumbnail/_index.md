---
"description": "Naučte se, jak vytvářet miniatury tvarů s ohraničeními pomocí Aspose.Slides pro Javu. Tento podrobný návod vás provede celým procesem."
"linktitle": "Vytvořit miniaturu tvaru ohraničení"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vytvořit miniaturu tvaru ohraničení"
"url": "/cs/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit miniaturu tvaru ohraničení

## Zavedení
Aspose.Slides pro Javu je výkonná knihovna, která umožňuje vývojářům v Javě programově vytvářet, manipulovat a převádět prezentace v PowerPointu. V tomto tutoriálu se naučíme, jak pomocí Aspose.Slides pro Javu vytvořit miniaturu tvaru s ohraničeními.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
2. Knihovna Aspose.Slides pro Javu byla stažena a přidána do vašeho projektu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Importovat balíčky
Ujistěte se, že jste do kódu Java importovali potřebné balíčky:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Nastavení projektu
Vytvořte nový projekt Java ve vašem preferovaném IDE a přidejte knihovnu Aspose.Slides for Java do závislostí vašeho projektu.
## Krok 2: Vytvoření instance prezentačního objektu
Vytvořte instanci `Presentation` objekt zadáním cesty k souboru prezentace v PowerPointu.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Krok 3: Vytvořte miniaturu tvaru ohraničení
Nyní si z prezentace vytvořme miniaturu tvaru s hranicemi.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Závěr
V tomto tutoriálu jsme se naučili, jak vytvořit miniaturu tvaru s ohraničeními pomocí Aspose.Slides pro Javu. Dodržením těchto kroků můžete snadno programově generovat miniatury tvarů ve vašich prezentacích v PowerPointu.
## Často kladené otázky
### Mohu vytvořit miniatury pro konkrétní tvary v rámci snímku?
Ano, k jednotlivým tvarům v rámci snímku můžete přistupovat a generovat pro ně miniatury pomocí Aspose.Slides pro Javu.
### Je Aspose.Slides pro Javu kompatibilní se všemi verzemi souborů PowerPointu?
Aspose.Slides pro Javu podporuje různé formáty souborů PowerPointu, včetně PPT, PPTX, PPS, PPSX a dalších.
### Mohu si přizpůsobit vzhled vygenerovaných miniatur?
Ano, vlastnosti miniaturních obrázků, jako je velikost a kvalita, můžete upravit podle svých požadavků.
### Podporuje Aspose.Slides pro Javu i jiné funkce než generování miniatur?
Ano, Aspose.Slides pro Javu poskytuje rozsáhlé funkce pro práci s prezentacemi v PowerPointu, včetně manipulace se snímky, extrakce textu a generování grafů.
### Je k dispozici zkušební verze Aspose.Slides pro Javu?
Ano, můžete si stáhnout bezplatnou zkušební verzi z [zde](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}