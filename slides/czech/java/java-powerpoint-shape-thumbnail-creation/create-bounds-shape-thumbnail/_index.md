---
title: Vytvořte miniaturu tvaru ohraničení
linktitle: Vytvořte miniaturu tvaru ohraničení
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet miniatury tvarů s ohraničením pomocí Aspose.Slides for Java. Tento tutoriál vás krok za krokem provede celým procesem.
type: docs
weight: 10
url: /cs/java/java-powerpoint-shape-thumbnail-creation/create-bounds-shape-thumbnail/
---
## Úvod
Aspose.Slides for Java je výkonná knihovna, která umožňuje vývojářům Java vytvářet, manipulovat a převádět PowerPointové prezentace programově. V tomto tutoriálu se naučíme, jak vytvořit miniaturu tvaru s ohraničením pomocí Aspose.Slides pro Java.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Knihovna Aspose.Slides for Java byla stažena a přidána do vašeho projektu. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Ujistěte se, že do kódu Java importujete potřebné balíčky:
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Nastavte svůj projekt
Vytvořte nový projekt Java ve vašem preferovaném IDE a přidejte knihovnu Aspose.Slides for Java do závislostí vašeho projektu.
## Krok 2: Vytvořte instanci objektu prezentace
 Instantovat a`Presentation` objekt poskytnutím cesty k souboru prezentace PowerPoint.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
```
## Krok 3: Vytvořte miniaturu tvaru ohraničení
Nyní vytvoříme miniaturu tvaru s hranicemi z prezentace.
```java
try {
    BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Appearance, 1, 1);
    ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_Bound_Shape_out.png"));
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Závěr
V tomto tutoriálu jsme se naučili, jak vytvořit miniaturu tvaru s ohraničením pomocí Aspose.Slides for Java. Pomocí těchto kroků můžete snadno programově generovat miniatury obrazců v prezentacích PowerPoint.
## FAQ
### Mohu vytvořit miniatury pro konkrétní tvary na snímku?
Ano, můžete přistupovat k jednotlivým tvarům na snímku a generovat pro ně miniatury pomocí Aspose.Slides for Java.
### Je Aspose.Slides for Java kompatibilní se všemi verzemi souborů PowerPoint?
Aspose.Slides for Java podporuje různé formáty souborů PowerPoint, včetně PPT, PPTX, PPS, PPSX a dalších.
### Mohu upravit vzhled generovaných miniatur?
Ano, vlastnosti miniatur obrázků, jako je velikost a kvalita, můžete upravit podle svých požadavků.
### Podporuje Aspose.Slides for Java další funkce kromě generování náhledů?
Ano, Aspose.Slides for Java poskytuje rozsáhlé funkce pro práci s PowerPoint prezentacemi, včetně manipulace se snímky, extrakce textu a generování grafů.
### Je k dispozici zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).