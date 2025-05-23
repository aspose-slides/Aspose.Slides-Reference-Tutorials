---
"description": "Naučte se, jak nastavit formát výplně odrážek v SmartArt pomocí Javy s Aspose.Slides. Podrobný návod pro efektivní manipulaci s prezentací."
"linktitle": "Nastavení formátu výplně odrážek v SmartArt pomocí Javy"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení formátu výplně odrážek v SmartArt pomocí Javy"
"url": "/cs/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení formátu výplně odrážek v SmartArt pomocí Javy

## Zavedení
V oblasti programování v Javě je efektivní manipulace s prezentacemi běžným požadavkem, zejména při práci s prvky SmartArt. Aspose.Slides pro Javu se pro takové úkoly jeví jako výkonný nástroj a nabízí řadu funkcí pro programovou práci s prezentacemi. V tomto tutoriálu se krok za krokem ponoříme do procesu nastavení formátu výplně odrážkami v SmartArt pomocí Javy s Aspose.Slides.
## Předpoklady
Než se pustíme do tohoto tutoriálu, ujistěte se, že máte splněny následující předpoklady:
### Vývojová sada pro Javu (JDK)
Musíte mít na svém systému nainstalovaný JDK. Můžete si ho stáhnout z [webové stránky](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) a postupujte podle pokynů k instalaci.
### Aspose.Slides pro Javu
Stáhněte a nainstalujte Aspose.Slides pro Javu z [odkaz ke stažení](https://releases.aspose.com/slides/java/)Postupujte podle pokynů k instalaci uvedených v dokumentaci pro váš konkrétní operační systém.

## Importovat balíčky
Pro začátek importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Pro jasné pochopení nastavení formátu výplně odrážkami v grafice SmartArt pomocí Javy s Aspose.Slides si rozdělme uvedený příklad do několika kroků.
## Krok 1: Vytvoření prezentačního objektu
```java
Presentation presentation = new Presentation();
```
Nejprve vytvořte novou instanci třídy Presentation, která reprezentuje prezentaci v PowerPointu.
## Krok 2: Přidání prvku SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Dále přidejte na snímek tvar SmartArt. Tento řádek kódu inicializuje nový tvar SmartArt se zadanými rozměry a rozvržením.
## Krok 3: Přístup k uzlu SmartArt
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Nyní přejděte k prvnímu uzlu (nebo libovolnému požadovanému uzlu) v rámci tvaru SmartArt a upravte jeho vlastnosti.
## Krok 4: Nastavení formátu výplně odrážek
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Zde zkontrolujeme, zda je formát výplně odrážkami podporován. Pokud ano, načteme soubor s obrázkem a nastavíme ho jako výplň odrážkami pro uzel SmartArt.
## Krok 5: Uložení prezentace
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Nakonec upravenou prezentaci uložte do určeného umístění.

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak nastavit formát výplně odrážek v grafickém prvku SmartArt pomocí nástroje Aspose.Slides v Javě. Tato funkce otevírá svět možností pro dynamické a vizuálně poutavé prezentace v aplikacích Java.
## Často kladené otázky
### Mohu použít Aspose.Slides pro Javu k vytváření prezentací od nuly?
Rozhodně! Aspose.Slides poskytuje komplexní API pro vytváření, úpravy a manipulaci s prezentacemi výhradně pomocí kódu.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Ano, Aspose.Slides zajišťuje kompatibilitu s různými verzemi aplikace Microsoft PowerPoint, což umožňuje bezproblémovou integraci do vašeho pracovního postupu.
### Mohu přizpůsobit prvky SmartArt nad rámec formátu výplně odrážkami?
Aspose.Slides vám skutečně umožňuje přizpůsobit si všechny aspekty tvarů SmartArt, včetně rozvržení, stylu, obsahu a dalších.
### Je k dispozici zkušební verze Aspose.Slides pro Javu?
Ano, funkce Aspose.Slides si můžete vyzkoušet s bezplatnou zkušební verzí. Jednoduše si ji stáhněte z [webové stránky](https://releases.aspose.com/slides/java/) a začněte prozkoumávat.
### Kde najdu podporu pro Aspose.Slides pro Javu?
V případě jakýchkoli dotazů nebo potřeby pomoci můžete navštívit fórum Aspose.Slides na adrese [tento odkaz](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}