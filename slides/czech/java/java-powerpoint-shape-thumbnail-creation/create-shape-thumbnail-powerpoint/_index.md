---
"description": "Naučte se, jak generovat miniatury tvarů v prezentacích PowerPointu pomocí Aspose.Slides pro Javu. K dispozici je podrobný návod."
"linktitle": "Vytvoření miniatury tvaru v PowerPointu"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vytvoření miniatury tvaru v PowerPointu"
"url": "/cs/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vytvoření miniatury tvaru v PowerPointu

## Zavedení
tomto tutoriálu se ponoříme do vytváření miniatur tvarů v prezentacích PowerPointu pomocí knihovny Aspose.Slides pro Javu. Aspose.Slides je výkonná knihovna, která umožňuje vývojářům programově pracovat se soubory PowerPointu a automatizovat různé úkoly, včetně generování miniatur tvarů.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.
- Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
- Knihovna Aspose.Slides pro Java byla stažena a nastavena ve vašem projektu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Importovat balíčky
Nejprve je potřeba importovat potřebné balíčky do kódu Java, abyste mohli využívat funkce Aspose.Slides. Na začátek souboru Java vložte následující příkazy importu:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Definování adresáře dokumentů
```java
String dataDir = "Your Document Directory";
```
Nahradit `"Your Document Directory"` s cestou k adresáři obsahujícímu váš soubor PowerPoint.
## Krok 2: Vytvoření instance prezentačního objektu
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
Vytvořte novou instanci `Presentation` třída, kde jako parametr předáte cestu k souboru aplikace PowerPoint.
## Krok 3: Vytvoření miniatury tvaru
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Z prvního snímku prezentace načtěte miniaturu požadovaného tvaru.
## Krok 4: Uložení miniatury
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Uložte vygenerovaný náhledový obrázek na disk ve formátu PNG se zadaným názvem souboru.

## Závěr
Závěrem tento tutoriál ukázal, jak vytvářet miniatury tvarů v prezentacích PowerPointu pomocí Aspose.Slides pro Javu. Dodržováním podrobných pokynů a využitím poskytnutých úryvků kódu můžete efektivně generovat miniatury tvarů programově.

## Často kladené otázky
### Mohu vytvořit miniatury tvarů na libovolném snímku v prezentaci?
Ano, kód můžete upravit tak, aby cílil na tvary na libovolném snímku, a to odpovídající úpravou indexu snímku.
### Podporuje Aspose.Slides i jiné formáty obrázků pro ukládání miniatur?
Ano, kromě PNG podporuje Aspose.Slides ukládání miniatur v různých obrazových formátech, jako jsou JPEG, GIF a BMP.
### Je Aspose.Slides vhodný pro komerční použití?
Ano, Aspose.Slides nabízí komerční licence pro firmy a organizace. Licenci si můžete zakoupit od [zde](https://purchase.aspose.com/buy).
### Mohu si Aspose.Slides vyzkoušet před zakoupením?
Rozhodně! Zkušební verzi Aspose.Slides si můžete stáhnout zdarma z [zde](https://releases.aspose.com/) aby zhodnotili jeho vlastnosti a možnosti.
### Kde najdu podporu pro Aspose.Slides?
Pokud máte jakékoli dotazy nebo potřebujete pomoc s Aspose.Slides, můžete navštívit [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) pro podporu.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}