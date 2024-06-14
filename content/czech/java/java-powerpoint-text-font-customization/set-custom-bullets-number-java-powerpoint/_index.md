---
title: Nastavte počet vlastních odrážek v Java PowerPointu
linktitle: Nastavte počet vlastních odrážek v Java PowerPointu
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit vlastní čísla odrážek v Java PowerPointu pomocí Aspose.Slides, čímž se zvýší přehlednost a struktura prezentace programově.
type: docs
weight: 15
url: /cs/java/java-powerpoint-text-font-customization/set-custom-bullets-number-java-powerpoint/
---
## Úvod
V dnešní digitální době je vytváření dynamických prezentací zásadní pro efektivní sdělování nápadů a dat. Aspose.Slides for Java poskytuje výkonnou sadu nástrojů pro programovou manipulaci s prezentacemi v PowerPointu a nabízí rozsáhlé funkce pro vylepšení procesu vytváření prezentací. Tento článek se ponoří do nastavení vlastních čísel odrážek v prezentacích Java PowerPoint pomocí Aspose.Slides. Ať už jste ostřílený vývojář nebo nováček, tento tutoriál vás krok za krokem provede celým procesem a zajistí, že můžete tuto schopnost efektivně využít.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte ve vývojovém prostředí nastaveny následující předpoklady:
- Java Development Kit (JDK) nainstalován
- Integrované vývojové prostředí (IDE), jako je IntelliJ IDEA nebo Eclipse
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/)
- Základní znalost programovacího jazyka Java a objektově orientovaných konceptů

## Importujte balíčky
Nejprve importujte potřebné třídy Aspose.Slides a další standardní knihovny Java:
```java
import com.aspose.slides.*;
```
## Krok 1: Vytvořte objekt prezentace
Začněte vytvořením nové prezentace PowerPoint pomocí Aspose.Slides.
```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```
## Krok 2: Přidejte automatický tvar s textem
Vložte automatický tvar (obdélník) na snímek a otevřete jeho textový rámeček.
```java
IAutoShape shape = presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 200, 400, 200);
ITextFrame textFrame = shape.getTextFrame();
```
## Krok 3: Odeberte výchozí odstavec
Odeberte výchozí existující odstavec z textového rámečku.
```java
textFrame.getParagraphs().removeAt(0);
```
## Krok 4: Přidejte očíslované odrážky
Přidejte odstavce s vlastními číslovanými odrážkami počínaje konkrétními čísly.
```java
// Příklad odstavce s odrážkou začínající od 2
Paragraph paragraph1 = new Paragraph();
paragraph1.setText("bullet 2");
paragraph1.getParagraphFormat().setDepth((short) 4);
paragraph1.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 2);
paragraph1.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph1);
// Příklad odstavce s odrážkou začínající od 3
Paragraph paragraph2 = new Paragraph();
paragraph2.setText("bullet 3");
paragraph2.getParagraphFormat().setDepth((short) 4);
paragraph2.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 3);
paragraph2.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph2);
// Příklad odstavce s odrážkou začínající od 7
Paragraph paragraph3 = new Paragraph();
paragraph3.setText("bullet 7");
paragraph3.getParagraphFormat().setDepth((short) 4);
paragraph3.getParagraphFormat().getBullet().setNumberedBulletStartWith((short) 7);
paragraph3.getParagraphFormat().getBullet().setType(BulletType.Numbered);
textFrame.getParagraphs().add(paragraph3);
```
## Krok 5: Uložte prezentaci
Nakonec upravenou prezentaci uložte na požadované místo.
```java
presentation.save(dataDir + "SetCustomBulletsNumber-slides.pptx", SaveFormat.Pptx);
```

## Závěr
Na závěr, Aspose.Slides for Java zjednodušuje proces programového nastavení vlastních čísel odrážek v prezentacích PowerPoint. Dodržováním kroků uvedených v tomto kurzu můžete efektivně zlepšit vizuální čistotu a strukturu svých prezentací.
## FAQ
### Mohu si vzhled střel dále upravit?
Ano, Aspose.Slides nabízí rozsáhlé možnosti přizpůsobení typu, velikosti, barvy a dalších odrážek.
### Je Aspose.Slides kompatibilní se všemi verzemi PowerPointu?
Aspose.Slides podporuje formáty PowerPoint od 97-2003 až po nejnovější verze.
### Jak mohu získat technickou podporu pro Aspose.Slides?
 Návštěva[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) za technickou pomoc.
### Mohu vyzkoušet Aspose.Slides před nákupem?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Kde mohu zakoupit Aspose.Slides?
 Aspose.Slides můžete zakoupit od[tady](https://purchase.aspose.com/buy).