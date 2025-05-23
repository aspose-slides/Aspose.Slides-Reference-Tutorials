---
"description": "Naučte se, jak v Javě vytvářet miniatury podřízených poznámek SmartArt pomocí Aspose.Slides a bez námahy vylepšit své prezentace v PowerPointu."
"linktitle": "Vytvořit miniaturu podřízené poznámky SmartArt"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Vytvořit miniaturu podřízené poznámky SmartArt"
"url": "/cs/java/java-powerpoint-shape-thumbnail-creation/create-smartart-child-note-thumbnail/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořit miniaturu podřízené poznámky SmartArt

## Zavedení
tomto tutoriálu se podíváme na to, jak v Javě vytvářet miniatury podřízených poznámek SmartArt pomocí Aspose.Slides. Aspose.Slides je výkonné Java API, které umožňuje vývojářům programově pracovat s prezentacemi v PowerPointu a snadno vytvářet, upravovat a manipulovat se snímky.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
1. Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
2. Knihovna Aspose.Slides pro Java byla stažena a nakonfigurována ve vašem projektu. Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Importovat balíčky
Nezapomeňte importovat potřebné balíčky do vaší třídy Java:
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
## Krok 1: Nastavení projektu
Ujistěte se, že máte nastavený a nakonfigurovaný projekt Java s knihovnou Aspose.Slides.
## Krok 2: Vytvořte prezentaci
Vytvořte instanci `Presentation` třída pro reprezentaci souboru PPTX:
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```
## Krok 3: Přidání prvku SmartArt
Přidání prvku SmartArt do snímku prezentace:
```java
ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicCycle);
```
## Krok 4: Získejte referenci uzlu
Získejte referenci uzlu pomocí jeho indexu:
```java
ISmartArtNode node = smart.getNodes().get_Item(1);
```
## Krok 5: Získejte miniaturu
Načíst miniaturní obrázek uzlu SmartArt:
```java
BufferedImage bmp = node.getShapes().get_Item(0).getThumbnail();
```
## Krok 6: Uložení miniatury
Uložení náhledového obrázku do souboru:
```java
ImageIO.write(bmp, "jpeg", new File(dataDir + "SmartArt_ChildNote_Thumbnail_out.jpeg"));
```
Tyto kroky opakujte pro každý uzel grafiky SmartArt podle potřeby v prezentaci.

## Závěr
V tomto tutoriálu jsme se naučili, jak v Javě vytvářet miniatury podřízených poznámek SmartArt pomocí Aspose.Slides. S těmito znalostmi můžete programově vylepšit své prezentace v PowerPointu a snadno do nich přidat vizuálně atraktivní prvky.
## Často kladené otázky
### Mohu použít Aspose.Slides k manipulaci se stávajícími soubory PowerPointu?
Ano, Aspose.Slides umožňuje upravovat existující soubory PowerPointu, včetně přidávání, odebírání nebo úpravy snímků a jejich obsahu.
### Podporuje Aspose.Slides export snímků do různých formátů souborů?
Rozhodně! Aspose.Slides podporuje export snímků do různých formátů, včetně PDF, obrázků a HTML, mimo jiné.
### Je Aspose.Slides vhodný pro automatizaci PowerPointu na podnikové úrovni?
Ano, Aspose.Slides je navržen tak, aby efektivně a spolehlivě zvládal úlohy automatizace PowerPointu na podnikové úrovni.
### Mohu programově vytvářet složité diagramy SmartArt pomocí Aspose.Slides?
Jistě! Aspose.Slides poskytuje komplexní podporu pro vytváření a manipulaci s diagramy SmartArt různé složitosti.
### Nabízí Aspose.Slides technickou podporu pro vývojáře?
Ano, Aspose.Slides poskytuje specializovanou technickou podporu pro vývojáře prostřednictvím svých [forum](https://forum.aspose.com/c/slides/11) a další kanály.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}