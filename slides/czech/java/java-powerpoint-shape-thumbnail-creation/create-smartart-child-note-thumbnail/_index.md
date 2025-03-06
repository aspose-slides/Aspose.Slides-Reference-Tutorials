---
title: Vytvořte miniaturu podřízené poznámky SmartArt
linktitle: Vytvořte miniaturu podřízené poznámky SmartArt
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet miniatury podřízených poznámek SmartArt v Javě pomocí Aspose.Slides, které bez námahy vylepší vaše PowerPointové prezentace.
weight: 15
url: /cs/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
V tomto tutoriálu prozkoumáme, jak vytvořit miniatury podřízených poznámek SmartArt v Javě pomocí Aspose.Slides. Aspose.Slides je výkonné Java API, které umožňuje vývojářům pracovat s PowerPointovými prezentacemi programově, což jim umožňuje snadno vytvářet, upravovat a manipulovat se snímky.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Java Development Kit (JDK) nainstalovaný ve vašem systému.
2.  Knihovna Aspose.Slides for Java stažená a nakonfigurovaná ve vašem projektu. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Ujistěte se, že importujete potřebné balíčky do vaší třídy Java:
```java
import com.aspose.slides.ISmartArt;
import com.aspose.slides.ISmartArtNode;
import com.aspose.slides.Presentation;
import com.aspose.slides.SmartArtLayoutType;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Krok 1: Nastavte svůj projekt
Ujistěte se, že máte projekt Java nastaven a konfigurován pomocí knihovny Aspose.Slides.
## Krok 2: Vytvořte prezentaci
 Vytvořte instanci`Presentation` třída reprezentující soubor PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Krok 3: Přidejte SmartArt
Přidejte SmartArt do snímku prezentace:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Krok 4: Získejte referenci uzlu
Získejte odkaz na uzel pomocí jeho indexu:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Krok 5: Získejte miniaturu
Načtěte obrázek miniatury uzlu SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Krok 6: Uložte miniaturu
Uložte miniaturu obrázku do souboru:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Opakujte tyto kroky pro každý uzel SmartArt podle potřeby v prezentaci.

## Závěr
V tomto tutoriálu jsme se naučili, jak vytvořit miniatury podřízených poznámek SmartArt v Javě pomocí Aspose.Slides. S těmito znalostmi můžete své PowerPointové prezentace programově vylepšit a snadno přidat vizuálně přitažlivé prvky.
## FAQ
### Mohu použít Aspose.Slides k manipulaci se stávajícími soubory PowerPoint?
Ano, Aspose.Slides umožňuje upravovat stávající soubory PowerPoint, včetně přidávání, odebírání nebo úpravy snímků a jejich obsahu.
### Podporuje Aspose.Slides export snímků do různých formátů souborů?
Absolutně! Aspose.Slides podporuje export snímků do různých formátů, včetně PDF, obrázků a HTML, mezi ostatními.
### Je Aspose.Slides vhodný pro automatizaci PowerPoint na podnikové úrovni?
Ano, Aspose.Slides je navržen tak, aby efektivně a spolehlivě zvládal úkoly automatizace PowerPoint na podnikové úrovni.
### Mohu programově vytvářet složité diagramy SmartArt pomocí Aspose.Slides?
Rozhodně! Aspose.Slides poskytuje komplexní podporu pro vytváření a manipulaci s diagramy SmartArt různé složitosti.
### Nabízí Aspose.Slides technickou podporu pro vývojáře?
 Ano, Aspose.Slides poskytuje specializovanou technickou podporu pro vývojáře prostřednictvím jejich[Fórum](https://forum.aspose.com/c/slides/11) a další kanály.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
