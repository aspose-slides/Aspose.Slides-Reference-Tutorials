---
title: Přidejte odrážky odstavců v PowerPointu pomocí Java
linktitle: Přidejte odrážky odstavců v PowerPointu pomocí Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se přidávat odrážky odstavců do snímků aplikace PowerPoint pomocí Aspose.Slides for Java. Tento tutoriál vás provede krok za krokem s příklady kódu.
weight: 15
url: /cs/java/java-powerpoint-text-paragraph-management/add-paragraph-bullets-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
Přidání odrážek odstavců zlepšuje čitelnost a strukturu prezentací PowerPoint. Aspose.Slides for Java poskytuje robustní nástroje pro programovou manipulaci s prezentacemi, včetně možnosti formátovat text pomocí různých stylů odrážek. V tomto tutoriálu se naučíte, jak integrovat odrážky do snímků aplikace PowerPoint pomocí kódu Java s využitím Aspose.Slides.
## Předpoklady
Než začnete, ujistěte se, že máte následující:
- Základní znalost programování v Javě.
- JDK (Java Development Kit) nainstalovaný ve vašem systému.
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky Aspose.Slides do svého projektu Java:
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
## Krok 1: Nastavte svůj projekt
Nejprve vytvořte nový projekt Java a přidejte knihovnu Aspose.Slides for Java do cesty sestavení vašeho projektu.
## Krok 2: Inicializujte prezentaci
Inicializujte objekt prezentace (`Presentation`), abyste mohli začít pracovat se snímky.
```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvoření instance prezentace
Presentation pres = new Presentation();
```
## Krok 3: Otevřete snímek a textový rámeček
Přístup ke snímku (`ISlide`a jeho textový rámeček (`ITextFrame`), kam chcete přidat odrážky.
```java
// Přístup k prvnímu snímku
ISlide slide = pres.getSlides().get_Item(0);
// Přidávání a přístup k automatickému tvaru
IAutoShape aShp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
// Přístup k textovému rámečku vytvořeného automatického tvaru
ITextFrame txtFrm = aShp.getTextFrame();
```
## Krok 4: Vytvořte a formátujte odstavce s odrážkami
Vytvořte odstavce (`Paragraph`) a nastavte jejich styly odrážek, odsazení a text.
```java
// Vytvoření odstavce
Paragraph para = new Paragraph();
para.getParagraphFormat().getBullet().setType(BulletType.Symbol);
para.getParagraphFormat().getBullet().setChar((char) 8226);
para.setText("Welcome to Aspose.Slides");
para.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para);
// Vytvoření dalšího odstavce
Paragraph para2 = new Paragraph();
para2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
para2.getParagraphFormat().getBullet().setNumberedBulletStyle(NumberedBulletStyle.BulletCircleNumWDBlackPlain);
para2.setText("This is numbered bullet");
para2.getParagraphFormat().setIndent(25);
txtFrm.getParagraphs().add(para2);
```
## Krok 5: Uložte prezentaci
Uložte upravenou prezentaci do souboru PowerPoint (`PPTX`).
```java
// Zápis prezentace jako souboru PPTX
pres.save(dataDir + "Bullet_out.pptx", SaveFormat.Pptx);
```
## Krok 6: Vyčistěte zdroje
Zlikvidujte objekt prezentace, abyste uvolnili zdroje.
```java
// Zlikvidujte předmět prezentace
if (pres != null) {
    pres.dispose();
}
```

## Závěr
Přidání odrážek odstavců v PowerPointu pomocí Aspose.Slides for Java je s poskytnutými příklady kódu přímočaré. Přizpůsobte styly odrážek a formátování tak, aby hladce vyhovovaly vašim potřebám prezentace.

## Nejčastější dotazy
### Mohu přizpůsobit barvy odrážek?
Ano, můžete nastavit vlastní barvy pro odrážky pomocí Aspose.Slides API.
### Jak přidám vnořené odrážky?
Vkládání odrážek zahrnuje přidávání odstavců do odstavců a odpovídající úpravu odsazení.
### Mohu vytvořit různé styly odrážek pro různé snímky?
Ano, na různé snímky můžete programově použít jedinečné styly odrážek.
### Je Aspose.Slides kompatibilní s Java 11?
Ano, Aspose.Slides podporuje Java 11 a vyšší verze.
### Kde najdu další příklady a dokumentaci?
 Návštěva[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/) pro komplexní návody a příklady.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
