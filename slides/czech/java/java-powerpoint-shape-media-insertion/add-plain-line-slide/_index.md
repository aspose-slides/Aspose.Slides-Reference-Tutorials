---
"description": "Naučte se, jak programově přidat do snímku PowerPointu obyčejný řádek pomocí Aspose.Slides pro Javu. Zvyšte svou produktivitu s tímto podrobným návodem."
"linktitle": "Přidat na snímek prostou čáru"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidat na snímek prostou čáru"
"url": "/cs/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidat na snímek prostou čáru

## Zavedení
Aspose.Slides pro Javu je výkonná knihovna, která umožňuje vývojářům v Javě programově pracovat s prezentacemi v PowerPointu. S Aspose.Slides můžete snadno vytvářet, upravovat a převádět soubory PowerPointu, což vám ušetří čas a úsilí. V tomto tutoriálu vás provedeme procesem přidání prostého řádku do snímku v prezentaci PowerPointu pomocí Aspose.Slides pro Javu.
## Předpoklady
Než začneme, ujistěte se, že máte následující předpoklady:
- Sada pro vývoj Java (JDK) nainstalovaná ve vašem systému
- Knihovna Aspose.Slides pro Javu byla stažena a přidána do vašeho projektu v Javě
- Základní znalost programovacího jazyka Java

## Importovat balíčky
Pro začátek je potřeba importovat potřebné balíčky do kódu Java. Zde je návod, jak to udělat:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## Krok 1: Nastavení prostředí
Nejprve vytvořte nový projekt v jazyce Java a přidejte knihovnu Aspose.Slides for Java do cesty tříd vašeho projektu. Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/).
## Krok 2: Vytvořte novou prezentaci
Dále vytvořte instanci `Presentation` třída pro vytvoření nové prezentace v PowerPointu.
```java
Presentation pres = new Presentation();
```
## Krok 3: Přidání snímku
Získejte první snímek prezentace a uložte ho do proměnné.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Krok 4: Přidání tvaru čáry
Nyní přidejte na snímek automatický tvar textové čáry.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Krok 5: Uložte prezentaci
Nakonec uložte prezentaci na disk.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Závěr
Gratulujeme! Úspěšně jste přidali prostý řádek do snímku v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. S Aspose.Slides můžete snadno programově manipulovat se soubory PowerPointu, což otevírá svět možností pro vaše Java aplikace.

## Často kladené otázky
### Mohu si přizpůsobit vlastnosti tvaru čáry?
Ano, pomocí rozhraní Aspose.Slides API si můžete přizpůsobit různé vlastnosti, jako je barva čáry, šířka, styl a další.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Ano, Aspose.Slides podporuje různé formáty PowerPointu, včetně PPT, PPTX a dalších, což zajišťuje kompatibilitu mezi různými verzemi.
### Poskytuje Aspose.Slides podporu pro přidávání dalších tvarů kromě čar?
Rozhodně! Aspose.Slides nabízí širokou škálu typů tvarů, včetně obdélníků, kruhů, šipek a dalších.
### Mohu na snímek přidat text spolu s tvarem čáry?
Ano, text, obrázky a další obsah můžete do snímku přidat pomocí rozhraní Aspose.Slides API.
### Je k dispozici bezplatná zkušební verze Aspose.Slides?
Ano, můžete si stáhnout bezplatnou zkušební verzi Aspose.Slides z [zde](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}