---
title: Nastavte formát výplně odrážek v obrázku SmartArt pomocí jazyka Java
linktitle: Nastavte formát výplně odrážek v obrázku SmartArt pomocí jazyka Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit formát odrážkové výplně v SmartArt pomocí Java s Aspose.Slides. Podrobný průvodce pro efektivní manipulaci s prezentacemi.
weight: 18
url: /cs/java/java-powerpoint-smartart-manipulation/set-bullet-fill-format-smartart-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavte formát výplně odrážek v obrázku SmartArt pomocí jazyka Java

## Úvod
oblasti programování v jazyce Java je efektivní manipulace s prezentacemi běžným požadavkem, zejména při práci s prvky SmartArt. Aspose.Slides for Java se ukazuje jako výkonný nástroj pro takové úkoly, který nabízí řadu funkcí pro programové zpracování prezentací. V tomto tutoriálu se krok za krokem ponoříme do procesu nastavení formátu výplně odrážek v obrázku SmartArt pomocí Java s Aspose.Slides.
## Předpoklady
Než se pustíme do tohoto tutoriálu, ujistěte se, že máte splněny následující předpoklady:
### Java Development Kit (JDK)
 V systému musíte mít nainstalovaný JDK. Můžete si jej stáhnout z[webová stránka](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) a postupujte podle pokynů k instalaci.
### Aspose.Slides pro Javu
 Stáhněte a nainstalujte Aspose.Slides for Java z[odkaz ke stažení](https://releases.aspose.com/slides/java/). Postupujte podle pokynů k instalaci uvedených v dokumentaci pro váš konkrétní operační systém.

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky do svého projektu Java:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
#Pojďme si uvedený příklad rozdělit do několika kroků, abychom jasně porozuměli tomu, jak nastavit formát výplně odrážek v SmartArt pomocí Java s Aspose.Slides.
## Krok 1: Vytvořte objekt prezentace
```java
Presentation presentation = new Presentation();
```
Nejprve vytvořte novou instanci třídy Presentation, která představuje prezentaci v PowerPointu.
## Krok 2: Přidejte SmartArt
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 500, 400, SmartArtLayoutType.VerticalPictureList);
```
Dále přidejte na snímek obrazec SmartArt. Tento řádek kódu inicializuje nový tvar SmartArt se zadanými rozměry a rozložením.
## Krok 3: Přístup k SmartArt Node
```java
ISmartArtNode node = smart.getAllNodes().get_Item(0);
```
Nyní přejděte k prvnímu uzlu (nebo libovolnému požadovanému uzlu) v rámci tvaru SmartArt a upravte jeho vlastnosti.
## Krok 4: Nastavte formát výplně odrážek
```java
if (node.getBulletFillFormat() != null) {
    BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    IPPImage image = presentation.getImages().addImage(img);
    node.getBulletFillFormat().setFillType(FillType.Picture);
    node.getBulletFillFormat().getPictureFillFormat().getPicture().setImage(image);
    node.getBulletFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
}
```
Zde zkontrolujeme, zda je podporován formát odrážky. Pokud ano, načteme soubor obrázku a nastavíme jej jako výplň odrážky pro uzel SmartArt.
## Krok 5: Uložte prezentaci
```java
presentation.save(dataDir + "out.pptx", SaveFormat.Pptx);
```
Nakonec upravenou prezentaci uložte na určené místo.

## Závěr
Gratulujeme! Úspěšně jste se naučili, jak nastavit formát výplně odrážek v obrázku SmartArt pomocí Java s Aspose.Slides. Tato schopnost otevírá svět možností pro dynamické a vizuálně přitažlivé prezentace v aplikacích Java.
## FAQ
### Mohu použít Aspose.Slides pro Java k vytváření prezentací od začátku?
Absolutně! Aspose.Slides poskytuje komplexní rozhraní API pro vytváření, úpravy a manipulaci s prezentacemi výhradně prostřednictvím kódu.
### Je Aspose.Slides kompatibilní s různými verzemi PowerPointu?
Ano, Aspose.Slides zajišťuje kompatibilitu s různými verzemi aplikace Microsoft PowerPoint a umožňuje bezproblémovou integraci do vašeho pracovního postupu.
### Mohu přizpůsobit prvky SmartArt mimo formát odrážkové výplně?
Aspose.Slides vám skutečně umožňuje přizpůsobit každý aspekt tvarů SmartArt, včetně rozvržení, stylu, obsahu a dalších.
### Je k dispozici zkušební verze pro Aspose.Slides pro Java?
 Ano, funkce Aspose.Slides můžete prozkoumat pomocí bezplatné zkušební verze. Jednoduše si jej stáhněte z[webová stránka](https://releases.aspose.com/slides/java/) a začít prozkoumávat.
### Kde najdu podporu pro Aspose.Slides pro Java?
 V případě jakýchkoli dotazů nebo pomoci můžete navštívit fórum Aspose.Slides na adrese[tento odkaz](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
