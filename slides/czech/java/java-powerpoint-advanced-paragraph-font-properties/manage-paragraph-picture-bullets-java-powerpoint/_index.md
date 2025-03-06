---
title: Správa odrážek odstavcových obrázků v Java PowerPointu
linktitle: Správa odrážek odstavcových obrázků v Java PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přidávat vlastní obrázkové odrážky do snímků aplikace PowerPoint pomocí Aspose.Slides for Java. Postupujte podle tohoto podrobného průvodce krok za krokem pro bezproblémovou integraci.
weight: 11
url: /cs/java/java-powerpoint-advanced-paragraph-font-properties/manage-paragraph-picture-bullets-java-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Úvod
Vytváření poutavých a vizuálně přitažlivých prezentací je klíčovou dovedností v moderním obchodním světě. Vývojáři Java mohou využít Aspose.Slides k vylepšení svých prezentací pomocí přizpůsobených obrázkových odrážek na snímcích PowerPoint. Tento výukový program vás provede procesem krok za krokem a zajistí, že do svých prezentací můžete s jistotou přidávat obrázkové odrážky.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
- Java Development Kit (JDK) nainstalován
- Integrované vývojové prostředí (IDE), jako je Eclipse nebo IntelliJ IDEA
- Aspose.Slides pro knihovnu Java
- Základní znalost programování v Javě
- Soubor obrázku pro obrázek odrážky
 Chcete-li stáhnout knihovnu Aspose.Slides for Java, navštivte[stránka ke stažení](https://releases.aspose.com/slides/java/) . Pro dokumentaci zkontrolujte[dokumentace](https://reference.aspose.com/slides/java/).
## Importujte balíčky
Nejprve se ujistěte, že jste naimportovali potřebné balíčky pro váš projekt. Na začátek souboru Java přidejte následující importy:
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Pojďme si tento proces rozdělit na zvládnutelné kroky.
## Krok 1: Nastavte adresář projektu
Vytvořte nový adresář pro váš projekt. Tento adresář bude obsahovat váš soubor Java, knihovnu Aspose.Slides a soubor obrázku pro odrážku.
```java
String dataDir = "Your Document Directory";
```
## Krok 2: Inicializujte prezentaci
 Inicializujte novou instanci souboru`Presentation` třída. Tento objekt představuje vaši prezentaci v PowerPointu.
```java
Presentation presentation = new Presentation();
```
## Krok 3: Otevřete první snímek
Otevřete první snímek prezentace. Snímky mají nulový index, takže první snímek má index 0.
```java
ISlide slide = presentation.getSlides().get_Item(0);
```
## Krok 4: Načtěte obrázek odrážky
Načtěte obrázek, který chcete použít pro odrážky. Tento obrázek by měl být umístěn ve vašem projektovém adresáři.
```java
BufferedImage image = ImageIO.read(new File(dataDir + "bullets.png"));
IPPImage ippxImage = presentation.getImages().addImage(image);
```
## Krok 5: Přidejte na snímek automatický tvar
Přidejte na snímek automatický tvar. Tvar bude obsahovat text s vlastními odrážkami.
```java
IAutoShape autoShape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
```
## Krok 6: Otevřete textový rámeček
Otevřete textový rámeček automatického tvaru, abyste mohli manipulovat s jeho odstavci.
```java
ITextFrame textFrame = autoShape.getTextFrame();
```
## Krok 7: Odeberte výchozí odstavec
Odeberte výchozí odstavec, který se automaticky přidá do textového rámečku.
```java
textFrame.getParagraphs().removeAt(0);
```
## Krok 8: Vytvořte nový odstavec
Vytvořte nový odstavec a nastavte jeho text. Tento odstavec bude obsahovat vlastní obrázkové odrážky.
```java
Paragraph paragraph = new Paragraph();
paragraph.setText("Welcome to Aspose.Slides");
```
## Krok 9: Nastavte styl odrážky a obrázek
Nastavte styl odrážek, abyste použili vlastní obrázek načtený dříve.
```java
paragraph.getParagraphFormat().getBullet().setType(BulletType.Picture);
paragraph.getParagraphFormat().getBullet().getPicture().setImage(ippxImage);
```
## Krok 10: Upravte výšku střely
Nastavte výšku odrážky, abyste se ujistili, že v prezentaci vypadá dobře.
```java
paragraph.getParagraphFormat().getBullet().setHeight(100);
```
## Krok 11: Přidejte odstavec do textového rámečku
Přidejte nově vytvořený odstavec do textového rámečku automatického tvaru.
```java
textFrame.getParagraphs().add(paragraph);
```
## Krok 12: Uložte prezentaci
Nakonec uložte prezentaci jako soubor PPTX i PPT.
```java
presentation.save(dataDir + "ParagraphPictureBulletsPPTX_out.pptx", SaveFormat.Pptx);
presentation.save(dataDir + "ParagraphPictureBulletsPPT_out.ppt", SaveFormat.Ppt);
```
## Závěr
 A tady to máte! Pomocí následujících kroků můžete snadno přidat vlastní obrázkové odrážky do prezentací PowerPoint pomocí Aspose.Slides for Java. Tato výkonná knihovna nabízí širokou škálu funkcí, které vám pomohou vytvářet profesionální a vizuálně přitažlivé prezentace. Nezapomeňte prozkoumat[dokumentace](https://reference.aspose.com/slides/java/)pro pokročilejší funkce a možnosti přizpůsobení.
## FAQ
### Co je Aspose.Slides for Java?
Aspose.Slides for Java je výkonná knihovna, která umožňuje vývojářům v jazyce Java vytvářet, upravovat a manipulovat s prezentacemi PowerPoint programově.
### Mohu použít jakýkoli obrázek pro obrázkové odrážky?
Ano, pro obrázkové odrážky můžete použít jakýkoli obrázek, pokud je dostupný z adresáře vašeho projektu.
### Potřebuji licenci k používání Aspose.Slides for Java?
 Aspose.Slides for Java vyžaduje licenci pro plnou funkčnost. Dočasnou licenci můžete získat od[tady](https://purchase.aspose.com/temporary-license/) nebo zakoupit plnou licenci[tady](https://purchase.aspose.com/buy).
### Mohu přidat více odstavců s různými styly odrážek do jednoho automatického tvaru?
Ano, do jednoho automatického tvaru můžete přidat více odstavců s různými styly odrážek tak, že vytvoříte a nakonfigurujete každý odstavec samostatně.
### Kde najdu další příklady a podporu?
 Další příklady najdete v[dokumentace](https://reference.aspose.com/slides/java/) a získat podporu od komunity Aspose na[fórech](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
