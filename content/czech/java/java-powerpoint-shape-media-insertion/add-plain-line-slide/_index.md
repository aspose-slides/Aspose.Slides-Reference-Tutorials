---
title: Přidat obyčejnou čáru do snímku
linktitle: Přidat obyčejnou čáru do snímku
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak přidat prostou čáru do snímku aplikace PowerPoint pomocí programu Aspose.Slides for Java. Zvyšte svou produktivitu pomocí tohoto podrobného průvodce.
type: docs
weight: 14
url: /cs/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/
---
## Úvod
Aspose.Slides for Java je výkonná knihovna, která vývojářům v jazyce Java umožňuje programově pracovat s prezentacemi v PowerPointu. S Aspose.Slides můžete snadno vytvářet, upravovat a převádět soubory PowerPoint, což vám ušetří čas a námahu. V tomto tutoriálu vás provedeme procesem přidání prosté čáry na snímek v prezentaci PowerPoint pomocí Aspose.Slides for Java.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Java Development Kit (JDK) nainstalovaný ve vašem systému
- Knihovna Aspose.Slides for Java byla stažena a přidána do vašeho projektu Java
- Základní znalost programovacího jazyka Java

## Importujte balíčky
Chcete-li začít, musíte do kódu Java naimportovat potřebné balíčky. Můžete to udělat takto:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
import com.aspose.slides.examples.RunExamples;
import java.io.File;
```
## Krok 1: Nastavte prostředí
 Nejprve vytvořte nový projekt Java a přidejte knihovnu Aspose.Slides for Java do cesty třídy vašeho projektu. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).
## Krok 2: Vytvořte novou prezentaci
 Dále vytvořte instanci`Presentation` třídy k vytvoření nové prezentace PowerPoint.
```java
Presentation pres = new Presentation();
```
## Krok 3: Přidejte snímek
Získejte první snímek prezentace a uložte jej do proměnné.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 4: Přidejte tvar čáry
Nyní přidejte na snímek automatický tvar typové čáry.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Krok 5: Uložte prezentaci
Nakonec prezentaci uložte na disk.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Závěr
Gratulujeme! Úspěšně jste přidali holou čáru na snímek v prezentaci PowerPoint pomocí Aspose.Slides for Java. S Aspose.Slides můžete snadno programově manipulovat se soubory PowerPoint, čímž se otevírá svět možností pro vaše Java aplikace.

## FAQ
### Mohu přizpůsobit vlastnosti tvaru čáry?
Ano, pomocí Aspose.Slides API si můžete přizpůsobit různé vlastnosti, jako je barva čáry, šířka, styl a další.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Ano, Aspose.Slides podporuje různé formáty PowerPoint, včetně PPT, PPTX a dalších, což zajišťuje kompatibilitu napříč různými verzemi.
### Poskytuje Aspose.Slides podporu pro přidávání dalších tvarů kromě čar?
Absolutně! Aspose.Slides nabízí širokou škálu typů tvarů, včetně obdélníků, kruhů, šipek a dalších.
### Mohu na snímek přidat text spolu s tvarem čáry?
Ano, pomocí Aspose.Slides API můžete na snímek přidat text, obrázky a další obsah.
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides?
Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Slides z[tady](https://releases.aspose.com/).