---
title: Vyplňte tvary obrázkem v PowerPointu
linktitle: Vyplňte tvary obrázkem v PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak vyplnit tvary obrázky v prezentacích PowerPoint pomocí Aspose.Slides for Java. Vylepšete vizuální přitažlivost bez námahy.
weight: 12
url: /cs/java/java-powerpoint-shape-formatting-geometry/fill-shapes-picture-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vyplňte tvary obrázkem v PowerPointu

## Úvod
PowerPointové prezentace často vyžadují vizuální prvky, jako jsou tvary vyplněné obrázky, aby se zvýšila jejich přitažlivost a efektivně předávaly informace. Aspose.Slides for Java poskytuje výkonnou sadu nástrojů pro bezproblémové splnění tohoto úkolu. V tomto tutoriálu se naučíme, jak vyplnit tvary obrázky pomocí Aspose.Slides pro Java krok za krokem.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Stažena knihovna Aspose.Slides pro Java. Můžete to získat od[tady](https://releases.aspose.com/slides/java/).
3. Základní znalost programování v Javě.
## Importujte balíčky
Do svého projektu Java naimportujte potřebné balíčky:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Nastavte adresář projektu
```java
String dataDir = "Your Document Directory";
boolean isExists = new File(dataDir).exists();
if (!isExists)
    new File(dataDir).mkdirs();
```
 Zajistěte výměnu`"Your Document Directory"` s cestou k adresáři vašeho projektu.
## Krok 2: Vytvořte prezentaci
```java
Presentation pres = new Presentation();
```
 Vytvořte instanci`Presentation` třídy k vytvoření nové powerpointové prezentace.
## Krok 3: Přidejte snímek a tvar
```java
ISlide sld = pres.getSlides().get_Item(0);
IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 75, 150);
```
Přidejte snímek do prezentace a vytvořte na něm tvar obdélníku.
## Krok 4: Nastavte Typ výplně na Obrázek
```java
shp.getFillFormat().setFillType(FillType.Picture);
```
Nastavte typ výplně tvaru na obrázek.
## Krok 5: Nastavte režim vyplnění obrázku
```java
shp.getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Tile);
```
Nastavte režim výplně obrázku tvaru.
## Krok 6: Nastavte obrázek
```java
BufferedImage img = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
shp.getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
Načtěte obrázek a nastavte jej jako výplň tvaru.
## Krok 7: Uložte prezentaci
```java
pres.save(dataDir + "RectShpPic_out.pptx", SaveFormat.Pptx);
```
Uložte upravenou prezentaci do souboru.

## Závěr
S Aspose.Slides pro Java se vyplnění tvarů obrázky v prezentacích PowerPoint stává přímočarým procesem. Podle kroků uvedených v tomto kurzu můžete snadno vylepšit své prezentace vizuálně přitažlivými prvky.

## FAQ
### Mohu pomocí Aspose.Slides for Java vyplnit různé tvary obrázky?
Ano, Aspose.Slides pro Java podporuje vyplňování různých tvarů obrázky a poskytuje flexibilitu v designu.
### Je Aspose.Slides for Java kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides for Java generuje prezentace kompatibilní s PowerPoint 97 a vyšší, což zajišťuje širokou kompatibilitu.
### Jak mohu změnit velikost obrázku v rámci tvaru?
Velikost obrázku v rámci tvaru můžete změnit tak, že upravíte rozměry tvaru nebo odpovídajícím způsobem změníte měřítko obrázku, než jej nastavíte jako výplň.
### Existují nějaká omezení pro formáty obrázků podporované pro vyplňování tvarů?
Aspose.Slides for Java podporuje širokou škálu obrazových formátů, včetně JPEG, PNG, GIF, BMP a TIFF, mezi ostatními.
### Mohu použít efekty na vyplněné tvary?
Ano, Aspose.Slides for Java poskytuje komplexní rozhraní API pro aplikaci různých efektů, jako jsou stíny, odrazy a 3D rotace, na vyplněné tvary.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
