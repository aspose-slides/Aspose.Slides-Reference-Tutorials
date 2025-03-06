---
title: Přidejte rámeček obrázku v relativním měřítku výšky v aplikaci PowerPoint
linktitle: Přidejte rámeček obrázku v relativním měřítku výšky v aplikaci PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přidávat rámečky obrázků v relativním měřítku do prezentací aplikace PowerPoint pomocí Aspose.Slides for Java a vylepšit tak svůj vizuální obsah.
weight: 15
url: /cs/java/java-powerpoint-shape-media-insertion/add-relative-scale-height-picture-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte rámeček obrázku v relativním měřítku výšky v aplikaci PowerPoint

## Úvod
V tomto tutoriálu se naučíte, jak přidat rámeček obrázku s relativní výškou měřítka v prezentacích PowerPoint pomocí Aspose.Slides for Java.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2. Knihovna Aspose.Slides for Java byla stažena a přidána do vašeho projektu Java.

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.slides.*;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Nastavte svůj projekt
Nejprve se ujistěte, že máte pro svůj projekt nastaven adresář a vaše prostředí Java je správně nakonfigurováno.
## Krok 2: Instanciujte objekt prezentace
Vytvořte nový objekt prezentace pomocí Aspose.Slides:
```java
Presentation presentation = new Presentation();
```
## Krok 3: Načtěte obrázek, který chcete přidat
Načtěte obrázek, který chcete přidat do prezentace:
```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage image = presentation.getImages().addImage(img);
```
## Krok 4: Přidejte rámeček obrázku do snímku
Přidejte rámeček obrázku na snímek v prezentaci:
```java
IPictureFrame pf = presentation.getSlides().get_Item(0).getShapes().addPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
## Krok 5: Nastavte relativní šířku a výšku měřítka
Nastavte relativní šířku a výšku měřítka pro rám obrazu:
```java
pf.setRelativeScaleHeight(0.8f);
pf.setRelativeScaleWidth(1.35f);
```
## Krok 6: Uložte prezentaci
Uložte prezentaci s přidaným rámečkem obrázku:
```java
presentation.save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```

## Závěr
Pomocí těchto kroků můžete snadno přidat rámeček obrázku s relativní výškou měřítka v prezentacích PowerPoint pomocí Aspose.Slides pro Java. Experimentujte s různými hodnotami měřítka, abyste dosáhli požadovaného vzhledu obrázků.

## FAQ
### Mohu pomocí této metody přidat více rámečků obrázků na jeden snímek?
Ano, na snímek můžete přidat více rámečků obrázků opakováním postupu pro každý obrázek.
### Je Aspose.Slides for Java kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides for Java je kompatibilní s různými verzemi PowerPointu a zajišťuje flexibilitu při vytváření prezentací.
### Mohu upravit polohu a velikost rámečku obrazu?
 Absolutně můžete upravit parametry pozice a velikosti v`addPictureFrame` způsob, který vyhovuje vašim požadavkům.
### Podporuje Aspose.Slides for Java jiné formáty obrázků kromě JPEG?
Ano, Aspose.Slides for Java podporuje různé formáty obrázků, včetně PNG, GIF, BMP a dalších.
### Je pro uživatele Aspose.Slides k dispozici komunitní fórum nebo kanál podpory?
Ano, můžete navštívit fórum Aspose.Slides pro jakékoli dotazy, diskuze nebo pomoc týkající se knihovny.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
