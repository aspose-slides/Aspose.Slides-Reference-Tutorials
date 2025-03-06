---
title: Nastavte jazyk prezentace a text tvaru v Javě
linktitle: Nastavte jazyk prezentace a text tvaru v Javě
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se automatizovat prezentace PowerPoint pomocí Aspose.Slides for Java. Vytvářejte, upravujte a vylepšujte snímky snadno programově.
type: docs
weight: 19
url: /cs/java/java-powerpoint-text-font-customization/set-presentation-language-shape-text-java/
---
## Úvod
Vytváření a manipulace s prezentacemi PowerPoint programově v Javě může zefektivnit automatizaci pracovních postupů a zvýšit produktivitu. Aspose.Slides for Java poskytuje robustní sadu nástrojů pro efektivní dosažení těchto úkolů. Tento tutoriál vás provede základními kroky k nastavení jazyka prezentace a tvaru textu pomocí Aspose.Slides pro Java.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte následující:
- Java Development Kit (JDK) nainstalován
-  Knihovna Aspose.Slides for Java, kterou si můžete stáhnout[tady](https://releases.aspose.com/slides/java/)
- Integrované vývojové prostředí (IDE), jako je IntelliJ IDEA nebo Eclipse nastavené na vašem systému
- Základní znalost programovacího jazyka Java
## Importujte balíčky
Chcete-li začít, importujte potřebné balíčky Aspose.Slides do souboru Java:
```java
import com.aspose.slides.IAutoShape;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;
```
## Krok 1: Vytvořte objekt prezentace
 Začněte inicializací a`Presentation` objekt:
```java
Presentation pres = new Presentation();
```
Tím se vytvoří nová prezentace PowerPoint.
## Krok 2: Přidejte a nakonfigurujte automatický tvar
Dále přidejte automatický tvar na první snímek a nakonfigurujte jeho vlastnosti:
```java
ISlide slide = pres.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
```
Zde přidáme automatický tvar obdélníku na souřadnicích (50, 50) o rozměrech 200x50 pixelů.
## Krok 3: Nastavte text a jazyk
Nastavte obsah textu a určete jazyk pro kontrolu pravopisu:
```java
shape.addTextFrame("Text to apply spellcheck language");
shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setLanguageId("en-EN");
```
 Nahradit`"Text to apply spellcheck language"` s požadovaným textem. ID jazyka`"en-EN"`určuje angličtinu (Spojené státy americké).
## Krok 4: Uložte prezentaci
Uložte upravenou prezentaci do určeného výstupního adresáře:
```java
pres.save("Your Output Directory" + "test1.pptx", SaveFormat.Pptx);
```
 Zajistěte výměnu`"Your Output Directory"` s vaší skutečnou cestou k adresáři, kam chcete soubor uložit.
## Krok 5: Zlikvidujte zdroje
 Správně zlikvidujte`Presentation` protest proti uvolnění zdrojů:
```java
pres.dispose();
```
Tento krok je zásadní, abyste se vyhnuli únikům paměti.

## Závěr
Závěrem lze říci, že Aspose.Slides for Java zjednodušuje proces vytváření a manipulace s prezentacemi v PowerPointu programově. Pomocí těchto kroků můžete efektivně nastavit jazyk prezentace a nakonfigurovat vlastnosti textu podle vašich požadavků.
## FAQ
### Mohu použít Aspose.Slides pro Java k vytvoření prezentací PowerPoint od začátku?
Ano, Aspose.Slides poskytuje komplexní rozhraní API pro vytváření prezentací zcela programově.
### Jak mohu použít různá písma na text ve snímcích PowerPoint pomocí Aspose.Slides for Java?
 Vlastnosti písma můžete nastavit pomocí`IPortionFormat` objekty spojené s částmi textu.
### Je k dispozici zkušební verze pro Aspose.Slides pro Java?
 Ano, můžete získat bezplatnou zkušební verzi od[tady](https://releases.aspose.com/).
### Kde najdu dokumentaci k Aspose.Slides pro Javu?
 K dispozici je podrobná dokumentace[tady](https://reference.aspose.com/slides/java/).
### Jaké možnosti podpory jsou k dispozici pro Aspose.Slides for Java?
 Můžete navštívit fórum Aspose.Slides[tady](https://forum.aspose.com/c/slides/11) za podporu komunity.