---
title: Vytvořte miniaturu tvaru v PowerPointu
linktitle: Vytvořte miniaturu tvaru v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se generovat miniatury tvarů v prezentacích PowerPoint pomocí Aspose.Slides for Java. Poskytován průvodce krok za krokem.
weight: 14
url: /cs/java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte miniaturu tvaru v PowerPointu

## Úvod
tomto tutoriálu se ponoříme do vytváření miniatur tvarů v prezentacích PowerPoint pomocí Aspose.Slides pro Java. Aspose.Slides je výkonná knihovna, která umožňuje vývojářům pracovat se soubory PowerPoint programově, což umožňuje automatizaci různých úkolů, včetně generování miniatur tvarů.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Základní znalost programování v Javě.
- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Knihovna Aspose.Slides for Java byla stažena a nastavena ve vašem projektu. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Nejprve musíte do kódu Java importovat potřebné balíčky, abyste mohli využívat funkce Aspose.Slides. Na začátek souboru Java vložte následující příkazy pro import:
```java
import com.aspose.slides.Presentation;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Definujte adresář dokumentů
```java
String dataDir = "Your Document Directory";
```
 Nahradit`"Your Document Directory"` s cestou k adresáři obsahujícímu váš PowerPoint soubor.
## Krok 2: Instanciujte objekt prezentace
```java
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
 Vytvořte novou instanci souboru`Presentation` class, předáním cesty k vašemu PowerPoint souboru jako parametru.
## Krok 3: Vygenerujte miniaturu tvaru
```java
BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
```
Načtěte miniaturu požadovaného tvaru z prvního snímku prezentace.
## Krok 4: Uložte obrázek miniatury
```java
ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
```
Uložte vygenerovanou miniaturu na disk ve formátu PNG se zadaným názvem souboru.

## Závěr
Na závěr tento tutoriál ukázal, jak vytvořit miniatury tvarů v prezentacích PowerPoint pomocí Aspose.Slides for Java. Pokud budete postupovat podle podrobného průvodce a pomocí poskytnutých úryvků kódu, můžete efektivně generovat miniatury tvarů programově.

## FAQ
### Mohu vytvořit miniatury obrazců na libovolném snímku prezentace?
Ano, kód můžete upravit tak, aby cílil na obrazce na libovolném snímku, a to odpovídající úpravou indexu snímku.
### Podporuje Aspose.Slides jiné formáty obrázků pro ukládání náhledů?
Ano, kromě PNG podporuje Aspose.Slides ukládání miniatur v různých formátech obrázků, jako jsou JPEG, GIF a BMP.
### Je Aspose.Slides vhodný pro komerční použití?
 Ano, Aspose.Slides nabízí komerční licence pro firmy a organizace. Licenci si můžete zakoupit od[tady](https://purchase.aspose.com/buy).
### Mohu vyzkoušet Aspose.Slides před nákupem?
 Absolutně! Můžete si stáhnout bezplatnou zkušební verzi Aspose.Slides z[tady](https://releases.aspose.com/) vyhodnotit jeho vlastnosti a možnosti.
### Kde najdu podporu pro Aspose.Slides?
 Pokud máte nějaké dotazy nebo potřebujete pomoc s Aspose.Slides, můžete navštívit stránku[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) pro podporu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
